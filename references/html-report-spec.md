# HTML Report Spec

Use this when the user asks for an HTML report, GUI, dashboard, viewer, board, visualization, hover/click interactions, or a future visual design for Foresight Radar.

## Product Intent

The HTML report is not a KPI dashboard and not a single decorative radar chart. It is a discussion surface for exploring signals.

It should help the user:

- notice what changed
- compare themes, categories, and sources
- inspect original evidence
- form hypotheses
- see counter-signals and uncertainty
- decide what to watch next

## Metric Integrity

Foresight Radar does not assume exhaustive collection. Raw counts from news articles, search results, collected items, or source mentions are usually not meaningful measures of importance, momentum, urgency, or market heat.

Do not use raw item counts to drive:

- heatmap color
- bubble size
- rank
- trend direction
- urgency
- importance
- "hotness"

unless the report uses a fixed source universe, a stable collection protocol, comparable time windows, and a disclosed denominator.

Counts may be shown as corpus or coverage metadata:

- items reviewed
- sources checked
- primary sources represented
- evidence rows supporting a claim

When counts are shown, label them as coverage metadata and include the caveat that they are not a measure of total market activity unless the collection method supports that claim.

Prefer meaningful metrics:

- official or primary-source figures
- calculated rates with a clear denominator
- disclosed company metrics
- regulatory actions from a defined register
- severity measures such as CVSS or official incident severity
- source diversity and primary-source confirmation
- time-to-event, filing date, enforcement date, release date, or deployment milestone
- analyst judgment with a visible rubric and per-item rationale

If no meaningful metric exists, use qualitative labels, evidence cards, timelines, or debate cards instead of a quantitative-looking chart.

## View Design Checklist

Before adding a visual panel, define:

- question: what does this view help the user understand?
- basis: what evidence, metric, or qualitative rubric drives it?
- source owner: official statistic, calculated metric, analyst judgment, or not scored
- denominator: source universe or denominator when using a count/rate
- caveat: what the view must not be interpreted to mean
- fallback: how to show the same idea without scores if the data is thin

Good Foresight Radar views usually answer one of these:

- What changed during the period?
- Which signals have the strongest primary-source support?
- Which signals have high impact but high uncertainty?
- Which themes are early, emerging, material, or cautionary?
- Which risks or themes appear connected?
- Which sources are high-yield, noisy, or missing?
- Which hypotheses are supported, contradicted, or still open?
- What should be watched next?

Avoid views whose only answer is:

- more articles appeared here
- this category has the most collected items
- this query returned more search results
- this source mentioned the topic more often

## Minimum Data Model

The report should render from Foresight Radar items plus run metadata.

Run metadata:

```json
{
  "theme": "risk-security-governance",
  "focus_tags": ["ai-security", "privacy"],
  "period_start": "YYYY-MM-DD",
  "period_end": "YYYY-MM-DD",
  "geography": "Japan + global",
  "profiles_used": ["risk-security-governance"],
  "coverage_summary": "Core sources checked; discovery used for gaps",
  "limitations": ["No login-gated sources", "Coverage is not exhaustive"]
}
```

Item fields:

- `title`
- `original_title`
- `url`
- `source_name`
- `source_type`
- `published_at`
- `captured_at`
- `category`
- `subcategory`
- `focus_tags`
- `raw_excerpt`
- `summary`
- `importance_score`
- `novelty_score`
- `source_quality_score`
- `theme_relevance_score`
- `confidence_score`
- `momentum`
- `entities`
- `fact_or_inference`
- `why_it_matters`
- `counterpoint`
- `watch_next`
- `limitations`

Score fields are optional. Use them only when they improve comparison, filtering, or visualization. If any score field is shown or used to drive position, color, rank, heatmap intensity, confidence, or bubble size, apply `scoring-governance.md`.

Optional derived fields:

- `signal_strength`: weighted score from importance, novelty, source quality, relevance, and confidence.
- `evidence_strength`: source quality plus source diversity.
- `urgency`: time sensitivity plus impact.
- `uncertainty`: low confidence, conflict, or lack of source diversity.

## Page Structure

```text
Header
  Theme, focus tags, period, geography, coverage, confidence

Snapshot
  Top changes, strongest signal, weakest evidence, watch next

Main Workbench
  Left rail: filters and taxonomy
  Center: visual panels
  Right drawer: selected signal evidence

Discussion Layer
  Debate cards and hypotheses

Evidence Layer
  Evidence table and source health
```

## Visual Panels

Choose panels using `visual-patterns.md`. The goal is not to imitate any named firm. Use public visual grammar as design inspiration, then adapt it to Foresight Radar's evidence model.

### 1. Signal Heatmap

Purpose: show where evidence-backed intensity, impact, uncertainty, or source quality concentrates.

Single-theme mode:

- rows: subcategories
- columns: impact, urgency, novelty, evidence, confidence
- color: score intensity
- badge: coverage metadata only, such as evidence rows reviewed, when useful
- methodology: visible or one click away when color represents a score

Multi-theme mode:

- rows: verticals or subthemes
- columns: horizontals or focus tags
- color: signal strength
- cell size or border: evidence strength or momentum
- methodology: visible or one click away when color, size, or border represents a calculated or judged value

Interactions:

- hover: show coverage metadata, top signal, confidence basis, source diversity
- click: filter item list to that cell and open a cell summary
- click score/method label: show score owner, scale, dimensions, weights, formula, and caveats

### 2. Radar / Scatter View

Purpose: show signal maturity and confidence without pretending precision.

Use a scatter or radar-like layout:

- x-axis: maturity or evidence strength
- y-axis: impact or urgency
- point size: source diversity
- point color: category
- outline: new or accelerating

Interactions:

- hover: title, source, date, scores
- click: open evidence drawer
- click axis/method label: show axis definitions and whether each value is measured, calculated, or analyst judgment

Avoid over-reading exact coordinates. Treat position as a visual guide.

### 3. Timeline

Purpose: show sequence, clustering, and acceleration.

- x-axis: date
- lanes: categories or source tiers
- marker size: severity, official magnitude, or analyst-scored signal strength only when the method is visible

Interactions:

- hover: original title and source
- click: open event detail
- brush or date range filter when enough items exist

### 4. Cluster Map

Purpose: show topic groups and repeated patterns.

Simple first version:

- grouped cards by cluster
- cluster title
- representative item
- coverage metadata when useful
- confidence

Later version:

- force-directed or bubble cluster map only if it improves comprehension

### 5. Signal Cards

Purpose: make each signal discussable.

Card fields:

- title
- category
- date
- source
- one-sentence summary
- why it matters
- confidence
- watch next

Interactions:

- click expands evidence, counterpoint, raw excerpt, source links
- keyboard accessible

### 6. Source Health

Purpose: show whether the radar itself is healthy.

Panels:

- Core sources checked
- High-yield sources
- New source candidates
- Noisy or rejected sources
- Coverage gaps

Interactions:

- click source: show all items from that source
- click candidate: show reason to promote/watch/reject

### 7. Debate Cards

Purpose: turn evidence into discussion.

Each card:

- Hypothesis
- Evidence
- Counterpoint
- Confidence
- What would change our mind
- Watch next

Interactions:

- expand/collapse evidence
- filter evidence table to supporting and contradicting items

### 8. Evidence Table

Purpose: make claims inspectable.

Columns:

- date
- source
- category
- signal
- evidence excerpt
- relevance
- confidence

Interactions:

- sort by date, score, confidence
- filter by source tier, category, focus tag
- open URL

## Interaction Rules

Hover is for preview:

- short tooltip
- no layout shift
- never hide source and date

Click is for depth:

- open right drawer or expand a card
- preserve current filters
- show original title, URL, excerpt, scores, and limitations

Filter is for reframing:

- category
- focus tag
- source tier
- confidence
- novelty
- source type

The UI should always make it clear when filters are active.

## Information Design Rules

- Every visual must answer a question.
- Do not use charts that imply precision the data does not support.
- Do not use raw news/item/source counts as proxies for heat, importance, urgency, or momentum.
- If a count appears, disclose the source universe and label it as coverage metadata unless it is an official statistic or a calculated metric with a valid denominator.
- Keep raw evidence one click away.
- Mark low-confidence and weak-source items visibly.
- Show counter-signals and unknowns, not only confirming evidence.
- Avoid generic KPI cards unless they change interpretation.
- Use color for meaning: category, intensity, confidence, or alert state.
- Do not rely on color alone; include labels or symbols.
- Scores are not mandatory. If the underlying data is qualitative or thin, use labels such as `high / medium / low`, `emerging`, `watch`, or `unknown` rather than invented precision.
- If numeric scores, ranks, indexes, heatmaps, bubble size, color intensity, or confidence values are shown, the scoring method must be visible in the page or drawer.
- Do not present analyst judgment scores as official statistics, probabilities, forecasts, or measured facts.

## Visual Style

Use a calm analytical interface:

- high information density
- restrained color
- strong typographic hierarchy
- compact cards
- tables for evidence
- no decorative hero
- no generic gradient dashboard look

Suitable palette:

- neutral background
- category colors with limited saturation
- warm accent for uncertainty or watchpoints
- strong accent for selected state

## Responsive Behavior

Desktop:

- three-zone workbench: filters, visuals, drawer

Tablet:

- filters collapse to top bar
- drawer becomes side sheet

Mobile:

- single column
- visual panels become stacked summaries
- drawer becomes full-screen sheet
- touch targets at least 44px

## Empty And Error States

No items:

- show period and coverage
- explain likely reason
- suggest source-map or discovery mode

Thin evidence:

- show low coverage warning
- suggest source candidates and queries

Conflicting evidence:

- show contradiction badge
- link supporting and contradicting items

## Performance Notes

V0 should be a static local HTML file with embedded or loaded JSON. Avoid a backend.

Good first implementation:

- plain HTML/CSS/JS
- local JSON array embedded in script tag
- no external API calls
- no build step unless the surrounding project already has one

Use heavier libraries only when they earn their cost:

- D3 for complex custom visualizations
- Observable Plot for quick analytical charts
- Chart.js for simple charts

## Quality Gates

Before considering an HTML report good:

- first screen explains the theme, period, and current state in 5 seconds
- each panel supports a different question
- each panel has a clear evidence basis and caveat
- hover and click reveal evidence, not decorative effects
- a user can trace every major statement to a source
- low confidence and unknowns are visible
- mobile is understandable, not just stacked
- no chart is decorative-only
- the design does not look like a generic AI dashboard
- the chosen visual pattern matches the data type according to `visual-patterns.md`
- any numeric score, rank, index, confidence value, color intensity, or bubble size has visible methodology according to `scoring-governance.md`
- no visual uses non-exhaustive item counts as if they measured market activity or importance

## Suggested V1 Panels

For the first prototype, build only:

1. Snapshot
2. Heatmap
3. Timeline
4. Signal cards
5. Evidence drawer
6. Source health
7. Debate cards

Defer:

- force-directed cluster maps
- hosted app
- authentication
- real-time updates
- automatic scheduling UI
- export workflow
