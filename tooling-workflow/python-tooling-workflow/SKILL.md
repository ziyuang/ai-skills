---
name: python-tooling-workflow
description: Use a strict Python tooling workflow for environment setup, dependency management, and fast code search. Use when bootstrapping or maintaining Python projects.
---

# Python Tooling Workflow

1. Detect host OS before activating virtual environment.
  - Windows: `.venv\Scripts\activate`
  - Linux/macOS: `source .venv/bin/activate`
2. Use `uv` for dependency changes (`uv add`, `uv remove`).
3. Do not hand-edit dependency adds/removals in `pyproject.toml`.
4. Prefer `rg` and `rg --files` for search.
5. Run static checks as default gate (`ruff`, `mypy`, tests).
