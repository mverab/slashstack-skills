# Contributing to SlashStack Free Skills

Thanks for considering a contribution. This repository holds the **MIT-licensed free layer** of [SlashStack](https://slashstack.dev) — eleven workflow skills for AI coding agents. The Pro layer lives in a private upstream and is intentionally out of scope here.

## Ways to contribute

### 1. Report a bug or weakness in a skill

Skills are prompts, and prompts have failure modes. If a skill:

- produces bad agent behavior in a real session,
- misses an important verification step,
- or conflicts with a common tool's conventions,

…[open an issue](https://github.com/mverab/slashstack-skills/issues) with:

1. **Which skill** and which agent (Claude Code, Codex, Cursor, Hermes, …)
2. **What you asked** and **what the agent did** (a short transcript excerpt helps enormously)
3. **What you expected** instead

Concrete failure transcripts are the single most valuable contribution to this repo.

### 2. Improve an existing skill (PR)

Pull requests that tighten, clarify, or fix an existing skill are welcome.

**Rules of the house:**

- Skills must stay **plain Markdown with YAML frontmatter** (`name`, `description`). No runtime code, no dependencies.
- Keep the **existing structure**: Purpose → When to Use → Workflow. Agents rely on that shape.
- **Shorter beats longer.** Every line in a skill costs context-window tokens in every future session. Cut before you add.
- Safety-related steps (secret scanning, verification-before-done) can be *strengthened* but never *weakened* in a drive-by PR.
- One skill per PR. Explain the failure mode your change fixes.

### 3. Propose a new skill

Open an issue first — do not PR a new skill cold. The free layer is deliberately focused, and new additions need to justify their context cost against the existing eleven. A good proposal includes:

- The **recurring task** it automates (with a real example)
- Why none of the existing eleven cover it
- Why it belongs in the *free* layer rather than Pro

## Style

- English only (this repo is global-facing).
- Imperative voice in workflow steps ("Run the tests", not "You should run the tests").
- Keep frontmatter `description` under ~120 characters — agents use it for skill selection.

## Code of conduct

Be direct, be technical, be kind. Assume competence; critique artifacts, not people.

## License

By contributing, you agree your contributions are licensed under the [MIT License](LICENSE).
