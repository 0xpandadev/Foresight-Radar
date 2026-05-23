# Visual Patterns Reference

Use this when designing Foresight Radar HTML reports or deciding how to visualize a theme. These are public-output patterns to learn from, not proprietary methods to copy or impersonate.

## Boundary Rule

Do not say the report uses McKinsey, Gartner, Forrester, Bloomberg, WEF, Thoughtworks, DHL, Sitra, or GOV.UK methodology. Say it uses public visual patterns inspired by comparable artifacts.

Always adapt the pattern to Foresight Radar's evidence model:

```text
Signal -> Evidence -> Interpretation -> Counter-signal -> Watch Next
```

## Pattern Catalog

### Technology Radar

Public examples:

- Thoughtworks Technology Radar
- DHL Logistics Trend Radar

Core visual grammar:

- items as "blips" or trend points
- quadrants for categories
- rings for adoption, maturity, confidence, or urgency
- movement across editions matters more than exact angular position

Use when:

- showing many signals in one theme
- comparing maturity or recommendation level
- showing movement between runs

Foresight Radar adaptation:

- quadrants: regulation, company moves, technology/product, incidents/research
- rings: watch, assess, act, caution; or weak signal, emerging, material, critical
- point shape: new, moved, unchanged, contradicted

Avoid when:

- there are fewer than 8 items
- the user needs exact quantitative comparison
- the categories are unclear

### Hype / Maturity Curve

Public examples:

- Gartner Hype Cycle public methodology pages
- S-curve and maturity-curve analyses in technology and strategy work

Core visual grammar:

- technologies or concepts move through stages over time
- expectation, maturity, or adoption is separated from true evidence

Use when:

- tracking emerging technologies
- separating hype from deployment evidence
- showing where a trend sits in its lifecycle

Foresight Radar adaptation:

- x-axis: maturity stage
- y-axis: market attention or expectation
- overlay: evidence strength, deployment proof, or failure signals
- stages: trigger, hype, disillusionment, learning, productivity

Avoid when:

- the theme is a risk event stream rather than a technology lifecycle
- there is no time-series or stage evidence

### Analyst Quadrant / Wave

Public examples:

- Gartner Magic Quadrant public methodology pages
- Forrester Wave public methodology pages

Core visual grammar:

- 2D competitive or category positioning
- axes represent different strategic dimensions
- scoring criteria and weights should be visible or inspectable

Use when:

- comparing vendors, institutions, sources, or subthemes
- showing relative position with uncertainty
- mapping current capability against future direction

Foresight Radar adaptation:

- x-axis: evidence strength, momentum, or strategic direction
- y-axis: impact, readiness, or current traction
- bubble size: meaningful magnitude, source diversity, or official/carefully defined metric
- opacity: confidence
- show criteria drawer, not a black-box ranking
- if values are judgment-based, label them as analyst judgment, not measured facts

Avoid when:

- the data is too thin for relative ranking
- users might over-interpret exact position
- criteria cannot be explained

### Risk Landscape / Interconnection Map

Public examples:

- World Economic Forum Global Risks Report risk landscape and interconnection maps
- Public-sector futures and horizon-scanning toolkits

Core visual grammar:

- risks placed by likelihood, severity, time horizon, or category
- connections show influence, contagion, or co-occurrence
- uncertainty is central, not hidden

Use when:

- visualizing risk themes
- showing systemic relationships
- explaining why a signal matters beyond itself

Foresight Radar adaptation:

- nodes: signals, risks, actors, or subthemes
- edges: co-occurrence, causal link, shared source, or plausible influence
- node color: category
- node size: severity or signal strength
- edge style: direct evidence vs inference

Avoid when:

- links are speculative and not labeled
- a simple table would be clearer

### Market Map / Landscape Map

Public examples:

- PitchBook market maps
- Bloomberg Intelligence-style industry dashboards
- consulting market maps and segmentation maps

Core visual grammar:

- organize entities by segment, use case, buyer, geography, or value chain
- reveal white spaces, clusters, and crowded areas
- allow drill-down to companies or evidence

Use when:

- mapping companies, products, sources, policies, or categories
- showing market structure
- identifying crowded vs under-covered areas

Foresight Radar adaptation:

- rows or groups: value-chain segments, buyer groups, technical layers
- cards: entities or signals
- badge: latest evidence, source quality, confidence, or coverage metadata
- click: evidence drawer

Avoid when:

- the theme is event-driven rather than landscape-driven

### Heatmap / Bubble Heatmap

Public examples:

- McKinsey-style industry-by-technique heatmaps in public reports
- financial market heatmaps and tree/heat maps
- Bloomberg-style chart dashboards and market-view composites

Core visual grammar:

- matrix of rows and columns
- color encodes intensity
- bubble size can encode meaningful magnitude, impact, evidence strength, or source diversity
- hover reveals detail

Use when:

- comparing verticals x horizontals
- comparing subcategories x metrics
- spotting concentration, gaps, and outliers

Foresight Radar adaptation:

- rows: categories, subthemes, verticals, source tiers
- columns: impact, urgency, novelty, evidence, confidence, momentum
- color: signal strength
- size: meaningful magnitude, source diversity, or coverage metadata only when labeled
- border: accelerating or new
- if signal strength is composite, expose the formula, dimensions, and weights

Avoid when:

- scores are arbitrary and not explained
- color or size would be driven by non-exhaustive news/item counts
- too many categories make the grid unreadable

### Timeline / Event Stream

Public examples:

- Bloomberg and market-monitor workflows
- competitive intelligence dashboards
- policy and incident trackers

Core visual grammar:

- sequence matters
- lanes separate categories or source types
- marker size or color shows meaningful magnitude, official severity, or disclosed analytical judgment

Use when:

- period tracking is central
- users need to see acceleration or clusters
- source dates are reliable

Foresight Radar adaptation:

- lanes: regulation, incidents, company moves, research, weak signals
- marker: item
- marker size: severity or signal strength only when the method is visible
- marker outline: primary source

Avoid when:

- dates are missing or unreliable

### Trend / Signal Cards

Public examples:

- Sitra Megatrend Cards
- futures and weak-signal card decks

Core visual grammar:

- one card per trend or signal
- plain-language description
- implication and uncertainty
- prompts for discussion

Use when:

- the goal is discussion and ideation
- items need qualitative context
- users need to compare "what this means"

Foresight Radar adaptation:

- Signal
- Evidence
- Why now
- Why it matters
- Counterpoint
- Watch next
- Falsifier

Avoid when:

- the report needs dense comparison of many items

### Source Health Board

Public inspiration:

- research ledgers
- analyst transparency practices
- competitive intelligence source tracking

Core visual grammar:

- show coverage, not just findings
- separate core, watch, discovery, and rejected sources
- reveal gaps and noise

Use when:

- source quality is part of the product
- the user wants recurring monitoring
- coverage or bias risk matters

Foresight Radar adaptation:

- source tier columns
- yield score
- noise score
- latest useful item
- suggested promotion, demotion, or rejection

Avoid when:

- it distracts from a one-off lightweight brief

## Pattern Selection Guide

Use this table before designing the HTML.

| User question | Best pattern | Secondary pattern |
|---|---|---|
| What changed this period? | Timeline | Signal cards |
| Where is evidence-backed impact, uncertainty, or source quality concentrated? | Heatmap | Cluster map |
| Which signals are mature vs weak? | Radar | Hype/maturity curve |
| How do risks relate? | Risk network | Debate cards |
| How do vendors/entities compare? | Quadrant/wave | Market map |
| What should we discuss? | Signal cards | Debate cards |
| Are our sources good enough? | Source health board | Evidence table |
| What is moving between runs? | Radar movement | Timeline |

## Scientific / Analytical Discipline

Use these principles so the visual is not just decoration:

- Start with the analytical question, not the chart type.
- State what each axis means.
- Show the scoring fields that drive position, color, or size.
- Use scores only when they add clarity. Prefer qualitative labels when data is thin.
- Do not use non-exhaustive news, search-result, or collected-item counts as proxies for importance, urgency, momentum, or heat.
- If counts are displayed, label them as coverage metadata unless they come from an official statistic, fixed source universe, or defined register.
- Prefer meaningful measured or calculated metrics: official counts, rates with denominators, severity ratings, filing dates, source diversity, primary-source confirmation, or deployment evidence.
- Identify score owner: official statistic, calculated metric, analyst judgment, or not scored.
- Show scale definitions, weights, formulas, and per-item rationale for scores that affect the visual.
- Warn when scores are not probabilities, forecasts, or official measurements.
- Mark inference separately from fact.
- Treat visual position as approximate unless the data is quantitative.
- Include source and date in every detail view.
- Make uncertainty visible.
- Show counter-signals when available.
- Prefer inspectable evidence over polished narrative.

## References To Consult

Use current official or primary pages when exact details matter:

- Thoughtworks Technology Radar: quadrants, rings, blips, movement.
- DHL Logistics Trend Radar: industry trend radar and periodic refresh.
- Gartner Hype Cycle: lifecycle stages for technology maturity and expectation.
- Gartner Magic Quadrant: two-axis provider positioning.
- Forrester Wave: transparent vendor comparison dimensions and criteria.
- World Economic Forum Global Risks Report: risk severity, landscape, interconnections.
- GOV.UK Futures Toolkit: horizon scanning, driver mapping, 2x2 scenario logic.
- Sitra Megatrend Cards and weak signals: trend cards and futures prompts.
- Bloomberg charting and Bloomberg Intelligence public materials: multi-chart, market-view, industry dashboard grammar.
- PitchBook Market Maps: segmentation and drill-down market landscapes.

Do not copy proprietary visuals. Use these only as public inspiration for choosing appropriate chart grammar.
