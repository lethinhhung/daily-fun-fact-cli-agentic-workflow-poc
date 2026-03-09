# Command: `workflow code`

## Purpose

Generate project source code, tests, and package configuration from the derived specs. Translates specifications into a runnable project scaffold.

## Input

- `derived-spec/*` — the derived specification files produced by `workflow init`.

## Output

- `src/` — source code files (placeholder implementations)
- `tests/` — test files matching the test cases in `derived-spec/tests.md`
- `package.json` — project manifest with name, version, scripts, and dependencies

## Behavior

1. Verify `derived-spec/` exists and contains the expected files.
2. Read each derived spec file.
3. Generate `src/` with placeholder module files based on `derived-spec/architecture.md`.
4. Generate `tests/` with placeholder test files based on `derived-spec/tests.md`.
5. Generate `package.json` based on `derived-spec/implementation.md`.
6. Print a summary of generated files to stdout.

## Error Handling

- Exit with error if `derived-spec/` does not exist (run `workflow init` first).
- Exit with error if `src/` or `tests/` already exist (use `--force` to overwrite).

## Example

```
$ workflow code
✓ Read derived-spec/architecture.md
✓ Read derived-spec/implementation.md
✓ Read derived-spec/tests.md
✓ Generated src/index.ts
✓ Generated tests/index.test.ts
✓ Generated package.json
Code generation complete — 3 files generated.
```
