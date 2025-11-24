# Copilot instructions for this repository

This repository is a **uv-based Python CLI template**.

- Main entrypoint: `bin/script.py`
- CLI uses `docopt` to parse arguments.
- Current flags: `--debug` and `--verbose`
- Tests live under `tests/` and use `pytest`.

## Environment and setup

- Use Python 3.12+.
- Use `uv` for dependency management and execution.

### Basic commands

- Install dependencies: `uv sync`
- Run tests: `uv run pytest -q`
- Run the CLI (normal): `uv run python bin/script.py`
- Run the CLI (debug): `uv run python bin/script.py --debug`
- Run the CLI (verbose): `uv run python bin/script.py --verbose`

When you propose changes that require running code or tests, prefer these commands.

## Project structure expectations

- Keep the main CLI entrypoint at `bin/script.py`.
- Add new library code under a dedicated package (for example: `src/p6_crapys_py/` or `p6_crapys_py/`) rather than expanding `bin/script.py` into a monolith.
- Keep tests in `tests/` and mirror the structure of the code under test.

## Coding style and conventions

- Use **type hints** everywhere (functions, return types, module-level constants where appropriate).
- Prefer small, pure functions that are easy to test.
- Avoid side effects at import time; keep logic inside functions.
- Log via the standard library `logging` module, not `print`, except in very small, clearly intentional places.

## How to modify the CLI

- The `__doc__` string in `bin/script.py` defines the CLI usage for `docopt`.
- When adding or changing CLI options:
  - Update the `Usage:` and `Options:` sections in `__doc__`.
  - Keep the behavior in `main()` in sync with the docstring.
  - Add or update tests that cover new options or behaviors.

## Tests and quality

- For any non-trivial change, add or update tests in `tests/`.
- Keep tests:
  - Fast
  - Deterministic
  - Focused on behavior, not implementation details
- Use `pytest` idioms (fixtures, parametrization) instead of inventing custom test harnesses.

## What **not** to do by default

- Do **not** introduce new dependencies unless necessary. If you must, favor well-known, maintained libraries.
- Do **not** change existing public CLI flags without updating docs and tests.
- Do **not** reformat the entire repo just to satisfy a style preference; keep diffs minimal and focused.

## Pull request behavior

When drafting PRs or suggested changes:

- Explain in plain language what you changed and why.
- Include any new or updated commands that a human should run to verify the changes.
- If you touch tests, mention how coverage or behavior improved.
