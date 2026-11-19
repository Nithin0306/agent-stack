# Agent Stack

A personal collection of reusable AI-agent skills for software engineering workflows.

## Skills

| Skill | Trigger | What it does |
|---|---|---|
| `codebase-design` | `/codebase-design` · "design this codebase" | Helps reason about architecture, boundaries, dependencies, and maintainable design choices. |
| `commit-and-pr` | `/commit-and-pr` · "commit and create a PR" | Checks changes, prepares a meaningful commit, and assists with pull-request creation. |
| `explore-codebase` | `/explore-codebase` · "explore this codebase" | Maps the project structure, identifies important files, and explains the architecture before changes. |
| `security-review` | `/security-review` · "security review" | Examines code and design for security risks, unsafe input handling, authentication issues, secrets, and vulnerabilities. |
| `test-first` | `/test-first` · "write tests first" | Defines expected behavior with tests before implementation. |
| `code-review` | `/code-review` · "review this code" | Reviews changes for correctness, regressions, maintainability, security, and missing tests. |
| `debug-protocol` | `/debug-protocol` · "debug this" | Reproduces, isolates, investigates, and verifies the root cause of a bug systematically. |
| `prototype` | `/prototype` · "prototype this idea" | Quickly builds a prototype to explore an idea or validate an approach. |
| `tdd` | `/tdd` · "use TDD" | Guides development through failing tests, a minimal implementation, and refactoring. |

> Use the slash trigger to invoke a skill explicitly. Natural-language triggers are descriptive examples; model-invoked skills may also activate automatically when their task matches.

## Global Instructions

`AGENTS.md` contains the persistent engineering rules used across projects: understand the codebase first, test before implementation where appropriate, debug from evidence, make minimal changes, review significant work, validate changes, and be honest about checks that were not run.

## Installation

Copy the skills you want into your agent's skills directory. For Gemini/Antigravity:

```bash
# Shared skills (CLI + GUI)
cp -r skills/<skill-name> ~/.gemini/skills/

# Global CLI-only skills
cp -r skills/<skill-name> ~/.gemini/antigravity-cli/skills/
```

Keep `AGENTS.md` in the repository root for project-level instructions, or copy the global instruction file to the appropriate global configuration location if you want it applied across projects.
