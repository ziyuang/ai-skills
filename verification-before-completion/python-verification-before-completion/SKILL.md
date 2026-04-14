---
name: python-verification-before-completion
description: Final Python completion gate with required static and runtime checks before claiming code is complete, fixed, or ready. Use immediately before completion claims. Do not use as a substitute for setup/maintenance workflow guidance.
---

# Python Verification Before Completion

- This skill is a mandatory completion gate after Python code edits and before any claim that work is complete, fixed, or ready.
- No completion claims without fresh command output from the relevant verification commands.
- Run narrow checks first, then full project checks when the narrow checks pass and the repo workflow calls for them.

## Standard gate order
1. `ruff format --check .`
2. `ruff check .`
3. `mypy .`
4. `pytest -q`

## Rules
- At minimum, run the gate on the touched files or the narrowest relevant test target before ending the task.
- If the repository standard is broader than touched-file checks, run the repository-standard commands before claiming completion.
- If a project uses different commands, run its local equivalents.
- If formatting is required to make the gate pass, run the formatter, then rerun the verification commands and report the final clean output.
- If any gate is skipped, state why and state risk.
- If any gate fails, do not claim completion.
- For bug fixes, include or update a regression test.
- Do not merge formatting, refactor, and functional fixes without separate verification evidence.
- Apply `skills/testing-principles/SKILL.md` when creating or reviewing tests.
