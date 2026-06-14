# Streeka — Lead Magnet & Email Funnel Plan
**Filed:** 2026-06-05  
**Goal:** Capture email from the ICP before they're ready to trial. Warm them up. Convert to trial.

---

## The Problem This Solves

The current funnel has one step: visit streeka.com → start free trial.

That's a high-commitment first ask for someone who just heard about the product. Most desk-job cyclists will hit the site, think "interesting," and leave. No way to follow up.

A lead magnet funnel adds a middle step: low-commitment opt-in → value delivery → earned trust → trial.

---

## The Lead Magnet: "The Self-Coached Cyclist's Playbook: Training when your week never goes to plan"

**Status:** Title locked. ✓

**What it is:** A free guide (web page) that combines two things the ICP wants:
- The aspiration: coaching-quality training without paying for a coach
- The differentiator: it works when the week falls apart, not just when it's clean

**Why this wins over the alternatives:**
- "12-week plan for time-crunched cyclists" — rejected. Static plans contradict Streeka's positioning. Every competitor has one.
- "Train like you've got a coach" — strong angle, wrong job for the magnet. Used as the email sequence through-line instead (see emails 2–5).
- This title gets both: aspiration (self-coached) + differentiator (handles disruption). Pre-qualifies the ICP, creates the obvious bridge to the product.

**URL:** `streeka.com/guide` — generic enough to survive if the magnet evolves later.

**Format:** Web page only. No PDF to maintain. Add PDF later if users ask for it.

**Content outline:**
1. Why most training plans fail desk-job cyclists (the design problem, not a you problem)
2. What a real coach does when your week falls apart — and how to do it yourself
3. The 3-move adjustment: one session drops, what next
4. What to do when the whole week blows up (not just one session)
5. When to push through vs. when to cut load
6. The one thing that separates cyclists who improve from those who plateau: consistency of direction, not perfection of execution

**Voice constraint:** Use Sam's voice guide anti-patterns as the QA gate. No "leveraged," no rhetorical Q+A, no performed vulnerability.

---

## CTA Strategy

One funnel, two CTAs — don't mix them.

| CTA | Where | Ask Level | Goal |
|-----|-------|-----------|------|
| "Get the free guide" | Blog posts, LinkedIn, social, bio links | Low — just an email | Top-of-funnel capture |
| "Start free trial" | Email sequence (emails 5+), end of guide, homepage | High | Conversion |

**Rules:**
- Blog posts end with the guide CTA, not the trial CTA. The trial CTA is earned through the sequence.
- LinkedIn posts drive to the guide landing page, not directly to the app store.
- The guide itself has one CTA at the end: start the free trial. No email capture there (they're already on the list).

**Primary CTA copy:**
> "Get the Self-Coached Cyclist's Playbook — free"

**What not to use:**
- "Download our free guide" (generic)
- "Sign up for our newsletter" (wrong framing — this isn't a newsletter)
- "Learn more" (never)

---

## Landing Page

**URL:** `streeka.com/guide` ✓  
**Purpose:** One job — capture the email.

### Structure

```
[Above the fold]
Headline: "The Self-Coached Cyclist's Playbook"
Subhead:  "Training when your week never goes to plan. Free guide from the founder of Streeka."

[Form]
Email input + "Send me the playbook" button
[Note: No spam. Unsubscribe any time.]

[What's inside — 3 bullets, max]
- What a real coach does when your week falls apart — and how to do it yourself
- The 3-move adjustment when a session drops out
- When to push through and when to cut load (and how to know the difference)

[Social proof — one quote]
Use the ultra runner's testimonial — pick the quote that most directly references
schedule disruption, not general satisfaction. Confirm name before writing.

[Footer]
Streeka — AI training for cyclists. iOS + Android. Free 2-week trial.
```

**Design constraints:**
- No nav menu (removes exit paths)
- Mobile-first (most traffic will be from social/email links on a phone)
- No hero image needed — one strong headline does more work
- Trust signal: founder photo + "Built by a cyclist who had the same problem"

**Skill to use for copy QA:** `de-ai-ify` → `voice-extractor` (Sam's guide)

---

## Email Capture Setup

**Platform:** Kit (already set up). ✓

**Kit automation needed:**
- Tag on sign-up: `self-coached-playbook`
- Sequence: 7 emails, starts immediately on sign-up
- Exit condition: RevenueCat fires trial-started event → Zapier/Make tags subscriber as `trialist` in Kit → removed from sequence
  - RevenueCat webhook → Zapier → Kit tag `trialist` → sequence exits
  - Don't keep selling to someone who already converted

---

## Email Sequence: 7 Emails

**Sequence name:** The Self-Coached Cyclist Series  
**Cadence:** Day 0, 2, 4, 7, 10, 16, 23  
**Voice:** Sam's voice throughout — plain, direct, no corporate language  
**Skill to use for drafting + QA:** `newsletter-creation-curation` (for structure), `de-ai-ify` (for AI-slop removal), voice guide anti-patterns as gate

---

### Email 1 — Day 0 (Immediate)
**Subject:** Here's your Messy Week Protocol  
**Goal:** Deliver the guide. Build trust. No sell.  
**Structure:**
- Here's the link (immediate delivery — don't make them wait)
- One thing to actually do with it today (actionable, not vague)
- Brief note on who wrote it and why (Sam, cyclist, built Streeka)
- No CTA beyond "hit reply if you have a question"

**Tone signal:** Warm but not effusive. Like handing something useful to someone at a café, not a sales handoff.

---

### Email 2 — Day 2
**Subject:** The real reason your training plan keeps falling apart  
**Goal:** Install the core belief: most plans are built wrong for your life.  
**Structure:**
- The real problem isn't you (it's the plan design)
- Plans built for clean weeks break under the first disruption
- Three patterns that cause this (name them specifically)
- No CTA — this email just builds belief

**Tone signal:** Analytical. Sam diagnosing a problem, not selling a fix.

---

### Email 3 — Day 4
**Subject:** Tim trained for a backyard ultra. Here's how his weeks actually looked.  
**Goal:** Social proof — real story, specific numbers, disruption as the protagonist.  
**Structure:**
- One user story — **Tim** (backyard ultra runner — trained for a 24+ hour ultra event with Streeka around a full-time job)
- Before: what their life looked like, what was going wrong
- After: what changed, with specific numbers if available
- Soft mention of Streeka (what they use to manage it now) — not a pitch, just context

**Tone signal:** Story-mode. First two paragraphs are scene-setting, not setup for a sell.

---

### Email 4 — Day 7
**Subject:** Why I built this  
**Goal:** Founder story — earns the right to sell later.  
**Structure:**
- Sam's specific moment of frustration (the gap between training intention and reality)
- What existing apps failed to solve
- What Streeka does differently — in one plain sentence
- No CTA — this email is the trust-builder

**Tone signal:** Sam's most unfiltered register. Voice guide's "active exploration" energy. Not polished product copy.

---

### Email 5 — Day 10
**Subject:** The thing the playbook can't do for you  
**Goal:** First real conversion push. Bridge from guide to trial.  
**Structure:**
- Acknowledge the guide is useful but manual work
- Streeka automates exactly this — briefly explain how
- The trial is free, 2 weeks, no commitment
- CTA: "Start your free trial →" (one link, one ask)

**Tone signal:** Direct. No apology for selling. The offer is genuinely good — treat it that way.

---

### Email 6 — Day 16
**Subject:** "I don't have time to learn a new app"  
**Goal:** Handle the main objection. Second conversion opportunity.  
**Structure:**
- Name the objection directly (don't pretend it doesn't exist)
- Address it: how long setup actually takes
- One proof point (testimonial or specific claim)
- CTA: Start trial — same link

**Tone signal:** Straight answer to a fair question. Not defensive, not dismissive.

---

### Email 7 — Day 23
**Subject:** Last one from me for a while — one question  
**Goal:** Soft exit + segment for re-engagement.  
**Structure:**
- "This is the last email in this series"
- One question: "Still working through the self-coached training problem, or did you find something that works?"
- If they reply → flag for personal follow-up (Sam replies manually)
- If no reply → move to low-cadence list (1 email/month, new Streeka content)
- Final CTA: trial offer, framed as "here if you want it"

**Tone signal:** The break-up email from cold-outreach-sequence. Final offer, no pressure, genuine close.

---

## Execution Sequence

Build in this order. Each step unblocks the next.

| Step | Task | Skill | Blocker |
|------|------|-------|---------|
| 1 | Decide email platform | — | Sam's call. Recommend Kit. |
| 2 | Write "Messy Week Protocol" guide content | `de-ai-ify` + voice guide | None |
| 3 | Write landing page copy | `de-ai-ify` + voice guide | None |
| 4 | Build landing page in Streeka's site | — | Needs platform access |
| 5 | Set up email capture form → Kit/Mailchimp | — | Email platform decided |
| 6 | Draft all 7 emails | `newsletter-creation-curation` + `de-ai-ify` | Voice guide anti-patterns as gate |
| 7 | Load sequence into email platform | — | Emails approved |
| 8 | Confirm exit condition (trial → remove from sequence) | — | Email platform setup |
| 9 | Point blog post CTAs at landing page | — | Landing page live |
| 10 | Update LinkedIn bio link to landing page | `linkedin-authority-builder` | Landing page live |

**Start here:** Steps 2 and 3 can run in parallel — both are writing tasks, no platform needed.

---

## What Good Looks Like

The funnel is working when:
- 30%+ of guide downloads open Email 1
- 20%+ are still opening by Email 4 (the founder story)
- 5–10% of guide downloads convert to trial within 30 days
- Replies to Email 7 give signal on what's stopping conversion

These are realistic targets for a warm, ICP-specific sequence with good copy. Generic newsletter sequences hit 2–3%.

---

## What to Avoid

**Don't make the guide too long.** One page, 500 words max. Long guides don't get read. The goal is "this was immediately useful" not "this is comprehensive."

**Don't lead with the trial in early emails.** You're borrowing trust. Spend 4 emails earning it before you ask for anything.

**Don't use a generic form headline** like "Join our newsletter." The copy must say what they're getting. "Get the Self-Coached Cyclist's Playbook" beats "Subscribe" in every test.

**Don't email more than once a week** in this sequence. Desk-job cyclists are busy — that's the whole point of the product. Don't prove you don't understand that by flooding their inbox.

---

## Decisions — Status

| Decision | Status |
|----------|--------|
| Lead magnet title | ✓ "The Self-Coached Cyclist's Playbook: Training when your week never goes to plan" |
| Email platform | ✓ Kit (already set up) |
| Landing page URL | ✓ `streeka.com/guide` |
| Guide format | ✓ Web page only. PDF later if demand. |
| Exit condition source | ✓ RevenueCat → Zapier → Kit tag `trialist` |
| User story for Email 3 | ✓ Tim — backyard ultra runner, trained with Streeka around a full-time job |

---

*Ready to execute. Start with steps 2 + 3 in parallel: guide content + landing page copy. Both are writing tasks, no platform needed.*
