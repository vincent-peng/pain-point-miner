# Frustration Signal Reference

Mine complaints from social posts, forums, product reviews, app reviews, and marketplace reviews.

## Source Types

| Source | Best for | Caveat |
|--------|----------|--------|
| Reddit/forums | raw pain, workarounds, niche language | loud threads may overstate demand |
| X/Twitter | fresh emotion, trend hints | noisy and shallow |
| HN/dev forums | devtool/workflow pain | skewed technical audience |
| V2EX/豆瓣/non-English forums | international and Chinese-language pains | translation/context needed |
| App Store reviews | mobile competitor pain, post-install intent | iOS-biased; may be app-quality complaints |
| G2/Capterra/Product Hunt | SaaS/B2B competitor pain | often polished or vendor-influenced |
| Chrome/marketplace reviews | extension/workflow pain | review volume may be thin |

## Search Queries by Platform

### Reddit
```text
"[frustration phrase]" site:reddit.com
"[frustration phrase]" site:reddit.com/r/[subreddit]
"what app do you wish existed" site:reddit.com
"someone should make" OR "someone should build" site:reddit.com
"why is there no" app site:reddit.com
```

### X / Twitter
```text
"[frustration phrase]" site:x.com
"wish there was an app" site:x.com
"I hate using" "[category]" site:x.com
"烦死了" OR "太麻烦了" site:x.com
```

### Hacker News
```text
"wish there was" OR "someone should build" site:news.ycombinator.com
"I hate" "[tool/category]" site:news.ycombinator.com
```

### V2EX / Chinese communities
```text
"[frustration phrase]" site:v2ex.com
"有没有好用的" OR "太麻烦了" site:v2ex.com
"有没有人做" site:douban.com
```

### App Store / mobile reviews
Use `app-store-product-researcher` where available. Mine reviews for:
- repeated 1-2 star complaints
- 3-star nuanced feature gaps
- recent rating lower than overall rating
- "wish", "please add", "missing", "used to love", "subscription", "crash", "can't share", "sync"

## Frustration Signal Taxonomy

### Tier 1: Strong Buy Intent
- "I'd pay for..."
- "Why isn't there a..."
- "Can someone please make..."
- "Is there a paid tool that..."
- "有没有付费的" / "愿意花钱"

### Tier 2: Active Pain
- "so annoying", "so frustrating", "I hate having to..."
- "every [X] app fails me"
- "烦死了", "真的受不了", "气死"
- "めんどくさすぎ"

### Tier 3: Latent Pain
- "wish there was"
- "it would be nice if..."
- "太麻烦了", "能不能有个"
- "なんでないの"

### Tier 4: Speculative
- "has anyone tried"
- "what do you use for..."
- "有没有推荐"
- "有没有人也觉得"

## Deduplication Rules

1. Count each platform/source type as one independent signal.
2. Same platform, different threads can count separately only if different users and contexts.
3. Same user cross-posting = one signal.
4. Reddit post + comments in same thread = one cluster unless comments introduce distinct pains.
5. Product reviews from one app count as one source; multiple apps can count as separate competitor sources.

## Domain Coverage Checklist

- Productivity & workflow
- Household & home management
- Finance & money management
- Health & wellness
- Developer tools & infrastructure
- Education & learning
- Social & communication
- Entertainment & media
- Shopping & commerce
- Travel & logistics
- SMB/B2B operations
- Marketplace/platform workflows

## Noise Filters

Skip or downgrade complaints that are:
- about specific people only, with no repeatable product angle
- political/ideological rants
- pricing-only complaints for a product users otherwise like
- feature requests already solved or announced
- one-off bugs fixed in recent updates
- generic "AI should do this" without workflow pain
- review complaints about support/logins/crashes unless repeated across competitors
