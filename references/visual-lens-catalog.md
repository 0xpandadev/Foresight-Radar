# Visual Lens Catalog

Use this catalog when choosing what an HTML report should show. A lens is not a chart type. It is a decision view: a way to turn evidence into a question the user can discuss.

Do not always output Summary, Radar, and Heatmap. Choose the lenses that fit the assignment, evidence shape, and user decision.

## Lens Selection Protocol

Before designing the report, classify the assignment.

1. User intent:
   - understand what changed
   - make a strategy choice
   - map a market or ecosystem
   - monitor risk or regulation
   - compare technologies, vendors, or sources
   - form hypotheses
   - audit evidence quality
2. Evidence shape:
   - dated events
   - comparable entities
   - lifecycle or maturity stages
   - relationships and dependencies
   - official metrics or measured values
   - qualitative signals only
   - conflicting claims
   - source coverage and gaps
3. Output posture:
   - executive brief
   - analyst landscape
   - risk watch
   - strategy workshop
   - source audit
   - trend exploration
   - investment or market memo

Then select:

- 1 orientation lens: what this report is about
- 2 to 4 analysis lenses: how to see the pattern
- 1 evidence lens: how to inspect support
- 1 method lens: how definitions, scoring, and caveats are explained
- 1 to 3 plus-alpha elements from `plus-alpha.md`: the extra interpretive value the user did not explicitly request

Use 3 to 7 substantive lenses for most reports. More than 7 usually becomes a gallery rather than a useful workbench.

## Metric Guardrail

A lens does not make weak numbers valid. If a lens uses color intensity, rank, bubble size, quadrant position, trend direction, or any quantitative-looking encoding, apply `scoring-governance.md`.

Do not use raw article counts, search-result counts, collected-item counts, or opportunistic mention counts as proxies for importance, momentum, urgency, adoption, or market heat. Use qualitative labels or evidence cards when meaningful metrics are not available.

## Always Include

These are not optional when producing an interactive report.

### Executive Summary

Question: What should the reader understand in the first 60 seconds?

Use for:

- every report

Good contents:

- bottom line
- what changed
- strongest signal
- weakest evidence
- watch next
- key caveat

### Evidence Ledger

Question: Can every important claim be traced back to a source?

Use for:

- every report

Good contents:

- date
- source
- source tier
- original title
- excerpt
- signal
- confidence
- URL

### Method And Definitions

Question: What do the axes, colors, labels, and scores mean?

Use for:

- every report

Good contents:

- selected lenses and why they were chosen
- definitions
- scale meanings
- source coverage
- scoring rules when used
- limitations
- caveats about non-exhaustive collection

## Strategy And Decision Lenses

### Strategic Implications Map

Question: What does this change imply for choices, capabilities, and risks?

Use when:

- the user wants strategy, not only news
- signals affect operating model, investment, product, risk, or policy

Structure:

- columns: implication, evidence, affected actors, decision, watch next

Avoid when:

- evidence is too early to infer implications

### Option Portfolio

Question: Which actions are available, and how do they compare?

Use when:

- the output should support a decision
- the user needs options rather than a passive brief

Structure:

- options as cards
- axes: upside, effort, reversibility, risk, evidence strength

Avoid when:

- the user has not asked for action or decision framing

### Strategic Portfolio Matrix

Question: Where should attention or resources go?

Use when:

- comparing initiatives, technologies, markets, or risks
- resource allocation is the hidden decision

Structure:

- x-axis: evidence strength or readiness
- y-axis: strategic importance or downside exposure
- labels: invest, monitor, experiment, avoid

Avoid when:

- exact position would be arbitrary and unexplainable

### Scenario Matrix

Question: What futures should we prepare for?

Use when:

- uncertainty is high
- two major uncertainties shape outcomes

Structure:

- 2x2 scenario axes
- scenario names
- evidence pushing toward each scenario
- early indicators

Avoid when:

- the uncertainty drivers are not clear

### Decision Tree

Question: What should we do depending on what happens next?

Use when:

- watchpoints can trigger different actions
- thresholds or milestones matter

Structure:

- trigger
- evidence condition
- action
- owner or next research step

Avoid when:

- there are no meaningful trigger conditions

### Tradeoff Board

Question: What are we gaining and giving up?

Use when:

- the topic has competing objectives, such as speed vs control or growth vs resilience

Structure:

- tradeoff pairs
- evidence supporting each side
- unresolved tension

Avoid when:

- the report is mostly descriptive

## Trend And Foresight Lenses

### Technology Or Trend Radar

Question: Which signals are weak, emerging, material, or critical?

Use when:

- many signals can be grouped into meaningful quadrants and rings
- movement between runs matters

Structure:

- quadrants: categories
- rings: stage, confidence, urgency, or recommendation
- blip states: new, moved, unchanged, contradicted

Avoid when:

- there are too few items or the categories are unclear

### Maturity Curve

Question: Is this hype, early deployment, scaling, or normalization?

Use when:

- lifecycle stage matters
- technology readiness or adoption maturity is central

Structure:

- stages over a curve
- evidence of deployment, failures, regulation, or buyer adoption

Avoid when:

- the theme is an event stream with no lifecycle pattern

### Adoption S-Curve

Question: Is adoption still experimental or beginning to scale?

Use when:

- there is evidence of trials, pilots, deployment, budget, or mainstreaming

Structure:

- stages: experiment, early adoption, expansion, mainstream, saturation
- evidence markers

Avoid when:

- there is no adoption evidence beyond commentary

### Horizon Scan Board

Question: What is near, next, and distant?

Use when:

- the time horizon matters
- weak signals and watchpoints need separation

Structure:

- lanes: now, next, later
- cards: signal, evidence, uncertainty, watch next

Avoid when:

- all items are in the same time window and horizon

### Driver Map

Question: What forces are pushing the theme?

Use when:

- political, economic, social, technical, legal, environmental, or operational drivers interact

Structure:

- driver categories
- supporting evidence
- affected signals

Avoid when:

- the report has only isolated events

### Signal Card Wall

Question: Which individual signals are worth discussing?

Use when:

- qualitative interpretation is more useful than measurement
- the report is used in discussion or ideation

Structure:

- signal
- evidence
- why now
- implication
- counterpoint
- watch next

Avoid when:

- dense comparison is the priority

## Market And Ecosystem Lenses

### Market Landscape Map

Question: How is the space structured?

Use when:

- mapping companies, technologies, policies, use cases, or sources

Structure:

- segments, use cases, value-chain stages, or buyer groups
- entities or signals as cards

Avoid when:

- the theme is a short-term event watch

### Value Chain Map

Question: Where in the chain is change happening?

Use when:

- upstream, midstream, downstream, infrastructure, customer, or operations layers matter

Structure:

- value-chain stages
- signals and actors by stage
- bottlenecks and dependencies

Avoid when:

- the theme has no clear chain or workflow

### Ecosystem Network

Question: Who is connected to whom, and why does that matter?

Use when:

- partnerships, dependencies, standards, funding, or influence links matter

Structure:

- nodes: actors, standards, policies, technologies, risks
- edges: evidence-backed relationship or labeled inference

Avoid when:

- relationships are speculative and cannot be labeled

### Competitive Positioning Map

Question: How do comparable entities differ?

Use when:

- vendors, countries, institutions, sources, or subthemes can be compared

Structure:

- axes based on explicit criteria
- uncertainty and source basis visible

Avoid when:

- criteria are unclear or arbitrary

### Buyer / Workflow Map

Question: Where does this matter in the real workflow?

Use when:

- enterprise adoption, operational friction, or user behavior is central

Structure:

- workflow stages
- pain points
- affected roles
- evidence and implications

Avoid when:

- the report has no buyer or operator context

### Profit Pool / Economic Layer Map

Question: Where could economic value or cost pressure move?

Use when:

- market structure, margins, capex, pricing, or business model shifts matter

Structure:

- layers or segments
- value capture logic
- evidence and unknowns

Avoid when:

- no economic evidence or mechanism is available

## Risk, Regulation, And Security Lenses

### Risk Landscape

Question: Which risks are most material and uncertain?

Use when:

- risk, security, regulation, resilience, or governance is central

Structure:

- axes: impact and uncertainty, or severity and time horizon
- labels: direct evidence vs inference

Avoid when:

- risk categories are not defined

### Risk Interconnection Map

Question: Which risks influence or amplify each other?

Use when:

- systemic relationships matter
- one signal can trigger another

Structure:

- nodes: risks or signals
- edges: evidence, plausible mechanism, or shared source

Avoid when:

- links would be purely decorative

### Regulation Timeline

Question: What obligations, deadlines, and policy moves are coming?

Use when:

- laws, consultations, enforcement, standards, or compliance dates matter

Structure:

- dates and milestones
- source authority
- affected actors
- required action or watchpoint

Avoid when:

- dates are unknown or unreliable

### Obligation Matrix

Question: Who has to do what, by when, and under which authority?

Use when:

- compliance or policy obligations need operational clarity

Structure:

- rows: actors or obligations
- columns: authority, deadline, scope, evidence, uncertainty

Avoid when:

- the report is exploratory and obligations are not defined

### Exposure Map

Question: Where are vulnerabilities, dependencies, or concentrations?

Use when:

- security, supply chain, infrastructure, or operational exposure matters

Structure:

- assets, actors, dependencies, and weak points
- evidence and severity basis

Avoid when:

- exposure cannot be linked to evidence

### Control Gap Map

Question: Which controls or mitigations are missing?

Use when:

- the output should support risk management, governance, or audit thinking

Structure:

- risk
- current control
- gap
- evidence
- next check

Avoid when:

- no control framework is relevant

## Evidence And Research Quality Lenses

### Claim Evidence Map

Question: Which claims are supported, weak, or contradicted?

Use when:

- the report includes hypotheses or contested narratives

Structure:

- claim
- supporting evidence
- contradicting evidence
- confidence
- what would change our mind

Avoid when:

- the report is only listing facts

### Contradiction Matrix

Question: Where do sources disagree?

Use when:

- conflicting reports, competing interpretations, or uncertain data matter

Structure:

- rows: claims
- columns: support, contradiction, unknown, implication

Avoid when:

- no meaningful disagreement exists

### Confidence Waterfall

Question: Why is confidence high or low?

Use when:

- the user may over-trust the conclusion
- evidence quality varies sharply

Structure:

- starting hypothesis
- confidence boosters
- confidence reducers
- final confidence label

Avoid when:

- confidence is not important to the decision

### Source Health Board

Question: Is the radar itself healthy?

Use when:

- recurring monitoring, source quality, or coverage gaps matter

Structure:

- core, watch, discovery, rejected
- yield, noise, freshness, inspectability

Avoid when:

- it distracts from a lightweight one-off report

### Coverage Gap Map

Question: What are we not seeing?

Use when:

- missing sources, missing geographies, or missing actor types could bias the report

Structure:

- gaps by geography, source tier, actor, language, or category
- suggested source candidates

Avoid when:

- the report does not make broad claims

## Data And Metric Lenses

### Meaningful Metrics Panel

Question: Which numbers are actually decision-relevant?

Use when:

- official figures, disclosed metrics, rates, severity scores, filings, or denominators exist

Structure:

- metric
- owner
- denominator
- interpretation
- caveat

Avoid when:

- only raw news or item counts are available

### Threshold Watch

Question: Which leading indicators would change the interpretation?

Use when:

- the next decision depends on crossing a threshold

Structure:

- indicator
- threshold
- current evidence
- action if crossed

Avoid when:

- thresholds are invented or arbitrary

### Momentum With Method

Question: Is change accelerating in a measurable way?

Use when:

- comparable time windows, fixed source universe, official series, or defined registers exist

Structure:

- metric series
- collection method
- denominator
- caveat

Avoid when:

- momentum would be inferred from opportunistic article counts

## Recommended Lens Bundles

Use these as starting points, then adapt.

### Strategy Decision

- Executive Summary
- Strategic Implications Map
- Option Portfolio
- Strategic Portfolio Matrix
- Claim Evidence Map
- Evidence Ledger
- Method And Definitions

### Trend Exploration

- Executive Summary
- Horizon Scan Board
- Technology Or Trend Radar
- Maturity Curve
- Signal Card Wall
- Coverage Gap Map
- Evidence Ledger
- Method And Definitions

### Market / Ecosystem Landscape

- Executive Summary
- Market Landscape Map
- Value Chain Map
- Ecosystem Network
- Competitive Positioning Map
- Evidence Ledger
- Method And Definitions

### Risk / Security / Regulation Watch

- Executive Summary
- Risk Landscape
- Regulation Timeline
- Exposure Map
- Control Gap Map
- Contradiction Matrix
- Evidence Ledger
- Method And Definitions

### Source Audit

- Executive Summary
- Source Health Board
- Coverage Gap Map
- Claim Evidence Map
- Evidence Ledger
- Method And Definitions

### Thin Evidence / Early Signal

- Executive Summary
- Signal Card Wall
- Horizon Scan Board
- Claim Evidence Map
- Confidence Waterfall
- Coverage Gap Map
- Evidence Ledger
- Method And Definitions

## Lens Quality Gate

Before finalizing the report, write a short lens rationale:

```text
Selected lenses:
- Lens: why it fits this assignment, evidence basis, caveat
Rejected lenses:
- Lens: why it would mislead or add noise
```

Never choose a lens only because it looks impressive. A good lens changes the conversation.
