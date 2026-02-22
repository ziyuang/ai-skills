---
name: typescript-verification-before-completion
description: Final TS/JS completion gate with required lint, typecheck, tests, and build evidence before claiming work is complete. Use immediately before completion claims. Do not use as a substitute for setup/maintenance workflow guidance.
---

# TypeScript Verification Before Completion

- No completion claims without fresh command output.
- Run targeted checks first, then full checks.

## Standard gate order
1. Lint: `npm run lint` or `pnpm lint` or `yarn lint`
2. Typecheck: `npm run typecheck` or `pnpm typecheck` or `npx tsc --noEmit`
3. Tests: `npm test` or `pnpm test` or project test command
4. Build: `npm run build` or `pnpm build` when build artifacts are part of the change

## Rules
- Use the package manager already used by the repo.
- If a gate is unavailable, run the closest equivalent and state it.
- If any gate fails, do not claim completion.
- For bug fixes, add or update regression coverage.
- Do not claim success from lint-only output when typecheck or tests were not executed.
- Apply `skills/testing-principles/SKILL.md` when creating or reviewing tests.
