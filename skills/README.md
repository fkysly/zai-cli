# Skills Marketplace

This directory contains skills for AI agents. Each skill has a `SKILL.md` file with YAML frontmatter and markdown instructions.

## Available Skills

| Skill | Description |
|-------|-------------|
| [zai-cli](zai-cli/SKILL.md) | Z.AI vision, search, reader, and GitHub repo exploration |

## Install Skills

**OpenSkills** (universal):
```bash
npx openskills install numman-ali/zai-cli
```

**Claude Code**:
```bash
claude skill install numman-ali/zai-cli --skill zai-cli
```

## Add a Skill

1. Create a folder under `skills/` (lowercase, hyphens)
2. Add `SKILL.md` with YAML frontmatter (`name`, `description`)
3. Keep instructions concise - point to CLI `--help` for details
4. Update this README
