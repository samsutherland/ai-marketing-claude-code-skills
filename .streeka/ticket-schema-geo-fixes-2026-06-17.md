# Implementation Ticket — Streeka schema/meta + geo fixes

**Source:** AI discoverability re-audit 2026-06-17 (`.streeka/ai-discoverability-reaudit-2026-06-17.md`). Score 13/30.

> ⚠️ **CORRECTION 2026-06-19 — Strava removed.** Streeka does **not** connect to Strava (Garmin + Wahoo OAuth only). The schema `description` and `featureList` in this ticket originally said "Garmin, Wahoo and Strava." **If this ticket was already shipped to streeka.com, the live JSON-LD now publishes a false integration as an AI entity signal — verify and redeploy.** This matters more than a normal typo: schema is exactly what AI search scrapes, so a wrong "Strava sync" line actively trains the misread.
**Goal:** Fix the entity signals AI scrapes so Streeka reads as an *AI cycling training app* (not a streak/habit tracker) and stops being geo-anchored to Sydney. All changes are to **streeka.com** + two external directory listings.

---

## A. Homepage JSON-LD (`SoftwareApplication`)

Replace the current block with the corrected one below. Changes are flagged inline.

```json
{
  "@context": "https://schema.org",
  "@type": "SoftwareApplication",
  "name": "Streeka",
  "url": "https://www.streeka.com/",
  "image": "https://www.streeka.com/og-image.png",
  "description": "Streeka is an AI training app for cyclists (and runners). It builds an adaptive coaching plan and rebuilds your week around missed sessions, fatigue, and a messy schedule — reading what you actually rode from Garmin and Wahoo.",
  "applicationCategory": "SportsApplication",
  "applicationSubCategory": "AI cycling training and coaching app",
  "operatingSystem": ["iOS", "Android"],
  "audience": {
    "@type": "Audience",
    "audienceType": "Cyclists and runners training around work, family, and unpredictable schedules"
  },
  "featureList": [
    "AI cycling coach",
    "Adaptive training plans that rebuild around your week",
    "Schedule-aware workout adjustments",
    "Garmin and Wahoo sync",
    "Structured endurance workouts",
    "Training streak and consistency tracking"
  ],
  "downloadUrl": [
    "https://apps.apple.com/us/app/streeka-cycling-run-coach/id6477632458",
    "https://play.google.com/store/apps/details?id=com.streeka.android"
  ],
  "sameAs": [
    "https://www.linkedin.com/company/streeka",
    "https://instagram.com/streeka.cc",
    "https://instagram.com/streeka.run"
  ],
  "publisher": {
    "@type": "Organization",
    "name": "Streeka Pty Ltd",
    "url": "https://www.streeka.com/"
  },
  "offers": {
    "@type": "Offer",
    "price": "14",
    "priceCurrency": "USD",
    "description": "2-week free trial, then $14/month (US)"
  }
}
```

**What changed and why:**

1. **`description` rewritten** — now leads with "AI training app for cyclists," the adaptive/rebuild differentiator, and Garmin/Wahoo. Old version had no "AI" or "coach" in it, which let the model default to the streak/habit read.
2. **`applicationSubCategory`** — "Adaptive endurance training app" → "AI cycling training and coaching app" (puts AI + cycling in the category signal).
3. **`featureList` reordered** — "AI cycling coach" first, "Training streak…" last (LLMs weight order; streaks was floating mid-list and the name amplifies it). Added "Garmin and Wahoo sync" explicitly.
4. **`availableOnDevice` REMOVED** — not a valid Schema.org property. It was removed in the May fix and has regressed back in; delete it (it can invalidate the block).
5. **`downloadUrl` — US App Store first** — was `apps.apple.com/au/app/…`. US-based crawlers read the `/au/` path as "Australian app." Lead with `/us/app/…`. **CONFIRMED 2026-06-18: US store shares ID `6477632458` — this is a one-word `/au/` → `/us/` path swap.**
6. **`offers` price** — kept `14 USD` and made the description say "(US)" so it's internally consistent with the fix in section B.
7. **`aggregateRating` REMOVED** — current block had `reviewCount: 3`. Thin counts get distrusted/ignored and the May plan said hold until 10+. **CONFIRMED 2026-06-18: pull it now.** Re-add the block once App Store reviews ≥ 10.

---

## B. Homepage `<meta name="description">`

```
Current: "Training plans for cyclists preparing for endurance events. Adapts when life gets in the way. Free 14-day trial, then $29/month."

New:     "AI training app for cyclists. Streeka builds an adaptive plan and rebuilds your week around missed sessions, work, and fatigue. Free 2-week trial, then $14/month."
```

**Why:** (a) front-loads "AI training app for cyclists" to match the schema and fight the streak-read; (b) the old meta said **$29** (AU) while the schema says **$14 USD** — US crawlers saw conflicting prices. Standardize on $14 USD for crawlers (the app still shows AU users $29 via location-aware pricing — that's unaffected).

*(Title is fine as-is: "Streeka. Never generic. Always yours.")*

---

## C. Geo de-anchoring (off-site — the #1 un-actioned item since May)

1. **Prospeo** — edit the Streeka listing: remove Sydney / Australia as location, set to **Global** (or remove the location field).
2. **F6S** — same: remove the Sydney anchor, set location to Global.
3. **Stone & Chalk** — AI search now cites "Streeka, part of the Stone & Chalk community, Sydney-based accelerator." Can't remove the accelerator tie, but wherever Streeka controls that listing's blurb, add a global-market framing line (users in the UK, US, AU) so it's not read as AU-only.

---

## Acceptance check (run after deploy)

- [ ] `https://www.streeka.com` returns 200 to crawlers (still holding from the 403 fix).
- [ ] JSON-LD validates (Google Rich Results / schema.org validator) with `availableOnDevice` gone.
- [ ] Schema `description` + meta description both lead with "AI training app for cyclists."
- [ ] No price conflict: schema and meta both say $14 USD.
- [ ] `downloadUrl` leads with the US App Store path.
- [ ] Prospeo + F6S no longer show Sydney.
- [ ] 60-day re-audit (~2026-07-20): re-run "What is Streeka?" — does it still lead with streaks/habits, or with AI cycling coaching now?
