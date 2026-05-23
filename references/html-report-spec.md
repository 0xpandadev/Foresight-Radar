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

## Portable Artifact Requirement

Default to a single self-contained `.html` artifact.

The file should:

- open directly from the filesystem with a double click or `file://` URL
- be easy to send to another person as one file
- render without starting a local server
- embed report data as JSON inside a script tag
- embed CSS and JavaScript in the HTML
- avoid local asset paths that will break on another machine
- avoid remote API calls, login, backend services, or runtime secrets
- preserve hover, click, tab, filter, sort, and drawer interactions offline

Do not create a React, Vite, Next.js, Node, Express, or other server/build-based UI for a normal report. Use a multi-file or server app only when the user explicitly asks for one, the dataset is too large for a single file, or the report needs authentication, persistence, collaboration, recurring refresh, or hosted deployment.

If a server-based UI is necessary, state:

- why single-file HTML is insufficient
- what command starts it
- what still works if the server is not running
- whether a portable export is also provided

Avoid CDN dependencies by default. If a library is necessary, prefer embedding the minimal code or choose plain HTML/CSS/JS. A shared report should not go blank because another user's browser cannot reach a CDN.

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

## Adaptive Lens Selection

Do not hard-code the report into Summary + Radar + Heatmap. Those are useful only when they fit the assignment.

Before designing the tabs or panels, use `visual-lens-catalog.md` to select the right lenses. Choose based on:

- user intent: strategy choice, trend exploration, market map, risk watch, source audit, technology adoption, evidence review
- evidence shape: dated events, comparable entities, lifecycle stages, relationships, official metrics, qualitative signals, contradictions, coverage gaps
- output posture: executive brief, analyst landscape, risk monitor, strategy workshop, source audit, investment memo, or trend exploration

Most reports should include:

- 1 orientation lens
- 2 to 4 analysis lenses
- 1 evidence inspection lens
- 1 method and definition lens

Always include a way to inspect evidence and a way to inspect method. Do not include a lens only because it looks impressive.

At generation time, include a short rationale in the Method section:

- selected lenses and why they fit
- rejected lenses that would have misled or added noise
- caveats for each quantitative-looking view

## Plus-Alpha Intelligence Layer

Use `plus-alpha.md` after selecting the lens set. The report should not merely visualize what was collected; it should add compact, evidence-linked interpretive value.

Include 1 to 3 plus-alpha elements by default, unless the user explicitly asks for a plain export.

Good plus-alpha elements include:

- hidden decision: the choice implied by the evidence
- unexpected signal: the non-obvious item that changes interpretation
- tension or contradiction: where evidence disagrees
- strategic implication: what this means for options, capabilities, timing, or risk
- watch trigger: the next event, threshold, filing, standard, release, incident, or date that would change the interpretation
- better lens suggestion: what view should be used next time and why
- source gap: missing source type, geography, actor, or language
- discussion prompt: a question the user should debate
- what not to conclude: a tempting but unsupported interpretation
- metric opportunity: meaningful metric to add if this becomes recurring

Placement:

- Summary can show a compact "So What / Watch Next" strip.
- Signal cards can carry plus-alpha badges.
- Method can show "what not to conclude" and lens rationale.
- Sources can show source gaps and candidates.
- Evidence drawer can show the evidence behind each plus-alpha item.

Guardrails:

- tie each plus-alpha item to evidence, a source gap, or an explicit inference
- do not add unsupported recommendations
- do not add more than 3 unless the user asks for a workshop view
- do not use plus-alpha to hide weak evidence behind confident language
- if the evidence is thin, prefer source gaps, caveats, and next-collection suggestions

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
  "limitations": ["No login-gated sources", "Coverage is not exhaustive"],
  "plus_alpha": [
    {
      "type": "watch_trigger",
      "title": "Next signal to watch",
      "body": "Short evidence-linked prompt",
      "evidence_refs": ["item_id_or_url"],
      "confidence": "medium",
      "action": "What to watch next",
      "caveat": "Why this is not a forecast"
    }
  ]
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

## Adaptive Navigation

Every interactive HTML report should include a compact sticky top header with tabs. The exact labels should come from the selected lenses, not a fixed dashboard template.

Always include:

- `Summary`: strategic summary, key changes, watch next
- `Method`: definitions, scoring rules, visual encodings, denominators, and limitations
- an evidence inspection view, usually `Evidence`, `Signals`, `Sources`, or `Ledger`

Common optional tabs:

- `Radar`: maturity, impact, urgency, evidence strength, or other meaningful axes
- `Heatmap`: evidence-backed intensity, uncertainty, impact, source quality, or rubric-based judgment
- `Timeline`: sequence of developments and milestones
- `Portfolio`: strategic options, resource allocation, or action posture
- `Landscape`: market, value-chain, category, or ecosystem structure
- `Scenario`: uncertainty drivers and plausible futures
- `Risk`: exposure, interconnection, regulation, control gaps
- `Sources`: source health, coverage, candidates, gaps, and caveats

Tabs may switch visible panels or scroll to sections, but they must:

- work without page reloads
- show an active state
- preserve current filters where practical
- remain usable on mobile as a horizontal tab strip, dropdown, or segmented control
- never hide the current theme, period, or coverage caveat

Standard interaction behavior:

- hover previews title, source, date, summary, and basis
- click opens a drawer, expanded card, cell summary, or filtered evidence table
- clicking a visual method label opens the relevant definition or scoring explanation
- filters show an active state and a clear reset action
- evidence URLs remain one click away

## Visual Panels

Choose panels using `visual-lens-catalog.md` first and `visual-patterns.md` second. A lens defines the analytical question; a visual pattern defines the chart grammar. The goal is not to imitate any named firm. Use public visual grammar as design inspiration, then adapt it to Foresight Radar's evidence model.

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

V0 should be a static local HTML file with embedded JSON. Avoid a backend and avoid loading a separate local JSON file unless the user explicitly wants a folder-based artifact.

Good first implementation:

- plain HTML/CSS/JS
- local JSON array embedded in a script tag
- no external API calls
- no local server
- no build step
- no required CDN

Use heavier libraries only when they earn their cost:

- D3 for complex custom visualizations
- Observable Plot for quick analytical charts
- Chart.js for simple charts

## Quality Gates

Before considering an HTML report good:

- it opens as a single `.html` file without running a server
- it has a sticky top header with tabs chosen from the selected lens set
- it includes a visible lens rationale in Method or Definitions
- it includes 1 to 3 plus-alpha elements, or clearly explains why evidence is too thin and what should be collected next
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
- hover, click, filter, sort, and drawer interactions still work offline

## Suggested V1 Lens Set

For the first prototype, build only the lenses justified by the assignment. A common baseline is:

1. Executive Summary
2. 2 to 4 selected analysis lenses from `visual-lens-catalog.md`
3. Signal or Evidence Ledger
4. Source Health or Coverage Gap when source quality matters
5. Method And Definitions

Example bundles:

- strategy work: Executive Summary, Strategic Implications Map, Option Portfolio, Evidence Ledger, Method
- trend work: Executive Summary, Horizon Scan, Trend Radar or Maturity Curve, Signal Cards, Evidence Ledger, Method
- risk work: Executive Summary, Risk Landscape, Regulation Timeline, Exposure or Control Gap Map, Evidence Ledger, Method
- source audit: Executive Summary, Source Health, Coverage Gap, Evidence Ledger, Method

Defer:

- force-directed cluster maps
- hosted app
- authentication
- real-time updates
- automatic scheduling UI
- export workflow
