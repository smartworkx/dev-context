---
name: feature-branch
description: Create a feature branch from a GitHub issue
allowed-tools: Bash, Read, Glob, Grep, AskUserQuestion
---

Create a feature branch from a GitHub issue.

## Steps

1. Determine the issue — the argument can be:
   - A **GitHub issue number or URL** → fetch with `gh issue view`
   - A **description** → search with `gh issue list --search "<description>"` to find the matching issue
   - Nothing → ask the user what they're working on, then search

2. Generate a branch name:
   - Format: `<issue-number>-<kebab-case-summary>` (e.g. `42-add-user-export`)
   - Keep it under 50 characters where possible

3. Ensure `main` is up to date:
   - `git fetch origin main`

4. Create and check out the branch:
   - `git checkout -b <branch-name> origin/main`

5. Confirm to the user:
   - Show the branch name
   - Summarize what the issue is about
