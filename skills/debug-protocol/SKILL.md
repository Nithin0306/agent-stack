---
name: debug-protocol
description: Disciplined debugging workflow: reproduce, isolate, hypothesize, verify, fix. Use whenever the user reports a bug, failing test, panic, stack trace, flaky behavior, wrong output, race condition, or says "it doesn't work", "why does this fail", or "debug this". Use it before proposing any fix.
---

# Debug Protocol

Never propose a fix before you can reproduce the failure.

1. **Reproduce.** Get the exact failing command/input. Run it and capture the real error. If it cannot be reproduced, say so and ask for the missing detail instead of guessing.
2. **Minimize.** Shrink to the smallest failing case (one test, one input, one request).
3. **Hypothesize.** Write 2-3 candidate causes ranked by likelihood, each with the observation that would confirm or kill it.
4. **Verify.** Test hypotheses with evidence: add logging, print intermediate values, use a debugger, `git bisect` for regressions. Change one thing at a time.
5. **Fix the root cause**, not the symptom. If you are adding a nil check or try/except to silence an error, stop and ask why the bad value exists.
6. **Lock it in.** Add a regression test that fails before the fix and passes after. Run the full relevant suite.
7. **Report:** root cause, evidence, fix, test added. Separate what you verified from what you inferred.

## Language notes
- Go: read the whole panic trace; use `go test -race` for anything concurrent; check for ignored `error` returns and loop-variable capture in goroutines.
- Python: read the traceback bottom-up; check mutable default args, late-binding closures, async/await misuse, and type mismatches at boundaries.
- JS/TS: check `undefined` vs `null`, async ordering, stale closures, missing `await`, and `this` binding; verify actual runtime types, not annotated ones.
