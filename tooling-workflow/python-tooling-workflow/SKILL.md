---
name: python-tooling-workflow
description: Python tooling workflow for environment setup, dependency management, and fast code search during project setup and maintenance. Use when bootstrapping or maintaining Python projects. Do not use as the final completion gate before claiming code is complete (use python-verification-before-completion).
---

# Python Tooling Workflow

* If you need to activate the virtual environment, detect host OS first.
  - Windows: `.venv\Scripts\activate`
  - Linux/macOS: `source .venv/bin/activate`
* Use `uv` as the project command runner and dependency manager.
  - For dependency changes, use `uv add` and `uv remove`. Do not use `pip`.
  - To execute Python commands, use `uv run` (`uv run python`, `uv run pytest`, `uv run ruff`). Do not invoke bare `python` for project commands.
  - Do not hand-edit dependency adds/removals in `pyproject.toml`.
* Run static checks as default gate (`ruff`, `mypy`, tests).
