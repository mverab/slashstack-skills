---
name: execute
description: Use before beginning any multi-step task with multiple files, tests, or verification steps.
---

# Execute

## Purpose

Turn multi-step tasks into goals with explicit scope, acceptance criteria,
verification commands, and completion expectations.

## When to Use

Use before beginning any multi-step task that involves multiple files, tests,
or verification steps.

## Workflow

1. Read the registry: open `.agents/memory/goal-registry.json` to see active and
   completed goals.
2. Define scope: list the file path globs this goal may read or write.
3. Set acceptance criteria: describe what "done" looks like in a single sentence.
4. List verification commands: the test, build, or lint commands that must pass.
5. Declare commit and push expectations: whether the goal requires a commit
   and/or a push upon completion.
6. Check for scope overlaps: if any active goal's scope intersects with yours,
   report the overlap, name the conflicting goal id, and refuse to start until
   the conflict is resolved.
7. Do the work: edit only files within the declared scope.
8. Run verification: execute every command in the verification list and record
   the pass/fail result.
9. Mark complete with evidence: update the goal `status` to `completed`, set
   `updatedAt`, and record a brief evidence summary.
10. Archive stale goals: set `archived: true` on completed goals older than 30 days.

## Output

If complete: updated goal entry with `status: completed`, `updatedAt`, and
an evidence summary.

If abandoned: updated goal entry with `status: abandoned`, `updatedAt`, and
a reason.
