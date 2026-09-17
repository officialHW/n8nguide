# Example 1 — Small-business enquiry triage

## Objective

Classify incoming enquiries, store the result and alert the appropriate person without manually reading every enquiry first.

## Workflow

```text
Form / Webhook
      ↓
Validate input
      ↓
Claude classification
      ↓
Validate structured output
      ↓
IF / Switch
   ↙       ↘
Sales     Support / Other
  ↓             ↓
CRM / Sheet   CRM / Sheet
      \       /
       Notification
```

## Suggested AI output

```json
{
  "category": "Sales",
  "urgency": "medium",
  "summary": "Potential customer asking about pricing",
  "reason": "The enquiry requests commercial information"
}
```

## Drawdowns

- Reject missing email/message fields.
- Validate the AI response before routing.
- Treat invalid JSON as a workflow error rather than guessing.
- Detect duplicate submissions.
- Route uncertain classifications to a human.
- Limit API retries.
