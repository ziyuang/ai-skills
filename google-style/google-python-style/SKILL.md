---
name: google-python-style
description: Apply Google Python style and typing discipline with strict simplicity rules. Use when writing or reviewing Python code for naming, structure, docstrings, and static type safety.
---

# Google Python Style

## Authoritative guides
- Python style guide: `https://google.github.io/styleguide/pyguide.html`
- Google-style docstrings are mandatory for public modules, classes, and functions.

## Required rules
- Follow Google naming, import, and module structure conventions.
- Annotate public APIs with Python 3.12+ type syntax.
- Use `Any` instead of `object` when a deliberately wide type is required.
- Keep APIs explicit: avoid hidden side effects and magic sentinel values.
- Prefer explicit constants and helper predicates for special states.
- Keep module boundaries clean: parse/validate external input at edges.

## Type discipline
- Use precise return types; avoid implicit `None` return paths.
- Use union syntax (`T | None`) for optional values.
- Use dataclasses or typed classes for structured data, not loose dicts.
- Keep `Any` usage intentional and local.
