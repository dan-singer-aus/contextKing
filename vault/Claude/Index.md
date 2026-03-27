---
title: Claude Index
description: Navigation guide — use this to find the right file to read before coding
---
# Claude Index

This index tells you **which file to read** for a given task or question.
Always read the referenced file directly — do not rely on this index as a substitute.

---

## What to read and when

| Task / Question | Read this file |
| --- | --- |
| Starting work in any language or framework | `Claude/Style/<language>.md` |
| Understanding general coding preferences | `Claude/Preferences.md` |
| Understanding the tech stack in use | `Claude/Stacks.md` |
| Understanding a specific project's goals or decisions | `Claude/Projects/<project-name>/context.md` |
| Deciding whether to fetch live docs | `Claude/Preferences.md` § Documentation Lookup |

Add rows here as you create new style rules files.

---

## Vault structure

```
Claude/
  Index.md                         ← you are here
  Preferences.md                   ← general coding and collaboration preferences
  Stacks.md                        ← tech stack defaults
  memory.md                        ← loose items not yet formalised into rules
  vault-actions.md                 ← workflows for vault operations
  Style/
    README.md                      ← how to add language/framework style rules
    ...                            ← one file per language or area
  Projects/
    _template/                     ← copy this to start a new project context
    ...                            ← per-project context stores
  Threads/
    README.md                      ← thread file shape and evolution types
    ...                            ← persistent discussion threads
```
