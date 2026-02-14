---
name: typescript-tooling-workflow
description: Use a strict TypeScript tooling workflow for environment setup, package management, and fast code search. Use when bootstrapping or maintaining TypeScript projects.
---

# TypeScript Tooling Workflow

1. Pick one package manager per repo (`pnpm`, `npm`, or `yarn`) and never mix.
  - Default bias: `pnpm` unless repo already chose differently.
2. Change dependencies via package-manager commands only.
3. Keep typecheck as a first-class gate (`tsc --noEmit` or project equivalent).
4. Keep lint and tests in the default loop.
5. Prefer `rg` and `rg --files` for search.
