# contextKing

A structured context store for Claude Code — persistent memory, style rules, project context, and discussion threads that survive across sessions.

## The problem

Claude Code is stateless between sessions. Without structure, you end up re-explaining your preferences, re-loading project context, and repeating yourself constantly. `contextKing` gives Claude a persistent, well-organised place to store everything it needs to work effectively with you over time.

## How it works

The vault is a folder that lives alongside (or inside) your projects, or as a standalone Obsidian vault. Claude reads it at the start of each session — but only the parts relevant to the current task.

```
contextKing/
  CLAUDE.md             ← entry point: tells Claude what to load and when
  INDEX.md              ← active projects and threads (read every session)
  Claude/
    Index.md            ← which rules file to read for which task
    Preferences.md      ← your coding style and collaboration preferences
    Stacks.md           ← your tech stack defaults
    memory.md           ← loose notes not yet formalised into rules
    vault-actions.md    ← reference for vault skills
    Style/              ← language-specific style rules (one file per language/area)
    Projects/           ← per-project context stores
    Threads/            ← persistent discussion threads across sessions
```

## Getting started

1. Clone or fork this repo
2. Copy `CLAUDE.md` into your user-level Claude config (`~/.claude/CLAUDE.md`) or into your project root
3. Fill in `Claude/Preferences.md` with your preferences
4. Fill in `Claude/Stacks.md` with your stack
5. Add style rules to `Claude/Style/` (see the example file)
6. Start a session — Claude will load the vault automatically

## Skills

The vault works best with a set of Claude Code skills for managing threads, memory, and vault files. These are distributed separately as a Claude Code plugin. See [vault-actions.md](Claude/vault-actions.md) for the full list.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md).
