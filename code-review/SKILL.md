---
name: code-review
description: Severity-first code review across languages focused on correctness, regressions, data safety, and unnecessary abstraction. Use when the user asks for a review or to audit a diff/PR. Do not use as the primary writing/style guide.
---

# Code Review First Principles

## Posture
- Findings first. Summary second.
- Prioritize correctness, data safety, and regressions over style nits.
- Reject complexity that does not buy immediate value.
- Treat "future-proofing" as a smell unless tied to current requirements.

## Finding format
- `Severity`: critical | important | minor
- `Where`: exact file and function
- `Why`: concrete failure mode
- `Fix direction`: smallest safe correction

## Checklist
1. Which invariant is now explicit?
2. Is boundary validation/error handling in the right layer?
3. Can a layer/helper/abstraction be deleted?
4. What smallest input breaks this change?
5. Is there regression coverage for that failure mode?
6. Are language escape hatches (`Any`, `any`, casts/assertions) justified and contained?

## Forbidden review behavior
- Do not block on preference when behavior is correct.
- Do not hide critical findings behind polite noise.
- Do not request abstractions without present pressure.
