# Opportunity Score

Use a 0-100 score to rank candidates across niches. It is a decision aid, not scientific precision.

## Weighting

| Component | Points | What to check |
|-----------|--------|---------------|
| Pain intensity | 25 | Emotion, urgency, concrete cost/time/risk impact |
| Evidence breadth | 20 | Independent sources, recency, repeated clusters |
| Willingness to pay | 20 | Paid alternatives, explicit WTP, budget owner, pricing tolerance |
| Competition gap | 15 | Repeated incumbent failures, declining reviews, underserved wedge |
| Founder fit / distribution | 15 | Reachable users, domain access, channel, unfair edge |
| Build feasibility | 5 | Solo MVP difficulty, infra, integrations, platform risk |

## Thresholds

| Score | Verdict |
|-------|---------|
| 80+ | BUILD candidate |
| 65-79 | BUILD only with clear wedge and validation plan |
| 50-64 | PIVOT or validate harder |
| <50 | SKIP |

## Caps

Apply [fatal-flags.md](fatal-flags.md) after scoring. Caps override the raw score.

## Output

```markdown
Opportunity score: 68/100
- Pain intensity: 18/25 — ...
- Evidence breadth: 14/20 — ...
- WTP: 12/20 — ...
- Competition gap: 10/15 — ...
- Founder fit: 10/15 — ...
- Feasibility: 4/5 — ...
Caps: none / capped at X because ...
Verdict: PIVOT to ...
```

## Calibration Notes

- Easy build should not rescue weak WTP.
- Strong pain should not rescue impossible distribution.
- High ratings do not kill an opportunity if recent reviews show a specific unresolved wedge.
- Adjacent giants prove broad demand but do not prove a niche-specific revenue ceiling.
