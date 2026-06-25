# Campaign: Bowral Classic, Club Partnership

**Created:** 2026-06-22
**Status:** 🟡 Approval pack **sent to Anthony 2026-06-24** — awaiting yes by Fri 27 Jun for a Sun 28 Jun launch.
**Owner:** Sam
**Single source of truth for this collaboration. Link out; don't duplicate.**

---

## In a nutshell

Partner with a cycling club around the **Bowral Classic** (Gran Fondo, NSW). Club members
signing up for the event get Streeka at a **discounted rate** to train for it. We produce
**content around the partnership** to reach the club's audience and build proof.

The offer is a concrete instance of the already-drafted event page:
[[landing-page-event-offer-v1]], "Be ready for your event in 12 weeks."

---

## The deal (fill in from the agreement)

| Field | Value |
|-------|-------|
| Club name | **Pastries** (cycling club) |
| Main contact + role | **Anthony** Nguyen, club contact / approver |
| Contact email / phone | apnguyen91@gmail.com |
| Event date | **Sunday 18 October 2026** (Bowral Classic) |
| Event distances supported | 85 km · 120 km · 150 km |
| Member count / expected signups | _TBD (working target: 30 activations)_ |
| Discount offered to members | **20% off, through to the event (~4 months)** for Pastries members; **free access for Ride Leaders** |
| Discount code / mechanism | iPhone: **Apple Offer Code** `BOWRAL` (20%); Android: **manual RevenueCat comp** (free month). Info hub at `streeka.com/bowral`. |
| Offer live window | Late June → event week (18 Oct 2026); expiry of discount _TBD_ |
| What the club gives us | Anthony approves concept/branding; posts/forwards approved msgs into Pastries WhatsApp + **Instagram (confirmed)**; group rides run as **official Pastries rides** (training/Bowral flavour); provides Ride Leader list |
| What we give the club | Member 20% / ~4 months (new sign-ups only) + free Ride Leader access + all content/admin (Sam owns delivery) |
| Money flow | None for v1 (discount-only). **Next step = paid revenue-share partnership** (only model that works for Sam long-term), this campaign is the proof-of-concept. |
| Exclusivity / term | _TBD_ |

---

## What each side owes (deliverables)

**Streeka / Sam:** own campaign plan + delivery; configure offer + onboarding; produce all
content; member support; coordinate training meet-ups; track + report; send Anthony materials
for approval.

**Anthony / Pastries:** approve concept, messages, branding use; post/forward approved messages
into Pastries channels; approve proposed rides vs existing calendar; provide Ride Leader list /
distribute free-access instructions.

**Ride Leaders:** get free access; use Streeka where practical; mention the challenge naturally;
help set the tone on designated rides; lightweight feedback. **No obligation** to do support,
content, or admin.

Full delivery plan + timeline: [[campaign-bowral-classic-plan]] _(to be created, see critique
before building)_.

---

## Pricing / offer mechanic

Baseline from the event page: **$29/mo, 14-day free trial, no card to start.**
Decisions to make:
- [x] Discount: **20% off for new member sign-ups, through to the event (~4 months); free for Ride Leaders**
      (agreed; bumped from 10% → 20% on 2026-06-23, time-limited to the campaign).
  - **Existing subscribers: no discount** (decided 2026-06-24). New sign-ups only. Rationale: if they
    were happy paying full price, fine; and it kills the Apple/Google retro-discount problem entirely.
  - Ride Leader free access = set up via **RevenueCat** (download → entitlement as if already paid).
  - **Don't advertise the Ride Leader freebie in member messaging**, kept between Sam + Anthony.
  - Anyone in the club can take the 20%, no need to be entered for Bowral or even training.
  - Implementation note: 20% needs to be **time-limited (~4 months / through the event)**, not perpetual.
- **20% off $29/mo = ~$5.80**, more meaningful than the old 10%, but the hook is still the
      *challenge + the club*, not the discount. Lead messaging on "Road to Bowral with your club."
- [x] Tracking: just **eyeball redemptions / comps in RevenueCat**. No Zapier `bowral-classic` tag.
- [ ] Offer expiry (event date? or rolling?)

### Offer mechanics, platform-split (revised 2026-06-23)

Apple and Google handle this differently, so the offer is delivered two ways:

- [ ] **iPhone, Apple Offer Code** `BOWRAL` = 20% off, **time-limited to ~4 months / through the event**.
      Apple's one-tap redemption URL = the link on the info page.
- [ ] **Android, manual RevenueCat comp** (Google has no equivalent code mechanism). Plan: when an
      Android member joins, **comp them a free month** in RevenueCat. They download + message us to be sorted.
- [ ] **Ride Leaders**, free via RevenueCat: they download, start a trial, email `sam@streeka.com`
      ("I'm a Pastries ride leader and I've started a trial in Streeka") → comp to free.
- [ ] **Existing subscribers**, no discount (killed 2026-06-24).
- [ ] Test the iOS offer-code redeem once on a real device.
- [ ] Track by eyeballing redemptions + comps in RevenueCat.

> Note: the iOS 20%/4-month and Android free-month deals aren't identical, pragmatic equivalence,
> not worth engineering parity for ~20 users. Public wording stays simple ("we'll sort your discount").

---

## The offer page, simple info hub (back on, 2026-06-23)

✅ **BUILT in the site repo:** `streeka-site/src/pages/bowral.astro` → **`www.streeka.com/bowral`**
(content source: [[landing-page-bowral-classic]]). Astro page modelled on `what-is-streeka.astro`:
Layout + SoftwareApplication/FAQPage JSON-LD, iOS/Android claim cards, group rides, FAQ, support.
Builds clean, in the sitemap, deliberately **not** in the main nav (club-only, reached via the link).
Info page, not a sales funnel.

Before it goes live:
- [x] Apple Offer Code redeem URL **confirmed correct** (Sam, 2026-06-24) — still need the `BOWRAL`
      code created in App Store Connect.
- [ ] **Pastries logo** (co-branding) — ON HOLD per Sam (2026-06-24), waiting on the asset.
- [ ] Confirm the official **Bowral Classic** event URL (currently `bowralclassic.com.au`)
- [ ] Confirm support email (currently `sam@streeka.com`)
- [ ] Deploy + (optional) submit sitemap per the repo's SEO workflow

---

## Content plan (the "content around the partnership")

✅ **Written: [[bowral-messaging-and-socials]]** (2026-06-23), paste-ready WhatsApp messages
(launch → event week → wrap), the Ride Leader preview message, IG launch post, 12 weekly IG angles,
and the cadence rules. Repurpose existing reels for IG; don't film a new set.

**Instagram = Collab post** (decided 2026-06-24): Sam tags Pastries as collaborator, Anthony accepts,
post lands on both profiles (≈ doubles reach). Not a repost.

Reach lesson from [[session-notes]]: broad, universal pain = shareable reach; narrow = conversion.
Lead promo with the universal "ride to Bowral with your club" angle, not app features.

---

## Success metric

**Member signups → paid** (decided 2026-06-22). Members who redeem `BOWRAL`, start a trial, and
convert to paying, counted by eyeballing code redemptions in RevenueCat. Not impressions, not trial starts.
(Echoes [[session-notes]]: top-of-funnel reach is easy; conversion is the real test.)

---

## Open questions / next actions

- [ ] Capture the agreed deal terms above (from the conversation with the club)
- [ ] Confirm Bowral Classic 2026 date → sets the content + offer timeline
- [ ] Decide discount amount + mechanism (code vs URL)
- [ ] Fork the event landing page
- [ ] Draft + send the club the assets they need to promote on their side
- [ ] _TBD_

---

## Scope decision (2026-06-22)

Running **lean / conversion-first**, not the full 9-phase plan. Cut to what moves
activated→paid: offer mechanics, Ride Leader preview, launch, ~1 content piece/week
(repurpose existing reels), **4 group rides on existing Pastries rides**, a 4-week check-in,
end-of-campaign testimonials + App Store reviews. The comprehensive version is kept as a
"scale it if it works" reference, not the v1.

**Timeline:** Anthony approves by **Fri 27 Jun** → **public launch Sun 28 Jun** (exactly **16 weeks**
to Bowral on 18 Oct) → **launch ride Thu 2 Jul at Centennial Park** (show the app for a coffee on
Streeka) → simulation ride (mid-Sep) → final long ride (early Oct) → shakeout (Sat 17 Oct) → Bowral
(Sun 18 Oct) → wrap (late Oct).

**Critical path = offer mechanics live + tested before launch (Sun 28 Jun):** iOS Apple Offer Code +
Android comp plan + Ride Leader comp + the `streeka.com/bowral` page. Everything else is blocked on this.

## Links

- **Anthony approval pack (send, approve by Fri 27 Jun):** [[bowral-anthony-approval-pack]]
- **Messaging & socials:** [[bowral-messaging-and-socials]]
- **Info-page content source:** [[landing-page-bowral-classic]] · built at `streeka-site/src/pages/bowral.astro`
- Original event page it was seeded from: [[landing-page-event-offer-v1]]
- Positioning: [[positioning-2026-06-19]]
- Voice guide: [[voice-guide-sam-sutherland]]
- Running marketing log: [[session-notes]]
