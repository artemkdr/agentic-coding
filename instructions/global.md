# Engineering Principles

## Your context
- The codebase is your main context - keep it clean, simple and compact.
- Ask questions in any doubt about the global context.
- Use semantic and graph code search where it's possible to understand the code.
- Be aware of code duplicates as much as possible without creating tight coupling.

## Security
- **Zero Trust for Inputs:** Validate, sanitize, and strongly type all data at system boundaries. Never trust user or external API input.
- **Default Deny:** Start with zero access. Unless an action, route, or network request is explicitly authorized, it must be blocked.
- **Principle of Least Privilege:** When granting access, scope permissions (IAM, database roles, file access) to the bare minimum required for the task.
- **Fail Closed:** If a system errors out or a security check fails, it must default to a secure, restricted state—never fail open.
- **Secrets & Credentials:** Never hardcode secrets, API keys, or environment-specific credentials in the codebase.
- **Explain Trade-offs:** Always explain the security risks and consequences of different architectural or coding options.
- **Defend the Basics:** Actively guard against common vulnerabilities (e.g., SQLi, XSS, SSRF). Use parameterized queries and established escaping mechanisms.

## Root Cause First
- Identify and state the root cause before writing any fix.
- Do not patch symptoms. If the cause is unclear, say so and investigate before proceeding.
- Prefer a correct solution over a fast one that hides the problem.

## Scope Discipline
- Change only what the task requires. Do not refactor, rename, or restructure unrelated code.
- If you spot something worth improving outside of scope, note it as a follow-up item — do not act on it.

## Iterative Validation
- Work in small, verifiable steps. After each meaningful change, validate: run tests, check types, lint.
- If validation fails, fix the root cause of the failure — not just the failing check.

## Change Summary
- After completing a task, briefly state: what changed, why, and how it was validated.
- Call out risks, assumptions, or recommended follow-up items.
