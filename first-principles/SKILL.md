---
name: first-principles
description: Fallback first-principles engineering guardrails for Python/TypeScript/JavaScript when correctness, simplicity, and explicit invariants need to be re-established. Use when no more specific skill fits or when design constraints are unclear. Do not use instead of specialized skills such as debugging, testing, error-handling, style, tooling, or verification gates.
---

# Engineering First Principles

## Non-negotiables
- Correctness first. Performance second. Pretty last.
- Keep code obvious. If it needs a paragraph to explain, rewrite it.
- Encode invariants in code (types, asserts, guards, constraints), not prose.
- Prefer deletion over abstraction. Every new layer must pay rent immediately.

## Control and data
- Prefer early returns to nested branches.
- If a condition is hard to parse, name it.
- Do not encode state machines in loose booleans.
- Keep functions single-purpose and data-shape focused.

## Error model
- Validate and sanitize at boundaries.
- In core logic, fail fast on impossible states.
- Catch only what you can repair or translate.

## Banned moves
- No speculative abstractions for future use.
- No magic sentinels for domain meaning.
- No broad exception swallowing.
- No micro-optimization without measurement.

## Review pressure
- If complexity increases, remove larger complexity elsewhere.
- If no invariant is added or clarified, the change is suspect.
