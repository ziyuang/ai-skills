---
name: testing-principles
description: Design tests that prove real behavior and catch invalid states early. Use when writing or reviewing tests across Python, TypeScript, and JavaScript.
---

# Testing Principles

## What tests must prove
1. Coverage is meaningful: core paths, edge paths, and failure paths are exercised.
2. Behavior works in realistic execution paths, not toy-only cases.
3. Invalid states fail loudly; they must not pass silently.

## Test design rules
- Do not write tests just to increase test count.
- Model production-like inputs and transitions where possible.
- Keep pass conditions tied to real invariants, not helper-only internals.
- For bug fixes, assert the failure first, then assert the corrected behavior.

## Illegal-state discipline
- If a value or state is unexpected (examples: `null`/`None`/`undefined`), stop and ask why it is legal.
- Do not add permissive branches only to make tests pass.
- Encode legality explicitly: if illegal, fail; if legal, type/validate and test both paths.

## Anti-patterns
- Assertions that only mirror mock setup and do not verify outcomes.
- Tests that pass because of fallback defaults masking bad state.
- Broad try/catch in tests that hides real failures.
