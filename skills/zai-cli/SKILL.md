---
name: zai-cli
description: |
  Z.AI capabilities for agents via zai-cli: (1) Vision - analyze images, screenshots, diagrams, charts, videos, OCR, error diagnosis using GLM-4.6V (2) Search - real-time web search with domain/recency filtering (3) Reader - fetch and parse web page content to markdown (4) Repo - search and read GitHub repository code and documentation via ZRead. Use when needing to analyze visual content, search the web, read web pages, or explore GitHub repos. Requires Z_AI_API_KEY environment variable.
---

# ZAI CLI Tools

Access Z.AI capabilities via `npx zai-cli`. No installation required.

## Setup

Set the `Z_AI_API_KEY` environment variable. The CLI provides clear guidance if missing.

```bash
export Z_AI_API_KEY="your-api-key"
```

Get your key at: https://z.ai/manage-apikey/apikey-list

## Capabilities

| Domain | Use For | Command |
|--------|---------|---------|
| Vision | Images, screenshots, diagrams, videos | `npx zai-cli vision <cmd>` |
| Search | Real-time web search | `npx zai-cli search <query>` |
| Reader | Web page content extraction | `npx zai-cli read <url>` |
| Repo | GitHub repository exploration | `npx zai-cli repo <cmd>` |
| Tools | MCP discovery + schemas | `npx zai-cli tools` |
| Call | Invoke any tool | `npx zai-cli call <tool>` |
| Code | Tool chaining (TypeScript) | `npx zai-cli code <cmd>` |

## Quick Examples

```bash
# Analyze an image
npx zai-cli vision analyze ./screenshot.png "What errors do you see?"

# Search the web
npx zai-cli search "React 19 new features" --count 5
```

## Output Format

Default output is **data-only** for token efficiency. Use `--output-format json` to wrap responses:

```json
{
  "success": true,
  "data": "...",
  "timestamp": 1234567890
}
```

Errors include actionable help (stderr):

```json
{
  "success": false,
  "error": "Error message",
  "code": "ERROR_CODE",
  "help": "How to fix..."
}
```

## Detailed References

- **Vision commands (8 tools)**: See [references/vision.md](references/vision.md) for all parameters and examples
- **Search options**: See [references/search.md](references/search.md) for filtering and output format
- **Reader options**: See [references/reader.md](references/reader.md) for format and caching options
- **Repo commands**: See [references/zread.md](references/zread.md) for GitHub operations
- **Tool discovery & raw calls**: See `zai-cli tools`, `zai-cli tool <name>`, and `zai-cli call <tool>` in the CLI help
- **Code Mode**: See `zai-cli code --help` for tool-chaining workflows
