# Funnel 2 (AI Cheat Sheet) — Ship Runbook
**Filed:** 2026-06-17
**Status:** Copy done + QA'd. Remaining work is platform build + launch.

All four assets are written, in Sam's voice, and passed the voice-guide + de-ai-ify gate:
- Guide: `guide-cyclists-ai-cheat-sheet.md`
- Landing page: `landing-page-ai-guide.md` (testimonial blocker now resolved — Tim's quote slotted in)
- Email sequence: `email-sequence-ai-training-edge.md` (5 emails)
- Viral LinkedIn post: `linkedin-post-ai-cheat-sheet.md` (A/B versions)

---

## Decisions already resolved this session
- **Testimonial:** Use Tim's quote ("I came back without guessing, panicking, or overdoing it"). Done in landing copy.
- **Strava vs Garmin/Wahoo:** Not a conflict. Guide = "Claude + Strava (read-only)". Streeka connects via Garmin + Wahoo OAuth (fuller data) — **not Strava** (corrected 2026-06-19). The contrast is the whole funnel argument, and it's *sharper* this way: Claude+Strava (read-only, limited) vs Streeka's fuller Garmin/Wahoo device data. Leave the funnel framing as-is.

---

## The 6-hour ship sequence (in order)

### Block 1 — Build the pages (≈2.5h, platform)
1. Build `streeka.com/ai-guide` (landing) from `landing-page-ai-guide.md`. Single purpose, no nav, mobile-first, form above fold.
2. Build `streeka.com/ai-guide/read` (the guide itself) from `guide-cyclists-ai-cheat-sheet.md`.
3. Wire form submit → redirect to `/ai-guide/read` (or inline confirm + link).
4. Drop founder photo into the About block.

### Block 2 — Wire Kit (≈1h, platform)
5. Create Kit form, tag on sign-up: `ai-cheat-sheet`.
6. Create sequence "The AI Training Edge", paste 5 emails from `email-sequence-ai-training-edge.md`. Cadence: Day 0/3/7/12/20. Email 1 fires within 5 min.
7. Set reply-to = Sam's email, sender = Sam Sutherland.
8. Confirm exit: RevenueCat trial-started → Zapier → Kit tag `trialist` → removes from sequence. (Reuse the LM1 Zap; just add this sequence to the exit logic.)
9. Send yourself a test sign-up. Verify Email 1 lands + guide link works.

### Block 3 — Launch the viral post (≈30min active, then monitor)
10. Post **Version A** (observation-led) on LinkedIn. Same platform as the 127k post.
11. **Immediately** drop the `streeka.com/ai-guide` link in the first comment.
12. Reply to the first 10–20 comments yourself in the first hour — early velocity is the algorithm signal.
13. If a comment asks Garmin/Strava/app compatibility: answer helpfully, do NOT pitch Streeka. The guide does that.

### Block 4 — Track + decide (ongoing)
14. After 48h: if Version A engagement is below the 127k post, queue **Version B** (story-led).
15. Track **link clicks**, not just likes. Target from the plan: 500+ clicks, 40%+ click→email capture.

---

## Definition of done
- Landing + guide pages live and mobile-clean
- Kit sequence live, test sign-up received Email 1, exit tag wired
- Version A posted, link in first comment, early comments answered

## Targets (from funnel plan 2)
- 500+ link clicks from the post
- 40%+ landing → email capture (warmer ICP than LM1)
- 25%+ still opening at Email 4
- 8–15% of signups → trial within 30 days
