# Example 2 — The Signal content pipeline

## Objective

Turn a topic or source article into a structured, review-ready content brief for **The Signal**.

## Workflow

```text
Topic / Article
      ↓
Research notes
      ↓
Claude summary
      ↓
Claude content angles
      ↓
Structured content brief
      ↓
Notion content library
      ↓
Human review
      ↓
Publish manually
```

## Suggested output

```json
{
  "main_idea": "",
  "why_it_matters": "",
  "evidence_to_verify": [],
  "linkedin_angle": "",
  "instagram_angle": "",
  "newsletter_angle": "",
  "sources": [],
  "review_status": "Needs review"
}
```

## Guardrails

- Preserve source links.
- Do not invent citations or evidence.
- Flag missing or weak sources.
- Keep publication behind a human review step.
- Store generated drafts separately from published content.
- Avoid putting secrets or unnecessary personal data into prompts.

## Drawdowns

If research is incomplete, set `review_status` to `Needs research` and stop the publication path.
