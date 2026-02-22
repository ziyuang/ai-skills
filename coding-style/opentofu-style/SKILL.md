---
name: opentofu-style
description: OpenTofu/Terraform HCL authoring style for explicit module contracts, stable resource addressing, and reproducible provider/version constraints. Use when writing or reviewing .tf/.tfvars/.hcl infrastructure code. Do not use for command workflow or final completion-gate decisions.
---

# OpenTofu Style

## Authoritative guides
- Terraform style guide: `https://developer.hashicorp.com/terraform/language/style`
- OpenTofu docs: `https://opentofu.org/docs/`

## Required rules
- Keep module layout explicit: `versions.tf`, `providers.tf`, `variables.tf`, `locals.tf`, `main.tf`, `outputs.tf`.
- Define variable `description` and `type` for every input; add `validation` where unsafe input is possible.
- Define `required_version` and pin provider versions with bounded constraints.
- Prefer `for_each` over `count` for resources with identity to keep addresses stable.
- Keep data sources before dependent resources and keep outputs minimal.
- Mark sensitive outputs with `sensitive = true`; never output raw secrets.
- Use `locals` for naming/tag conventions and repeated expressions.
- Avoid broad `depends_on`; use implicit dependency unless ordering is truly non-obvious.
- Keep HCL formatting canonical and deterministic; one argument per line for non-trivial blocks.

## OpenTofu-first command examples
- Format: `tofu fmt -recursive`
- Validate: `tofu validate`
- Plan: `tofu plan`
