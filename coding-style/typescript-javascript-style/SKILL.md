---
name: typescript-javascript-style
description: Apply Google JavaScript and TypeScript style guidance with strict type and module discipline. Use when writing or reviewing TS/JS code for language-specific conventions (imports/modules), type safety (avoid implicit any/coercions), and boundary typing. Combine with readable-clean-code for cross-language readability tie-breakers.
---

# Google TypeScript + JavaScript Style

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
