# ClaudeBrain — Project Index

## How to Use (AI Instructions)

**Reading context:**
- Start with `task.md` for current work, come here for project lookup, read `projects/{slug}.md` for depth.

**After completing work:**
- Update `task.md` and the relevant `projects/{slug}.md` cold file.

**Creating a new project:**
1. If Ed provides a project name only, generate a slug automatically.
2. Add a row to the Project Registry table below.
3. Create `projects/{slug}.md` using the Project File Format below.
4. Add a backlog section in `task.md` under `## Project Backlog` with the slug as heading.

**Updating project status:**
- `active` → currently being worked on
- `paused` → on hold, will resume later
- `archived` → done or abandoned; move remaining backlog items to cold file under "Backlog Archive"

**Slug rules:**
- Use lowercase, hyphenated, short slugs (e.g. `my-app`, `api-gateway`).
- Slugs are internal project IDs and file path keys.
- Ed can use natural project names in prompts; AI must generate and maintain slug mapping automatically.
- Ask Ed for a slug only when disambiguation is required.

---

## Project Registry

| Slug | Status | Stack | Description | Cold File |
|------|--------|-------|-------------|-----------|
| claudebrain | active | Markdown | AI context & task management system | [projects/claudebrain.md](projects/claudebrain.md) |

---

## Project File Format

When creating a new `projects/{slug}.md`, use these sections:

```
# {Project Name}
> Status: active | paused | archived
> Last updated: YYYY-MM-DD

## Overview
Brief description — what it is, why it exists.

## Goals
Concrete objectives and success criteria.

## Tech Stack
Languages, frameworks, services, infra.

## Architecture
High-level design: components, data flow, key patterns.

## Key Decisions
Important choices made and their rationale (ADR-style).

## File Map
Notable files/dirs and their purpose.

## API Contracts
Endpoints, schemas, or integration interfaces.

## Current State
What works, what's broken, what's in progress.

## Open Questions
Unresolved decisions or unknowns.

## Related Resources
Links, docs, references.

## Backlog Archive
Completed or moved backlog items from task.md.
```
