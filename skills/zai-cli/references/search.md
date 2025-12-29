# Search Command Reference

Real-time web search using Z.AI Search Prime.

## Table of Contents

- Usage
- Options
- Examples
- Output Format
- Tips

## Usage

```bash
npx zai-cli search <query> [options]
```

## Options

| Option | Description | Values |
|--------|-------------|--------|
| `--count <n>` | Number of results | 1-50 (default: 10) |
| `--domain <d>` | Limit to domain | e.g., `github.com`, `docs.python.org` |
| `--recency <r>` | Time filter | `oneDay`, `oneWeek`, `oneMonth`, `oneYear`, `noLimit` |
| `--content-size <s>` | Result size | `medium`, `high` |
| `--location <l>` | Location hint | `cn`, `us` |

## Examples

```bash
# Basic search
npx zai-cli search "React 19 new features"

# Limit results
npx zai-cli search "TypeScript best practices" --count 5

# Domain-specific search
npx zai-cli search "authentication" --domain github.com
npx zai-cli search "useEffect" --domain react.dev

# Recent results only
npx zai-cli search "AI news" --recency oneWeek
npx zai-cli search "security vulnerabilities" --recency oneDay

# Combined options
npx zai-cli search "Node.js 22" --count 10 --recency oneMonth
npx zai-cli search "React tools" --content-size high --location us
```

## Output Format

Default output is **data-only** (results array). Use `--output-format json` to wrap.

```json
[
  {
    "rank": 1,
    "title": "React 19 Release Notes",
    "url": "https://react.dev/blog/2024/...",
    "summary": "React 19 introduces...",
    "source": "react.dev",
    "date": "2024-12-01"
  }
]
```

## Tips

- Use quotes for multi-word queries: `"server components"`
- Combine with `read` command to fetch full content of results
- Use `--recency oneDay` for breaking news or recent updates
- Domain filter is exact match (e.g., `github.com` won't match `gist.github.com`)
