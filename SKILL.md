---
name: foresight-radar
description: Profile-driven external intelligence radar for themes, industries, risks, technologies, and market shifts. Use when Codex needs to create or update source maps, run an on-demand watch over a date range, produce evidence-linked briefs, compare against a previous run, audit sources, or decide whether a theme is ready for recurring monitoring without relying on paid APIs.
---

# Foresight Radar

## Overview

Operate as a practical external-signal desk. Turn a theme plus a time window into a source-backed radar brief, while improving the theme's source map over time.

This skill is generic. Do not hard-code industries as the supported universe. Compose the closest profile from vertical, horizontal, and intersection lenses. Use test profiles only to validate the workflow.

## Core Principle

Start from known good sources, then expand only when the evidence is thin.

```text
profile sources -> primary sources -> credible context -> community/weak signals
```

Prefer 5 high-signal updates with clear evidence over 20 shallow items.

## Modes

Infer the mode from the user request.

- `source-map`: discover and evaluate sources for a theme.
- `watch`: summarize important developments for a theme and period.
- `diff`: compare the current brief against a previous run or report.
- `source-audit`: promote, demote, reject, or add source candidates.
- `schedule-ready`: decide whether the theme is mature enough for recurring monitoring.
- `html-report`: specify or generate an interactive local HTML report from Foresight Radar items.

If the user gives only a theme, default to `watch` over the last 7 days and say the exact date window used.

## Workflow

1. Resolve the assignment.
   - Extract theme, geography, period, depth, and output format.
   - Normalize near-duplicate themes using `references/taxonomy.md` before creating a new profile.
   - Map the theme to vertical, horizontal, and intersection lenses when possible.
   - If no profile exists, create a lightweight temporary profile from the profile template.

2. Select the source set.
   - Load the relevant profile or source map when available.
   - Check Core sources first.
   - Use Watch sources when Core is thin.
   - Use Discovery only to fill gaps or find new source candidates.
   - Keep Rejected sources and negative keywords out unless the user asks to audit them.

3. Collect evidence.
   - Use current web research when the task depends on recent information.
   - Prefer official, primary, or inspectable sources.
   - Preserve original titles, URLs, dates, source names, and short excerpts.
   - Separate `published_at` from `captured_at` when possible.
   - Do not claim completeness. State coverage limits clearly.

4. Normalize items.
   - Use the item schema in `references/item-schema.md`.
   - Cluster duplicates before summarizing.
   - Score items only when scores improve comparison, ranking, filtering, or visualization.
   - If scores are used, apply the scoring governance rules in `references/scoring-governance.md`.

5. Produce the brief.
   - Use `references/brief-format.md`.
   - Put direct evidence before interpretation.
   - Separate Fact, Inference, Assumption, Unknown, and Watchpoint.
   - Include source links for important claims.
   - If the user asks for an HTML, GUI, dashboard, viewer, board, visualization, hover/click behavior, or interactive report, use `references/html-report-spec.md`.

6. Improve the radar.
   - List new source candidates with reasons.
   - Suggest source promotions, demotions, and rejections.
   - Add negative keywords or noise patterns when found.
   - Do not automatically rewrite saved profiles unless the user asks.

## Source Tiers

Use this ranking unless a profile overrides it.

```text
Tier 0: Saved profile feeds and watchlists
Tier 1: Primary sources
        regulators, official company pages, IR, blogs, release notes,
        standards bodies, GitHub releases, papers, datasets, filings
Tier 2: Credible context
        specialist media, interviews, expert newsletters, analyst notes
Tier 3: Community and weak signals
        Reddit, Hacker News, X, LinkedIn, forums, operator commentary
```

Tier 3 is for early signals and disagreement, not for establishing facts.

## Source Map Rules

Use `references/source-map-template.md` for new source maps.

Classify each source as:

- `core`: check every run when relevant.
- `watch`: useful but not always high-signal.
- `discovery`: useful for finding new sources or weak signals.
- `rejected`: noisy, duplicative, unreliable, or off-scope.

Evaluate sources by:

- originality: primary, secondary, aggregator, commentary
- relevance: hit rate for the theme
- freshness: update cadence and date clarity
- inspectability: stable URLs, archives, RSS, searchable pages
- bias risk: promotional, political, financial, community hype
- language and geography
- cost and access friction

## Profile Shape

Profiles are lightweight lenses, not separate skills. Use `references/profile-template.md`.

Each profile should include:

- theme definition
- included and excluded scope
- core questions
- source tiers
- discovery queries
- keywords and negative keywords
- categories
- entity list
- scoring notes
- report sections
- falsifiers and watchpoints

When multiple profiles apply, compose them instead of creating a new intersection profile immediately. Propose an intersection profile only after repeated use.

## Taxonomy And Alias Rules

Avoid creating many profiles for near-duplicate themes. Read `references/taxonomy.md` when the user asks about broad, overlapping, or ambiguous areas such as security, privacy, AI risk, compliance, IT risk, governance, regulation, energy, utilities, grid, or climate.

Use this order:

1. Map the user's wording to an existing canonical profile when possible.
2. Treat close variants as focus tags, not new profiles.
3. Create a child profile only when the source map, scoring rubric, or audience is materially different.
4. Create an intersection profile only after repeated use of the same combination.

Example:

```text
User says: security risk
Canonical horizontal: risk-security-governance
Focus tags: cybersecurity, enterprise-security, incidents

User says: privacy risk
Canonical horizontal: risk-security-governance
Focus tags: privacy, data-protection, compliance

User says: AI security risk
Canonical horizontal: risk-security-governance
Focus tags: ai-security, model-risk, agent-risk
```

Do not create `security-risk`, `cyber-risk`, `privacy-risk`, and `ai-risk` as separate profiles unless the user explicitly wants separate recurring watches or the source maps diverge.

## Recurring Monitoring Readiness

Only recommend recurring monitoring when:

- the source map has at least 5 credible Core sources or a clear reason fewer are enough
- the theme has been run manually at least twice
- noise patterns and rejected sources are known
- the item schema is stable
- the brief format is useful to the user
- the cost of missing updates is meaningful

If these are not met, recommend another on-demand run or source-map pass first.

## Output Standards

Always include:

- exact period covered
- source coverage summary
- top updates or signals
- evidence links
- why it matters
- watch next
- source candidates or source-map changes
- limitations

Do not present a generic trend list. Every item should change what the user understands, watches, or does next.

## Interactive HTML Reports

HTML reports are discussion surfaces, not decorative dashboards. Use them after Markdown and item data exist, or when the user explicitly asks for a prototype.

Default HTML purpose:

```text
notice signals -> compare patterns -> inspect evidence -> debate hypotheses -> decide what to watch next
```

Use `references/html-report-spec.md` for:

- information architecture
- visual panels
- hover and click behavior
- data fields
- responsive rules
- empty and error states
- design quality gates

Use `references/visual-patterns.md` when deciding which visualization pattern fits the data. The patterns are inspired by public, inspectable examples from technology radars, foresight toolkits, analyst quadrants/waves, risk maps, market maps, and financial dashboards. Do not claim proprietary access to any firm's methods.

Use `references/scoring-governance.md` whenever the report uses numeric scores, ranks, indexes, heatmaps, color intensity, bubble size, confidence values, or other quantitative-looking encodings.

Do not reduce the report to one radar chart. Prefer multiple coordinated views: snapshot, heatmap, radar/scatter, timeline, cluster map, signal cards, source health, debate cards, and evidence table.

## Not In Scope For V0

- full web crawling
- login-gated monitoring
- paid API dependence
- social media firehose monitoring
- automatic source promotion without user approval
- vector databases
- production-grade hosted dashboards
- multi-agent orchestration

## Test Prompts

Use these to validate the generic workflow. They are not hard-coded product scope.

```text
Use $foresight-radar to create a source map for tech risk, AI risk, cybersecurity, and risk management.
Use $foresight-radar to watch tech-risk-security over the last 7 days.
Use $foresight-radar to create a source map for energy, utilities, grid tech, and data-center power demand.
Use $foresight-radar to watch energy-utility-tech for 2026-05-01 to 2026-05-22.
Use $foresight-radar to audit this source map and recommend promotions, demotions, and rejected sources.
```
