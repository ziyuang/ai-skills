---
name: opentofu-verification-before-completion
description: Enforce hard OpenTofu completion gates with fmt, init, validate, and plan evidence before claiming infrastructure changes are complete.
---

# OpenTofu Verification Before Completion

- No completion claims without fresh command output.
- Run targeted checks first, then full environment checks.

## Standard gate order
1. `tofu fmt -check -recursive`
2. `tofu init` (or `tofu init -backend=false` for module-only/offline validation)
3. `tofu validate`
4. `tofu plan -out=tfplan` (or environment-specific equivalent)

## Rules
- If any gate fails, do not claim completion.
- If `plan` cannot run (credentials/backend/policy), state the exact blocker and residual risk.
- For production-impacting changes, require plan evidence for each affected environment.
- Do not run `apply`/`destroy` without explicit user instruction.
- Delete stale `tfplan` artifacts when they are no longer needed.

