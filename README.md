# Foresight Radar

**Turn any theme into a living signal map.**

Foresight Radar is an agent skill for watching markets, technologies, risks, industries, and weird emerging intersections without drowning in feeds. Give it a theme and a time window. It builds a source map, finds high-signal updates, preserves evidence, and turns the result into a brief you can actually discuss.

It is built for people who do not want another generic news digest. The point is to see what is changing, why it might matter, what evidence supports it, what is still uncertain, and what to watch next.

## Why It Exists

Most monitoring workflows fail in one of two ways:

- they collect too much and become unreadable
- they summarize too quickly and lose the evidence

Foresight Radar sits between those extremes. It starts from a source map, expands only when needed, separates facts from interpretation, and keeps the original source trail close to every claim.

```text
Theme + period
  -> source map
  -> evidence items
  -> signal brief
  -> source candidates
  -> optional interactive HTML report
```

## What It Can Track

Use it for a single theme:

- cybersecurity risk
- AI regulation
- grid technology
- climate adaptation
- semiconductor supply chain

Use it for an intersection:

- AI security + enterprise risk
- energy utilities + data-center power demand
- healthcare + AI governance
- semiconductors + geopolitics

Use it for a source system:

- Which sources are worth watching?
- Which sources are noisy?
- Which new sources should be promoted?
- Is this theme ready for recurring monitoring?

## Core Modes

| Mode | What it does |
|---|---|
| `source-map` | Discovers, evaluates, and organizes sources for a theme |
| `watch` | Produces an evidence-linked brief for a theme and period |
| `diff` | Compares the current run with a previous brief |
| `source-audit` | Promotes, demotes, rejects, or adds source candidates |
| `schedule-ready` | Decides whether the theme is mature enough for recurring monitoring |
| `html-report` | Specifies or generates an interactive local HTML report |

## The Big Idea

Foresight Radar treats monitoring as a learning system.

Sources are not just inputs. They are part of the product.

Each run can improve the radar:

- Core sources become clearer
- Noisy sources get rejected
- New source candidates are surfaced
- Repeated theme combinations can become reusable profiles
- Watchpoints become sharper over time

## Built-In Taxonomy Discipline

The skill avoids profile sprawl.

If you ask for `security risk`, `cyber risk`, `privacy risk`, `AI risk`, or `technology risk`, it does not automatically create five overlapping profiles. It normalizes them into a broader canonical lens such as:

```text
risk-security-governance
  focus: cybersecurity
  focus: privacy
  focus: ai-security
  focus: model-risk
```

Narrow child profiles are created only when the source map, scoring rubric, audience, or recurring use case is materially different.

## Evidence First

Every important claim should stay attached to inspectable evidence:

- original title
- source URL
- source type
- publication date
- captured date
- short excerpt
- fact vs inference
- why it matters
- limitations

The output should make it easy to ask: “Where did this come from?”

## Optional Scoring, Not Fake Precision

Foresight Radar does not require scoring.

If scores, ranks, indexes, heatmaps, bubble sizes, confidence values, or color intensity are used, the method must be visible. The report should disclose:

- whether the value is an official statistic, calculated metric, analyst judgment, or not scored
- what the scale means
- what dimensions and weights were used
- the formula for any composite index
- the per-item rationale
- a caveat when scores are not probabilities, forecasts, or official measurements

If the evidence is thin, qualitative labels are preferred over invented precision.

## Counts Are Not Insight

Foresight Radar does not assume exhaustive collection.

That means raw news counts, search-result counts, article counts, or collected-item counts should not be used as a proxy for importance, momentum, urgency, or market heat.

Counts can be useful as coverage metadata:

- how many evidence rows were reviewed
- how many core sources were checked
- how many primary-source items support a claim

But a category with more collected articles is not automatically more important. If a heatmap, bubble size, rank, or trend line uses a number, the report must explain why that number is meaningful, what the denominator is, and what the visual must not be interpreted to mean.

When the data is qualitative or incomplete, Foresight Radar should use evidence cards, timelines, debate cards, or clear labels instead of pretending a weak count is a metric.

## Interactive HTML Reports

Foresight Radar can also produce a local HTML discussion surface.

The default output is a portable single-file `.html` report. It should open directly in a browser, work from a file preview, and be easy to send to another person without asking them to start a server. CSS, JavaScript, and report data should be embedded in the file unless the user explicitly asks for a hosted app or a larger operational UI.

Reports use an adaptive top tab bar. The exact tabs should be chosen from the report's evidence and purpose, not from a fixed dashboard template.

Common tabs include:

- Summary or Executive Summary
- Radar
- Heatmap
- Timeline
- Portfolio
- Landscape
- Scenario
- Risk
- Signals
- Sources or Evidence
- Method

Hover should preview the signal. Click should open evidence, a detail drawer, or a filtered table. The Method tab should explain definitions, visual encodings, scoring rules, caveats, and source coverage.

The goal is not one decorative radar chart. The goal is a set of coordinated views that help you notice, compare, inspect, debate, and decide what to watch next.

The skill includes a visual lens catalog so each report can choose the right workbench:

- strategy portfolio for decision work
- trend radar or horizon scan for foresight work
- market landscape or value-chain map for ecosystem work
- risk landscape, regulation timeline, exposure map, or control gap map for risk work
- source health, coverage gap, and evidence ledger for research quality

Reports also include a plus-alpha intelligence layer: 1 to 3 compact, evidence-linked additions that make the output more useful than a mechanical dashboard. Examples include hidden decisions, unexpected signals, contradictions, watch triggers, source gaps, discussion prompts, what not to conclude, and better-lens suggestions for the next run.

Common lens examples:

- Snapshot
- Signal Heatmap
- Radar / Scatter View
- Timeline
- Signal Cards
- Evidence Drawer
- Source Health
- Debate Cards
- Evidence Table

Hover is for preview. Click is for evidence. Filters are for reframing the discussion.

## Visual Pattern Library

The skill includes a visual reference catalog inspired by public, inspectable artifacts:

- technology radars
- hype and maturity curves
- analyst quadrants and waves
- risk landscape maps
- market maps
- heatmaps and bubble heatmaps
- timelines and event streams
- trend cards
- source health boards

It does not claim proprietary access to any firm's methods. It borrows public visual grammar and adapts it to a transparent evidence model:

```text
Signal -> Evidence -> Interpretation -> Counter-signal -> Watch Next
```

## Example Prompts

Create a source map:

```text
Use $foresight-radar to create a source map for AI security risk, with public sources only and no paid APIs.
```

Run a watch:

```text
Use $foresight-radar to watch energy utilities and data-center power demand for the last 30 days.
```

Generate a discussion-ready HTML report:

```text
Use $foresight-radar to research cybersecurity risk for the last 14 days and produce an interactive local HTML report with hover/click evidence.
```

Audit sources:

```text
Use $foresight-radar to audit this source map and recommend which sources to promote, demote, reject, or keep as discovery-only.
```

Check recurring-readiness:

```text
Use $foresight-radar to decide whether this theme is ready for weekly monitoring.
```

## Repository Structure

```text
.
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    ├── brief-format.md
    ├── html-report-spec.md
    ├── item-schema.md
    ├── profile-template.md
    ├── scoring-governance.md
    ├── visual-lens-catalog.md
    ├── source-map-template.md
    ├── taxonomy.md
    ├── test-profiles.md
    └── visual-patterns.md
```

## Design Principles

- Start with source maps, not vibes.
- Prefer five high-signal updates over twenty shallow ones.
- Keep evidence close to every claim.
- Normalize overlapping themes instead of multiplying profiles.
- Use scores only when they clarify.
- Make uncertainty visible.
- Treat HTML reports as discussion surfaces, not dashboards full of decoration.
- Let the radar improve with every run.

## What This Is Not

Foresight Radar is not:

- a full web crawler
- a paid data platform
- a social media firehose
- a black-box ranking engine
- a replacement for professional legal, medical, investment, or security advice
- a dashboard that hides weak evidence behind beautiful colors

It is a practical skill for building a sharper external-signal habit.
