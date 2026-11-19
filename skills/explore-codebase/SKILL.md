---
name: explore-codebase
description: Maps an unfamiliar repo before any edits. Use at the start of any task in a codebase you have not yet read this session, when asked to "understand", "explore", "onboard to" or "find where X happens", or before any change spanning more than one file. Use it even if the task looks small; editing blind is the most common cause of wrong changes.
---

# Explore Codebase

Goal: build enough understanding to make a correct, minimal change. Do not edit anything in this skill.

## Steps
1. Read the root: README, AGENTS.md/GEMINI.md, Makefile/justfile/package.json scripts, go.mod / pyproject.toml / package.json. Identify language versions, build, test, lint commands.
2. List top-level directories; identify entrypoints (`main.go`, `cmd/*`, `__main__.py`, `src/index.*`, server/app factory).
3. Trace the exact code path for the task: start at the entrypoint or the failing symbol and follow calls. Use search (grep/ripgrep) for symbol definitions AND callers before concluding where logic lives.
4. Read the existing tests for the area. They show intended behavior and the project's test style.
5. Check recent history for the files involved (`git log -n 10 -- <path>`) to learn why code looks the way it does.

## Output
Report in under 15 lines: entrypoint, files involved, how to run tests, conventions to match, risks/unknowns. Mark anything unverified as "unverified". Never describe code you did not open.
