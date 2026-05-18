# Multi-Agent Mode

Use multi-agent mode for broad discovery, high-stakes validation, or comparing multiple niches. Keep agents evidence-first.

## Principles

- Coordinator owns final judgment.
- Subagents collect evidence or challenge assumptions.
- Subagents should not independently generate polished product ideas unless asked.
- Merge and dedupe before scoring.
- Prefer fewer, focused agents over many vague agents.

## Broad Pain Mining

```text
Coordinator
  ├── Reddit/forum agent: Reddit, HN, niche forums
  ├── Social/non-English agent: X, V2EX, 豆瓣, Japanese/Chinese signals when relevant
  ├── Review-mining agent: App Store/Product reviews/marketplace reviews
  ├── Competitor agent: existing solutions, pricing, positioning
  └── Skeptic agent: WTP, distribution, regulation, fake-pain traps
```

Coordinator output:
- merged evidence cards
- deduped pain clusters
- source confidence
- fatal flags
- opportunity score
- build/skip/pivot verdict

## Mobile Niche Deep Dive

Use `app-store-product-researcher` as the review/competitor specialist.

```text
Coordinator
  ├── Search agent: 3+ App Store keyword angles
  ├── Review agents: top 3 direct competitors
  ├── Social agent: Reddit/X/forum pain outside App Store
  └── Skeptic agent: market saturation, WTP, distribution
```

## Comparing Niches

```text
Coordinator
  ├── Niche agent A
  ├── Niche agent B
  ├── Niche agent C
  └── Skeptic/ranker
```

Each niche agent returns the same compact structure:

```markdown
Niche:
Evidence cards:
Direct competitors:
WTP signal:
Fatal flags:
Opportunity score:
Verdict:
```

## Skeptic Agent Checklist

- Is the pain repeated or just loud?
- Who pays, and why now?
- Is this just an easy-build trap?
- Are competitors highly rated with no real wedge?
- Are reviews complaining about bugs rather than unmet demand?
- Does this require distribution the founder does not have?
- Is regulation/liability being underestimated?

## When Not to Use Multi-Agent Mode

- User asks for a quick screen.
- Niche is narrow and one or two deterministic lookups are enough.
- The added parallelism would only produce more summaries, not better evidence.
