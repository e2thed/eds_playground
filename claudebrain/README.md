# ClaudeBrain

ClaudeBrain is Ed's persistent project memory for AI-assisted work across sessions.

`../.github/copilot-instructions.md` is for AI assistants.
This `README.md` is for humans.

## Purpose

Chat context is temporary. Files in `claudebrain/` preserve:
- active tasks
- project status
- decisions and rationale
- open questions and next steps

## Structure

| Tier | File | Purpose |
|------|------|---------|
| Hot | `task.md` | Current priorities and project backlog |
| Warm | `index.md` | Project registry, status, and project file format |
| Cold | `projects/` | Full project files and archived backlog |

## Daily Workflow

1. Start session by asking for task status (`task.md`).
2. During work, record completed items, decisions, and open questions.
3. End session with updated `task.md` and the relevant project file in `projects/`.

## Starting a New Project

1. Use the project name in plain language.
2. AI adds the project to `index.md`.
3. AI creates the project file in `projects/` using the format in `index.md`.
4. AI adds a backlog section for that project in `task.md`.

You never need to provide a slug. AI manages internal project IDs and file names.

## Status Model

- `active`: currently being worked on
- `paused`: on hold
- `archived`: complete or discontinued

When a project is archived, move remaining backlog items from `task.md` into that project's file under `Backlog Archive`.

## Prompt Shortcuts

Use prompts like these to keep files current:

```text
Project update for <project name>:
Completed: ...
In progress: ...
Next: ...
Decisions: ...
Open questions: ...
```

```text
Begin next project:
Name: ...
Folder: ...
Stack: ...
Goal: ...
```

```text
Archive project <project name> and move remaining backlog to cold storage.
```

## Notes

- Keep this repo in your workspace as your long-lived memory system.
- Project repos can be separate and added alongside it.
- A project folder can be initialized with local Git only (`git init`) and pushed later when ready.