# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Repo Is

A private registry of [Agent Skills](https://github.com/vercel-labs/skills.sh) and shared development context for SmartWorkx projects. Each top-level directory (e.g. `create-adr/`, `create-doc/`, `create-issue/`) contains a `SKILL.md` file defining a single skill.

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
- GitHub issues follow imperative titles under 70 chars
