# Landing Page Copy — streeka.com/ai-guide
**Status:** Draft — ready for review  
**Purpose:** Single job — capture email. No nav. No exit paths.

---

## Page Title (browser tab)
The Cyclist's AI Cheat Sheet — Free from Streeka

---

## Above the Fold

**Headline:**
The Cyclist's AI Cheat Sheet

**Subhead:**
What to ask Claude when it has your training data. Free guide from Sam Sutherland, founder of Streeka.

---

## Email Capture Form

**Form label / supporting line:**
Get the cheat sheet — it's free.

**Email field placeholder:**
Your email address

**Button:**
Send me the cheat sheet

**Privacy note (below button, small):**
No spam. One guide, then a short email series. Unsubscribe any time.

---

## What's Inside (3 bullets — below the form)

- 10 specific prompts for getting useful answers from Claude when it has your Strava data
- How to find the training problem hiding in your data — easy day audit, hard session quality, missed weeks
- Where a read-only connection stops being enough, and what Streeka does instead

---

## Social Proof

**[Quote block]**

> "[Quote referencing AI interaction with Streeka or 'I didn't have to think about how to ask it']"
>
> — [Name], [brief context]

**Note for build:** Use a testimonial that references Streeka's AI specifically — something like "I just asked it" or "it already knew." If no AI-specific quote available, use Tim's quote from the first guide as placeholder and flag for replacement.

---

## About (short founder note — below the fold)

**Heading:** Why I wrote this

I discovered structured training and it changed how I rode. The problem was that good coaching was expensive, and generic plans don't survive contact with real life.

So I built Streeka — an AI training app that delivers structured training and adapts when the week falls apart.

When Claude started connecting directly to Strava, I started watching how cyclists used it. The connection is genuinely useful. But most people ask the wrong questions and get surface-level answers.

This guide is the better ones.

— Sam Sutherland, founder, Streeka

**[Founder photo here]**

---

## Footer

Streeka — AI training for cyclists and runners. iOS + Android. Free 2-week trial.

streeka.com · [App Store] · [Google Play]

---

## Design Notes for Build

- No navigation menu — single purpose page, no exit paths
- Mobile-first — most traffic arrives from LinkedIn on a phone
- Form sits above the fold on all device sizes
- Social proof sits directly below the form — visible before scroll on desktop, just below fold on mobile
- No hero image — headline carries the page
- Founder photo in the "About" section only
- CTA button colour: match streeka.com primary
- Background: white or very light — this should feel like a document, not a marketing page
- After form submit: redirect to guide page (`streeka.com/ai-guide/read`) or show inline confirmation + guide link

---

## Kit Setup Notes

- Form tag on sign-up: `ai-cheat-sheet`
- Sequence start: immediate (Email 1 fires within 5 minutes of sign-up)
- Exit tag: `trialist` (fired via RevenueCat → Zapier when someone starts a free trial)
- Sequence name in Kit: "The AI Training Edge"
- Do not merge with "The Self-Coached Cyclist Series" — separate funnel, different ICP signal
