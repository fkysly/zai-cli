# Skills Specification

This repository uses the SKILL.md format with progressive disclosure. Each skill is a folder containing a required SKILL.md and optional resources.

## Directory structure

```
skill-name/
├── SKILL.md
├── references/   (optional)
├── scripts/      (optional)
└── assets/       (optional)
```

## SKILL.md requirements

- YAML front matter with only:
  - `name`
  - `description`
- Markdown body with concise, action-oriented instructions.
- Avoid long prose; assume the agent is capable and needs only non-obvious steps.

### Front matter example

```markdown
---
name: example-skill
description: Brief description with clear trigger conditions.
---
```

## Naming rules

- Lowercase letters, numbers, and hyphens only.
- Keep names under 64 characters.

## Resource folders

- `references/` for documentation to load on demand.
- `scripts/` for reusable automation.
- `assets/` for templates or files used in output.

## Quality bar

- Default to data-only output for CLI examples.
- Include clear prerequisites (environment variables, credentials).
- Validate examples against the current CLI version.

## Non-goals

Do not add extra documentation inside a skill folder (README, changelog, etc.).
