---
name: error-handling
description: Apply boundary-first error handling with fail-fast core logic across languages. Use when designing exceptions/errors, retries, translation layers, and operational failure paths.
---

# Error Handling First Principles

## Core model
- Validate and handle expected failures at boundaries; fail fast inside core logic.
- Return/raise errors for user/input/environment failures.
- Assert/crash on programmer-bug impossible states.

## Rules
- Catch only errors you can repair or translate.
- Preserve causality when translating errors.
- Keep one owner for retry policy; avoid stacked retries.
- Do not log-and-raise in the same layer.
- Keep error messages machine-usable and developer-actionable.

## Boundary checklist
1. Validate external input once.
2. Convert to internal typed/domain form early.
3. Handle transport/storage failures at boundary adapters.
4. Keep core logic free of transport/storage exception noise.

## Anti-patterns
- Bare `except Exception` / blanket `catch (e)`.
- Silent failure (`pass`, ignored promise rejection).
- Retrying non-idempotent writes blindly.
- Converting all failures to generic "unknown error."
