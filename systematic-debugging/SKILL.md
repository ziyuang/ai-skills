---
name: systematic-debugging
description: Evidence-driven debugging with root-cause isolation before patching. Use for Python/TypeScript/JavaScript when failures, flaky behavior, or regressions appear and the cause is unknown. Do not use for feature implementation when there is no observed failure.
---

# Systematic Debugging First Principles

## Phase gates
1. Reproduce with a stable command.
2. Capture evidence (inputs, env, trace/logs, relevant diff).
3. State expected invariant and exact break point.
4. Isolate boundary and test one hypothesis at a time.
5. Apply smallest root-cause fix.
6. Verify with targeted checks + regression coverage.

## Rules
- No repro, no fix claim.
- No multi-change guess patches.
- No symptom-only patches.
- If you cannot verify, say so and stop claiming success.

## Red flags
- "Should work now."
- "Could not reproduce, but fixed."
- "Refactored while debugging."
