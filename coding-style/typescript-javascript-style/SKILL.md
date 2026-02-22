---
name: typescript-javascript-style
description: Google JavaScript and TypeScript style guidance with strict type and module discipline. Use after readable-clean-code when TS/JS-specific conventions (imports/modules), type safety, and boundary typing constraints are required. Keep this skill complementary to readable-clean-code; workspace skills override only when they explicitly state an override.
---

# Google TypeScript + JavaScript Style

## Precedence contract
1. Apply `readable-clean-code` first for the general readability/simplicity baseline.
2. Apply this skill second for TypeScript/JavaScript-specific conventions and typing constraints.
3. If a workspace skill explicitly states it overrides a rule here, follow the explicit override; otherwise keep this skill in effect.

## Authoritative guides
- JavaScript style guide: `https://google.github.io/styleguide/jsguide.html`
- TypeScript style guide: `https://google.github.io/styleguide/tsguide.html`

## Required rules
- Follow Google naming, import, and file-organization conventions.
- Favor explicit types at module boundaries.
- Avoid implicit `any` and hidden coercions.
- Do not use `if (!...) ... else ...`; prefer positive conditions with `if (...) ... else ...`.
- Keep functions focused and predictable.
- Use constants for special states; avoid magic literals.

## Type safety baseline
- Prefer `strict` TypeScript configuration.
- Prefer `unknown` over `any` at uncertain boundaries, then narrow.
- Use discriminated unions for stateful flows.
- Avoid free-form string keys when the key set is fixed; model fixed-key data with interfaces or other typed object shapes.
- Keep runtime validation at trust boundaries.
