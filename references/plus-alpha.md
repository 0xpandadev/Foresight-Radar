# Plus-Alpha Layer

Use this when a Foresight Radar output should feel smarter than a mechanical summary. Plus-alpha is the extra interpretive value that makes the report useful for discussion, not just readable.

It is not decoration and not another chart. It is a small set of evidence-linked prompts, implications, cautions, or next moves that the user did not explicitly ask for but would likely want once they see the evidence.

## Core Rule

For every `watch` or `html-report` output, consider plus-alpha. For interactive HTML reports, include 1 to 3 compact plus-alpha elements by default.

If the evidence is too thin for a strong plus-alpha, include a source gap, caveat, or next-collection suggestion instead of inventing insight.

## Good Plus-Alpha Elements

Choose from these when they fit the assignment.

### Hidden Decision

What decision is implied but not stated?

Use when:

- the user asks for a theme watch but the evidence points to a strategic choice
- multiple plausible actions exist

Example:

- "The real decision is whether to monitor this as regulation risk or operating-model risk."

### Unexpected Signal

What changed in a way the user might miss?

Use when:

- a signal is not the loudest item but changes the interpretation
- a primary-source item contradicts the market narrative

### Tension Or Contradiction

Where does the evidence disagree?

Use when:

- official sources, companies, researchers, or commentators point in different directions
- the report would otherwise look too confident

### Strategic Implication

What does this mean for options, capabilities, timing, or risk?

Use when:

- the theme affects resource allocation, product, investment, compliance, governance, or partnerships

### Watch Trigger

What should change the user's mind next?

Use when:

- there are clear future dates, thresholds, filings, consultations, standards, incidents, releases, or adoption milestones

### Better Lens Suggestion

What additional view would clarify the topic next time?

Use when:

- the current evidence suggests a stronger lens for the next run
- the user may be using the wrong framing

Example:

- "Next run should use a value-chain map rather than a trend radar because the core pattern is infrastructure bottleneck, not adoption maturity."

### Source Gap

What important source type, geography, actor, or language is missing?

Use when:

- the report could be biased by source coverage
- recurring monitoring is being considered

### Discussion Prompt

What question should the user debate after reading the report?

Use when:

- the report is for planning, strategy, or team discussion

### What Not To Conclude

What tempting conclusion would be wrong or premature?

Use when:

- the evidence is early, qualitative, non-exhaustive, or dominated by commentary
- a visualization could invite over-reading

### Metric Opportunity

What meaningful metric should be added if this becomes recurring?

Use when:

- useful official data, registers, disclosed metrics, severity measures, or denominators may exist but were not collected in this run

## HTML Placement

In HTML reports, plus-alpha can appear as:

- a compact strip in Summary
- a "Discussion Prompts" or "So What" panel
- badges attached to selected signal cards
- a Watch Next module
- a Method note explaining what not to conclude

Do not create a tab named `Plus Alpha` unless that is clearer than integrating the elements into the selected lenses. The user should feel the extra intelligence, not see a gimmick.

## Data Shape

Represent plus-alpha elements as:

```json
{
  "type": "hidden_decision | unexpected_signal | contradiction | implication | watch_trigger | better_lens | source_gap | discussion_prompt | not_to_conclude | metric_opportunity",
  "title": "Short label",
  "body": "One or two sentences",
  "evidence_refs": ["item_id_or_url"],
  "confidence": "high | medium | low",
  "action": "Optional next move or watchpoint",
  "caveat": "Optional limitation"
}
```

## Guardrails

- Tie every plus-alpha element to evidence, a coverage gap, or an explicit inference.
- Label inferences and assumptions.
- Do not add more than 3 plus-alpha elements unless the user asks for a deep workshop view.
- Do not use plus-alpha to smuggle in unsupported recommendations.
- Do not turn plus-alpha into a generic tips section.
- Do not repeat the executive summary in different words.
- If a plus-alpha element depends on scoring, the scoring method must be visible.

## Quality Test

Before finalizing, ask:

```text
Would this element change what the user notices, debates, watches, or does next?
```

If the answer is no, remove it.
