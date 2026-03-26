# Style Rules

One file per language or framework area. Claude reads the relevant file when working in that area.

## File naming

Use lowercase, hyphen-separated names that match what Claude would search for:
- `typescript.md`
- `typescript-react.md`
- `python.md`
- `go.md`

## File structure

Each style file should cover the rules Claude needs to apply code — not philosophy or rationale (those belong in a human-readable guide). Keep rules concrete and actionable.

Suggested sections:
- **Core rules** — the non-negotiables
- **Naming** — variables, files, functions, types
- **Imports / exports** — how to organise them
- **Error handling** — how to handle and propagate errors
- **Comments** — when and how to comment

## Register in the index

After creating a new style file, add a row to `Claude/Index.md` so Claude knows when to load it.

## Example

See `example.md` in this directory for a minimal example of the file structure.
