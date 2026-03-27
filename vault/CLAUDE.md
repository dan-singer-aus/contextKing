# CLAUDE.md

This is the entry point for Claude Code when working with this vault.

## Session Start

At the start of any session involving coding work, a project, or a discussion:

1. Read `INDEX.md` — lists active projects and threads
2. Read `Claude/Index.md` — tells you which rules files to load for the current task
3. Load only what is relevant to the session

Do not load everything upfront. Read rules files on demand, as the task requires them.

## Vault Structure

```
Claude/
  Index.md            ← which file to read for which task
  Preferences.md      ← coding style and collaboration preferences
  Stacks.md           ← tech stack defaults
  memory.md           ← loose notes not yet formalised into rules
  vault-actions.md    ← skills reference for vault operations
  Style/              ← language/framework-specific style rules
  Projects/           ← per-project context stores
  Threads/            ← persistent discussion threads
```

## Shorthand

| Shorthand | Refers to |
|---|---|
| `vault-c` | `Claude/` — the Claude context store |

## Local Project Files (`CLAUDE.md` / `AGENTS.md`)

When working on a project, check for `CLAUDE.md` or `AGENTS.md` in the project root and read it before doing any work there.

**Conflict resolution — local file wins on workflow, vault wins on style defaults:**

| Concern | Authority |
|---|---|
| Dev commands, build, lint, test | Local project file |
| Quality checklist (what to run before committing) | Local project file |
| File structure, naming conventions specific to the project | Local project file |
| Code style, naming, architecture principles | Vault preferences (as default where local file is silent) |

If a local project file explicitly overrides a vault preference, follow the local file — but flag the conflict once at the start of the session. Don't repeat it on every response; one mention per session is enough. After flagging, follow the local file silently.

## Thread Updates

When updating a thread mid-conversation, use a background agent rather than inline skill invocation. This keeps the conversation flowing without interruption.
