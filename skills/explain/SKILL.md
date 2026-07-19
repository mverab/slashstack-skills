---
name: explain
description: Use when technical agent output needs beginner-friendly translation without losing exact details.
---

# Explain

## Purpose

Translate technical agent output into beginner-friendly language while preserving
the exact file paths, commands, errors, and decisions the user needs.

## When to Use

Use when output from an agent, terminal, test run, error message, pull request,
or implementation plan is too technical for the user to act on confidently.

## Workflow

1. Identify the source: name the command, file, diff, error, or agent message
   being explained.
2. Preserve exact details: keep file paths, commands, package names, versions,
   error text, and config keys unchanged.
3. Translate jargon: explain unfamiliar terms in beginner language.
4. Separate facts from interpretation: clearly label what the output proves,
   what it suggests, and what remains unknown.
5. Explain impact: state whether the issue blocks progress, is safe to ignore,
   or needs a specific action.
6. Give the next safe action: provide one concrete prompt or command the user
   can run next.
7. Aprendiz Mode: for the MOST confusing concept in the output, include three
   sub-fields in beginner-friendly Spanish:
   - Qué significa: what the concept means in plain language.
   - Por qué importa: why it matters for the project.
   - Qué hacer ahora: one concrete action to take now.

## Output

A beginner explanation containing:
- Plain version: the short explanation in non-technical language
- Exact details: file paths, commands, or error lines that must not be changed
- Why it matters: the practical impact
- Aprendiz Mode: the most confusing concept with Qué significa, Por qué importa, and Qué hacer ahora
- Next safe step: one prompt or command to run next
