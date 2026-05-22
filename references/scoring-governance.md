# Scoring Governance

Use this whenever a Foresight Radar output uses numeric scores, ranks, indexes, confidence values, heatmaps, color intensity, bubble size, point position, or any other quantitative-looking encoding.

## Default Rule

Scores are optional. Do not invent scores just because the report is visual.

Use scores only when they help:

- compare items
- filter items
- prioritize evidence
- explain a visual encoding
- support a repeatable watch process

When the evidence is qualitative, sparse, or not comparable, prefer labels:

- `high / medium / low`
- `new / accelerating / stable / declining`
- `watch / assess / act / caution`
- `strong evidence / mixed evidence / weak evidence`
- `unknown`

## Required Disclosure

If scores, heatmaps, ranks, indexes, confidence values, color intensity, bubble size, or point positions are shown, the report must make the scoring method visible in the same screen or in a drawer.

Include:

- score owner: `official statistic`, `calculated metric`, `analyst judgment`, or `not scored`
- scale definition, including what low, middle, and high values mean
- dimensions used
- weights, if any
- formula for any composite index
- per-item score basis or short rationale
- caveat when a score is not a probability, forecast, official metric, or measured fact

## Score Owner

Use these labels:

### official statistic

Use when the value comes directly from a public agency, company filing, audited source, exchange, regulator, standards body, or other primary source.

Examples:

- published incident count
- official enforcement action count
- reported capex
- grid interconnection queue size

### calculated metric

Use when the value is computed from inspectable inputs.

Examples:

- number of source items in the period
- source diversity count
- share of items from primary sources
- week-over-week change in item count

Always show formula.

### analyst judgment

Use when the score reflects qualitative assessment.

Examples:

- importance
- novelty
- strategic relevance
- confidence based on mixed evidence

Always show rubric and rationale. Do not present as fact.

### not scored

Use when the report intentionally avoids scoring.

## Default 1-5 Rubric

Use only when a profile-specific rubric does not exist.

### Importance

- `1`: minor, narrow, or unlikely to affect the theme
- `3`: relevant and worth monitoring, but not clearly material
- `5`: material change, major actor, major policy, major incident, or high downstream impact

### Novelty

- `1`: repeat of known narrative or incremental update
- `3`: new detail, new actor, or meaningful confirmation
- `5`: genuinely new development, new category, new risk, or clear shift in direction

### Source Quality

- `1`: unsourced, promotional, secondhand, or low-inspectability
- `3`: credible secondary source or partial primary evidence
- `5`: primary, official, inspectable, dated, and stable source

### Theme Relevance

- `1`: adjacent or weakly related
- `3`: relevant but not central
- `5`: directly answers the theme question

### Confidence

- `1`: weak, conflicting, or single low-quality source
- `3`: plausible but incomplete or mixed
- `5`: strong evidence from primary or multiple independent credible sources

## Composite Index Rule

Do not create a composite index unless it is useful and inspectable.

If used, include:

```text
Index name:
Purpose:
Formula:
Dimensions:
Weights:
Scale:
Owner:
Caveat:
```

Example:

```text
Signal Strength =
  0.30 importance
+ 0.20 novelty
+ 0.25 source quality
+ 0.15 theme relevance
+ 0.10 confidence

Caveat: analyst support score, not a probability or forecast.
```

Avoid composite indexes when:

- the user did not ask for prioritization
- scores are mostly judgment-based and thinly evidenced
- the visual can work with categories or labels
- the formula would create false precision

## GUI Requirements

For HTML reports:

- show a `Method` or `Scoring` control when any scoring is used
- each visual must disclose what drives position, color, size, opacity, or rank
- each scored item must show a score basis in the detail drawer
- confidence must not be described as probability unless statistically estimated
- heatmap cells must show item count and scoring method on hover or click
- allow `not scored` panels when scoring would be misleading

## Bad Patterns

Avoid:

- unexplained red/yellow/green heatmaps
- ranking items without criteria
- fake precision such as `83.7` when the evidence is qualitative
- calling analyst judgment "data"
- using confidence as probability
- hiding weights or formulas
- scoring every item just because the interface supports scores

## Good Patterns

Prefer:

- visible rubric drawer
- simple 1/3/5 scale with text definitions
- per-item rationale
- source owner labels
- qualitative labels when evidence is thin
- explicit caveat: "This is a prioritization aid, not a forecast."
