---
name: audit
description: Use when reviewing changes for bugs, regressions, and missing tests.
---

# Audit

## Purpose

Review changes for bugs, regressions, and missing tests.

## When to Use

Use when reviewing changes for bugs, regressions, and missing tests.

## Workflow

1. Review the diff against the original goal. Verify the changes address what was intended.
2. Detect issues:
   - Bugs: logic errors, off-by-one mistakes, null dereferences.
   - Missing edge cases: empty inputs, error paths, boundary conditions.
   - Potential regressions: changes that could break unrelated behavior.
   - Unintended modifications: files changed outside the intended scope.
3. Verify test coverage: confirm tests exist and exercise the changed behavior.
4. Look for security issues: injection risks, unsafe defaults, exposed secrets.

## Output

If approved: state approval with concrete evidence (files reviewed, tests observed, verification steps taken).

If rejected: list each issue with:
- File reference: the specific file and line context
- Severity: Critical / High / Medium / Low
- Suggested fix: a concrete correction or next step
