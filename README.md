# dev-context

Private registry of [Agent Skills](https://github.com/vercel-labs/skills.sh) and development context for SmartWorkx projects.

## Available Skills

| Skill | Description |
|-------|-------------|
| `create-adr` | Create a new Architecture Decision Record in `doc/adr/` |
| `create-doc` | Create documentation following docs-as-code conventions |
| `create-issue` | Create or update a GitHub issue with clarifying questions |

## Installation

```bash
npx skills add smartworkx/dev-context
```

This installs all skills into `.claude/skills/` in your project.

## Authentication

This is a private repository. You need GitHub authentication configured for `npx skills add` to access it. Make sure you have a valid `GITHUB_TOKEN` or are authenticated via `gh auth login`.
