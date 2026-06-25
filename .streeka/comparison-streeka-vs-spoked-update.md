# Update: existing `/compare/streeka-vs-spoked` page — Spoked shutdown

**Part of [[campaign-spoked-shutdown]]** · 2026-06-23 · For the coding agent.
The live `/compare/streeka-vs-spoked` page (built 2026-06-20) compares Streeka to a product that
**shuts down 1 July 2026**. It still earns "Spoked alternative / discontinued" searches, so don't
delete it — repurpose it to capture that intent and route to `/spoked`.

**DECISION (Sam, 2026-06-23): Option A — keep the page + add the shutdown banner. Do NOT 301 it.**
(Option B / redirect kept at the bottom for the record only — do not implement.)

---

## Option A — keep the page, add a shutdown banner ✅ CHOSEN

Keeps the page ranking for "Streeka vs Spoked" and "Spoked alternative," and funnels the now-stranded
traffic to the switch page. Drop this banner at the **top of the page, above the H1.**

### Banner copy (pre-1-July, present tense)

> **Spoked is shutting down on 1 July 2026.** If you're here because your Spoked subscription is
> ending, here's the short version: the free icTrainer they're offering is an indoor-trainer app, not
> a coach. If you want a coaching replacement, we wrote a quick guide to switching.
> **[Coming from Spoked? Start here →](/spoked)**

### Banner copy (swap in on 1 July, past tense)

> **Spoked shut down on 1 July 2026.** If your Spoked subscription has ended, the free icTrainer they
> offered is an indoor-trainer app, not a coach. If you want a coaching replacement, here's how to
> switch. **[Coming from Spoked? Start here →](/spoked)**

### Metadata changes (do these now)

- **Meta title →** Streeka vs Spoked (Shutting Down 1 July) — Your Coaching Replacement
- **Meta description →** Spoked shuts down 1 July 2026. See how Streeka compares and how to switch
  without losing your training history. An AI cycling coach you chat with, with a 2-week free trial.
- **Add internal link** body → `/spoked` (anchor: "Coming from Spoked? Start here").
- **On 1 July:** swap banner + meta to past tense ("shut down on 1 July 2026").

### Accuracy note (don't break this)

The existing page compares Streeka to Spoked-the-product, which was **near-feature-parity** (per the
Jun-20 Tier-2 build lesson — it likely "explained why" too). Leave that honest comparison as-is; the
banner adds the shutdown context and the route to `/spoked`. **Don't retro-fit "unlike Spoked, Streeka
explains why" into this page** — that wedge only holds against icTrainer (the indoor gift), not Spoked.

---

## Option B — 301 redirect to `/spoked` (NOT CHOSEN — record only)

Rejected in favour of Option A. Left here only so the reasoning is on file: a `301
/compare/streeka-vs-spoked → /spoked` would consolidate signal but lose the standalone "Streeka vs
Spoked" comparison ranking. We're keeping both pages instead.

---

## Also update the `/compare` hub

The hub lists "Streeka vs Spoked." Either relabel it "Streeka vs Spoked (shutting down)" with the
`/spoked` link, or, if you take Option B, repoint that hub tile to `/spoked`.
