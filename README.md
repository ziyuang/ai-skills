# curated-dev-skills

A curated collection of opinionated software engineering skills for AI coding agents. Covers code review, testing, debugging, error handling, language style guides, tooling workflows, and pre-completion verification gates.

## Install

```sh
# Install all skills
npx skills add <owner>/<repo>

# List available skills without installing
npx skills add <owner>/<repo> --list

# Install specific skills
npx skills add <owner>/<repo> --skill code-review
npx skills add <owner>/<repo> --skill testing-principles
```

## Available skills

### Cross-cutting

| Skill | Description |
|-------|-------------|
| `code-review` | Severity-first review focused on correctness, regressions, data safety, and unnecessary abstraction |
| `error-handling` | Boundary-first error handling with fail-fast core logic |
| `first-principles` | Fallback engineering guardrails when invariants, simplicity, or correctness need re-establishing |
| `systematic-debugging` | Evidence-driven debugging with root-cause isolation before patching |
| `testing-principles` | Behavior-first test design for regression coverage and invalid-state detection |
| `postgresql-table-design` | PostgreSQL schema and migration design with explicit constraints and safety |

### Coding style

| Skill | Description |
|-------|-------------|
| `readable-clean-code` | Cross-language readability and simplicity baseline — apply before language-specific style skills |
| `python-style` | Google Python style and typing discipline |
| `typescript-javascript-style` | Google TypeScript/JavaScript style with strict type and module discipline |
| `opentofu-style` | OpenTofu/Terraform HCL authoring style for explicit contracts and stable resource addressing |

### Tooling workflow

| Skill | Description |
|-------|-------------|
| `python-tooling-workflow` | Python environment setup, dependency management, and repo-maintenance workflow |
| `typescript-tooling-workflow` | TypeScript environment, package manager, and repo-maintenance workflow |
| `opentofu-tooling-workflow` | OpenTofu initialization, formatting, validation, planning, and state-handling workflow |

### Verification before completion

| Skill | Description |
|-------|-------------|
| `python-verification-before-completion` | Final Python completion gate — run before claiming code is done |
| `typescript-verification-before-completion` | Final TypeScript/JavaScript completion gate — lint, typecheck, tests, build |
| `opentofu-verification-before-completion` | Final OpenTofu/Terraform completion gate — fmt/init/validate/plan |

## Curation principles

- Simplicity over abstraction
- Correctness before performance
- Explicit invariants, boundary-only error handling, and hard verification gates
- No speculative complexity

See [`SOURCES.md`](SOURCES.md) for full provenance and upstream references.
