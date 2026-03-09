# My Claude Code Config

My `CLAUDE.md` configurations for [Claude Code](https://docs.anthropic.com/en/docs/claude-code), Anthropic's agentic coding tool.

## Files

### [`global-claude.md`](./global-claude.md) → `~/.claude/CLAUDE.md`
Global config that applies to **every project**. Covers:
- Commit hygiene — no auto-generated footers or Claude mentions
- Code style — no unsolicited comments
- Second Brain integration — Claude knows where my notes live (PARA method) and can capture ideas, field notes, and daily entries hands-free
- Shell function awareness — so Claude uses my shortcuts instead of raw commands

### [`project-claude.md`](./project-claude.md) → `your-repo/.claude/CLAUDE.md`
Project-level config for an **iOS app**. Covers:
- Custom skills — Claude invokes project-specific workflows (build, test, create MR, review MR, localization, etc.) instead of guessing commands
- Git conventions — branching rules, naming format, shell functions, oh-my-zsh aliases
- Merge request rules — target branch, templates, ticket references
- Testing & verification — run tests before committing, verify fixes by building
- Localization workflow
- Project info and company resources

## How Claude Code loads these

1. **Global** `~/.claude/CLAUDE.md` is loaded into every session
2. **Project** `your-repo/.claude/CLAUDE.md` is loaded when working inside that repo

Project-level instructions build on top of global ones. Keep global config lean and put project-specific details in the project file.

## Usage

1. Copy `global-claude.md` to `~/.claude/CLAUDE.md`
2. Copy `project-claude.md` to `your-repo/.claude/CLAUDE.md`
3. Replace placeholders (paths, ticket prefixes, URLs) with your own
4. Add your own sections as needed

## Tips

- Keep it concise — these files are loaded into context every session
- Focus on **behaviors** you want to change from defaults
- Use it for things you'd otherwise repeat every conversation
- Shell functions and aliases are great here — teach Claude your shortcuts once
- Skills (slash commands) let you encode complex multi-step workflows that Claude follows exactly
