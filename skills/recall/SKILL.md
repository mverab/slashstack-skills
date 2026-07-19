---
name: recall
description: Use before working in a subsystem with saved reference material.
---

# Recall

## Purpose

Load saved subsystem knowledge.

## When to Use

Use before working in a subsystem with saved reference material.

## Workflow

1. Load references: read all files in `.agents/references/`.
2. Validate against the current codebase:
   - Check that every referenced file still exists.
   - Flag stale references: files that have moved, been renamed, or deleted.
   - Note any drift between the saved description and the current implementation.
3. Summarize: subsystem purpose, entry points, conventions, and risks.

## Output

A concise summary containing:
- Subsystem purpose: what it does and why
- Entry points: key files, functions, and APIs
- Conventions: patterns and rules that govern the subsystem
- Risks: known gotchas, edge cases, or fragile areas
- Stale references flagged: any saved references that no longer match the codebase
