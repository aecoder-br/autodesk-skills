# Autodesk Skills

Autodesk Skills is an open source repository for AI assistant skills focused on Autodesk developer workflows. The goal is to collect practical, reusable skill packs for Autodesk APIs, including Revit API, Autodesk Platform Services (APS), Design Automation, Data Management, Model Derivative, Viewer, ACC integrations, and related automation patterns.

This repository is designed as a skill storage and curation project, not as a runtime package. Each skill should be self-contained, documented, source-aware, and useful to assistants or developers who need reliable Autodesk API guidance.

## Current Skills

| Skill | Status | Scope |
| --- | --- | --- |
| [`aps-automation-api`](skills/aps-automation-api/SKILL.md) | Draft | Autodesk Platform Services Design Automation v3, including AppBundles, Activities, WorkItems, aliases, callbacks, and product-specific workflows for Revit, AutoCAD, Inventor, and Fusion. |

## Repository Layout

```text
.
|-- skills/
|   |-- README.md
|   `-- aps-automation-api/
|       |-- SKILL.md
|       |-- assets/
|       |-- references/
|       `-- scripts/
|-- templates/
|   `-- skill/
|       |-- SKILL.md
|       `-- references/
|-- docs/
|   `-- SKILL_AUTHORING.md
|-- CONTRIBUTING.md
|-- CODE_OF_CONDUCT.md
|-- SECURITY.md
|-- SUPPORT.md
|-- NOTICE.md
|-- CHANGELOG.md
|-- LICENSE
`-- README.md
```

## What Belongs Here

Add skills that help an AI assistant or developer work with Autodesk APIs accurately and safely. Good candidates include:

- Autodesk Platform Services API workflows.
- Revit API patterns and transaction rules.
- ACC, BIM 360, Data Management, Viewer, Model Derivative, and OSS workflows.
- Design Automation setup, deployment, troubleshooting, and engine-specific behavior.
- Autodesk product API notes for AutoCAD, Inventor, Fusion, Civil 3D, Navisworks, Dynamo, and related tools.
- Tested scripts, request payloads, validation checklists, and troubleshooting playbooks.

Avoid adding:

- Secrets, access tokens, client IDs, client secrets, private tenant IDs, or customer project data.
- Large copied documentation dumps unless their license clearly allows redistribution.
- Product claims that are not tied to official Autodesk documentation, observed behavior, or reproducible tests.
- Skills that depend on private infrastructure without documenting the public fallback.

## Skill Format

Each skill should live under `skills/<skill-name>/` and use this baseline structure:

```text
skills/<skill-name>/
|-- SKILL.md
|-- references/
|-- scripts/
`-- assets/
```

- `SKILL.md` is the entry point. It should explain when to use the skill, what the assistant should do, and which references or scripts matter.
- `references/` contains concise source notes, links, API summaries, examples, and compatibility details.
- `scripts/` contains helper scripts for validation, extraction, scaffolding, or repeatable workflows.
- `assets/` contains diagrams, screenshots, payload examples, or other supporting files.

For the full authoring standard, see [`docs/SKILL_AUTHORING.md`](docs/SKILL_AUTHORING.md).

## Using a Skill

1. Find the skill under [`skills/`](skills/).
2. Read its `SKILL.md` first.
3. Load only the reference files needed for the task.
4. Prefer scripts in the skill folder when they exist.
5. Verify version-sensitive API details against official Autodesk documentation before making production decisions.

## Contributing

Contributions are welcome. Start with [`CONTRIBUTING.md`](CONTRIBUTING.md) and use the skill template under [`templates/skill/`](templates/skill/).

Before opening a pull request:

- Keep all content in English.
- Include official source links or clear evidence for API behavior.
- Remove credentials, private project identifiers, and customer data.
- Prefer concise, maintainable reference notes over pasted documentation.
- Update [`skills/README.md`](skills/README.md) when adding or renaming a skill.

## Legal And Trademark Notice

This project is independent and is not affiliated with, endorsed by, sponsored by, or supported by Autodesk, Inc. Autodesk product names and service names are trademarks or registered trademarks of Autodesk, Inc. See [`NOTICE.md`](NOTICE.md).

## License

This repository is released under the [MIT License](LICENSE).
