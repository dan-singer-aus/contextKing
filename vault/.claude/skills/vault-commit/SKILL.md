---
name: vault-commit
description: Update an authoritative vault file to reflect something discussed in the current conversation. Use when a preference, rule, or decision has changed.
argument-hint: [file-path]
allowed-tools: Read, Edit, Glob
---

Update the authoritative file to reflect what was discussed.

## Step 1 — Identify the file

If `$0` is provided, use that path (resolve relative to the vault root).

If not, determine from the conversation which file should be updated:

| What changed | Where to update |
|---|---|
| Code style or language rules | `Claude/Style/` files |
| General preferences | `Claude/Preferences.md` |
| Stack choices | `Claude/Stacks.md` |
| Project goals or decisions | `Claude/Projects/<name>/context.md` |

If ambiguous, ask the user which file.

## Step 2 — Read the file

Read the target file in full before editing.

## Step 3 — Edit

Rewrite the relevant section(s) to reflect the new understanding. This is a rewrite of the affected content — preserve everything that hasn't changed.

Do not add changelog entries or "updated on" dates. The file should read as the current truth, not a history.

## Step 4 — Confirm

Tell the user what was changed and in which file.
