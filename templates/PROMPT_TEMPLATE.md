---
title: "Prompt Title"
category: presentations   # presentations | knowledge-transfer | writing | coding
tags: [tag-one, tag-two]
best_models: [model-name]  # only models you actually tested
version: 0.1.0
last_tested: YYYY-MM-DD
---

# Prompt Title

One sentence on what this prompt produces.

## When to Use

- A situation where this prompt helps.
- A situation where it doesn't, and what to use instead.

## Prompt

Copy the block below and replace every `{{VARIABLE}}` before sending.

```text
Role: You are {{ROLE}}.

Context:
{{CONTEXT}}

Task:
{{TASK}}

Constraints:
- {{CONSTRAINT}}

Output format:
{{OUTPUT_FORMAT}}
```

If the prompt itself contains a triple-backtick block, open and close the block above with four backticks instead.

## Variables to Fill

| Variable | What to put here | Example |
|---|---|---|
| `{{ROLE}}` | Who the model should act as | Senior data scientist |
| `{{CONTEXT}}` | Background the model needs | Notes, a transcript, or a draft |
| `{{TASK}}` | The specific job, in one or two sentences | Turn these notes into a 10-slide outline |
| `{{CONSTRAINT}}` | Limits on length, tone, or scope | Max 15 words per bullet |
| `{{OUTPUT_FORMAT}}` | Exact shape of the answer | Markdown table with 3 columns |

## Quality Rules

Check every output against these before using it. Replace the examples with rules specific to this prompt.

- Follows the requested format with no filler or preamble.
- Uses only facts from the provided context and flags gaps instead of guessing.
- Reads like a person wrote it: plain words, varied sentences, no stock phrases.

## Changelog

| Version | Date | Change |
|---|---|---|
| 0.1.0 | YYYY-MM-DD | First version. |
