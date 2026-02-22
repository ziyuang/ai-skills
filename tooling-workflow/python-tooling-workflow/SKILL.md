---
name: python-tooling-workflow
description: Python tooling workflow for environment setup, dependency management, and fast code search during project setup and maintenance. Use when bootstrapping or maintaining Python projects. Do not use as the final completion gate before claiming code is complete (use python-verification-before-completion).
---

# Python Tooling Workflow

* Detect host OS before activating virtual environment.
  - Windows: `.venv\Scripts\activate`
  - Linux/macOS: `source .venv/bin/activate`
* Use `uv` for dependency changes (`uv add`, `uv remove`).
* Do not hand-edit dependency adds/removals in `pyproject.toml`.
* Run static checks as default gate (`ruff`, `mypy`, tests).
