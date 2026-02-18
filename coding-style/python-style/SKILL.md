---
name: python-style
description: Apply Google Python style and typing discipline with strict simplicity rules. Use when writing or reviewing Python code for naming, structure, docstrings, and static type safety. Combine with readable-clean-code for cross-language readability tie-breakers and complexity reduction.
---

# Google Python Style

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
- Refrain from annotating `Any`; find concrete library types or introduce typed wrappers/protocols.
