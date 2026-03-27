---
name: thread-start
description: Create a new persistent discussion thread in the vault. Use when the user wants to start tracking a topic across sessions.
argument-hint: [topic]
allowed-tools: Read, Write, Edit
---

Create a new thread file and update the index.

## Step 1 — Create the thread file

Write `Claude/Threads/$0.md` with this exact structure:

```
---
type: discussion
status: active
---

# $0

## Current Thinking
[Summarise the current state of the discussion from this conversation]

## Log
!`date +%Y-%m-%d` — created
```

## Step 2 — Update INDEX.md

Read `INDEX.md` first to preserve existing content.

Add a row under **Active Threads**:

```
- [$0](Claude/Threads/$0.md) — newly created
```

## Step 3 — Confirm

Tell the user the thread has been created and what's in Current Thinking.
