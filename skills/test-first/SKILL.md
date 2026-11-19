---
name: test-first
description: Test-driven workflow for adding features or fixing bugs with tests in Go, Python, or JavaScript/TypeScript. Use whenever writing or changing logic, adding a feature, fixing a bug, or when the user mentions tests, coverage, TDD, pytest, `go test`, vitest, or jest. Use it when changed code has no test coverage.
---

# Test First

1. Find how the project tests (existing test files, CI config). Match its framework and style; do not introduce a new one.
2. Write a failing test that captures the required behavior or the bug. Run it and confirm it fails **for the right reason**.
3. Write the minimum code to pass. Run it.
4. Refactor with tests green. Run the full relevant suite, not just the new test.
5. Report the commands you ran and their results.

## Rules
- Test behavior and public contracts, not implementation details.
- Cover: happy path, empty/zero/nil input, boundaries, error paths, and at least one realistic failure case.
- No sleeps for synchronization; use channels, events, fake clocks, or polling with timeout.
- Never weaken or delete an existing test to make it pass. If a test is wrong, explain why before changing it.
- Mock only at system boundaries (network, clock, filesystem, DB). Prefer real in-memory fakes over deep mock chains.

## Go
Table-driven tests with `t.Run` subtests; `t.Helper()` in helpers; `t.Parallel()` only when safe; run `go test ./... -race`. Use `t.TempDir()` and `httptest` for IO and HTTP.

## Python
pytest with fixtures and `parametrize`; `tmp_path`, `monkeypatch`; for async use the project's pytest-asyncio/anyio setup. Run `pytest -x -q` then the full suite.

## JavaScript/TypeScript
Use the project's runner (vitest/jest/node:test). `await` every async assertion; reset mocks between tests; for UI use Testing Library queries by role/label, not CSS selectors.
