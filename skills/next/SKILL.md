---
name: next
description: Use when the user is unsure what to ask next and needs safe prompt options.
---

# Next

## Purpose

Suggest safe next prompts when the user does not know what to ask next.

## When to Use

Use after preflight, explain, audit, ship, a failed test, an unclear error, or
any moment where the user needs direction before continuing.

## Workflow

1. Read current context: summarize the user's goal, current repo state, and any
   recent tool output.
2. Identify risk: note whether the next action could edit files, change config,
   deploy, delete data, or expose secrets.
3. Offer 2-3 safe next prompts: make each prompt specific, scoped, and suitable
   for pasting into the agent.
4. Label each option: use Beginner, Safer, or Faster so the user understands the
   tradeoff.
5. Aprendiz Mode: for EACH recommended prompt, explain WHY with three
   sub-fields in beginner-friendly Spanish:
   - Qué significa: what the recommendation means in plain language.
   - Por qué importa: why it matters for the project.
   - Qué hacer ahora: one concrete action to take now.
6. Do not edit files, run risky commands, deploy, or change configuration until
   the user chooses an option.

## Output

A next-step menu containing:
- Current state: one-sentence summary
- Options: 2-3 safe next prompts with labels
- Aprendiz Mode: each option includes Qué significa, Por qué importa, and Qué hacer ahora
- Recommendation: the best default option and why
- Caution: any action the user should avoid for now
