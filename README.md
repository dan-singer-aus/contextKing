# contextKing

A structured context store for Claude Code — persistent memory, style rules, project context, and discussion threads that survive across sessions.

## The problem

Claude Code is stateless between sessions. Without structure, you end up re-explaining your preferences, re-loading project context, and repeating yourself constantly. `contextKing` gives Claude a persistent, well-organised place to store everything it needs to work effectively with you over time.

## How it works

The vault is a folder that lives alongside (or inside) your projects, or as a standalone Obsidian vault. Claude reads it at the start of each session — but only the parts relevant to the current task.

**Local project files are respected.** If a project has its own `CLAUDE.md` or `AGENTS.md`, Claude reads it before doing any work in that project. Local files take authority over project-specific concerns (dev commands, build, lint, file structure); vault preferences apply as defaults where the local file is silent. If a local file explicitly overrides a vault preference, the local file wins — Claude flags the conflict once at session start, then follows it silently.

```
vault/
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
  .claude/
    skills/             ← vault skills (install these separately — see below)
```

## Viewing the vault

The vault is plain markdown, so any markdown viewer works — Obsidian, Typora, VS Code, or even just a file browser. The point of having a viewer is simply to give you a readable window into what's in the context store: what Claude knows, what threads are active, what preferences are set.

Obsidian is what this system was built with, but there's nothing Obsidian-specific about the vault itself.

## Getting started

1. Clone or fork this repo
2. Copy the `vault/` folder to wherever you want your vault to live (alongside your projects, in your home directory, or as an Obsidian vault)
3. In your user-level Claude config (`~/.claude/CLAUDE.md`) or your project's `CLAUDE.md`, add a line pointing at the vault:
   ```
   See /path/to/vault/CLAUDE.md for full instructions.
   ```
   The vault's own `CLAUDE.md` stays where it is — your pointer file just tells Claude where to find it.
4. Fill in `Claude/Preferences.md` with your preferences
5. Fill in `Claude/Stacks.md` with your stack
6. Add style rules to `Claude/Style/` (see the example file)
7. Install the skills (see below)
8. Start a session — Claude will load the vault automatically

## Skills

The vault works best with the included Claude Code skills for managing threads, memory, and vault files. To install them, copy the skills folder into your user-level Claude config directory:

```
cp -r vault/.claude/skills ~/.claude/
```

Or copy individual skill folders if you only want specific ones. See [vault/Claude/vault-actions.md](vault/Claude/vault-actions.md) for the full skill reference.

## Recommended setup

For the best experience, configure Claude Code to auto-approve writes to the vault's mutable files. This lets thread and memory skills run in the background without interrupting your session.

In your Claude Code settings, add write permissions for:
- `Claude/Threads/` — thread skills write here
- `Claude/memory.md` — memory skills append here

(These paths are relative to your vault root, not the repo root.)

Without this, Claude will pause and ask for approval on every vault write, which breaks the background workflow.

## Status

The system is still being refined. Some conventions may shift as I learn what works in practice. The core structure is stable, but treat anything marked as experimental as subject to change.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md).
