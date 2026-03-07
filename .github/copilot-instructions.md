# Copilot Instructions

## Environment
- OS: Windows
- Workspace: eds_playground (general sandbox, multi-project)
- User: Edward

## AI Context System — ClaudeBrain
All project context lives in `claudebrain/` using a 3-tier storage model:

| Tier | File | When to read |
|------|------|-------------|
| **Hot** | `claudebrain/task.md` | User asks about tasks, todos, "what do I need to do" |
| **Warm** | `claudebrain/index.md` | User mentions a project by name, asks for overview, or you need to create/find a project |
| **Cold** | `claudebrain/projects/{slug}.md` | User wants deep detail on a specific project |

## Routing Rules
1. **Task questions** → Read `claudebrain/task.md` first
2. **Project questions** → Read `claudebrain/index.md` to find the project, then its cold file if detail is needed
3. **New project** → Read the Project File Format section in `claudebrain/index.md`, create `claudebrain/projects/{slug}.md`
4. **After completing work** → Update `task.md` (mark done, add next steps) and the relevant cold file if applicable

## Conventions
- Keep `task.md` current — it is the source of truth for what's in-flight
- Use project slugs (lowercase, hyphens) consistently across all tiers
- When archiving a project, move its backlog items into the cold file under "Backlog Archive"
