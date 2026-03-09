# AI Agent Config for iOS Development

Configuration files for AI coding agents, tailored for iOS development. Available in two formats:

## Files

### [`claude-ios-dev.md`](./claude-ios-dev.md) — Claude Code version
Place at `your-repo/.claude/CLAUDE.md`. Includes Claude-specific features:
- **Custom skills** (slash commands) for build, test, MR creation, code review, localization
- Git conventions, shell functions, oh-my-zsh aliases
- Merge request rules, testing & verification, localization workflow
- Project info and company resources

### [`agents-ios-dev.md`](./agents-ios-dev.md) — Vendor-agnostic version
Place at `your-repo/AGENTS.md`. Works with Claude Code, Cursor, GitHub Copilot, Google Jules, OpenAI Codex, and others. Same content minus Claude-specific skills — replaced with explicit build/test commands.

## CLAUDE.md vs AGENTS.md

| | `CLAUDE.md` | `AGENTS.md` |
|---|---|---|
| Supported by | Claude Code | Most AI coding agents |
| Skills (slash commands) | Yes | No |
| Format | Markdown | Markdown |
| Nesting (monorepos) | Yes | Yes |

Use `CLAUDE.md` if you're all-in on Claude Code and want skills. Use `AGENTS.md` if you work with multiple agents or want portability. You can also use both — Claude Code reads both files.

Learn more about the AGENTS.md convention at [agents.md](https://agents.md).

## Usage

1. Pick your version (or both)
2. Copy to your repo (`CLAUDE.md` → `.claude/CLAUDE.md`, `AGENTS.md` → repo root)
3. Replace placeholders (ticket prefixes, URLs, project names) with your own

## Tips

- Keep it concise — these files are loaded into context every session
- Focus on **behaviors** you want to change from defaults
- Shell functions and aliases are great — teach the agent your shortcuts once
- In Claude Code, skills let you encode multi-step workflows the agent follows exactly
