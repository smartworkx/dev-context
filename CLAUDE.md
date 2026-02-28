# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Repo Is

A private registry of [Agent Skills](https://github.com/vercel-labs/skills.sh) and shared development context for SmartWorkx projects. Each top-level directory (e.g. `create-adr/`, `create-doc/`, `create-issue/`) contains a `SKILL.md` file defining a single skill.

### Development Workflow

The skills support this workflow:

```
create-issue → feature-branch → create-adr → create-doc → create-spec → implement
```

| Skill | Purpose |
|-------|---------|
| `create-issue` | Define work as a GitHub issue |
| `feature-branch` | Create a branch from an issue |
| `create-adr` | Record architectural decisions |
| `create-doc` | Write documentation and diagrams |
| `create-spec` | Write BDD scenarios in Gherkin |
| `implement` | Implement the feature and create a PR |
| `commit` | Stage and commit with conventional messages |

**Issue numbers are transient workflow artifacts.** Branches and commits may reference them, but standing documentation (specs, ADRs, docs) must NOT embed issue numbers. The issue should reference the docs, not the other way around.

Skills are installed into consumer projects via:
```bash
npx skills add smartworkx/dev-context
```
This copies skills into `.claude/skills/` in the target project. The repo is private — requires GitHub auth (`GITHUB_TOKEN` or `gh auth login`).

## Adding a New Skill

Create a new directory with a `SKILL.md` file. The file uses YAML frontmatter:
```yaml
---
name: skill-name
description: Short description
allowed-tools: Bash, Read, Write, ...
---
```
Followed by the skill's instructions in Markdown.

## Conventions

- Docs use Markdown; diagrams use Mermaid fenced code blocks (GitHub renders natively)
- Architecture diagrams follow C4 notation via Mermaid flowcharts
- ADRs use the Nygard format, stored in `doc/adr/YYYY-MM-DD-kebab-case-title.md`
- BDD specs use Gherkin, stored in `doc/spec/<kebab-case-feature-name>.feature`
- GitHub issues follow imperative titles under 70 chars
