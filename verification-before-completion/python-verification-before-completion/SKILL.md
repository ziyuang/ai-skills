---
name: python-verification-before-completion
description: Final Python completion gate with required static and runtime checks before claiming code is complete, fixed, or ready. Use immediately before completion claims. Do not use as a substitute for setup/maintenance workflow guidance.
---

# Python Verification Before Completion

- No completion claims without fresh command output.
- Run narrow checks first, then full project checks.

## Standard gate order
1. `ruff format --check .`
2. `ruff check .`
3. `mypy .`
4. `pytest -q`

## Rules
- If a project uses different commands, run its local equivalents.
- If any gate is skipped, state why and state risk.
- If any gate fails, do not claim completion.
- For bug fixes, include or update a regression test.
- Do not merge formatting, refactor, and functional fixes without separate verification evidence.
- Apply `skills/testing-principles/SKILL.md` when creating or reviewing tests.
