# Landing Page Copy — streeka.com/guide
**Status:** Draft — ready for review  
**Purpose:** Single job — capture email. No nav. No exit paths.

---

## Page Title (browser tab)
The Self-Coached Cyclist's Playbook — Free from Streeka

---

## Above the Fold

**Headline:**
The Self-Coached Cyclist's Playbook

**Subhead:**
Training when your week never goes to plan. Free guide from Sam Sutherland, founder of Streeka.

---

## Email Capture Form

**Form label / supporting line:**
Get the playbook — it's free.

**Email field placeholder:**
Your email address

**Button:**
Send me the playbook

**Privacy note (below button, small):**
No spam. One guide, then a short email series. Unsubscribe any time.

---

## What's Inside (3 bullets — below the form)

- What a real coach does when your week falls apart — and how to do it yourself
- The 3-move adjustment when a session drops out of the week
- When to push through and when to cut load (and how to tell the difference)

---

## Social Proof

**[Quote block]**

> "I missed a full week sick. I told SAMI what had happened and it rebuilt the week around a sensible return instead of trying to make up for lost time. I came back without guessing, panicking, or overdoing it."
>
> — Tim, completed a backyard ultra while training with Streeka

---

## About (short founder note — below the fold)

**Heading:** Why I wrote this

I trained for Peaks Challenge twice — once with a coach, once without. The coach knew what to do when the week went wrong. When I had to figure that out myself, I looked for an app that could help. Couldn't find one. Built it.

This guide is the framework I used. Streeka is what automates it.

— Sam Sutherland, founder, Streeka

**[Founder photo here]**

---

## Footer

Streeka — AI training for cyclists and runners. iOS + Android. Free 2-week trial.

streeka.com · [App Store] · [Google Play]

---

## Design Notes for Build

- No navigation menu — single purpose page, no exit paths
- Mobile-first — most traffic arrives from LinkedIn, social, or email links on a phone
- Form sits above the fold on all device sizes
- Social proof (Tim quote) sits directly below the form — visible before scroll on desktop, just below fold on mobile
- No hero image needed — headline carries the page
- Founder photo in the "About" section only, not top of page
- CTA button colour: match streeka.com primary
- Page background: white or very light — guide content page should feel like a document, not a marketing landing page
- After form submit: redirect to guide page (`streeka.com/guide/read`) or show inline confirmation + guide link

---

## Kit Setup Notes

- Form tag on sign-up: `self-coached-playbook`
- Sequence start: immediate (Email 1 fires within 5 minutes of sign-up)
- Exit tag: `trialist` (fired via RevenueCat → Zapier when someone starts a free trial)
- Sequence name in Kit: "The Self-Coached Cyclist Series"
