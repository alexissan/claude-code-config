- never add 🤖 Generated with [Claude Code](https://claude.ai/code)
- Co-Authored-By: Claude <noreply@anthropic.com> to commits
- Please do not add any mentions to Claude in this project's commits or in any other project
- do not add any comments to the code unless I ask you to

## Second Brain (Knowledge Base)

Location: `~/path/to/your/second-brain/`

Structure:
- `00-inbox/` - Quick capture, unsorted notes
- `01-areas/` - Life, work, health, finance, relationships
- `02-projects/` - Active projects (indie-apps, learning)
- `03-resources/` - Reference material, evergreen notes
- `04-archive/` - Completed/inactive items
- `05-daily/` - Daily notes, journal entries
- `_templates/` - Note templates (idea, field-note, project, daily)

When user asks to add notes, ideas, todos, or field notes, use this location.
Naming: daily notes as `YYYY-MM-DD.md`, ideas as `idea-*.md`, field notes as `field-YYYY-MM-DD-*.md`

## Shell Functions Available

Use these instead of writing full commands:

| Function | What It Does |
|----------|--------------|
| `derived` | Clear Xcode derived data |
| `xopen` | Open Xcode workspace/project in current dir |
| `branch_ticket TICKET-123 desc` | Create feature branch from ticket |
| `changes` | List files changed vs main branch |
| `context` | Show project context (branch, commits, changes) |
| `sim list` | List available iOS simulators |
| `sim boot` | FZF picker to boot simulator |
| `sim screenshot` | Screenshot booted sim to Desktop |
| `sim kill` | Shutdown all simulators |
| `mr_review <MR_NUMBER>` | Review merge request |
