---
name: preflight
description: Use before editing code to inspect project state and constraints.
---

# Preflight

## Purpose

Inspect repo state before coding, in beginner-friendly language.

## When to Use

Use before editing code to inspect project state and constraints.

## Workflow

1. Respond in the user's language. If the user writes Spanish, answer in Spanish.
2. Explain what just happened: state that SlashStack added local agent guidance files and did not change app code.
3. Inspect git status: current branch, uncommitted changes, recent commits, and dirty working tree.
4. Inspect installed SlashStack skills: list the skills folder found, count the `SKILL.md` files, and name the installed skills.
5. Discover constraints: identify the test command, build command, lint command, and project conventions from `.agents/memory/project.md` or project files.
6. Flag risks with severity:
   - High: wrong branch, uncommitted changes that will conflict, failing tests on main.
   - Medium: missing tests for the target area, unknown build/lint commands.
   - Low: stale references in `.agents/references/`, unused dependencies, thin project memory.
7. Aprendiz Mode: for EACH risk item, include three sub-fields in beginner-friendly Spanish:
   - Qué significa: what the risk means in plain language.
   - Por qué importa: why it matters for the project.
   - Qué hacer ahora: one concrete action to take now.
8. Avoid jargon. Explain risks in beginner-friendly language without hiding exact commands or file paths.
9. Do not edit files, run fixes, deploy, or change configuration.

## Output

Use exactly these sections:
- What just happened: one short explanation of what SlashStack installed and what it did not change
- SlashStack installed: skills folder, number of skills, installed skill names
- Project state: branch, commits, uncommitted changes
- Commands detected: test, build, lint
- Risks: High / Medium / Low items with plain-language impact and recommended action; each item includes Qué significa, Por qué importa, and Qué hacer ahora
- What to do now: one concrete safest next step
- Exact next prompt: one copy-paste prompt the user can send next
