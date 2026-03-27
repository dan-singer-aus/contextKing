---
name: wrap
description: End-of-session checklist — reviews what happened and updates projects, threads, rules, memory, and the index as needed.
allowed-tools: Read, Write, Edit, Glob, Grep
effort: high
---

Run through the end-of-session checklist. Review the conversation and determine what needs to be persisted.

## Step 1 — Projects touched this session

For each project worked on:
- Read `Claude/Projects/<name>/sessions.md`
- Rewrite **Current Thinking** to reflect the session's progress
- Append a dated line to **Log**: `!`date +%Y-%m-%d` — [what happened]`
- Read `Claude/Projects/<name>/context.md` — update if anything structural changed (stack, location, purpose)

If no projects were touched, skip this step.

## Step 2 — Threads

- If a thread progressed: rewrite Current Thinking, append dated log entry
- If a thread was resolved or should be parked: update its status and remove from Active Threads in INDEX.md

If no threads are relevant, skip this step.

## Step 3 — Rules and preferences

- If a new coding convention, preference, or architectural decision was reached: update the relevant `Claude/` rules file
- If it hasn't fully crystallised yet: append a dated line to `Claude/memory.md`

## Step 4 — INDEX.md

Read `INDEX.md`. Verify:
- Active projects list is accurate — add or remove entries as needed
- Active threads list is accurate

## Step 5 — Nothing to save?

If the session was exploratory or everything is already captured, say so and skip. Not every session needs vault updates.

## Output

Summarise what was updated (or confirm nothing needed updating). List each file that was changed.
