# Contributing

Thank you for helping improve Autodesk Skills. This project collects practical AI assistant skills for Autodesk API workflows, so contributions should be accurate, source-aware, and safe to publish.

## Ground Rules

- Write all repository content in English.
- Do not commit secrets, tokens, credentials, tenant IDs, private project IDs, or customer data.
- Do not copy large sections of proprietary documentation unless redistribution is clearly permitted.
- Link to official Autodesk documentation whenever possible.
- Mark version-specific behavior clearly.
- Prefer small, focused pull requests.

## Adding A Skill

1. Create a folder under `skills/<skill-name>/`.
2. Start from `templates/skill/SKILL.md`.
3. Add concise reference files under `references/`.
4. Add helper scripts under `scripts/` only when they are useful and documented.
5. Add assets under `assets/` only when they support the skill directly.
6. Update `skills/README.md` and the root `README.md` skill table.

Skill names should be lowercase and use hyphens, for example `aps-model-derivative` or `revit-shared-parameters`.

## Skill Quality Checklist

Before submitting a skill, check that it:

- States when the skill should and should not be used.
- Names the relevant Autodesk APIs, products, engines, and versions.
- Separates durable guidance from version-sensitive details.
- Includes source links or explains where the behavior was verified.
- Uses examples that are safe to publish.
- Avoids vague instructions such as "use best practices" without concrete steps.
- Gives the assistant a clear workflow, not just background material.

## Pull Request Checklist

- The change is scoped to one skill, one documentation area, or one repository maintenance task.
- Markdown links work.
- New files use UTF-8 text and LF line endings where practical.
- No generated backups, local caches, or temporary files are included.
- `README.md`, `skills/README.md`, and `CHANGELOG.md` are updated when relevant.

## Reporting Problems

Use GitHub issues for bugs, missing API coverage, outdated guidance, or new skill requests. Use the security process in `SECURITY.md` for vulnerabilities or accidental secret exposure.
