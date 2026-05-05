---
name: pain-point-miner
description: Mine real user frustration signals from Reddit, X/Twitter, Hacker News, V2EX, and forums to find product opportunities, then challenge and validate app ideas with a 5-angle PM scoring system and App Store competitor analysis. Use when the user wants to find app ideas, validate a niche, research what people complain about, explore "wish this existed" signals, analyze App Store competition, identify market gaps from user complaints, or mentions "app idea", "niche research", "pain point", "frustration mining", "product validation", "complaint analysis", "market gap", or wants to check if an app concept is worth building.
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

**Search queries and platform strategies:** See [references/frustration-signals.md](references/frustration-signals.md)

### Frustration Phrases (quick reference)

| Language | Phrases |
|----------|---------|
| EN | "so annoying", "wish there was", "someone should build", "why is there no", "I wish this existed", "so frustrating", "why hasn't anyone made", "can someone please make", "every [X] app fails me" |
| CN | 烦死了, 太麻烦了, 为什么没人做, 真的受不了, 有没有好用的, 坑, 吐槽, 能不能有个 |
| JP | 面倒くさい, なんでないの, めんどくさすぎ |

### Search Rules

1. At least 3 searches per language with different keyword angles
2. Use site filters: `site:reddit.com`, `site:x.com`
3. Cross-platform appearance = stronger signal
4. Skip pure rants with no product angle
5. Prioritize specific workflow problems and feature gaps

### Output

| # | Complaint | Pain Point | Signal | Source |
|---|-----------|-----------|--------|--------|

Signal: 🔴 (3+ independent complaints across platforms) / 🟡 (2) / 🟢 (1, strong emotion)

Cover ≥15 unique pain points across domains. After the table, list **Top 5 Recurring Topics** with: independent source count, existing paid solutions (yes/no), one-line product opportunity.

## Phase 2: 5-Angle PM Challenge

Rate each dimension 1-10. **Scoring criteria:** See [references/scoring-rubric.md](references/scoring-rubric.md)

| Dimension | What to evaluate |
|-----------|-----------------|
| Need Strength | Painkiller or vitamin? Count complaints. Are people paying for inferior solutions? |
| Willingness to Pay | Existing app pricing, subscription tiers, free alternatives people hate but tolerate |
| Existing Alternatives | Top 5-7 apps: name, rating, pricing, biggest complaint. Tag Direct/Adjacent. Flag declining recent ratings = opportunity |
| Technical Feasibility | Solo dev in ~7 days with AI tools? Hardest challenges? Regulatory risks? (higher = easier) |
| Startup Cost | Dev time, infra cost, time to first paying user. Solo dev. (higher = cheaper) |

### Output

| Dimension | Score | Reasoning |
|-----------|-------|-----------|
| Need Strength | /10 | ... |
| Willingness to Pay | /10 | ... |
| Existing Alternatives | /10 | ... |
| Technical Feasibility | /10 | ... |
| Startup Cost | /10 | ... |
| **Average** | **/10** | |

**Verdict:** BUILD / SKIP / PIVOT to X (one sentence). If < 6, skip Phase 3 and suggest 2-3 adjacent niches.

## Phase 3: App Store Deep Validation

Run only if Phase 2 ≥ 6.

### Step 1: Competitor Intelligence

Search iTunes with ≥3 keyword angles (niche term, adjacent term, solution term). Single keywords miss 30-50% of competitors.

If `app-store-product-researcher` scripts are available:
```bash
SKILL_DIR=~/Developer/Github/personal/app-store-product-researcher
bash $SKILL_DIR/scripts/search_apps.sh "[keywords]"
bash $SKILL_DIR/scripts/fetch_app_stats.sh "ID1,ID2,ID3"
```
Otherwise, use web search and App Store pages.

Report per competitor: name, ID, Type (Direct/Adjacent), downloads, revenue, rating, value prop, pricing, why it leads. **Realistic Revenue Ceiling** = Direct app earnings only, not adjacent giants.

### Step 2: Review Analysis

Top 3 Direct competitors. Fetch reviews:
```bash
bash $SKILL_DIR/scripts/fetch_reviews.sh [APP_ID]
```

**Recent sentiment check** (most valuable signal): avg rating of recent 50 vs overall. Gap > 0.5 stars = declining = opportunity. Every tested niche had declining leaders.

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
- ≥3 Chinese-language pain points if niche has CN users.
- <3 direct competitors = flag (opportunity OR no market).
- Revenue figures = always estimates, label them.
- Ground findings in real evidence: quotes, data, pricing.
- Use `app-store-product-researcher` scripts when available for deterministic data.