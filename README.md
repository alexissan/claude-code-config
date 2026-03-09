# My Claude Code Config

My `CLAUDE.md` configuration for [Claude Code](https://docs.anthropic.com/en/docs/claude-code), Anthropic's agentic coding tool — tailored for iOS development.

## [`claude-ios-dev.md`](./claude-ios-dev.md)

Project-level config for an **iOS app** (`your-repo/.claude/CLAUDE.md`). Covers:

- **Custom skills** — Claude invokes project-specific workflows (build, test, create MR, review MR, localization, etc.) instead of guessing commands
- **Git conventions** — branching rules, naming format, shell functions, oh-my-zsh aliases
- **Merge request rules** — target branch, templates, ticket references
- **Testing & verification** — run tests before committing, verify fixes by building
- **Localization workflow**
- **Project info and company resources**

## How it works

Claude Code loads `your-repo/.claude/CLAUDE.md` when working inside that repo. You can also have a global config at `~/.claude/CLAUDE.md` that applies to every project.

## Usage

1. Copy `claude-ios-dev.md` to `your-repo/.claude/CLAUDE.md`
2. Replace placeholders (ticket prefixes, URLs, project names) with your own
3. Add your own sections as needed

## Tips

- Keep it concise — this file is loaded into context every session
- Focus on **behaviors** you want to change from defaults
- Use it for things you'd otherwise repeat every conversation
- Shell functions and aliases are great here — teach Claude your shortcuts once
- Skills (slash commands) let you encode complex multi-step workflows that Claude follows exactly
