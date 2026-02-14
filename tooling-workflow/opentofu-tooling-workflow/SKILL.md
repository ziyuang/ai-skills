---
name: opentofu-tooling-workflow
description: Use a strict OpenTofu workflow for initialization, formatting, validation, and planning with safe state handling. Use when bootstrapping or maintaining OpenTofu/Terraform infrastructure repositories.
---

# OpenTofu Tooling Workflow

1. Prefer `tofu` commands by default; use `terraform` only when the repo explicitly standardizes on it.
2. Run `tofu init` after provider/module/backend changes.
3. Keep formatting in the normal loop: `tofu fmt -recursive`.
4. Validate before planning: `tofu validate`.
5. Generate plans before apply and keep plan review explicit: `tofu plan -out=tfplan`.
6. Use remote state with locking for shared environments; do not rely on local state for team workflows.
7. Keep environment separation explicit (separate directories, workspaces, or var-files); do not mix patterns silently.
8. Prefer `rg` and `rg --files` for repository search.

