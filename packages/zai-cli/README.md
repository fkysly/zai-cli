# zai-cli

MCP-native CLI for Z.AI vision, search, reader, and repo tools.

## Install

```bash
npm i -g zai-cli
zai-cli --help
```

Or use npx:

```bash
npx zai-cli --help
```

## Setup

```bash
export Z_AI_API_KEY="your-api-key"
```

## Examples

```bash
# Vision analysis
zai-cli vision analyze ./screenshot.png "What errors do you see?"

# Web search
zai-cli search "React 19 new features" --count 5

# Read a page
zai-cli read https://example.com --format markdown
```

## Output format

Default output is data-only for token efficiency. Use `--output-format json` for structured output.

## Documentation

- CLI help: `zai-cli --help`
- Vision: `zai-cli vision --help`
- Tools: `zai-cli tools`, `zai-cli tool <name>`, `zai-cli call <tool>`

## License

MIT
