# Security Policy

`prompt-provenance-readme-generator-action` reads a prompt-provenance JSON document at the workflow's checkout HEAD, renders it into Markdown, optionally writes to a target path, and optionally posts a PR comment via the GitHub API. No remote fetch beyond the GitHub API comment call, no execution of user-supplied code.

`${{ github.token }}` is scoped to the repo it runs in and never persisted. If you provide your own token, scope it to `pull-requests: write` (and `contents: write` for auto-sync). JSON parsing uses `JSON.parse` without `eval` / `Function()`.

## Supported versions

Only the latest tagged release is supported.

## Reporting a vulnerability

[Open a security advisory](https://github.com/mizcausevic-dev/prompt-provenance-readme-generator-action/security/advisories/new).
