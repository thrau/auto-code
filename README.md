Automatically raise PRs from GitHub issues
==========================================

This repo contains GitHub Actions for agent-based development using Claude Code, that can be used by other repositories.

## Actions

**Write spec** (`needs spec` label): Takes a GitHub issue containing a brief description and a Linear ticket link, fetches the Linear issue for full context, explores the codebase, and rewrites the issue body as a clear technical specification. Sets the label to `needs human review` when done.

**Implement issue** (`ready for agent` label): Implements the feature described in the issue, following existing code patterns and writing tests. Raises a pull request that closes the issue.

**Handle PR review** (changes requested): Reads all review comments on a PR, implements the requested changes, and pushes updates to the PR branch.

## Setup

Copy the workflow files from `.github/workflows/` into your repository and add these secrets:

| Secret | Required for | Description |
|--------|-------------|-------------|
| `ANTHROPIC_API_KEY` | all actions | Claude API key from [console.anthropic.com](https://console.anthropic.com) |
| `LINEAR_API_KEY` | write-spec | Linear API key from your Linear workspace settings |

Create these labels in your repository: `needs spec`, `needs human review`, `ready for agent`.

Optionally add a `CLAUDE.md` file at the repo root with project-specific coding standards and conventions.

## Resources
* https://code.claude.com/docs/en/github-actions
* https://github.com/jerhadf/linear-mcp-server
