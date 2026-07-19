---
name: security
description: Use before deploy or sharing to check for beginner-visible security risks.
---

# Security

## Purpose

Run a beginner-friendly pre-deploy safety review for common security risks.

## When to Use

Use before deploy, sharing a repo, adding auth, connecting payments, exposing an
API, or asking an agent to make production-facing changes.

## Workflow

1. Inspect secrets: check for committed `.env` files, API keys, tokens,
   credentials, private URLs, and hardcoded secrets.
2. Check auth assumptions: identify pages, API routes, admin screens, and data
   mutations that appear to rely on weak or missing auth.
3. Review public routes: list routes, endpoints, storage buckets, or files that
   could be publicly reachable.
4. Check risky defaults: flag debug mode, permissive CORS, open redirects,
   client-side secret usage, broad database rules, or unsafe sample config.
5. Explain severity in plain language: High means do not deploy; Medium means
   fix before real users; Low means track or clean up soon.
6. Suggest safe fixes: provide concrete next prompts or commands without
   applying changes automatically.
7. Aprendiz Mode: for EACH security risk, include three sub-fields in
   beginner-friendly Spanish:
   - Qué significa: what the risk means in plain language.
   - Por qué importa: why it matters for the project.
   - Qué hacer ahora: one concrete action to take now.

## Output

A security review containing:
- High risks: secrets, auth, or public routes that block deploy
- Medium risks: likely unsafe defaults or missing checks
- Low risks: cleanup items
- Aprendiz Mode: each risk includes Qué significa, Por qué importa, and Qué hacer ahora
- Safe next prompt: one scoped prompt to fix the highest-risk item first
