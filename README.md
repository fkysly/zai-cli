# ZAI CLI + Skills Marketplace

ZAI CLI is an MCP-native command line interface for Z.AI vision, search, reader, and repo tools. This repository also hosts an open skills marketplace that follows the SKILL.md format used by Claude Code and OpenSkills-compatible agents.

## Quick start (CLI)

```bash
export Z_AI_API_KEY="your-api-key"

npx zai-cli --help
npx zai-cli vision analyze ./screenshot.png "What errors do you see?"
```

Install globally:

```bash
npm i -g zai-cli
zai-cli --help
```

## Skills marketplace

Skills live under `skills/` and follow the SKILL.md format.

Available skills:
- `skills/zai-cli` - Z.AI vision, search, reader, repo, and MCP tool discovery via zai-cli

See `skills/README.md` for contribution guidelines and the skill template.

## Repo layout

- `packages/zai-cli` - The npm package and CLI source
- `skills/` - Marketplace skills

## Development

```bash
cd packages/zai-cli
npm install
npm run build
npm test
```

## Releases

Release steps, tags, and release notes are documented in `RELEASING.md`.

## License

MIT. See `LICENSE`.
