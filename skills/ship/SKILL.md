---
name: ship
description: Use before handoff to verify behavior and summarize concrete evidence.
---

# Ship

## Purpose

Verify before handoff.

## When to Use

Use before handoff to verify behavior and summarize concrete evidence.

## Workflow

1. Execute tests: run the test command if one exists and report the results (pass/fail count, any failures).
2. Review the final diff: check for unintended changes outside the intended scope.
3. Check for blockers: test failures, lint errors, uncommitted changes, or unresolved merge conflicts.
4. Confirm the goal: verify the changes achieve the stated objective.

## Output

If clear to ship, an evidence summary containing:
- What changed: files modified and why
- test results: pass/fail status with counts
- goal confirmation: statement that the objective was met

If blocked, a blocker list containing:
- Each blocker with severity (Critical / High / Medium / Low)
- Next step: the one action required to unblock
