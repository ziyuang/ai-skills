---
name: python-tooling-workflow
description: Use a strict Python tooling workflow for environment setup, dependency management, and fast code search. Use when bootstrapping or maintaining Python projects.
---

# Python Tooling Workflow

* Detect host OS before activating virtual environment.
  - Windows: `.venv\Scripts\activate`
  - Linux/macOS: `source .venv/bin/activate`
* Use `uv` for dependency changes (`uv add`, `uv remove`).
* Do not hand-edit dependency adds/removals in `pyproject.toml`.
* Run static checks as default gate (`ruff`, `mypy`, tests).
