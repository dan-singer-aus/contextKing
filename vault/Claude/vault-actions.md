# Vault Actions Reference

Quick reference for vault operations. Full logic lives in Claude Code skills — this file is for reference and prototyping new skills.

---

## Skills

| Action | Skill | Example |
|---|---|---|
| Rewrite an authoritative file | `/vault-commit` | `/vault-commit Claude/Preferences.md` |
| Append to memory | `/memory-add` | `/memory-add prefer X over Y` |
| Evolve a thread | `/thread-evolve` | `/thread-evolve auth-refactor` |
| Start a thread | `/thread-start` | `/thread-start auth-refactor` |
| Update a thread | `/thread-update` | `/thread-update auth-refactor` |
| Park or close a thread | `/thread-park` | `/thread-park auth-refactor close` |
| End-of-session wrap-up | `/wrap` | `/wrap` |
| Load a project/thread context | — | *"open the [project/thread] context"* |

---

## Skill prototyping

Use this section to draft new vault action workflows before promoting them to `.claude/skills/`. Once a workflow is stable, create a skill file and remove the draft from here.

---

## Rewrite targets

| What changed | Where to update |
|---|---|
| Language/framework style rules | `Claude/Style/<language>.md` |
| General preferences | `Claude/Preferences.md` |
| Stack choices | `Claude/Stacks.md` |
| Project goals or decisions | `Claude/Projects/<name>/context.md` |

For thread file shape and evolution types, see `Claude/Threads/README.md`.
