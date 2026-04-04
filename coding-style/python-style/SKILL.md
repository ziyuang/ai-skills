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

## Core constraints
- Follow Google naming, import, and module structure conventions.
- Annotate public APIs with Python 3.12+ type syntax.
- Typing is modeling: use types to make domain structure and valid states explicit.
- Type determines behavior: prefer static, type-directed design over runtime value-driven branching.
- Avoid runtime type checks in core logic when behavior can be made explicit through type design.
- Prefer static structure over dynamic lookup; avoid `getattr`/`hasattr`-style designs when explicit types or protocols can model the behavior directly.
- Keep APIs explicit: avoid hidden side effects and magic sentinel values.
- Keep module boundaries clean: parse/validate external input at edges.

## Secondary style rules
- Do not use `if not ... else ...`; prefer positive conditions with `if ... else ...`.
- Prefer explicit constants and helper predicates for special states.
- `@abstractmethod` implementations should raise `NotImplementedError`.
- Module docstrings should use the multi-line form:
  `"""`
  `<docstring>`
  `"""`
  not the one-line form ``"""<docstring>"""``.
- If using `# noqa: <code>`, include the human-readable rule name in the form of `# noqa: <code> - <code-text>` so the suppression is understandable in review.
  - Example: `# noqa: E741 - ambiguous-variable-name`
- `StrEnum` members should use the member name as the value, for example `FIELD_NAME = "FIELD_NAME"`. Do not maintain parallel naming schemes in enum names and enum values.

## Type discipline
- Use precise return types; avoid implicit `None` return paths.
- Use `T | None` for optional values; avoid broader unions that make static behavior ambiguous.
- Use dataclasses or typed classes for structured data, not loose dicts.
- When a string-shaped domain is actually bounded, model it explicitly: use dataclasses or other typed classes for fixed-key structures, and use `enum.StrEnum` for fixed sets of string values.
- Prefer typed dispatch (`match`/`case`, explicit variant types, or protocols) over `hasattr`/`getattr` checks when behavior depends on shape or capability.
- Avoid `typing.TYPE_CHECKING` imports when they mainly paper over dependency direction problems; if type-only references are needed because modules point at each other, fix the module boundaries instead of normalizing the cycle.
- Treat `typing.cast` as a last resort; if a cast is needed to make the code type-check, first ask whether the data model, API boundary, or control flow should be made explicit in the types.
- Use `Any` only when it is genuinely unavoidable; otherwise find concrete library types or introduce typed wrappers/protocols. Do not use `object` as a fallback type.
