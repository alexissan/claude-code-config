# iOS Project

## Task Execution Principles
- When asked to do something, just do it — don't ask clarifying questions for straightforward requests like 'build the latest master'
- When searching for files, search system-wide unless the user specifies a directory

## General Rules
- Do not add any comments to the code unless explicitly asked
- Always use available simulators when trying to run builds or tests
- No AI attributions or co-author lines in commits
- Follow existing patterns in the codebase
- Add unit tests for new functionality
- When modifying a module (adding/removing public types, changing dependencies), update its `README.md` in the same PR

## Build & Test

Use `xcodebuild` for all build and test operations:

```bash
# Build
xcodebuild -project YourApp.xcodeproj -scheme YourAppBeta -destination 'platform=iOS Simulator,name=iPhone 16' build

# Run tests
xcodebuild -project YourApp.xcodeproj -scheme YourAppBeta -destination 'platform=iOS Simulator,name=iPhone 16' test
```

- Always pick an available simulator (`xcrun simctl list devices available`)
- Boot the simulator before installing/launching
- Verify fixes by building and running — never claim a fix works based on assumptions

## Git Conventions

### Branching Rules
- **ALWAYS branch from `master`**, never from `develop`
- Branch naming format: `feature/TICKET-XXXX-short-description`
- When creating worktrees/branches for JIRA tasks, name them after the NEW task ID, not the baseline branch
- When creating feature branches for new work, branch from `origin/master`

### Examples
```bash
# Creating a new feature branch
git fetch origin && git checkout -b feature/TICKET-1234-payment-flow origin/master

# Using the shell function (preferred)
branch_ticket TICKET-1234 payment-flow
# → Creates: feature/TICKET-1234-payment-flow

# Switching branches with fzf
fbr     # local branches only
fbrr    # includes remote branches
fco     # branches + tags
```

### Available Shell Functions (use these instead of raw git commands)

| Function | Usage | What It Does |
|----------|-------|-------------|
| `branch_ticket` | `branch_ticket TICKET-1234 desc` | Create feature branch `feature/TICKET-1234-desc` |
| `changes` | `changes` | List files changed vs base branch |
| `context` | `context` | Show branch, recent commits, changed files |
| `fbr` | `fbr` | FZF checkout local branch |
| `fbrr` | `fbrr` | FZF checkout branch (including remote) |
| `fco` | `fco` | FZF checkout branch or tag |
| `fcoc` | `fcoc` | FZF checkout specific commit |
| `fshow` | `fshow` | FZF git commit browser |
| `fcs` | `fcs` | Get commit SHA (e.g. `git rebase -i $(fcs)`) |
| `fstash` | `fstash` | FZF stash manager (enter=show, ctrl-d=diff, ctrl-b=branch) |
| `mr_review` | `mr_review 123` | Review MR #123 |
| `derived` | `derived` | Clear Xcode derived data |
| `xopen` | `xopen` | Open Xcode workspace/project in current dir |
| `sim` | `sim list\|boot\|screenshot\|kill` | Simulator helpers |

### Oh-My-Zsh Git Aliases (git plugin)
Common aliases available via the `git` oh-my-zsh plugin:

| Alias | Command |
|-------|---------|
| `gst` | `git status` |
| `gco` | `git checkout` |
| `gcb` | `git checkout -b` |
| `gcm` | `git checkout master` |
| `gp` | `git push` |
| `gl` | `git pull` |
| `ga` | `git add` |
| `gc` | `git commit` |
| `gd` | `git diff` |
| `glog` | `git log --oneline --decorate --graph` |
| `grb` | `git rebase` |

## Merge Requests
- **MRs must target `master` branch** (not develop)
- Include JIRA ticket reference in MR title and description
- Never skip the MR description template even for small changes
- When creating MRs, only include the commits that are part of the current task

## Testing & Verification
- After any code change, proactively run unit tests before committing
- After removing feature flags, check ALL references including plist bundles, not just Swift source files
- Never claim a fix works based on assumptions — verify by building and running

## Localization
- When adding translations (especially Spanish), scan ALL user-facing strings across ALL files in a single pass
- Do not use localization tools or frameworks unless explicitly asked — use mock TODOs or hardcoded strings for PoC work
- After adding translations, verify no strings remain in English by grepping for untranslated keys

## Project Info
- **Project**: YourApp.xcodeproj
- **Scheme**: YourAppBeta
- **Bundle ID**: com.yourcompany.yourapp.beta

## Company Resources

### Atlassian
- **Jira**: https://yourcompany.atlassian.net/browse/
- **Confluence**: https://yourcompany.atlassian.net/wiki/home
- **Key Spaces**: TECH (Product Engineering), PROD (Product)

### Test Environments
- **Dev environment**: https://your-dev-environment-url/
