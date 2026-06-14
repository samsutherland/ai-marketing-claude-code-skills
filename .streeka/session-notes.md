# Streeka — AI Marketing Skills Session Notes
**Date:** 2026-05-20  
**Skills used:** last30days, ai-discoverability-audit, positioning-basics, homepage-audit

---

## Product

**Streeka** — AI-powered training platform for cyclists and runners with big goals and messy lives.  
- iOS + Android  
- Publisher: Streeka Pty Ltd (Australia)  
- Pricing: $14/month (US) / $29/month (AU) — location-aware  
- Free 2-week trial  
- Founder: Sam Sutherland — built it for himself, still the first user

---

## ICP

**Primary: Recreational cyclists with desk jobs.**  
- Serious about improving, not racing professionally  
- Real constraints: work, family, fatigue, travel, inconsistent schedules  
- Current status quo: generic PDF plans, TrainingPeaks + a coach, or nothing structured  

Runners are secondary. No triathlon, no swimming. Cyclists are the world Sam knows and where he's already started.

---

## Positioning (Finalised)

**Positioning statement:**
> For desk-job cyclists who train seriously but can't predict their week,  
> Streeka is a training platform  
> that adapts your plan around the week you actually have — not the one you planned for.  
> Unlike TrainingPeaks (data tool, not a coach) and JOIN (rigid plan generator),  
> we treat disruption as default — recalibrating without guilt instead of leaving you to guess.

**One-liner:** Training that survives the week you actually get.

**Differentiator:** Treat disruption as default. Every competitor claims "adaptive training" — Streeka is the only one that treats a missed session or blown-out week as the expected state, not an exception to handle.

**Retired language:** "Adaptive training" — commoditised. Every competitor uses it. Not a differentiator.

**Competitors mapped:**
- TrainingPeaks — data tool for coached athletes, not a standalone coaching system
- JOIN Cycling — rigid plan generator, assumes clean weeks
- Stamina/HumanGO — newer, less established

**Brand collision risk:** "Streek App" (streek.run) — near-identical name, different running app. AI systems may conflate them.

---

## AI Discoverability Audit

**Score: 11/30 (Invisible → Weak)**

| Dimension | Score |
|---|---|
| Recognition | 2/5 |
| Accuracy | 2/5 |
| Sentiment | 3/5 |
| Category Presence | 1/5 |
| Authority | 1/5 |
| Competitive Position | 2/5 |

**Root causes found:**
1. **HTTP 403 blocking crawlers** — fixed by Sam during session. Subsequent fetch returned 200.
2. **Sydney geo anchor** — Prospeo and F6S listed Sydney as location, causing Perplexity to describe Streeka as "Sydney/Australia-specific." Needs fixing in those directories.
3. **No editorial roundup coverage** — Streeka doesn't appear in any "best cycling apps" lists.
4. **No quantified social proof** — no visible download count or app store rating.
5. **Brand collision** — "Streek App" causing potential misattribution.

**Perplexity description (at time of audit):**
> "Streeka appears to be an AI-powered training app for cyclists and runners that builds adaptive plans around your real-life schedule, fatigue, and habits... also described as an 'agentic AI coach'... with a focus on endurance athletes in Sydney, Australia."

**Re-audit schedule:**
- 30-day: ~2026-06-20 — check if 403 fix + schema fixes improved recognition
- 60-day: ~2026-07-20 — check for category query presence after any editorial coverage
- 90-day: ~2026-08-20 — full comparative re-audit with trend comparison

---

## Schema Fixes Applied

Issues found and fixed by Sam:

| Issue | Fix |
|---|---|
| `availableOnDevice` — not a standard Schema.org property | Removed |
| `audienceType` as array — Schema.org expects string | Fixed to string |
| `sameAs` pointing to app store download URLs | Should be social/identity profiles (LinkedIn, Twitter, Crunchbase) |

**Pending schema additions (when data exists):**
- `offers` — add once pricing is confirmed stable
- `aggregateRating` — add once 10+ App Store or Trustpilot reviews exist

---

## Homepage Audit

**Score: 3.19/5 — Needs Work**

| Section | Score | Weight |
|---|---|---|
| Above the Fold | 3.5/5 | 25% |
| Value Proposition | 3.5/5 | 25% |
| Social Proof | 2.5/5 | 10% |
| Clarity & Copy | 3.5/5 | 15% |
| CTA & Conversion | 2.5/5 | 15% |
| Trust & Risk | 2.5/5 | 10% |

### Fixes shipped (confirmed on second-pass audit 2026-05-20)

- ✅ **Founder section added to homepage** — "Built by a cyclist who needed this" with Rapha group ride photo (Sam, laughing, RCC cap, other cyclists). Copy: "Sam Sutherland built Streeka because he couldn't find a training app that handled the gap between ambitious goals and a genuinely messy schedule. So he built one. He's still the first user."
- ✅ **Testimonials named** — Rus (Cyclist, Sydney), Stephen (Runner, Derbyshire UK), Kim (Cyclist, Melbourne)
- ✅ **Pricing visible in hero** — "Free for 2 weeks, then $X/month" (location-aware)
- ✅ **Bottom CTA strengthened** — "Stop second-guessing. Start training around real life."
- ✅ **Carousel social proof added** — Real user DM/message screenshots in "For athletes too serious to wing it" section

### Still outstanding

- ✅ **"ADAPTIVE TRAINING" eyebrow badge** — replaced (2026-05-21)
- ✅ **Hero CTA structure** — restructured with action heading + pricing subtext above official badges (2026-05-21)
- ❌ **No aggregate social proof number** — App Store rating / download count not yet visible. Add once 10+ reviews exist.

### Discoverability note on testimonials
Rus is listed as "Sydney, Aus" — accurate, but reinforces the Australia-specific perception in AI systems. Stephen (Derbyshire, UK) and Kim (Melbourne) provide geographic spread — make sure those are equally visible.

---

## Pricing

- **US:** $14/month  
- **AU:** $29/month  
- Location-aware (implemented)  
- Free 2-week trial  

**Watch:** Schema markup and directory listings likely show a single static price. AI crawlers (typically US infrastructure) will index $14/month and surface that to AU visitors before they see the app price. Worth auditing static mentions.

---

## Pending Actions (Priority Order)

1. Fix Prospeo and F6S — remove Sydney geo anchor, set location to global
2. ✅ Replace "ADAPTIVE TRAINING" eyebrow text in hero (2026-05-21)
3. ✅ Restructure hero CTA — action heading + price subtext + official badges (2026-05-21)
4. ✅ Apply 7 copy rewrites from website copy audit (see `copy-rewrites-2026-05-21.md`) — handed to coding agent
5. Get into one editorial roundup — 220triathlon.com, transition.fun, or stas.run
6. Seed 10+ App Store reviews → add `aggregateRating` to schema
7. Add founder section photo — confirmed: use Rapha/RCC group ride photo (laughing, community context)

---

## Website Copy Audit (2026-05-21)

**Human-ness score: 7.5/10** — not heavily AI-generated. Issues were structural, not voice.

**7 rewrites handed to coding agent** (`copy-rewrites-2026-05-21.md`):
1. Hero sub — "cyclists and runners" → "cyclists"
2. Built-for tagline — "endurance athletes" → "cyclists (and runners)"
3. "Why not hire a coach?" — removed hedge ("you might not need one")
4. Solution one-liner — killed triple-negative AI pattern ("Not generic. Not rigid...")
5. How It Works Step 4 — made Streeka-specific (was generic coaching advice)
6a. Mid-page CTA — replaced "Stop guessing / second-guessing yourself" cluster
6b. Footer CTA — replaced "Stop second-guessing. Start training around real life."
7. Fit section — replaced "breaking on contact with real life"

**Key patterns fixed:**
- "Second-guessing" appeared 4x across the page — cut to 0
- "Real life" appeared 8+ times — trimmed to 3 intentional uses
- Both CTAs used identical Stop/Start structure — now distinct

---

## Blog Audit (2026-05-21)

**5 posts audited** — streeka.com/blog

**Two tiers of quality found:**
- Tier 1 (strong, minor fixes only): "Should You Do Strength Training as a Cyclist?" + "Why Generic Cycling Training Plans Stop Working"
- Tier 2 (batch-produced May 12, need work): "Can You Train for Cycling While Working Full Time?", "How Many Hours Per Week?", "How to Train for Cycling on a Tight Schedule" — all three cover nearly identical ground

**9 changes handed to coding agent** (`blog-rewrites-2026-05-21.md`):
- 5 CTA/close rewrites — stale "Stop guessing. Train smart." replaced with post-specific closes
- 3 FAQ section deletions (posts 3, 4, 5) — non-answer padding, all content already covered in post bodies
- 1 mid-post duplicate heading removed (post 2)

**Lines to protect — do not rewrite these:**
- "Boring is underrated. Boring works. Boring does not need a ring light."
- "Tiny spreadsheet dictator"
- "Coffee, pastry, and new wheels"
- "A plan that only works during ideal weeks is not really a plan. It is fan fiction."
- "Life is not becoming reasonable."
- "bin-fire week"
- "You are not trying to win the gym."

**Deferred (this month):**
- Posts 3, 4, 5 cover nearly identical ground — consider merging into one pillar post or genuinely differentiating them

---

## Pending Actions (Priority Order)

1. Fix Prospeo and F6S — remove Sydney geo anchor, set location to global
2. Apply homepage copy rewrites (`copy-rewrites-2026-05-21.md`)
3. Apply blog copy rewrites (`blog-rewrites-2026-05-21.md`)
4. Get into one editorial roundup — 220triathlon.com, transition.fun, or stas.run
5. Seed 10+ App Store reviews → add `aggregateRating` to schema
6. Add founder section photo — confirmed: use Rapha/RCC group ride photo (laughing, community context)
7. Merge or differentiate blog posts 3, 4, 5

---

## Editorial Outreach (2026-05-21)

**Original targets were wrong:**
- stas.run — competitor (AI training tool), not a publication
- transition.fun — competitor (AI triathlon training app), not a publication
- 220triathlon.com — wrong sport (triathlon), Streeka doesn't do swim

**Right target: BikeRadar**
- URL: bikeradar.com/advice/buyers-guides/best-cycling-apps
- Roundup: "Best cycling apps in 2026: 21 of the best iPhone and Android apps" — updated regularly, high Google authority
- Contact: **Stan Portus**, Content Editor — likely stan.portus@ourmedia.co.uk (verify on LinkedIn first)
- Gap: their "fitness" section has TrainingPeaks only — nothing for solo adaptive training for time-constrained cyclists
- Streeka fits: fills the exact hole between "data tool for coached athletes" (TrainingPeaks) and nothing

**Secondary target:** Cycling Weekly — similar roundup format, pitch after BikeRadar

**Pitch email (ready to send):**

> Subject: App for your Best Cycling Apps roundup — fills the adaptive training gap
>
> Hi Stan,
>
> Quick one — I think there's a gap in your best cycling apps roundup that Streeka fills.
>
> Your fitness section has TrainingPeaks, which you've correctly described as a tool for coached athletes. There's nothing in the list for the solo cyclist who wants training that adapts when the week goes sideways — missed session, work blew out, sleep was bad.
>
> That's what Streeka does. It's an AI training app for cyclists (and runners) that treats disruption as the default, not an exception to handle. Instead of leaving you to guess what to do when Tuesday falls apart, it helps you adjust the week without losing the plot.
>
> Key details:
> - iOS + Android
> - Free 2-week trial, then $14/month
> - Built by a cyclist who couldn't find an app that handled a genuinely messy schedule — so he built one
>
> Happy to set up a trial account for you or send anything else useful.
>
> Sam Sutherland
> Founder, Streeka
> streeka.com

**Status:** Draft ready — verify Stan's email before sending

---

## Competitor Research — RestOrTrain (2026-06-05)

**What it is:** AI-native cycling/triathlon/running coach app. 3 founders, Kraków Poland. Launched November 2025, iOS-first (Android coming). Integrates with Strava, Garmin, Intervals.icu. $12.99/month or $119.99/year.

**Their claimed 30,000+ users is almost certainly inflated:**
- Only 145 App Store ratings (at 1% conversion = ~14,500 users; at 2% = ~7,000)
- mwm.ai independently tracked "10k+ downloads"
- Instagram: 1,459 followers. YouTube: 22 subscribers. LinkedIn: 5 followers.
- The 30k figure is almost certainly total registered accounts ever, not active users.
- Streeka's 80 paying users beats their ghost accounts on any honest metric.

**Growth tactics worth borrowing:**
1. **Intervals.icu forum** (`forum.intervals.icu`) — posted directly into the most engaged data-nerd cycling community. Likely their biggest single growth channel.
2. **Ambassador program** — free Pro for mid-size creators + promo codes for their audience. Low cost, targeted.
3. **Free Pro for verifiable pro cyclists** — via ProCyclingStats profile check. Credibility play.
4. **Free tier** — minimal friction signup, clear upgrade path once you're hooked on your own data.
5. **Strava club + subreddit** — community infrastructure that turns users into distribution.

**What to note:** Their social presence is tiny. The 10-30k user range came from community seeding (Intervals.icu, Strava, cycling forums), not paid ads or large creators. Replicable at Streeka's current scale.

---

## Next Session

**Options:**
- AI discoverability re-audit — 30-day check due ~2026-06-20 (schema fixes, 403 fix)
- New blog content — use `content-idea-generator` anchored to desk-job cyclists ICP
- Prospeo + F6S geo fix — remove Sydney anchor, set location to global
- Intervals.icu forum — post about Streeka (forum.intervals.icu)
