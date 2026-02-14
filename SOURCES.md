# Global Skill Sources

Last refreshed: February 14, 2026.

Use this file as the source manifest for your global skills directory.

## Curation principles
- Simplicity over abstraction.
- Correctness before performance tuning.
- Explicit invariants, boundary-only error handling, and hard verification gates.
- No speculative complexity and no performative process language.

## Official language style guides (primary)
- Google Python Style Guide: https://google.github.io/styleguide/pyguide.html
- Google JavaScript Style Guide: https://google.github.io/styleguide/jsguide.html
- Google TypeScript Style Guide: https://google.github.io/styleguide/tsguide.html

## Official IaC guides (primary)
- Terraform style guide: https://developer.hashicorp.com/terraform/language/style
- OpenTofu docs: https://opentofu.org/docs/

## Local coding-style skill locations
- `coding-style/python-style/SKILL.md`
- `coding-style/typescript-javascript-style/SKILL.md`
- `coding-style/opentofu-style/SKILL.md`

## Local IaC tooling + verification skill locations
- `tooling-workflow/opentofu-tooling-workflow/SKILL.md`
- `verification-before-completion/opentofu-verification-before-completion/SKILL.md`

## Inspirations from skills.sh
- `verification-before-completion` (obra/superpowers): https://skills.sh/obra/superpowers/verification-before-completion
- `systematic-debugging` (obra/superpowers): https://skills.sh/obra/superpowers/systematic-debugging
- `test-driven-development` (obra/superpowers): https://skills.sh/obra/superpowers/test-driven-development
- `requesting-code-review` (obra/superpowers): https://skills.sh/obra/superpowers/requesting-code-review
- `receiving-code-review` (obra/superpowers): https://skills.sh/obra/superpowers/receiving-code-review
- `typescript-review` (metabase/metabase): https://skills.sh/metabase/metabase/typescript-review
- `python-type-safety` (wshobson/agents): https://skills.sh/wshobson/agents/python-type-safety
- `python-design-patterns` (wshobson/agents): https://skills.sh/wshobson/agents/python-design-patterns
- `python-anti-patterns` (wshobson/agents): https://skills.sh/wshobson/agents/python-anti-patterns
- `postgresql-table-design` (wshobson/agents): https://skills.sh/wshobson/agents/postgresql-table-design
- `code-review-excellence` (wshobson/agents): https://skills.sh/wshobson/agents/code-review-excellence
- `debugging-strategies` (wshobson/agents): https://skills.sh/wshobson/agents/debugging-strategies
- `error-handling-patterns` (wshobson/agents): https://skills.sh/wshobson/agents/error-handling-patterns

## Inspirations from skillsmp (API-backed)
- API endpoint used: `GET /api/v1/categories/development/skills`
- Query themes used:
  - `python-code-style`
  - `python-error-handling`
  - `python-testing-patterns`
  - `typescript`
  - `typescript-review`
  - `lint-typecheck`
  - `verification-before-completion`
  - `systematic-debugging`
  - `code-reviewer`
  - `python-anti-patterns`
  - `error-handling-patterns`
  - `code-review-excellence`
  - `debugging-strategies`

Selected transferable entries:
- `python-code-style` (wshobson): https://skillsmp.com/skills/wshobson-agents-plugins-python-development-skills-python-code-style-skill-md
- `python-error-handling` (wshobson): https://skillsmp.com/skills/wshobson-agents-plugins-python-development-skills-python-error-handling-skill-md
- `python-testing-patterns` (wshobson): https://skillsmp.com/skills/wshobson-agents-plugins-python-development-skills-python-testing-patterns-skill-md
- `verification-before-completion` (obra): https://skillsmp.com/skills/obra-superpowers-skills-verification-before-completion-skill-md
- `systematic-debugging` (obra): https://skillsmp.com/skills/obra-superpowers-skills-systematic-debugging-skill-md
- `typescript` (lobehub): https://skillsmp.com/skills/lobehub-lobehub-agents-skills-typescript-skill-md
- `typescript-review` (metabase): https://skillsmp.com/skills/metabase-metabase-claude-skills-typescript-review-skill-md
- `code-reviewer` (google-gemini): https://skillsmp.com/skills/google-gemini-gemini-cli-gemini-skills-code-reviewer-skill-md
- `lint-typecheck` (aiskillstore): https://skillsmp.com/skills/aiskillstore-marketplace-skills-applelamps-lint-typecheck-skill-md
- `python-anti-patterns` (wshobson): https://skillsmp.com/skills/wshobson-agents-plugins-python-development-skills-python-anti-patterns-skill-md
- `error-handling-patterns` (wshobson): https://skillsmp.com/skills/wshobson-agents-plugins-developer-essentials-skills-error-handling-patterns-skill-md
- `code-review-excellence` (wshobson): https://skillsmp.com/skills/wshobson-agents-plugins-developer-essentials-skills-code-review-excellence-skill-md
- `debugging-strategies` (wshobson): https://skillsmp.com/skills/wshobson-agents-plugins-developer-essentials-skills-debugging-strategies-skill-md

## Downloaded upstream SKILL.md files for adaptation
- https://raw.githubusercontent.com/obra/superpowers/main/skills/verification-before-completion/SKILL.md
- https://raw.githubusercontent.com/obra/superpowers/main/skills/systematic-debugging/SKILL.md
- https://raw.githubusercontent.com/wshobson/agents/main/plugins/python-development/skills/python-code-style/SKILL.md
- https://raw.githubusercontent.com/wshobson/agents/main/plugins/python-development/skills/python-error-handling/SKILL.md
- https://raw.githubusercontent.com/wshobson/agents/main/plugins/python-development/skills/python-testing-patterns/SKILL.md
- https://raw.githubusercontent.com/metabase/metabase/master/.claude/skills/typescript-review/SKILL.md
- https://raw.githubusercontent.com/google-gemini/gemini-cli/main/.gemini/skills/code-reviewer/SKILL.md
- https://raw.githubusercontent.com/wshobson/agents/main/plugins/python-development/skills/python-anti-patterns/SKILL.md
- https://raw.githubusercontent.com/wshobson/agents/main/plugins/developer-essentials/skills/error-handling-patterns/SKILL.md
- https://raw.githubusercontent.com/wshobson/agents/main/plugins/developer-essentials/skills/code-review-excellence/SKILL.md
- https://raw.githubusercontent.com/wshobson/agents/main/plugins/developer-essentials/skills/debugging-strategies/SKILL.md
- https://raw.githubusercontent.com/obra/superpowers/main/skills/receiving-code-review/SKILL.md
- https://raw.githubusercontent.com/obra/superpowers/main/skills/requesting-code-review/SKILL.md
- https://raw.githubusercontent.com/hashicorp/agent-skills/main/terraform/code-generation/skills/terraform-style-guide/SKILL.md
- https://raw.githubusercontent.com/hashicorp/agent-skills/main/terraform/code-generation/skills/terraform-test/SKILL.md
- https://raw.githubusercontent.com/hashicorp/agent-skills/main/terraform/module-generation/skills/refactor-module/SKILL.md
- https://raw.githubusercontent.com/hashicorp/agent-skills/main/terraform/module-generation/skills/terraform-stacks/SKILL.md
- https://raw.githubusercontent.com/cosmix/claude-loom/main/skills/terraform/SKILL.md

## Notes
- Local adaptation prioritized "minimal surface area, explicit invariants, fail-fast core logic."
- Keep language-specific variants only where behavior/check commands differ.
- IaC adaptation uses OpenTofu-first commands with Terraform compatibility where repositories still standardize on Terraform.
