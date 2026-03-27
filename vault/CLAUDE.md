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

## Thread Updates

When updating a thread mid-conversation, use a background agent rather than inline skill invocation. This keeps the conversation flowing without interruption.
