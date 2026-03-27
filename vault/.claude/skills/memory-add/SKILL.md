---
name: memory-add
description: Append a loose observation or preference to vault memory. Use when something is worth keeping but hasn't crystallised into a rule yet.
argument-hint: [note]
allowed-tools: Read, Edit
---

Append a dated one-liner to `Claude/memory.md`.

## Step 1 — Read current memory

Read `Claude/memory.md` to see existing entries.

## Step 2 — Determine what to add

If `$ARGUMENTS` is provided, use that as the note.

If no argument, summarise the key takeaway from the current conversation that's worth persisting.

## Step 3 — Append

Add a line to the end of `Claude/memory.md`:

```
- !`date +%Y-%m-%d` — [concise note]
```

Do not duplicate an existing entry. If a similar one exists, update it instead.

## Step 4 — Confirm

Tell the user what was added.
