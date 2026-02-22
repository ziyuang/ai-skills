---
name: python-style
description: Google Python style and typing discipline for Python code (naming, structure, docstrings, and static type safety). Use after readable-clean-code when Python-specific conventions and type constraints are required. Keep this skill complementary to readable-clean-code; workspace skills override only when they explicitly state an override.
---

# Google Python Style

## Precedence contract
1. Apply `readable-clean-code` first for the general readability/simplicity baseline.
2. Apply this skill second for Python-specific conventions and typing constraints.
3. If a workspace skill explicitly states it overrides a rule here, follow the explicit override; otherwise keep this skill in effect.

## Authoritative guides
- Python style guide: `https://google.github.io/styleguide/pyguide.html`
- Google-style docstrings are mandatory for public modules, classes, and functions.

## Required rules
- Follow Google naming, import, and module structure conventions.
- Annotate public APIs with Python 3.12+ type syntax.
- Type determines behavior: prefer static, type-directed design over runtime value-driven branching.
- Avoid runtime type checks in core logic when behavior can be made explicit through type design.
- Do not use `if not ... else ...`; prefer positive conditions with `if ... else ...`.
- Keep APIs explicit: avoid hidden side effects and magic sentinel values.
- Prefer explicit constants and helper predicates for special states.
- Keep module boundaries clean: parse/validate external input at edges.

## Type discipline
- Use precise return types; avoid implicit `None` return paths.
- Use `T | None` for optional values; avoid broader unions that make static behavior ambiguous.
- Use dataclasses or typed classes for structured data, not loose dicts.
- Avoid free-form string keys when the key set is fixed; model fixed-key data with dataclasses or other typed classes.
- Use `Any` only when it is genuinely unavoidable; otherwise find concrete library types or introduce typed wrappers/protocols. Do not use `object` as a fallback type.
