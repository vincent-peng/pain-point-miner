# Pain Point Miner

Evidence-first workflow for turning real user complaints into product opportunities — then killing weak ideas before they waste build time.

Pain Point Miner is an OpenClaw skill for cross-market pain mining, PM validation, competitor triage, and brutal BUILD / PIVOT / SKIP decisions.

## What it does

- Mines pain signals from forums, social posts, product reviews, marketplaces, and competitor complaints
- Groups repeated complaints into pain clusters
- Builds compact evidence cards before recommending anything
- Scores opportunities across pain, willingness to pay, competition, founder fit, feasibility, and cost
- Applies fatal flags so weak markets do not get inflated by optimism
- Routes specialist validation to the right path, including App Store research for mobile ideas
- Supports multi-agent research for broad or high-stakes niche comparisons

## Core principle

No evidence card, no BUILD recommendation.

A good idea needs more than a loud complaint. It needs repeated pain, source breadth, willingness-to-pay signals, competitor context, and a realistic path to first users.

## Workflow

### Phase 1 — Mine pain signals

Search real-world complaint sources and identify recurring pain clusters.

Output:

- Pain cluster
- Evidence summary
- Source breadth
- Confidence level
- Top recurring topics

See [`references/frustration-signals.md`](references/frustration-signals.md).

### Phase 1.5 — Evidence cards

Create compact, source-backed evidence cards for the strongest candidates.

Each card captures:

- Pain cluster
- User segment
- Representative complaints
- Source breadth
- Existing workarounds
- Paid-solution evidence
- Competitor context
- Confidence

See [`references/evidence-card.md`](references/evidence-card.md).

### Phase 2 — PM challenge + kill logic

Score the opportunity across:

- Need strength
- Willingness to pay
- Alternative gap
- Founder fit
- Technical feasibility
- Startup cost

Then apply fatal flags and calculate a 0–100 opportunity score.

See:

- [`references/scoring-rubric.md`](references/scoring-rubric.md)
- [`references/fatal-flags.md`](references/fatal-flags.md)
- [`references/opportunity-scoring.md`](references/opportunity-scoring.md)

### Phase 3 — Market validation router

Pick the right validation path for the market type.

Examples:

- iOS/mobile → App Store Product Researcher
- SaaS/B2B → G2, Capterra, Product Hunt, pricing pages, case studies
- Chrome extension → Chrome Web Store reviews and permissions
- Devtool → GitHub, npm, PyPI, HN, Reddit, docs, pricing
- Marketplace app → Shopify, WordPress, Slack, Notion, Zapier marketplaces

See [`references/market-validation-router.md`](references/market-validation-router.md).

### Phase 4 — Conditional blueprint

Only generate a product blueprint if the idea clears the evidence threshold.

Blueprints are allowed when:

- Opportunity score is 70+, or
- PM average is 7+, or
- The user explicitly asks for speculative concepts

Otherwise, return validation experiments or adjacent pivots.

## Verdicts

Pain Point Miner should end with one of:

- **BUILD** — strong evidence, clear wedge, reachable users
- **PIVOT** — real pain, wrong framing or market
- **VALIDATE FIRST** — promising but missing critical proof
- **SKIP** — weak pain, weak WTP, saturated market, or bad founder fit

Be blunt. A real 4/10 beats a polite 7/10.

## Multi-agent mode

For broad discovery or high-stakes validation, split research across focused agents:

- Reddit/forum evidence collector
- Social/non-English signal collector
- Review-mining specialist
- Competitor/pricing researcher
- Skeptic agent

The coordinator owns the final judgment and dedupes evidence before scoring.

See [`references/multi-agent-mode.md`](references/multi-agent-mode.md).

## When to use this skill

Use Pain Point Miner for:

- App idea generation
- Niche research
- Frustration and complaint analysis
- Product validation
- Market-gap research
- Comparing opportunity areas
- Deciding whether a concept deserves build time

Do not use it for pure App Store research alone. Use `app-store-product-researcher` for standalone iOS/App Store validation.

## Rules

- Never fabricate data
- Unknown beats invented
- Distinguish direct vs adjacent competitors
- Few competitors means either opportunity or no market — prove which
- Do not recommend generic AI wrappers unless workflow pain and paid alternatives are proven
- No BUILD verdict without source quotes, WTP evidence, competitor context, and founder-fit check
