---
name: typescript-javascript-style
description: Google JavaScript and TypeScript style guidance with strict type and module discipline. Use when writing, editing, or reviewing TypeScript or JavaScript code — pair with readable-clean-code and apply after it. Workspace skills override only when they explicitly state an override.
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

## Imports and modules
- Use named exports over default exports for modules with more than one export.
- Avoid barrel (`index.ts`) re-exports that obscure the real source; use them only at stable public API surfaces.
- Keep import order consistent: external packages first, then internal modules, then relative paths. Use the project's lint rules to enforce order.
- Use ES module syntax (`import`/`export`) exclusively; never mix with CommonJS (`require`/`module.exports`).

## Async patterns
- Prefer `async`/`await` over `.then()`/`.catch()` chains.
- Always `await` or explicitly ignore promises; never let floating promises silently discard errors.
- Prefer `Promise.all` for independent concurrent async calls; avoid sequential `await` when parallelism is possible.
- Do not swallow errors in `catch` blocks; handle or re-throw.

## Null and undefined
- Prefer `undefined` over `null` for optional values in new code.
- Never use `null` and `undefined` interchangeably; be explicit about which one a function returns.
- Avoid optional chaining (`?.`) as a way to mask required presence; if a value must exist, assert it.

## File organization
- Use `kebab-case` for file names.
- One primary export per file is a good signal; multiple tightly-coupled exports are acceptable in the same file.
- Keep test files adjacent to the code they test (`foo.ts` / `foo.test.ts`) unless the project already uses a `__tests__` convention.

## Type safety baseline
- Prefer `strict` TypeScript configuration.
- Prefer `unknown` over `any` at uncertain boundaries, then narrow.
- Use discriminated unions for stateful flows.
- Avoid free-form string keys when the key set is fixed; model fixed-key data with interfaces or other typed object shapes.
- Keep runtime validation at trust boundaries.
