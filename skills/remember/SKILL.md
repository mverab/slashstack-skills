---
name: remember
description: Use after learning durable subsystem facts that future sessions need.
---

# Remember

## Purpose

Save durable subsystem knowledge.

## When to Use

Use after learning durable subsystem facts that future sessions need.

## Workflow

1. Identify durable facts: architecture, conventions, commands, and risks.
2. Reject explicitly — do not save any of the following:
   - Transient task state: in-progress notes, temporary flags, current session context.
   - Commit hashes: specific SHAs that will become stale.
   - TODOs: one-off reminders that belong in issues, not memory.
   - Secrets: API keys, tokens, passwords, credentials.
3. Read existing `.agents/memory/project.md` and merge new facts, preserving all prior content.
4. Verify the updated file is clean: no secrets, no TODOs, no commit hashes, no transient state.

## Output

Updated `.agents/memory/project.md` with merged durable facts.
