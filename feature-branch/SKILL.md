---
name: feature-branch
description: >-
  Create a feature branch in a git worktree from a GitHub issue.
  TRIGGER when: user asks to create a branch, start working on an issue, or begin a feature.
  Examples: "create a branch for issue 42", "start working on the export feature", "branch off for issue 15".
  DO NOT TRIGGER when: user just wants to switch branches, view issues, or implement code.
allowed-tools: Bash, Read, Glob, Grep, AskUserQuestion
---

Create a feature branch in a new git worktree, as a sibling directory of the current project.

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

4. Create a worktree as a sibling of the current project directory:
   - `git worktree add ../<branch-name> -b <branch-name> origin/main`
   - This creates `../<branch-name>/` alongside the current project directory

5. Confirm to the user:
   - Show the branch name
   - Show the worktree path
   - Summarize what the issue is about
   - Remind them to `cd ../<branch-name>` to start working
