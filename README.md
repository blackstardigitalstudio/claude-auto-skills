<p align="center"><img src="https://raw.githubusercontent.com/blackstardigitalstudio/claude-auto-skills/main/banner.png" alt="banner" width="100%"></p>

# claude-auto-skills

Global instructions that make **Claude Code automatically pick and use the right
skills for each task** — without you having to name them.

This is **not a skill**. It is a `CLAUDE.md` file: standing instructions that
Claude Code reads at the start of every session. It adds a simple routine —
*analyze the request → review the available skills → use the relevant ones →
then act* — and tells Claude to skip it for trivial chat so you don't waste
tokens.

## What it does

When you give Claude a real task (write/modify code, test an app, set up a
project), it first looks at which of your installed skills fit, uses them, and
only then starts working. For simple questions or greetings it just answers
normally.

It also tells Claude to prefer the `test-app` / `agent-browser` skills for any
browser testing or automation.

## Install

### Global (all your projects)

Place `CLAUDE.md` in your user-level Claude folder.

```bash
# macOS / Linux
mkdir -p ~/.claude
curl -fsSL https://raw.githubusercontent.com/USER/REPO/main/CLAUDE.md -o ~/.claude/CLAUDE.md
```

```cmd
:: Windows
mkdir "%USERPROFILE%\.claude"
curl -fsSL https://raw.githubusercontent.com/USER/REPO/main/CLAUDE.md -o "%USERPROFILE%\.claude\CLAUDE.md"
```

> If you already have a `CLAUDE.md`, **append** this content to it instead of
> overwriting — don't lose your existing instructions.

### Per project

Put `CLAUDE.md` in the root of a project; it applies to that project and any
teammate who clones it.

## Note

Skill auto-matching is partly built into Claude already (skills trigger from
their descriptions). This file makes the behavior more deliberate and
consistent, and lets you point Claude at the skills you prefer.

## License

MIT — see [LICENSE](LICENSE).
