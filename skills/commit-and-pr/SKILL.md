---
name: commit-and-pr
description: Writes commit messages, branch names, and pull request descriptions, and prepares changes for commit. Use whenever the user asks to commit, write a commit message, open or describe a PR, summarize changes, or "prepare this for review".
---

# Commit and PR

## Before committing
Run `git status` and `git diff --staged` (or `git diff`). Verify tests/lint pass. Make sure no secrets, debug prints, or unrelated files are included. Never commit or push without being asked; never force-push or rewrite shared history without explicit approval.

## Commit message
Conventional Commits: `type(scope): imperative summary` (feat, fix, refactor, test, docs, chore, perf, build, ci). Summary under 72 chars. Body explains **why**, not just what. One logical change per commit. Use the repo's existing convention if it differs (check `git log`).

## PR description
- **What & why** (2-4 sentences)
- **Changes** (short list)
- **How tested** (exact commands and results)
- **Risks / rollout / follow-ups**
Link the issue. Only claim what the diff and test runs support.
