---
name: improve
description: Use after a session reveals a reusable self-improvement pattern.
---

# Improve

## Purpose

Capture reusable self-improvement patterns that shape future agent work
without overwriting existing learning.

## When to Use

Use after a session reveals a reusable self-improvement pattern.

## Workflow

1. Identify a pattern: a repeated mistake, useful tactic, repo convention, or
   verification habit likely to matter again.
2. Read `.agents/memory/patterns.json` before writing. Preserve every existing
   pattern unless the update is an intentional merge.
3. Add a concise pattern with: name, trigger (when to use), action (what to do),
   evidence (why it matters), confidence (0-1), and sources (files or sessions).
4. Keep entries repository-specific and durable. Do not store secrets, transient
   task status, commit hashes, or one-off TODOs.
5. Reuse relevant patterns during preflight, implementation, audit, and ship.

## Pattern Store Contract

- Schema version is `1`. Top-level fields: `version` (number) and `patterns` (array).
- Each pattern must have: `name`, `trigger`, `action`, `evidence`,
  `confidence` (number 0-1), `sources` (array of strings), `createdAt` (ISO string).
- Deduplication is by `id`. If `id` is missing, it is generated from `name` in kebab-case.
- Merging keeps the higher confidence, combines and deduplicates `sources`, and keeps
  the older `createdAt`.
- Invalid stores fail loudly: read and update operations throw rather than silently
  recovering or overwriting user data.

## Output

Updated `.agents/memory/patterns.json` with the new pattern merged in.
