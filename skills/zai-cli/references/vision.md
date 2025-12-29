# Vision Commands Reference

Analyze images and videos using the Z.AI Vision MCP server (GLM-4.6V).

## Table of Contents

- Commands
- Usage
- Constraints
- Command Details
  - analyze
  - ui-to-code
  - extract-text
  - diagnose-error
  - diagram
  - chart
  - diff
  - video
- Output Format

## Commands

| Command | Purpose |
|---------|---------|
| `analyze` | General-purpose image analysis |
| `ui-to-code` | Convert UI screenshot to code/prompt/spec |
| `extract-text` | OCR for code, terminals, documents |
| `diagnose-error` | Analyze error screenshots and suggest fixes |
| `diagram` | Interpret technical diagrams (architecture, UML, etc.) |
| `chart` | Analyze data visualizations and charts |
| `diff` | Compare two UI screenshots for differences |
| `video` | Analyze video content |

## Usage

```bash
npx zai-cli vision <command> <source> [prompt] [options]
```

## Constraints

- **Images**: ≤5MB, JPG/PNG/JPEG
- **Videos**: ≤8MB, MP4/MOV/M4V
- Supports both local files and URLs

## Command Details

### analyze

General image analysis.

```bash
npx zai-cli vision analyze ./image.png "Describe what you see"
npx zai-cli vision analyze https://example.com/image.png "What's in this?"
```

### ui-to-code

Convert UI screenshots to code, prompts, or specifications.

```bash
# Generate code (default)
npx zai-cli vision ui-to-code ./design.png

# Generate recreation prompt
npx zai-cli vision ui-to-code ./design.png --output prompt

# Generate design spec
npx zai-cli vision ui-to-code ./design.png --output spec

# Generate description
npx zai-cli vision ui-to-code ./design.png --output description
```

Options:
- `--output <type>`: `code` (default), `prompt`, `spec`, `description`

### extract-text

OCR for extracting text from screenshots.

```bash
# Basic extraction
npx zai-cli vision extract-text ./screenshot.png

# With language hint for better code formatting
npx zai-cli vision extract-text ./code.png --language python
npx zai-cli vision extract-text ./terminal.png --language bash
```

Options:
- `--language <lang>`: Hint for code formatting (python, javascript, typescript, bash, etc.)

### diagnose-error

Analyze error screenshots and provide solutions.

```bash
# Basic error diagnosis
npx zai-cli vision diagnose-error ./error.png

# With context for better diagnosis
npx zai-cli vision diagnose-error ./error.png --context "during npm install"
npx zai-cli vision diagnose-error ./crash.png --context "after updating dependencies"
```

Options:
- `--context <ctx>`: When/where the error occurred

### diagram

Interpret technical diagrams.

```bash
# General diagram analysis
npx zai-cli vision diagram ./diagram.png

# With diagram type hint
npx zai-cli vision diagram ./arch.png --type architecture
npx zai-cli vision diagram ./classes.png --type uml
npx zai-cli vision diagram ./flow.png --type flowchart
npx zai-cli vision diagram ./db.png --type er
npx zai-cli vision diagram ./seq.png --type sequence
```

Options:
- `--type <type>`: `architecture`, `uml`, `er`, `flowchart`, `sequence`

### chart

Analyze data visualizations.

```bash
# General chart analysis
npx zai-cli vision chart ./chart.png

# With analysis focus
npx zai-cli vision chart ./graph.png --focus trends
npx zai-cli vision chart ./dashboard.png --focus anomalies
npx zai-cli vision chart ./comparison.png --focus comparison
```

Options:
- `--focus <area>`: `trends`, `anomalies`, `comparison`

### diff

Compare two UI screenshots.

```bash
npx zai-cli vision diff ./expected.png ./actual.png
npx zai-cli vision diff ./design.png ./implementation.png "Check spacing and colors"
```

Arguments:
1. Expected/reference image
2. Actual/implementation image
3. Optional comparison prompt

### video

Analyze video content.

```bash
npx zai-cli vision video ./demo.mp4 "Summarize the key steps"
npx zai-cli vision video ./tutorial.mov "What is being demonstrated?"
```

## Output Format

Default output is **data-only** (analysis text). Use `--output-format json` to wrap.
