---
name: pain-point-miner
description: Orchestrate cross-market pain-point mining and opportunity triage from real complaints, product reviews, forums, and competitor signals. Use for finding pain clusters, validating whether complaints indicate a real opportunity, comparing niches, applying evidence cards/fatal flags/founder-fit checks, or routing to specialist market research. Not for standalone App Store competitor/review research; use app-store-product-researcher for pure iOS/App Store validation.
---

# Pain Point Miner

Real complaints → evidence cards → PM challenge → market router → brutal BUILD / PIVOT / SKIP.

Pain Point Miner is the **orchestrator**. It should not duplicate specialist skills. Route mobile/App Store work to `app-store-product-researcher` when available.

## Phase Selection

| Situation | Run |
|-----------|-----|
| No idea yet | Phase 1 → 2 |
| Have an idea, need quick screen | Phase 2 |
| Have an idea, want full validation | Phase 2 → 3 if evidence survives |
| Mobile/iOS niche | Phase 1 can use App Store reviews; Phase 3 delegates to App Store Product Researcher |
| Comparing niches | Multi-agent or one niche per pass → rank |
| User wants adversarial validation | Phase 2 + fatal flags + skeptic pass |

## Phase 1: Mine Pain Signals

Search for real frustration from social posts, forums, reviews, and competitor complaints.

Read [references/frustration-signals.md](references/frustration-signals.md) for query patterns, signal tiers, sources, dedupe, and noise filters.

For mobile/app niches, also use App Store review mining via `app-store-product-researcher` if available. App reviews are high-intent, post-install pain signals.

### Output

| # | Pain Cluster | Evidence | Source Breadth | Confidence |
|---|--------------|----------|----------------|------------|

After the table, list **Top 5 Recurring Topics** with: independent source count, paid-solution evidence, competitor category, and one-line opportunity.

## Phase 1.5: Evidence Cards

Before recommending anything, create compact evidence cards for the strongest candidates.

Read [references/evidence-card.md](references/evidence-card.md) for the format.

Rule: **no evidence card, no BUILD recommendation.** Weak evidence can still produce a watchlist or validation task.

## Phase 2: PM Challenge + Kill Logic

Read [references/scoring-rubric.md](references/scoring-rubric.md) for 1–10 dimensions and [references/fatal-flags.md](references/fatal-flags.md) for score caps.

| Dimension | What to evaluate |
|-----------|-----------------|
| Need Strength | Painkiller or vitamin? Complaint count, emotion, impact, workaround pain. |
| Willingness to Pay | Paid alternatives, explicit WTP, budget owner, payer/user alignment. |
| Alternative Gap | Direct/adjacent alternatives, satisfaction, recent decline, repeated failures. |
| Founder Fit | Can the builder reach/build for this market? Any unfair access or domain edge? |
| Technical Feasibility | Solo-dev feasible? Integrations, regulatory, reliability, platform risk. |
| Startup Cost | Time/cost to first validated user and first paying user. |

### Output

| Dimension | Score | Reasoning |
|-----------|-------|-----------|
| Need Strength | /10 | ... |
| Willingness to Pay | /10 | ... |
| Alternative Gap | /10 | ... |
| Founder Fit | /10 | ... |
| Technical Feasibility | /10 | ... |
| Startup Cost | /10 | ... |
| **Average** | **/10** | |

Then include:
- **Fatal flags:** none / list with score caps
- **Opportunity score:** 0–100 using [references/opportunity-scoring.md](references/opportunity-scoring.md)
- **Verdict:** BUILD / PIVOT to X / VALIDATE FIRST with Y / SKIP

If average < 6 or opportunity score < 65, skip deep validation unless the user explicitly asks.

## Phase 3: Market Validation Router

Use the market type to pick the right validation path. Read [references/market-validation-router.md](references/market-validation-router.md).

Default routes:
- **iOS/mobile:** delegate to `app-store-product-researcher` for competitor discovery, Sensor Tower estimates, recent reviews, gap, and App Store-specific score. Request an app concept only if Phase 4 blueprint thresholds pass.
- **Android:** Google Play/manual web fallback until a Google Play specialist exists.
- **SaaS/B2B:** G2, Capterra, Product Hunt, pricing pages, case studies, Reddit/forum complaints.
- **Chrome extension:** Chrome Web Store reviews, permissions, pricing, update cadence.
- **Devtool:** GitHub/npm/PyPI downloads, issues, HN/Reddit, docs/pricing.
- **Marketplace app:** Shopify/WordPress/Slack/Notion/Zapier marketplace reviews.

### Required Phase 3 Output

- Market type and selected route
- Direct vs adjacent competitors
- Recent complaint/review themes
- Competitor loophole: what incumbents ignore or consistently fail at
- Realistic revenue/market ceiling from direct competitors only
- Build/skip/pivot verdict with evidence confidence

## Phase 4: Conditional Blueprint

Only generate product blueprints if:
- opportunity score ≥ 70, or
- PM average ≥ 7, or
- the user explicitly asks for speculative concepts.

Blueprints for weak ideas create slop. If thresholds fail, give validation experiments or adjacent pivots instead.

Blueprint fields:
- Wedge
- First user segment
- MVP scope
- First validation test
- Pricing hypothesis
- Acquisition channel
- Why now

## Multi-Agent Mode

For broad or high-stakes research, use parallel evidence collectors and a skeptical coordinator.

Read [references/multi-agent-mode.md](references/multi-agent-mode.md).

Subagents should collect evidence or challenge assumptions — not independently invent product ideas.

## Rules

- Never fabricate data. Unknown beats invented.
- Brutally honest. A real 4/10 is better than a polite 7/10.
- Distinguish Direct vs Adjacent competitors.
- Few competitors is ambiguous: opportunity **or** no market.
- App reviews can be Phase 1 mining signals, not only Phase 3 validation.
- No BUILD verdict without source quotes, WTP evidence, competitor context, and founder-fit check.
- Do not recommend generic AI wrappers unless workflow pain and paid alternatives are proven.
- Prefer specialist scripts/skills for deterministic data; label unavailable fields as `unknown`.
