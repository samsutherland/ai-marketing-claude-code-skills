# AI Discoverability Audit: Streeka — 30-Day Re-Audit (2026-06-17)

Comparison against baseline audit 2026-05-20 (11/30). Method: Claude native knowledge + live web search (approximates grounded retrieval used by Perplexity / ChatGPT-with-search) + direct crawl of streeka.com. **Not** tested: ChatGPT and Perplexity's own model UIs — see Self-Critique. Exact paste-in queries listed at the end.

---

## Headline

**Score: 13/30 (Weak, trending up — +2 vs baseline).** The 403 crawler block — the single biggest baseline blocker — is **fixed and holding**: streeka.com now serves full content to crawlers, and a bare "Streeka" query resolves to the site with a coherent description. That lifted Recognition and Accuracy. But the **structural gaps did not move**: Streeka is still invisible in every category query, has zero authority citations, and a new competitor (Cycling Coach AI) is now actively occupying Streeka's exact "disruption as default" positioning in AI search results.

---

## Scores vs Baseline

| Dimension | Baseline (2026-05-20) | 30-Day (2026-06-17) | Δ |
|---|---|---|---|
| Recognition | 2/5 | 3/5 | +1 |
| Accuracy | 2/5 | 3/5 | +1 |
| Sentiment | 3/5 | 3/5 | 0 |
| Category Presence | 1/5 | 1/5 | 0 |
| Authority | 1/5 | 1/5 | 0 |
| Competitive Position | 2/5 | 2/5 | 0 (negative trend) |
| **TOTAL** | **11/30** | **13/30** | **+2** |

---

## What moved

**Recognition 2→3.** Bare "Streeka" now surfaces streeka.com + the /about page, and AI search returns a real description naming it as a training app with an AI coach, Garmin sync, and founder Sam Sutherland. This is a direct result of the 403 fix — crawlers can finally read the site. (Caveat: only on *branded* queries, and Claude's own model weights still have no native knowledge of Streeka — it's grounded-retrieval-only.)

**Accuracy 2→3.** Founder (Sam Sutherland), Garmin sync, and "AI coach that adapts to schedule/setbacks" all returned correctly. Two gaps remain (see Critical).

## What did NOT move

**Category Presence 1/5.** Streeka appears in **zero** category queries tested: "best AI cycling training app 2026," "cycling app that adapts when you miss sessions," "TrainingPeaks alternatives," "best cycling apps." Every one returns competitors — TrainerRoad, JOIN, Zwift, Strava, Athletica, Spoked, Cycling Coach AI, Athlin, CoachCat — and not Streeka. This is the core problem and it needs editorial coverage + answer-worthy content, neither of which has landed yet (press launched *today*).

**Authority 1/5.** Not cited anywhere. No editorial coverage live, no founder bylines. Press pitches went out 2026-06-17; if any land, expect movement at the 60-day check.

**Sentiment 3/5.** Neutral, unchanged. No reviews surface (still <10 App Store reviews → no `aggregateRating`).

---

## Critical (fix now)

1. **Brand name is being misread as a "streak / habit tracker."** AI search literally described Streeka as an app that "tracks your habits, celebrates your streaks... showcase your training streaks on your home screen." That's wrong — the name "Streeka" → "streak" is pulling the model toward habit-tracker. Fix: over-correct the entity signals AI scrapes. The /about page + schema `description` should hammer "**AI training app for cyclists**" and explicitly frame it as a coaching/plan-adaptation tool, not a streak counter. The name fights you; the copy has to win the argument.

2. **Sydney / Australia geo anchor is STILL live.** AI search returned "Streeka became part of the Stone & Chalk community, a Sydney-based accelerator," and the site's own AU App Store + Sydney/Melbourne testimonials reinforce it. **This was pending action #1 from the baseline and is still undone.** Fix Prospeo + F6S (remove Sydney, set global). Stone & Chalk now adds a third anchor — worth a global-framing line wherever that listing lives.

---

## High Priority (30 days)

3. **Category invisibility.** Two levers, both already in motion or cheap:
   - **Chase roundup inclusion specifically.** The press pitches (BikeRadar, Cycling Weekly) target apps roundups — those roundup pages are exactly what AI cites for "best cycling app" queries. Inclusion there is the fastest path to category presence.
   - **Publish answer-worthy comparison content.** Cycling Coach AI is out-ranking Streeka by running programmatic comparison pages (`/trainingpeaks-alternative`, `/athletica-ai-alternative`, `/gravel-cycling-coach`). Streeka has the blog infrastructure; point it at the exact category questions.

4. **App Store reviews → 10+.** Unlocks `aggregateRating` schema and gives sentiment something to read. Still the cheapest trust-signal win.

---

## Opportunity (90 days) + the strategic flag

5. **Competitive threat — Cycling Coach AI (cyclingcoachai.com).** Their homepage leads with: *"The app rebuilds your week when life gets in the way, so a missed session doesn't break your progress"* — and *"the AI reads your completed rides, sleep, and HRV to adjust next week's load. Missed a session? It reorganizes."* That is **Streeka's "treat disruption as default" differentiator, verbatim**, and they rank for it while Streeka doesn't appear. Same risk as "adaptive training" before it: the message is commoditizing. Either sharpen the differentiation beyond "rebuilds your week," or out-publish them on it. This is the most important strategic finding of this audit.

6. **Founder authority** — bylines / expert citations. Long game.

---

## Competitor playbook: how Cycling Coach AI wins the category queries (2026-06-17)

CCAI's footer is a programmatic AEO link farm — a dedicated, crawlable page per query LLMs get asked. This is the mechanism behind their category presence and Streeka's absence. Their footer columns:

- **Compare Us:** "Cycling Coach AI vs Human Cycling Coach," "vs ChatGPT" → comparison queries.
- **The Best Alternative To:** Zwift / TrainerRoad / Today's Plan / TrainingPeaks / Garmin Coach / JOIN / NUA Coach / Intervals.icu → captures every *"[competitor] alternative"* query.
- **Cycling Coach:** for Beginners / Road / Gravel / Mountain Bike / Indoor / Long Distance → use-case intent.
- **Cycling Training Plans:** Road / Gravel / MTB / Weight Loss / FTP / TT / 50-100-200-mile / Indoor / Hill / Triathlon → long-tail.
- **Resources:** Cycling Heart Rate, Best Cycling Training Apps, Best Apps for Beginners, HR Zone Calculators, iOS App Features.
- **About Us:** **"For AI Agents"** + **"What is Cycling Coach AI?"** (agent-readable entity pages) + an **MCP server** exposing their offer.

**Why it works for AEO specifically:** LLM/AI-search retrieval has a far lower bar than Google ranking — a crawlable page whose H1/body directly answers "TrainingPeaks alternative" with the brand in it is very likely to be retrieved and cited. That's why CCAI surfaced in 4/4 of this audit's category searches and Streeka in 0. **Caveat:** only works with real substance — thin doorway pages get ignored and can hurt. Don't mirror their volume; build a focused, substantive set framed on Streeka's own "disruption as default" differentiator.

**On the MCP server:** not a passive discoverability channel today (assistants don't crawl it in general search; a user must connect it). It's a future/agentic bet + "AI-native" PR signal. **But on-brand for Streeka specifically** — the breakout reel was "connect Strava to Claude," so an MCP server exposing a user's Streeka data to Claude is a real feature aligned to the funnel story. Treat as product/PR, **not** an AEO lever. The crawlable **"For AI Agents" page**, by contrast, *is* a cheap AEO win — do it.

### Concrete action — the comparison-page set (the Category-Presence fix)

Build these as substantive pages (not stubs), each ~600-1000 words, brand in H1 + meta, framed on "treat disruption as default":

**Tier 1 — head-to-head (highest intent):**
1. Streeka vs TrainingPeaks
2. Streeka vs JOIN
3. Streeka vs Cycling Coach AI
4. Streeka vs TrainerRoad

**Tier 2 — "alternative to" (captures competitor-alternative queries):**
5. "TrainingPeaks alternative for a messy schedule"
6. "JOIN alternative for time-crunched cyclists"
7. "Best adaptive cycling training apps" (own the roundup query)

**Tier 3 — entity/agent pages (cheap, do with the schema fixes):**
8. "For AI Agents" / `llms.txt` — agent-readable product summary
9. "What is Streeka?" — clean entity page hammering "AI cycling training app" (also fixes the streak-misread from Critical #1)

Each Tier 1/2 page must answer the query directly and lead with the differentiator, not feature-match CCAI. Re-check at 60-day whether any get cited in AI search.

---

## Re-Audit Schedule

| Dimension | Baseline 2026-05-20 | 30-Day 2026-06-17 | 60-Day (target) | 90-Day (target) |
|---|---|---|---|---|
| Recognition | 2 | 3 | | |
| Accuracy | 2 | 3 | | |
| Sentiment | 3 | 3 | | |
| Category | 1 | 1 | | |
| Authority | 1 | 1 | | |
| Competitive | 2 | 2 | | |
| **Total** | **11** | **13** | | |

- **60-day: ~2026-07-20** — measure: did press coverage land? Check Category Presence + Authority specifically (the two stuck dimensions). Re-check the "streak/habit tracker" misread after entity-signal fixes.
- **90-day: ~2026-08-20** — full comparative re-audit.

---

## Self-Critique / limitations

- Tested via **live web search + direct crawl**, which mirrors what Perplexity and ChatGPT-with-search *retrieve*, but I did **not** query ChatGPT's or Perplexity's own model UIs. For full triangulation, paste these into ChatGPT and Perplexity and compare:
  1. "What is Streeka?"
  2. "What does the Streeka app do?"
  3. "Best AI cycling training apps that adapt to a busy schedule"
  4. "TrainingPeaks alternatives for solo cyclists"
  5. "Streeka vs Cycling Coach AI vs JOIN"
- Claude's **native** (ungrounded) knowledge of Streeka is still effectively zero — all recognition here is grounded-retrieval. That's expected for an app this size and is why entity signals + third-party coverage matter more than on-site copy.
- Competitive set has grown since May (Spoked, Cycling Coach AI, Athletica, Athlin, CoachCat all now surfacing) — the category is getting more crowded in AI results, which is why Competitive Position is flat despite the recognition gain.
