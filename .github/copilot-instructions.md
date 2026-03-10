# Copilot Instructions

You are working with Ed in `eds_playground`. This file is auto-loaded every session and is AI-facing only.

## Audience and Scope
- Audience: AI assistants
- Human-facing guidance lives in `claudebrain/README.md`
- Keep this file concise and operational

## Communication Style
- Be direct and concise
- Take initiative on routine tasks
- Prefer implementation over suggestion when intent is clear

## Work Patterns
- Routine work (bug fixes, docs, straightforward implementation): execute immediately unless ambiguous
- Significant work (architecture, major process changes, broad refactors): summarize understanding, propose plan, ask clarifying questions, and wait for Ed's go-ahead before execution

## Multi-Project Instruction Layering
Treat this file as the global base policy for the workspace.

When working on another repo/project in the same VS Code workspace:
1. Detect the active project from the file paths being edited or commands being run.
2. Before making edits, read that project's `.github/copilot-instructions.md` if it exists.
3. Apply both policies together: global base + project overlay.
4. Conflict handling:
	- User's explicit message in the current chat wins.
	- For safety and git rules, apply the stricter rule.
	- For implementation details (paths, runbooks, naming), apply project-specific rules.
5. Do not copy project-specific rules into this global file just to switch context.

If the active project has no instruction file, suggest creating one.

## Project Activation Behavior
- If Ed names a project, treat it as active until Ed switches.
- If current files are outside the project repo but are inputs to that project workflow, keep the active project policy.
- When switching projects, state the active project policy file once in the next progress update.

## ClaudeBrain Routing
All project context lives in `claudebrain/`.

1. Task and priority questions: read `claudebrain/task.md` first
2. Project lookup and overview: read `claudebrain/index.md`
3. Deep project detail: read `claudebrain/projects/{slug}.md`

## Context Maintenance Rules
- Keep `claudebrain/task.md` current; it is the source of truth for in-flight work
- After completing work, update `task.md` and the relevant cold project file
- Use lowercase hyphenated slugs consistently for internal file paths and project IDs
- Ed can use natural project names in prompts; AI must generate and maintain slug mapping automatically
- When archiving a project, move remaining backlog items into the cold file's `Backlog Archive` section
- Do not leave durable requirements only in chat

## Git and Environment Notes
- One commit per logical change
- Commit signing should be enabled
- `eds_playground` may be pushed to GitHub when requested.
- For any other repo in the workspace, do not add remotes or push unless Ed explicitly asks in the current message.
- When a repo is designated local-only, keep it remote-free and block push workflows.
- If user interaction is required (passphrase prompt, browser auth), pause and wait for Ed
