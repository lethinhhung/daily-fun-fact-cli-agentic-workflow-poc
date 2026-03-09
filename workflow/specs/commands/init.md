# Command: `workflow init`

## Purpose

Generate derived specs from the core spec. This bootstraps the project by producing structured specification files that downstream commands (`code`, `feature`, `debug`) consume.

## Input

- `specs/core-spec.md` — the single source of truth for project requirements.

## Output

Creates a `derived-spec/` directory containing:

- `architecture.md` — high-level architecture and module breakdown
- `implementation.md` — implementation plan with steps and dependencies
- `tests.md` — test cases derived from the requirements

## Behavior

1. Read `specs/core-spec.md`.
2. Parse project name, goal, requirements, and testing sections.
3. Generate each derived spec file with placeholder content based on the parsed data.
4. Write files to `derived-spec/`.
5. Print a summary of generated files to stdout.

## Error Handling

- Exit with error if `specs/core-spec.md` does not exist.
- Exit with error if `derived-spec/` already exists (use `--force` to overwrite).

## Example

```
$ workflow init
✓ Read specs/core-spec.md
✓ Generated derived-spec/architecture.md
✓ Generated derived-spec/implementation.md
✓ Generated derived-spec/tests.md
Init complete — 3 files generated.
```
