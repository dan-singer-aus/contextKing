---
name: thread-evolve
description: Evolve a matured thread into its next form — a project, rules file, KB entry, or something else. Identifies the evolution type, asks clarifying questions, then executes.
argument-hint: [thread-name]
allowed-tools: Read, Write, Edit, Glob, Grep, AskUserQuestion
effort: high
---

Evolve the thread at `Claude/Threads/$0.md` into its proper permanent home.

If no argument was provided, list active threads and ask the user which one.

## Step 1 — Read and assess

Read `Claude/Threads/$0.md`. Determine what the thread has become:

| What it's become | What to create |
|---|---|
| A project | `Claude/Projects/<name>/` scaffold + INDEX.md entry |
| A new language or style area | `Claude/Style/<area>.md` rules file |
| A general principle or preference | Entry in the relevant `Claude/` rules file |
| Reference material | Entry in the knowledge base (wherever the user keeps one) |

This list is not exhaustive — use judgement.

## Step 2 — Confirm evolution type

Tell the user what you think the thread has become and why. Ask them to confirm or correct.

## Step 3 — Clarifying questions

Ask targeted questions based on the evolution type. Don't dump all questions at once — ask the most important ones first, follow up if needed.

### If evolving into a project

- Where does (or will) the project live on disk?
- Does the project have (or will it have) its own `CLAUDE.md` or `AGENTS.md`? (This determines how detailed `context.md` needs to be.)
- Is this active development or a reference codebase?
- What's the stack? (May already be clear from the thread.)
- Anything that should go into `sessions.md` right away — current status, known issues, next steps?

### If evolving into rules or preferences

- Which existing rules file does this belong in, or does it need a new one?
- Is this a hard rule or a preference?

### If evolving into KB material

- Where in your knowledge base does this fit?
- Is this a new entry or an addition to an existing one?

### If evolving into something else

- Ask what the user has in mind and work from there.

## Step 4 — Execute

Create/edit files based on the answers. Follow existing conventions:
- For projects: read `Claude/Projects/README.md` for the active vs reference patterns.
- For rules: match the style of the target file.

## Step 5 — Clean up

- Set the thread's frontmatter to `status: evolved`
- Add a note at the top of Current Thinking pointing to where the content landed
- Append a dated log entry: `YYYY-MM-DD — evolved into [destination]`
- Remove the thread from **Active Threads** in `INDEX.md`
- Remove any related entries from `Claude/memory.md`

## Step 6 — Verify indexes

Read `Claude/Index.md` and `INDEX.md`. Update both if the new content should be referenced.
