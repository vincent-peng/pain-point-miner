---
name: pain-point-miner
description: Mine real user complaints into app/product opportunities, then validate concepts with PM scoring and App Store competitor/review analysis. Use for app idea generation, niche research, pain-point mining, frustration/complaint analysis, product validation, market-gap research, App Store competitor checks, or deciding whether a consumer app concept is worth building.
---

# Pain Point Miner

Real complaints → PM challenge → App Store validation. Three phases, one flow.

## Phase Selection

| Situation | Run |
|-----------|-----|
| No idea yet | Phase 1 only |
| Have an idea, need quick screen | Phase 2 only |
| Have an idea, want full validation | Phase 2 → Phase 3 (if ≥ 6) |
| Want to find AND validate | Phase 1 → 2 → 3 |

## Phase 1: Mine Frustration Signals

Search Reddit, X, HN, V2EX, 豆瓣, niche forums for frustration signals.

Read [references/frustration-signals.md](references/frustration-signals.md) for platform-specific search queries, signal tiers (Strong Buy Intent → Speculative), deduplication rules, domain coverage checklist, and noise filters.

### Output

| # | Complaint | Pain Point | Signal | Source |
|---|-----------|-----------|--------|--------|

Signal: 🔴 (3+ independent complaints across platforms) / 🟡 (2) / 🟢 (1, strong emotion)

Scale breadth to the request: 10-15 pain points for broad ideation, fewer for scoped niches. After the table, list **Top 5 Recurring Topics** with: independent source count, existing paid solutions (yes/no), one-line product opportunity.

## Phase 2: 5-Angle PM Challenge

Read [references/scoring-rubric.md](references/scoring-rubric.md) for detailed scoring criteria per dimension.

| Dimension | What to evaluate |
|-----------|-----------------|
| Need Strength | Painkiller or vitamin? Count complaints. Are people paying for inferior solutions? |
| Willingness to Pay | Existing app pricing, subscription tiers, free alternatives people hate but tolerate |
| Alternative Gap | Top 5-7 apps: name, rating, pricing, biggest complaint. Tag Direct/Adjacent. Flag declining recent ratings = opportunity. (higher = fewer/worse alternatives) |
| Technical Feasibility | Solo dev feasible? Hardest challenges? Regulatory risks? (higher = easier) |
| Startup Cost | Dev time, infra cost, time to first paying user. Solo dev. (higher = cheaper) |

### Output

| Dimension | Score | Reasoning |
|-----------|-------|-----------|
| Need Strength | /10 | ... |
| Willingness to Pay | /10 | ... |
| Alternative Gap | /10 | ... |
| Technical Feasibility | /10 | ... |
| Startup Cost | /10 | ... |
| **Average** | **/10** | |

**Verdict:** BUILD / SKIP / PIVOT to X (one sentence). If average < 6, skip Phase 3 and suggest 2-3 adjacent niches.

## Phase 3: App Store Deep Validation

Run only if Phase 2 average ≥ 6.

### Step 1: Competitor Intelligence

Search iTunes with multiple keyword angles (niche term, adjacent term, solution term). Single keywords miss 30-50% of competitors.

If App Store research helper scripts are available, prefer them. Resolve location from `$APP_STORE_RESEARCHER_DIR` or local skill/script paths. If unavailable, use web search and App Store pages. Label any unavailable fields as `unknown` rather than fabricating.

Report per competitor: name, ID, Type (Direct/Adjacent), downloads, revenue, rating, value prop, pricing, why it leads. Include source, date, and estimate label for all figures. **Realistic Revenue Ceiling** = Direct app earnings only, not adjacent giants.

### Step 2: Review Analysis

Top 3 Direct competitors. Fetch reviews if helper scripts available; otherwise use web search.

**Recent sentiment check** (most valuable signal): avg rating of recent 50 vs overall. Gap > 0.5 stars = declining = opportunity.

**Positive:** Top 5 compliments (frequency), core emotional win, most-mentioned features.
**Negative:** Top 10 complaints (frequency), uninstall triggers, "wish list" items.
Include 2-3 verbatim quotes for strongest patterns.

### Step 3: Identify the Gap

1. **Biggest unmet need** — users keep describing, no app solves
2. **Consistent failure** — ALL top apps get wrong
3. **Switching trigger** — what makes a loyal user switch
4. **Emotional pain** — apps treat as edge case

Be specific. "Apps are buggy" ✗ — "Reminder system fails silently after iOS updates, breaking streak tracking" ✓

No gap found = say so. Satisfied users = move on.

### Step 4: App Concept

- **Names** (3): memorable, domain-available, communicates benefit
- **Features** (3-5 max): each mapped to a specific review complaint
- **Onboarding**: step-by-step, time-to-first-win
- **Monetization**: paywall timing, pricing vs competitors, free vs gated
- **Viral concept**: video hook (first 3s) + structure + why it resonates

### Step 5: Final Score

Read [references/scoring-rubric.md](references/scoring-rubric.md) for detailed criteria per dimension.

| Dimension | Score | Reasoning |
|-----------|-------|-----------|
| Pain severity | /10 | Review emotion + frequency |
| Market size | /10 | Direct competitor downloads |
| Competition gap | /10 | 10 = massive unmet need |
| Monetization potential | /10 | Competitor pricing + willingness |
| Build difficulty | /10 | 10 = trivial, 1 = deep expertise (inverse) |
| **Overall** | **/10** | |

**Verdict threshold:** ≥8 BUILD, 7-8 BUILD with differentiation, 6-7 PROMISING (needs X), <6 SKIP (suggest pivots).

## Rules

- Never fabricate data. Can't find it? Say so.
- Brutally honest. 4/10 > polite 7/10.
- Include non-English pain points if the niche has international users.
- <3 direct competitors = flag (opportunity OR no market).
- Revenue figures = always estimates, label with source and date.
- Ground findings in real evidence: quotes, data, pricing.
- Prefer helper scripts for deterministic data when available.