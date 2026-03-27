---
name: thread-update
description: Update a persistent thread after a conversation has progressed it. Rewrites Current Thinking and appends to the Log.
argument-hint: [thread-name]
allowed-tools: Read, Edit, Glob
---

Update the thread at `Claude/Threads/$0.md` to reflect what was discussed in this conversation.

## Step 1 — Read the thread

Read `Claude/Threads/$0.md` to understand its current state.

If no argument was provided, check `Claude/Threads/` for active threads and ask the user which one to update.

## Step 2 — Rewrite Current Thinking

Replace the **Current Thinking** section with a fresh summary that reflects the updated state of the discussion. This is a rewrite, not an append — it should read as a standalone summary.

## Step 3 — Append to Log

Add a dated one-liner to the top of the **Log** section (newest first):

```
!`date +%Y-%m-%d` — [concise summary of what changed]
```

## Step 4 — Confirm

Tell the user what changed in the thread.
