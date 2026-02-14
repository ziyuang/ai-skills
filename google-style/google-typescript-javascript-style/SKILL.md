---
name: google-typescript-javascript-style
description: Apply Google JavaScript and TypeScript style guidance with strict type and module discipline. Use when writing or reviewing TS/JS for style, naming, docs, and static safety.
---

# Google TypeScript + JavaScript Style

## Authoritative guides
- JavaScript style guide: `https://google.github.io/styleguide/jsguide.html`
- TypeScript style guide: `https://google.github.io/styleguide/tsguide.html`

## Required rules
- Follow Google naming, import, and file-organization conventions.
- Favor explicit types at module boundaries.
- Avoid implicit `any` and hidden coercions.
- Keep functions focused and predictable.
- Use constants for special states; avoid magic literals.

## Type safety baseline
- Prefer `strict` TypeScript configuration.
- Prefer `unknown` over `any` at uncertain boundaries, then narrow.
- Use discriminated unions for stateful flows.
- Keep runtime validation at trust boundaries.
