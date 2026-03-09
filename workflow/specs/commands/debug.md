# Command: `workflow debug`

## Purpose

Debug failing code or tests. Analyzes the provided error, proposes a fix, updates source code, and re-runs tests.

## Input

- An error description or failing test name passed as a CLI argument.

## Behavior

1. Validate that an error description is provided.
2. Verify `src/` and `tests/` exist.
3. **Analyze** — Print the error and identify the likely source file and line.
4. **Fix** — Apply a placeholder fix to the identified source file.
5. **Verify** — Simulate re-running tests and print results.
6. Print a summary of the debug session to stdout.

## Error Handling

- Exit with error if no error description is provided.
- Exit with error if project has not been scaffolded (`src/` missing).

## Example

```
$ workflow debug "TypeError: getFact is not a function"
→ Analyzing: "TypeError: getFact is not a function"
→ Likely source: src/index.ts
→ Applying fix...
✓ Updated src/index.ts
→ Re-running tests...
✓ All tests passed.
Debug complete.
```
