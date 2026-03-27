---
name: thread-park
description: Park or close a thread — marks it inactive and updates the index. Use "park" for paused threads, "close" for resolved ones.
argument-hint: [thread-name] [park|close]
allowed-tools: Read, Edit, Glob
---

Park or close the thread at `Claude/Threads/$0.md`.

## Step 1 — Determine action

- If `$1` is "close" or "resolve", set status to `resolved`
- Otherwise default to `parked`

If no argument was provided, list active threads from `INDEX.md` and ask the user which one.

## Step 2 — Update the thread file

Read `Claude/Threads/$0.md`.

- Change the frontmatter `status` to `parked` or `resolved`
- Append a dated log entry: `!`date +%Y-%m-%d` — parked` (or `resolved`)

## Step 3 — Update INDEX.md

Read `INDEX.md`. Remove the thread's row from **Active Threads**.

## Step 4 — Confirm

Tell the user the thread has been parked/closed.
