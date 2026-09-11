---
name: factory
description: Use to turn an intention into a bounded, verifiable factory order with a machine-checked receipt.
---

# Factory

## Purpose

Turn an intention into a bounded, verifiable factory order. The order freezes
what "correct" means before the work starts; the receipt proves what actually
ran, against which repository state, with which result. A green test alone is
never "done" — the acceptance criteria bound to the order decide.

## When to Use

Use when a change should be delivered as a verifiable unit: an export filter,
a bug fix with a regression test, a refactor with an observable contract.
Do not use it as a task queue or an autonomous scheduler — this vertical
delivers one bounded, verified change at a time.

## Workflow

1. Initialize once per repo: run `npx slashstack factory init`. It detects the
   test command and creates `.agents/factory/`. It never edits application code.
2. Define the goal first: if the work is multi-step, register it in
   `.agents/memory/goal-registry.json` with the execute workflow. The factory
   order is the delivery contract for that goal, not a replacement for it.
3. Create the order: `npx slashstack factory order create --title "<what>" --acceptance "<observable criterion>"`.
   Add `--bind-test` only when the frozen test command IS the acceptance check.
   Without it, verification stays blocked with `acceptance_not_evaluated` —
   that is the system refusing to call untested work "done".
4. Implement the change inside the order's intent. Keep the diff scoped.
5. Verify: `npx slashstack factory verify <order-id>`. It runs the frozen
   verifier and writes a receipt under `.agents/factory/receipts/` with the
   exact commit, duration, exit code, and redacted output.
6. Or let the configured agent implement it: set `agent.command` in
   `.agents/factory/config.json` (any agent CLI; it receives the order via
   FACTORY_ORDER_* env vars), then `npx slashstack factory run <order-id>`.
   The agent works in an isolated worktree under `.agents/factory/runs/` and
   the result is verified automatically. Your main checkout is never touched.
7. Read the receipt honestly: `failed` means repair; `blocked` means the
   contract itself changed (verifier, worktree mid-check, missing test command)
   or the run could not start (no agent command, another run active) —
   that needs a human decision, not a retry loop.
8. Ship through the normal `ship` workflow. Merge and deploy stay human
   decisions.

## Output

A receipt JSON with `status` (`passed` / `failed` / `blocked`), the
pre-check repository identity, the frozen command, and redacted evidence.
A `passed` receipt means: the checks named by the order ran green on the
recorded repository state. It does not prove the product is good — only that
the layer a machine can check is intact.
