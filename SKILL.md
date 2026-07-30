---
name: repository-review
description: Review a repository for actionable risks and recommend minimal, safe changes.
---

# Repository Review

## When to use

Use this skill when asked to inspect a repository, assess implementation or
maintenance risks, or recommend a small corrective change. Keep the review
general and scoped to the request.

## Procedure

1. **Inspect** - Identify the repository scope and read the relevant source,
   configuration, documentation, and tests. Check the existing conventions and
   available validation commands. Do not read, copy, or expose secret values.
2. **Identify risks** - Look for correctness, security, reliability,
   maintainability, documentation, and test-coverage issues. Separate observed
   evidence from assumptions, and prioritize concrete risks.
3. **Propose a minimal change** - Recommend the smallest clear, reversible
   change that addresses the risk. Avoid unrelated edits, broad refactors, and
   product-specific assumptions. Do not apply changes unless the request
   explicitly authorizes implementation.
4. **Validate** - When changes are authorized, inspect the diff and run the
   narrowest relevant tests, linters, or build checks. Also run `git diff
   --check` when possible. Never claim a check passed if it was not run.
5. **Report** - Give prioritized findings with file paths and line references
   when available, followed by recommendations and validation results. Say
   explicitly when no risks were found or validation was skipped.

## Response format

```text
Summary: <one sentence>

Findings:
- [high|medium|low] <path:line> - <risk and impact>

Recommendation: <minimal change, or "None">
Validation: <commands and results, or "Not run">
```

Do not include secrets, credentials, or unnecessary private data. Do not
commit, push, delete files, or change unrelated configuration as part of a
review unless the request explicitly requires it.
