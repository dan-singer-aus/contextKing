# Projects

One folder per project. Each folder is a context store — goals, stack, decisions, and session notes.

## Structure

```
Projects/
  _template/           ← copy this to start a new project
    context.md         ← goals, stack, key decisions (Claude reads this)
    sessions.md        ← append-only session log (optional)
  <project-name>/
    context.md
    sessions.md
```

## Register in the index

After creating a new project context, add it to `INDEX.md` so Claude loads it at session start.

## Conventions

- `context.md` — what the project *is*, what's been decided, what constraints apply. Claude reads this when working on the project.
- `sessions.md` — append-only log of what happened each session. Useful for picking up where you left off.
- Index descriptions identify what a project *is*, not its current status. Status lives in `sessions.md`.
