# prompt-provenance-readme-generator-action

[![CI](https://github.com/mizcausevic-dev/prompt-provenance-readme-generator-action/actions/workflows/ci.yml/badge.svg)](https://github.com/mizcausevic-dev/prompt-provenance-readme-generator-action/actions/workflows/ci.yml)
[![License: AGPL-3.0-or-later](https://img.shields.io/badge/License-AGPL--3.0--or--later-blue.svg)](LICENSE)

GitHub Action that **renders a human-readable Markdown README from a prompt-provenance JSON document**. Wraps [`prompt-provenance-readme-generator`](https://github.com/mizcausevic-dev/prompt-provenance-readme-generator). Posts as PR comment AND/OR writes to a target file path.

**Third in the per-protocol readme-generator Action quintet**.

Part of the [Kinetic Gain Suite](https://suite.kineticgain.com/).

---

## Usage

```yaml
- uses: mizcausevic-dev/prompt-provenance-readme-generator-action@v0.1-shipped
  with:
    doc-path: provenance/my-prompt.json
    output-path: docs/my-prompt.md   # optional auto-sync
```

## Inputs

| input            | required | default     | description |
|---|---|---|---|
| `doc-path`       | ✓        | —           | Path to the prompt-provenance JSON document. |
| `output-path`    |          | —           | Optional file destination for the rendered Markdown. |
| `comment-on-pr`  |          | `auto`      | `auto` posts only on `pull_request` events. |
| `hide-badges`    |          | `false`     | Suppress the trailing badges line. |
| `anchor-prefix`  |          | `section-`  | Anchor prefix for section headings. |
| `github-token`   |          | `${{ github.token }}` | Token for posting the PR comment. |

## Outputs

| output            | description |
|---|---|
| `markdown-length` | Length (in characters) of the rendered Markdown. |
| `output-written`  | `true` iff `output-path` was specified and successfully written. |

## Composes with

- [`prompt-provenance-diff-action`](https://github.com/mizcausevic-dev/prompt-provenance-diff-action) — diff catches breaking changes, this Action keeps the rendered docs in lockstep.
- Siblings: [`agent-card-readme-generator-action`](https://github.com/mizcausevic-dev/agent-card-readme-generator-action) · [`mcp-tool-card-readme-generator-action`](https://github.com/mizcausevic-dev/mcp-tool-card-readme-generator-action).

## License

[AGPL-3.0-or-later](LICENSE)
