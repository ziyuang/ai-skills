---
name: typescript-verification-before-completion
description: Enforce hard TS/JS completion gates with linting, type checking, tests, and build checks. Use before claiming TypeScript or JavaScript work is complete.
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
- Apply `skills/global/testing-principles/SKILL.md` when creating or reviewing tests.
