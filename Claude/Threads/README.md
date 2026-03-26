# Threads

Persistent discussion threads across sessions. Each file is a living document — Current Thinking is rewritten as the discussion evolves, Log is append-only.

## File shape

```
---
type: discussion | idea | learning
status: active | parked | resolved | evolved
---

# Title

## Current Thinking
[Living summary — rewritten, not appended]

## Log
YYYY-MM-DD — one-line entry, newest first
```

## When to start a thread

A thread is for ongoing thinking that spans multiple sessions — an idea you're exploring, a decision you're working through, something you're learning. It is not a task list or a project plan.

Use `/thread-start <name>` to create a new thread.

## Evolution types

When a thread matures into something more concrete, use `/thread-evolve`:

| What it's become | What gets created |
|---|---|
| A project | `Claude/Projects/<name>/` scaffold (context.md, sessions.md) + index updates |
| New language/framework area | `Claude/Style/<lang>.md` rules file + `Claude/Index.md` update |
| General principle or preference | Entry moved into relevant `Claude/` rules file, thread closed |
| Reference material | Saved elsewhere (docs, notes), thread closed |

This list is not exhaustive — use judgement and ask clarifying questions when the evolution type is unclear.

## Thread lifecycle

1. **active** — being discussed across sessions
2. **parked** — paused, may resume
3. **resolved** — answered or decided, no longer needs discussion
4. **evolved** — matured into a project, rule, or reference; thread is closed
