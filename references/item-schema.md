# Item Schema

Use this shape for collected items, whether written as Markdown, JSONL, CSV, or a table.

```json
{
  "id": "stable optional id",
  "theme": "theme or profile name",
  "run_id": "optional run id",
  "title": "original or normalized title",
  "original_title": "exact source title when available",
  "url": "source URL",
  "source_name": "publisher or organization",
  "source_type": "regulator | company | media | research | community | database | other",
  "published_at": "YYYY-MM-DD or unknown",
  "captured_at": "YYYY-MM-DD",
  "geography": "country/region/global",
  "raw_excerpt": "short original excerpt, not a long copied passage",
  "summary": "1-3 sentence summary",
  "category": "regulation | company_move | product_tech | capital | incident | research | weak_signal | other",
  "entities": ["companies", "institutions", "people"],
  "matched_keywords": ["keywords"],
  "importance_score": 1,
  "importance_score_basis": "why this score was assigned",
  "novelty_score": 1,
  "novelty_score_basis": "why this score was assigned",
  "source_quality_score": 1,
  "source_quality_score_basis": "why this score was assigned",
  "theme_relevance_score": 1,
  "theme_relevance_score_basis": "why this score was assigned",
  "score_owner": "official_statistic | calculated_metric | analyst_judgment | not_scored",
  "fact_or_inference": "fact | inference | assumption | unknown",
  "why_it_matters": "practical implication",
  "limitations": "what is not verified"
}
```

Scores are optional. Use them only when they improve comparison, ranking, filtering, or visualization.

Default scoring scale when no profile-specific rubric exists:

- `1`: weak, low, or thin evidence
- `3`: moderate or mixed evidence
- `5`: strong, high, or well-supported evidence

If scores drive ranking, color, size, position, confidence, or any composite index, include score bases and follow `scoring-governance.md`.
