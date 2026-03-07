# ClaudeBrain
> Status: active
> Last updated: 2026-03-07

## Overview
A tiered AI context management system that gives any AI assistant instant awareness of current tasks, project registry, and deep project knowledge. Lives in `claudebrain/` within the eds_playground workspace.

## Goals
- AI can answer "what do I need to do today?" without extra prompting
- AI can ramp up on any project from cold storage in one read
- Minimal autoload token cost via `.github/copilot-instructions.md` pointer
- Scales to 6+ concurrent projects without context bloat

## Tech Stack
Markdown files only. No tooling dependencies.

## Architecture
Three-tier storage:
- **Hot** — `copilot-instructions.md` (auto-loaded, ~25 lines) + `task.md` (daily focus + backlog)
- **Warm** — `index.md` (project registry, format spec, AI usage guide)
- **Cold** — `projects/{slug}.md` (one file per project, deep detail)

Data flows downward: hot points to warm, warm points to cold. AI reads only as deep as needed.

## Key Decisions
1. **No template file** — Format spec embedded in `index.md` warm tier to save a file read on project creation.
2. **One .md per project** — Flat file structure in `projects/`; subdirs only if a project needs assets later.
3. **copilot-instructions.md stays minimal** — Only env facts + routing rules. All real content lives in claudebrain/.
4. **Backlog archive in cold files** — When archiving a project, completed/remaining backlog moves here so task.md stays clean.

## File Map
```
.github/copilot-instructions.md  — Auto-loaded hot pointer (~25 lines)
claudebrain/task.md              — Daily focus + per-project backlog
claudebrain/index.md             — Project registry + format spec + AI guide
claudebrain/projects/            — Cold storage (one .md per project)
```

## Current State
Initial scaffolding complete. All files created. Needs first real-world test cycle.

## Open Questions
- Should index.md include a "recently updated" sort or stay alphabetical?
- Multi-workspace strategy: how to reference claudebrain from other VS Code workspaces?

## Related Resources
- VS Code Copilot custom instructions: https://code.visualstudio.com/docs/copilot/copilot-customization

## Backlog Archive
*(Empty — project just started)*
