# Frustration Signal Reference

## Search Queries by Platform

### Reddit
```
"[frustration phrase]" site:reddit.com
"[frustration phrase]" site:reddit.com/r/[subreddit]
"what app do you wish existed" site:reddit.com
"someone should make" OR "someone should build" site:reddit.com
"why is there no" app site:reddit.com
```

### X / Twitter
```
"[frustration phrase]" site:x.com
"烦死了" OR "太麻烦了" site:x.com
"wish there was an app" site:x.com
```

### Hacker News
```
"wish there was" OR "someone should build" site:news.ycombinator.com
```

### V2EX (Chinese tech forum)
```
"[frustration phrase]" site:v2ex.com
"有没有好用的" OR "太麻烦了" site:v2ex.com
```

### 豆瓣 (Chinese community)
```
"[frustration phrase]" site:douban.com
"有没有人做" site:douban.com
```

## Frustration Signal Taxonomy

### Tier 1: Strong Buy Intent
Phrases where the user is actively seeking a solution and would likely pay:
- "I'd pay for an app that..."
- "Why isn't there a..."
- "Can someone please make..."
- "有没有付费的" (is there a paid one)
- "愿意花钱" (willing to spend money)

### Tier 2: Active Pain
Phrases where the user is suffering but may not have considered paying:
- "so annoying", "so frustrating", "I hate having to..."
- "烦死了", "真的受不了", "气死"
- "every [X] app fails me", "I got annoyed by"
- "面倒くさい", "めんどくさすぎ"

### Tier 3: Latent Pain
Phrases where the user has accepted a workaround but complains about it:
- "wish there was", "it would be nice if..."
- "太麻烦了", "能不能有个"
- "なんでないの"

### Tier 4: Speculative
Phrases indicating curiosity but not urgent need:
- "has anyone tried", "what do you use for..."
- "有没有推荐" (any recommendations)
- "有没有人也觉得" (anyone else feel this way)

## Deduplication Rules

When the same pain point appears across multiple sources:
1. Count each platform as one independent signal (3 platforms = 🔴)
2. Same platform, different threads = 1 signal (avoid counting Reddit thread + Reddit comments separately)
3. Same user cross-posting = 1 signal
4. Aggregator posts (e.g., "top 10 annoying things") = verify individual complaints exist independently

## Domain Categories

When mining, ensure coverage across:
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

## Noise Filter Patterns

Skip complaints that are:
- About specific people (boss, family, landlord) — no product angle
- Political/ideological rants
- About pricing alone for a product that works (they're already paying, just want it cheaper)
- About a feature that's clearly on a roadmap (check if the company announced it)
- About a bug that's already fixed in a recent update