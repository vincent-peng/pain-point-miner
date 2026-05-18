# Market Validation Router

Pick the validation path based on where users already look for solutions and leave complaints.

## Routing Table

| Market type | Use |
|-------------|-----|
| iOS/mobile app | `app-store-product-researcher` if available; iTunes Search API, Sensor Tower estimates, iTunes RSS reviews |
| Android app | Google Play pages/reviews, web search; mark estimates unknown until a specialist exists |
| SaaS/B2B | G2, Capterra, Product Hunt, Reddit/forums, pricing pages, docs, case studies |
| Chrome extension | Chrome Web Store reviews, user count, update cadence, permissions, pricing |
| Devtool | GitHub issues/stars/releases, npm/PyPI downloads, HN/Reddit, docs, pricing |
| Marketplace app | Shopify/WordPress/Slack/Notion/Zapier marketplaces and reviews |
| Productized service | Reddit/forums, Google results, agency/service competitors, pricing pages |

## Mobile / App Store Delegation

When the opportunity is iOS/mobile:

1. Prefer the installed `app-store-product-researcher` skill.
2. Use its bundled scripts for deterministic data. Script paths are relative to the `app-store-product-researcher` skill, not this skill.
3. Treat App Store reviews as both:
   - Phase 1 pain-mining evidence
   - Phase 3 validation evidence
4. Bring back only the useful synthesis:
   - Direct vs Adjacent apps
   - downloads/revenue estimates
   - recent sentiment vs overall rating
   - review complaint clusters
   - realistic direct-competitor ceiling
   - market gap and App Store-specific verdict

Do not duplicate the full App Store workflow inside Pain Point Miner.

## Required Validation Questions

- Where do users search for this solution?
- Where do they complain after using existing solutions?
- Who pays?
- What direct competitors define the realistic market ceiling?
- What adjacent competitors inflate the market size but do not prove the niche?
- What would make a user switch?
- What would make acquisition impossible?

## Output

```markdown
Market type: [iOS mobile / SaaS / devtool / extension / marketplace / service]
Route used: [specialist skill, marketplace, review sources, or source set]
Direct competitors: ...
Adjacent competitors: ...
Recent complaint themes: ...
Competitor loophole: ...
Realistic ceiling: ...
Verdict impact: BUILD / PIVOT / SKIP because ...
```
