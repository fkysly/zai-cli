# Repo Commands Reference (ZRead)

Explore GitHub repositories using Z.AI ZRead.

## Table of Contents

- Commands
- Usage
- Command Details
  - search
  - tree
  - read
- Workflow Example
- Notes

## Commands

| Command | Purpose |
|---------|---------|
| `search` | Search docs and code in a repository |
| `tree` | Get repository directory structure |
| `read` | Read a specific file from repository |

## Usage

```bash
npx zai-cli repo <command> <owner/repo> [args]
```

**Important**: Repository format is always `owner/repo` (e.g., `facebook/react`, `vercel/next.js`)

## Command Details

### search

Search documentation and code within a repository.

```bash
npx zai-cli repo search <owner/repo> <query>
```

Examples:
```bash
# Search for concepts
npx zai-cli repo search facebook/react "server components"
npx zai-cli repo search vercel/next.js "app router"

# Search for code patterns
npx zai-cli repo search microsoft/typescript "type inference"
npx zai-cli repo search anthropics/anthropic-sdk-python "streaming"
```

Output (data-only by default):
```json
[
  {
    "title": "Server Components RFC",
    "content": "Server Components allow...",
    "url": "https://github.com/...",
    "type": "documentation"
  }
]
```

### tree

Get the directory structure of a repository.

```bash
npx zai-cli repo tree <owner/repo>
```

Examples:
```bash
npx zai-cli repo tree facebook/react
npx zai-cli repo tree vercel/next.js
```

Output (data-only by default):
```json
{
  "name": "react",
  "type": "dir",
  "children": [
    { "name": "packages", "type": "dir", "children": [...] },
    { "name": "src", "type": "dir", "children": [...] },
    { "name": "README.md", "type": "file" }
  ]
}
```

### read

Read a specific file from a repository.

```bash
npx zai-cli repo read <owner/repo> <path>
```

Examples:
```bash
# Read source files
npx zai-cli repo read facebook/react packages/react/src/React.js
npx zai-cli repo read vercel/next.js src/server/app-render.tsx

# Read documentation
npx zai-cli repo read anthropics/anthropic-cookbook README.md

# Read configuration
npx zai-cli repo read vercel/next.js package.json
```

Output (data-only by default):
```json
{
  "content": "/**\n * Copyright (c) Meta...\n */\n\nimport {...",
  "language": "javascript"
}
```

## Workflow Example

Explore a new repository:

```bash
# 1. Get the structure
npx zai-cli repo tree owner/repo

# 2. Search for specific functionality
npx zai-cli repo search owner/repo "authentication"

# 3. Read relevant files
npx zai-cli repo read owner/repo src/auth/handler.ts
```

## Notes

- Only public repositories are accessible
- Use exact `owner/repo` format
- Paths are relative to repository root
- Large files may be truncated
- Rate limits apply based on your Z.AI plan
