---
name: curated-dev-skills
description: Top-level navigation index for a curated collection of opinionated software engineering skills. Use this skill to identify the right nested skill by category, then load that skill directly. Do not use this file as a source bibliography; SOURCES.md serves that purpose.
---

# Global Skills Index

This file is the navigation index for the repository.

Use `SOURCES.md` for provenance and upstream references.
Use the nested `SKILL.md` files for the actual instructions.

## Cross-cutting skills
- `code-review`: Severity-first review focused on correctness, regressions, data safety, and unnecessary abstraction.
  Path: `code-review/SKILL.md`
- `error-handling`: Boundary-first error handling with fail-fast core logic.
  Path: `error-handling/SKILL.md`
- `first-principles`: Fallback engineering guardrails when invariants, simplicity, or correctness need to be re-established.
  Path: `first-principles/SKILL.md`
- `systematic-debugging`: Evidence-driven debugging with root-cause isolation before patching.
  Path: `systematic-debugging/SKILL.md`
- `testing-principles`: Behavior-first test design for regression coverage and invalid-state detection.
  Path: `testing-principles/SKILL.md`
- `postgresql-table-design`: PostgreSQL schema and migration design with explicit constraints and safety.
  Path: `postgresql-table-design/SKILL.md`

## Coding style skills
- `readable-clean-code`: Primary cross-language readability and simplicity baseline. Apply first before language-specific style skills.
  Path: `coding-style/readable-clean-code/SKILL.md`
- `python-style`: Google Python style and typing discipline. Use when writing Python — pair with `readable-clean-code`.
  Path: `coding-style/python-style/SKILL.md`
- `typescript-javascript-style`: Google TypeScript/JavaScript style with strict type and module discipline. Use when writing TS/JS — pair with `readable-clean-code`.
  Path: `coding-style/typescript-javascript-style/SKILL.md`
- `opentofu-style`: OpenTofu/Terraform HCL authoring style for explicit contracts and stable resource addressing.
  Path: `coding-style/opentofu-style/SKILL.md`

## Tooling workflow skills
- `python-tooling-workflow`: Python environment, dependency, linter/formatter, and repo-maintenance workflow (uv, pip, ruff, mypy, pytest).
  Path: `tooling-workflow/python-tooling-workflow/SKILL.md`
- `typescript-tooling-workflow`: TypeScript environment, package manager, linter/formatter, and repo-maintenance workflow (npm/pnpm, tsc, eslint, prettier).
  Path: `tooling-workflow/typescript-tooling-workflow/SKILL.md`
- `opentofu-tooling-workflow`: OpenTofu/Terraform day-to-day operations — init, fmt, validate, plan, apply, state.
  Path: `tooling-workflow/opentofu-tooling-workflow/SKILL.md`

## Verification-before-completion skills
- `python-verification-before-completion`: Final Python gate — use when code is described as done, fixed, or ready to commit/deploy.
  Path: `verification-before-completion/python-verification-before-completion/SKILL.md`
- `typescript-verification-before-completion`: Final TS/JS gate (lint + typecheck + tests + build) — use when code is described as done, fixed, or ready to commit/deploy.
  Path: `verification-before-completion/typescript-verification-before-completion/SKILL.md`
- `opentofu-verification-before-completion`: Final OpenTofu/Terraform gate (fmt/init/validate/plan) — use when infra changes are described as done or ready to apply.
  Path: `verification-before-completion/opentofu-verification-before-completion/SKILL.md`

## Selection rules
- Start with the most specific skill that matches the task.
- For Python or TypeScript style work, apply `readable-clean-code` before the language-specific style skill.
- Use tooling workflow skills for setup and day-to-day repository operations.
- Use verification-before-completion skills only as final gates, not as substitutes for workflow or implementation guidance.
- Use `first-principles` only when no more specific skill fits or when constraints are unclear.
