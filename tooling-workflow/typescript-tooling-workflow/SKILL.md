---
name: typescript-tooling-workflow
description: TypeScript tooling workflow for environment setup, package management, running linters/formatters, and repo maintenance. Use when bootstrapping, maintaining, or running TypeScript project tooling (npm/pnpm/yarn, tsc, eslint, prettier, etc.). Do not use as the final completion gate before claiming code is complete (use typescript-verification-before-completion).
---

# TypeScript Tooling Workflow

## Detect the package manager first
- Check lock files to determine which package manager the repo uses:
  - `pnpm-lock.yaml` → use `pnpm`
  - `yarn.lock` → use `yarn`
  - `package-lock.json` → use `npm`
- Default bias when no lock file exists: `pnpm`.
- Never mix package managers within a single repo.

## Bootstrap and install
- If `node_modules` is missing or outdated, install dependencies first:
  - `pnpm install` / `npm install` / `yarn install`
- Change dependencies via package-manager commands only:
  - `pnpm add <pkg>` / `pnpm remove <pkg>`
  - `npm install <pkg>` / `npm uninstall <pkg>`
  - Do not hand-edit `package.json` dependency versions for installs.
- When adding dependencies, do not pin versions unless the repo already pins them.

## Running tools
- Run scripts through the package manager: `pnpm run <script>`, `npm run <script>`, `yarn <script>`.
- For one-off TypeScript execution (not a build): `pnpm exec tsx <file>` or `npx tsx <file>`.
- Run typecheck without emitting: `pnpm exec tsc --noEmit` or the project's `typecheck` script.
- Run lint: `pnpm run lint` or `pnpm exec eslint <file>`.
- Run formatter: `pnpm run format` or `pnpm exec prettier --write <file>`.
- Run tests: `pnpm test` or the project's test script.
- Prefer `rg` and `rg --files` for searching the repo.

## Gates
- Keep typecheck as a first-class gate; never skip it.
- Keep lint and tests in the default loop.
- Do not install global CLI tools (`npm install -g`) unless there is no other option.
