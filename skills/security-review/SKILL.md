---
name: security-review
description: Security audit of code, configs, and dependencies. Use whenever the user mentions security, vulnerabilities, auth, secrets, injection, sandboxing, user input, file uploads, API keys, or asks to "harden" or "audit" something, and before shipping any code that handles untrusted input, credentials, or executes user-supplied code.
---

# Security Review

Review defensively. Report issues and fixes; do not produce working exploits.

## Check
- **Input:** SQL/command/template injection, path traversal, SSRF, XSS, unsafe deserialization, regex DoS. Parameterize queries; never build shell commands from input; avoid `shell=True`, `exec`, `eval`.
- **Authn/authz:** every endpoint authenticated and authorized per resource (IDOR); secure session/token handling; constant-time compares for secrets.
- **Secrets:** none in code, history, logs, error messages, or client bundles. Load from env/secret manager. If found, say they must be rotated.
- **Crypto:** use vetted libraries; no custom crypto, MD5/SHA1 for passwords, or hardcoded keys; use bcrypt/argon2 for passwords.
- **Dependencies:** run the ecosystem scanner (`govulncheck ./...`, `pip-audit`, `npm audit`) and report results.
- **Config:** CORS, debug modes, default credentials, overly broad permissions, containers running as root, open ports.
- **Resource abuse:** missing rate limits, size limits, and timeouts.

## Output
List findings by severity (Critical/High/Medium/Low) with location, impact, and fix. State what you checked and what you did not. Do not claim "secure"; claim only what was reviewed.
