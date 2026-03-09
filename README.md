# My Claude Code Config

My `CLAUDE.md` configuration for [Claude Code](https://docs.anthropic.com/en/docs/claude-code), Anthropic's agentic coding tool.

This is the global config I use at `~/.claude/CLAUDE.md` — it applies to every project Claude Code works on.

## What's in it

- **Commit hygiene** — no auto-generated footers or Claude mentions in commits
- **Code style** — no unsolicited comments in code
- **Second Brain integration** — Claude knows where my notes live and how they're organized (PARA method), so I can capture ideas, field notes, and daily entries hands-free
- **Shell function awareness** — custom shell functions for iOS development so Claude uses them instead of writing raw commands

## How it works

Claude Code loads `~/.claude/CLAUDE.md` at the start of every session. Think of it as persistent instructions that shape how the agent behaves across all your projects.

You can also have per-project `CLAUDE.md` files at the root of any repo for project-specific instructions.

## Usage

1. Copy `CLAUDE.md` to `~/.claude/CLAUDE.md`
2. Adjust paths and function names to match your setup
3. Add your own sections as needed

## Tips

- Keep it concise — this file is loaded into context every session
- Focus on **behaviors** you want to change from the defaults
- Use it for things you'd otherwise repeat every conversation
- Shell functions are great here — teach Claude your shortcuts once
