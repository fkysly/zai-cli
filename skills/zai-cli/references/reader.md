# Reader Command Reference

Fetch and parse web page content using Z.AI Web Reader.

## Table of Contents

- Usage
- Options
- Examples
- Output Format
- Use Cases
- Workflow with Search
- Notes

## Usage

```bash
npx zai-cli read <url> [options]
```

## Options

| Option | Description | Default |
|--------|-------------|---------|
| `--format <f>` | Output format | `markdown` |
| `--no-images` | Remove images | false |
| `--no-cache` | Disable cache | false |
| `--with-links` | Include links summary | false |
| `--timeout <s>` | Request timeout (seconds) | 20 |

## Examples

```bash
# Basic page read
npx zai-cli read https://docs.example.com/api

# Get plain text (no formatting)
npx zai-cli read https://blog.example.com/post --format text

# Remove images for cleaner output
npx zai-cli read https://example.com/article --no-images

# Disable cache
npx zai-cli read https://example.com/article --no-cache

# Include links summary
npx zai-cli read https://example.com/resources --with-links

# Increase timeout for slow pages
npx zai-cli read https://slow-site.com/page --timeout 60
```

## Output Format

Default output is **data-only** (string or structured object). Use `--output-format json` to wrap.

## Use Cases

### Documentation Reading
```bash
npx zai-cli read https://docs.python.org/3/library/asyncio.html
```

### Blog/Article Extraction
```bash
npx zai-cli read https://blog.example.com/post --no-images
```

### Resource Discovery
```bash
npx zai-cli read https://awesome-list.com --with-links
```

## Workflow with Search

Combine with search to find and read content:

```bash
# 1. Search for relevant pages
npx zai-cli search "React hooks best practices" --count 3

# 2. Read the most relevant result
npx zai-cli read https://react.dev/reference/react/hooks
```

## Notes

- Returns markdown by default for LLM-friendly output
- Images are retained by default (base64 in markdown)
- Some sites may block automated reading
- Timeout applies to the fetch operation, not parsing
