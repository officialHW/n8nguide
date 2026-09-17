# AI Workflow Builder Guide — Claude × n8n

## Build smarter workflows without starting from a blank canvas

A practical, beginner-friendly guide to turning an idea into a working automation.

---

## 01 — Start with the idea

### From “I have an idea” to “I have a workflow”

A useful workflow can be understood as five parts:

**Trigger → Understand → Decide → Act → Report**

Start with one repetitive task and define the outcome before choosing tools.

Ask:

> What do I keep doing manually that follows roughly the same pattern every time?

Then describe the result you want.

**Example:** When a new lead arrives, classify it, save it, and send the appropriate follow-up.

---

## 02 — The workflow mindset

### Old model vs new model

| Old model | New model |
|---|---|
| Start inside the tool | Start with the outcome |
| Add nodes until it works | Design the process first |
| Copy tutorials | Explain, generate, test and refine |
| Build one large workflow | Build focused workflows |
| Fix failures after launch | Design for failure from the start |

The important shift is simple:

**Design the process first. Wire the software second.**

---

## 03 — Required stacks

You do not need a huge software stack to begin.

| Stack | Purpose |
|---|---|
| **Claude** | Structure requirements, reason over language, classify, extract and draft |
| **n8n** | Connect applications, transform data and execute workflows |
| **Input source** | Form, email, webhook, spreadsheet, database or another application |
| **Destination** | CRM, database, Notion, spreadsheet, email, Slack or another system |
| **Credentials** | API keys, OAuth connections or service credentials |

### Keep the stack small

Add another service only when it solves a clearly defined problem.

---

## 04 — Setup process

### Step 1 — Prepare n8n

1. Create or open your n8n workspace.
2. Connect only the applications needed for the first workflow.
3. Decide what data the workflow can read and write.
4. Use test data before connecting production data.
5. Keep credentials out of prompts and source files.

### Step 2 — Give Claude a useful brief

The quality of the workflow starts with the quality of the brief.

Use this structure:

```text
Build an n8n workflow for this process.

Goal:
[What should happen?]

Trigger:
[What starts the workflow?]

Input data:
[What fields are available?]

Rules:
[How should the workflow decide what to do?]

Actions:
[What should happen after the decision?]

Output:
[What should the final result look like?]

Constraints:
[Security, rate limits, approvals and edge cases]
```

### Better input → better workflow design

Claude can structure your thinking, but vague requirements still produce vague automations.

---

## 05 — How to build workflows

### Example 1 — Small-business enquiry triage

**Use case:** A website enquiry arrives and needs to be classified before someone follows up.

**Flow**

`Form submission → Claude classification → IF / Switch → CRM / Sheet → Email or Slack alert`

**Logic**

1. A new enquiry arrives.
2. Claude extracts intent, urgency and key details.
3. n8n routes the enquiry by category.
4. The record is stored.
5. The relevant person receives a focused notification.

**Example Claude prompt**

```text
Classify this enquiry into one of:
Sales, Support, Partnership, Other.

Return JSON only:
{
  "category": "",
  "urgency": "low|medium|high",
  "summary": "",
  "reason": ""
}
```

---

### Example 2 — The Signal content pipeline

**Use case:** Turn a research idea into a repeatable content workflow for **The Signal**.

**Flow**

`Topic / article input → Research notes → Claude summarise → Claude generate angles → Content brief → Notion content library`

**Suggested output fields**

- Main idea
- Why it matters
- Evidence to verify
- LinkedIn angle
- Instagram carousel angle
- Newsletter angle
- Source links
- Review status

### Human review

The automation should prepare content, not silently publish factual or sensitive claims.

Keep a human review step before publication.

---

## 06 — Build in layers

### The four-layer method

**1. INPUT** — What enters the system?

**2. THINK** — What needs classifying, extracting or deciding?

**3. ACTION** — What should happen next?

**4. CONTROL** — What should happen when something goes wrong?

---

## Drawdowns: design for what can go wrong

A workflow is not production-ready because its happy path works.

**Drawdowns** are failure points, limits and controls that stop an automation from continuing blindly.

Consider:

| Situation | Control |
|---|---|
| Required field missing | Stop and request the missing information |
| Low-confidence AI output | Send to human review |
| API failure | Retry with a defined limit |
| Duplicate record | Detect and skip the duplicate |
| Sensitive action | Require approval before continuing |
| Unexpected output format | Validate before the next node |
| Rate limit | Back off or queue the request |

---

## 07 — Key principles

### 01 — Start with the outcome

Do not begin with a node. Begin with the result you want.

### 02 — Keep each workflow focused

One workflow should have one clear job.

### 03 — Use AI where reasoning is useful

Use Claude for language, classification, extraction, drafting and transformation. Use deterministic n8n logic for rules that do not need AI.

### 04 — Make outputs structured

Consistent JSON and fields are easier to validate, route and reuse than free-form text.

### 05 — Design for failure

Retries, validation, duplicate checks and human review are part of the workflow.

### 06 — Test with ugly data

Try blanks, duplicates, unexpected text, long inputs and API failures.

### 07 — Protect secrets

Never place API keys, passwords or unnecessary personal information into AI prompts.

### 08 — Keep human judgement where it matters

Automation should accelerate work, not remove judgement where accuracy, compliance or reputation matters.

---

## 08 — Your first build challenge

### Build this in 30–60 minutes

Create a workflow that takes a new content idea and turns it into a **review-ready content brief**.

**Input:** Topic

**AI step:** Summarise + generate three angles

**Rules:** Remove duplicates + flag missing sources

**Output:** Save to Notion

**Drawdown:** If no reliable source is provided, mark the item `Needs research` rather than inventing one.

The goal is not to build more nodes.

**The goal is to remove one repeatable piece of work from your week.**

---

## 09 — Before you download

If this guide is published through a landing page or Notion, place the review gate before the downloadable package.

Suggested flow:

`View guide → Leave quick review → Confirmation → Unlock download`

A true submit-to-unlock gate normally requires an external form/download service or a website layer that can verify submission before revealing the file.

Do not collect more personal information than necessary for the review.

---

## 10 — Companion links

Add the final creator links when publishing:

- GitHub — https://github.com/officialHW
- Linktree — [Add final URL]
- Instagram — [Add final URL]
- Stack — [Add final URL]

---

## Credits

Created by **Henry Williams** as a practical learning resource for AI automation, n8n, data and emerging technology.
