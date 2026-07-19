# SlashStack Free Skills

Eleven open-source workflows that help AI coding agents inspect before editing, verify before stopping, and preserve useful project context.

These skills are the MIT-licensed free layer of [SlashStack](https://slashstack.dev). They are plain Markdown files: local, readable, editable, and versionable with your project.

## Install

The recommended installer also adds the SlashStack agent kernel and local memory structure:

```bash
npx slashstack@latest install --target agents
```

For Claude Code:

```bash
npx slashstack@latest install --target claude
```

To copy only the skill files manually:

```bash
git clone https://github.com/mverab/slashstack-skills.git
mkdir -p your-project/.agents/skills
cp -R slashstack-skills/skills/* your-project/.agents/skills/
```

## Included skills

| Skill | Purpose |
| --- | --- |
| `/preflight` | Inspect project state and constraints before editing code. |
| `/vibe` | Shape a rough product idea before building. |
| `/audit` | Review changes for bugs, regressions, and missing tests. |
| `/ship` | Verify behavior with concrete evidence before handoff. |
| `/execute` | Plan and complete multi-step work across files and checks. |
| `/security` | Check visible risks before deployment or sharing. |
| `/remember` | Save durable facts that future sessions need. |
| `/recall` | Load saved project context before working. |
| `/improve` | Capture reusable patterns from completed work. |
| `/explain` | Translate technical output into plain language. |
| `/next` | Suggest safe next steps when the path is unclear. |

## Free and Pro boundary

This repository intentionally contains only the eleven free skills.

[SlashStack Pro](https://slashstack.dev/#pricing) adds:

- Eight additional skills, for nineteen total
- Six always-on guards
- Senior Mode
- Git pre-commit and pre-push protection
- Checkpoint recovery
- Offline license validation and lifetime updates

The Pro layer is not published in this repository.

## Compatibility

SlashStack is designed for repository-aware coding agents, including Claude Code, Codex, and Cursor. The skill files are agent-readable Markdown and do not require a runtime dependency.

## License

MIT. See [LICENSE](LICENSE).
