---
name: testing-principles
description: Behavior-first test design that proves real behavior and catches invalid states early. Use when writing or reviewing tests across Python/TypeScript/JavaScript, especially for bug fixes and regression coverage. Do not use as a substitute for lint/typecheck/build/runtime verification gates.
---

# Testing Principles

## What tests must prove
1. Coverage is meaningful: core paths, edge paths, and failure paths are exercised.
2. Keep tests small and atomic, but run through realistic unit-level execution paths (not toy-only cases).
3. Invalid states fail loudly, with state origin understood and legality made explicit.

## Test design rules
- Do not write tests just to increase test count.
- Model production-like inputs and transitions where possible.
- Keep pass conditions tied to real invariants, not helper-only internals.
- For bug fixes, assert the failure first, then assert the corrected behavior.

## Illegal-state discipline
- If a value or state is unexpected (examples: `null`/`None`/`undefined`), stop and ask why it is legal.
- Trace unexpected state to its source before changing behavior.
- Do not add arbitrary or permissive branches only to make tests pass.
- Encode legality explicitly: if illegal, fail; if legal, type/validate and test both paths.

## Anti-patterns
- Assertions that only mirror mock setup and do not verify outcomes.
- Tests that pass because of fallback defaults masking bad state.
- Broad try/catch in tests that hides real failures.
