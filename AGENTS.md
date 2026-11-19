# Global Agent Instructions

These instructions define my default engineering workflow. Apply them across projects unless the repository's own instructions or the task explicitly require a different approach.

## 1. Understand Before Changing
- Explore the codebase before proposing or making changes.
- Read relevant files, project instructions, and existing tests.
- Understand the architecture, conventions, and current behavior.
- Do not assume a file, function, API, or dependency exists; verify it.
- For non-trivial work, summarize the relevant architecture and implementation plan before proceeding.

## 2. Plan Proportionally
- Break complex work into clear, manageable steps.
- Identify affected components, dependencies, edge cases, and risks.
- Prefer the simplest design that satisfies the requirements.
- Avoid unnecessary abstractions, dependencies, or scope expansion.

## 3. Test-First Development
- For bug fixes, reproduce the bug or write a test that captures it before fixing it when practical.
- For new functionality, define expected behavior through tests before implementation when practical.
- Make the smallest change that causes the relevant tests to pass.
- Refactor only after behavior is validated.
- Do not modify or weaken tests merely to make an implementation pass.

## 4. Debugging
- Reproduce the issue and gather evidence before changing code.
- Trace the problem to its root cause rather than treating symptoms.
- Check logs, stack traces, inputs, state, and relevant execution paths.
- Form and test hypotheses systematically.
- Avoid speculative fixes and unrelated changes.
- Verify that the fix addresses the original failure and does not introduce regressions.

## 5. Implementation Quality
- Keep changes focused and minimal.
- Preserve existing behavior unless a change is explicitly requested.
- Follow the language, framework, and repository conventions.
- Use clear names and maintainable structure.
- Handle errors and edge cases explicitly where appropriate.
- Consider performance, security, concurrency, and failure modes when relevant.
- Avoid hard-coded secrets, unsafe input handling, and unnecessary sensitive-data exposure.

## 6. Code Review
For significant changes, review the diff as if reviewing a pull request:
- Correctness and unintended behavior
- Edge cases and error handling
- Security and privacy implications
- Performance and resource usage
- Concurrency and distributed-system risks
- Maintainability and consistency
- Test coverage

Fix identified issues before declaring the work complete.

## 7. Validation
- Run relevant tests after making changes.
- Run linting, formatting, type checking, and builds when available and relevant.
- Prefer targeted checks first, followed by broader checks when appropriate.
- Inspect the final diff for accidental changes.
- If a check cannot be run, state exactly what was not run and why.
- Never claim that tests, builds, or checks passed unless they were actually executed.

## 8. Git and Pull Requests
- Inspect the working tree before committing.
- Do not overwrite, discard, or revert the user's unrelated changes.
- Review staged changes before creating a commit.
- Use concise, descriptive commit messages.
- Include a clear PR summary, relevant testing, and known limitations.
- Do not commit secrets, generated files, or unrelated artifacts.

## 9. Communication
- Be concise, direct, and technically precise.
- Challenge incorrect assumptions and explain the reasoning.
- Distinguish verified facts from hypotheses.
- Ask questions only when missing information materially blocks progress.
- Explain important trade-offs rather than presenting a choice as unquestionably correct.
- Report what changed, what was validated, and any remaining risks.

## 10. Skill Usage
- Use relevant skills when they provide a specialized workflow.
- Explicitly invoke user-requested skills.
- Prefer codebase exploration before implementation, test-first workflows for changes, systematic debugging for defects, and code review before completing significant work.
- Avoid invoking multiple overlapping skills unless their distinct contributions are useful.
