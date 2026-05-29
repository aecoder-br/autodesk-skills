# Skill Authoring Guide

This guide defines the baseline standard for skills in this repository.

## Purpose

A skill should help an AI assistant perform a specific Autodesk API workflow with less guesswork. It should combine trigger guidance, workflow steps, reference pointers, examples, safety notes, and validation checks.

## Required Files

Every skill must include:

- `SKILL.md`: The entry point and operational instructions.
- `references/`: Source notes, API summaries, compatibility notes, and examples.

Recommended when useful:

- `scripts/`: Repeatable helpers for extraction, validation, scaffolding, or testing.
- `assets/`: Diagrams, screenshots, sample payloads, or other supporting artifacts.

## SKILL.md Sections

Use these sections unless there is a clear reason to deviate:

- `Name`: Human-readable skill name.
- `Purpose`: What problem the skill solves.
- `Use When`: Concrete triggers.
- `Do Not Use When`: Boundaries and handoff rules.
- `Workflow`: Ordered steps the assistant should follow.
- `References`: Which files to load for which task.
- `Validation`: How to check the answer or generated output.
- `Security`: Secret handling, authentication cautions, and private data rules.
- `Known Gaps`: Missing coverage or version-sensitive areas.

## Source Handling

Autodesk APIs change over time. For version-sensitive guidance:

- Link to official Autodesk documentation.
- Record the API version, engine version, endpoint family, or product version when known.
- State whether the behavior is documented, observed, or inferred.
- Prefer summaries and links over large copied documentation blocks.

## Examples

Examples should be safe to publish. Use placeholders for credentials and private identifiers:

```text
<AUTODESK_CLIENT_ID>
<AUTODESK_CLIENT_SECRET>
<ACCESS_TOKEN>
<PROJECT_ID>
<BUCKET_KEY>
<OBJECT_KEY>
```

Do not include customer model names, signed URLs, real tokens, private object keys, or private ACC project identifiers.

## Validation Checklist

Before a skill is merged:

- The skill has a clear scope and trigger.
- The workflow is actionable.
- Version-sensitive details are marked.
- Security and credential handling are explicit.
- Examples use placeholders only.
- Reference files are concise and linked to sources.
- The root `README.md` and `skills/README.md` are updated.
