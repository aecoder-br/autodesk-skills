# Skills

This folder contains Autodesk API skill packs. Each skill should be self-contained and should include a `SKILL.md` entry point.

## Catalog

| Skill | Scope | Entry Point |
| --- | --- | --- |
| `aps-automation-api` | Autodesk Platform Services Design Automation v3, including AppBundles, Activities, WorkItems, aliases, callbacks, and Revit, AutoCAD, Inventor, and Fusion workflows. | [`aps-automation-api/SKILL.md`](aps-automation-api/SKILL.md) |

## Expected Structure

```text
skills/<skill-name>/
|-- SKILL.md
|-- references/
|-- scripts/
`-- assets/
```

Use `../templates/skill/SKILL.md` when starting a new skill and update this catalog when the skill is added.
