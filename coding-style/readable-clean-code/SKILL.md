---
name: readable-clean-code
description: Primary cross-language readability and simplicity overlay based on The Art of Readable Code and The Art of Clean Code. Use first when writing, refactoring, or reviewing code, then pair with language-specific style/tooling/verification skills for constraints. Workspace skills may override rules here only when they explicitly state an override.
---

# Readable + Clean Code Style

## Precedence contract
1. Apply this skill first as the default readability and simplicity baseline.
2. Apply language-specific style skills (for example `python-style`, `typescript-javascript-style`) as complementary constraints, not replacements.
3. Allow workspace skills to override a rule in this skill only when the workspace skill explicitly states that override.

## Core goal
- Write code to minimize time-to-understand and prevent accidental complexity.
- Prefer clarity and simplicity over cleverness and compactness.

## What "understand" means
- A reader understands code if they can change it safely, spot bugs, and reason about its interactions with the rest of the system.

## "Readable" vs "clean"
- Readable code is quickly explainable.
- Clean code is readable and structured so change is safe and cheap (small units, low coupling, consistent conventions, tests, refactoring).

## Decision rule
- When choosing between two implementations, prefer the less intimidating / more inspectable version if it reduces time-to-understand.
- Consistency beats personal preference, within applicable language-specific and explicit workspace constraints.

## Agent workflow (apply in this order)
1. State intent in one sentence: "This code does X given Y."
2. Make the main path obvious: handle guard/exception cases early, keep nesting shallow.
3. Separate tasks: one responsibility per function/module; avoid mixing orchestration with low-level details.
4. Make names carry meaning: remove ambiguity, encode units/range/state when it prevents mistakes.
5. Add only high-signal comments: intent, constraints, invariants, and "why" (not narration).
6. Delete complexity: remove dead code/branches, avoid speculative features (YAGNI), avoid duplication when it is truly the same.
7. Protect behavior with tests: readable tests, simplest inputs that fully exercise behavior.

## Agent deliverables (when you change code)
- State the behavior you preserved or changed.
- List the readability/simplicity improvements in priority order.
- If there are many issues, propose an 80/20 plan (top 1-3 changes that remove most confusion/complexity).
- Call out any tradeoffs (e.g., more lines for clarity).
- Suggest the smallest relevant checks to run (tests/lint/typecheck).

## Principles (use as tie-breakers)
- Think about the big picture: keep the end-to-end story and interfaces simple.
- Optimize for humans: least surprise, quick inspection, easy safe change.
- Keep units small: small functions, small modules, shallow indentation.
- Separate responsibilities (SRP) and reduce coupling (Law of Demeter).
- Prefer Open-Closed designs at stable seams: allow extension via new modules/strategies/adapters instead of modifying proven core flows.
- Avoid duplication (DRY) and unnecessary features (YAGNI).
- Refactor continuously (Boy Scout rule); use metrics as smoke alarms.
- Avoid premature optimization; measure first and prefer algorithmic improvements.

## Names (pack information; prevent misunderstanding)
- Pack information into names; treat names as tiny comments.
- Choose specific words (concrete verbs/nouns) over generic names like `tmp`, `data`, `handle`, `process`, `retval`.
- Be clear and precise rather than cute.
- Encode important facts in names when they prevent mistakes: units (`seconds`, `bytes`), encoding (`utf8`), form (`raw`, `parsed`), state (`validated`, `normalized`, `escaped`).
- Use consistent naming patterns to convey meaning (e.g., `*_count`, `*_id`, `*_secs`, `is_*`, `has_*`).
- Name booleans as predicates; avoid double-negatives and "anti-names" like `disable_*` when a positive form exists.
- Scrutinize ambiguity: ask "What else could a reader think this means?"
- Prefer pronounceable names; readability includes how easily the name can be talked about in reviews.
- Be explicit about range semantics:
  - Prefer `min`/`max` for inclusive limits.
  - Prefer `first`/`last` for inclusive ranges.
  - Prefer `begin`/`end` when `end` is exclusive (half-open intervals).

## Comments (high signal, low noise)
- Comment to transfer knowledge: help the reader know what the writer knew.
- Comment intent, assumptions, constraints, and non-obvious reasoning; do not restate what the code already says.
- Do not comment on facts that can be derived quickly from the code itself.
- Keep a high information-to-space ratio.
- Record invariants and "why this is safe" reasoning when correctness is subtle.
- Keep comments compact and unambiguous; avoid vague pronouns ("this", "it", "that") when they can be misread.
- Prefer information-dense wording; replace long phrases with precise terms.
- Use input/output examples to illustrate corner cases when that is clearer than prose.
- Use "named-parameter" comments sparingly to disambiguate tricky call sites.
- Avoid "crutch comments" that compensate for unclear code; fix the code instead.
- Use structured markers like `TODO` / `FIXME` when leaving intentionally incomplete work.

## Formatting / aesthetics (consistency wins)
- Use whitespace to group related code into "paragraphs".
- Keep related declarations together and order them meaningfully (and keep the order consistent).
- Align columns only when it improves scanability and won't create noisy diffs.
- Normalize line breaks so similar statements look similar.
- Do not compress code into one-liners if it hides control flow or state changes.

## Control flow (make the execution path natural)
- Make conditionals, loops, and other control flow as natural as possible (do not make the reader stop and reread).
- Reduce nesting with guard clauses / early returns.
- Put the common case first when it makes the flow easier to follow.
- Prefer readable `if/else` blocks over dense conditional expressions (e.g., avoid complex ternaries).
- Avoid uncommon constructs when they slow down reading (e.g., `do/while`, `goto`-style flow).
- Make it easy to answer: "What happens next?" without rereading.
- Avoid hidden state changes in conditionals (assignments, mutations, I/O, or side effects).

## Expressions (break down "giant" logic)
- Break down your giant expressions into more digestible pieces.
- Replace dense expressions with explanatory variables or helper functions.
- Avoid relying on short-circuit logic for side effects.
- Prefer positive conditions when it reduces mental negation.
- Beware "clever nuggets" of code; trade micro-compactness for clarity.
- Use parentheses to make precedence explicit when mixed operators would slow down reading.

## Variables (minimize cognitive load)
- Make your variable visible by as few lines of code as possible.
- Minimize scope: declare variables as close as possible to first use; keep visibility tight.
- The more places a variable is manipulated, the harder it is to reason about its current value.
- Reduce mutation: prefer write-once/immutable values and avoid variables updated in many places.
- Delete variables that add no meaning; keep variables that explain intent or structure the code.
- Avoid shared mutable globals; if unavoidable, isolate and document invariants.

## Functions and modules (small, focused, low coupling)
- Make each function do one thing well; avoid mixed concerns.
- Keep indentation shallow; extract helpers to reduce nested control flow.
- Keep interfaces small and unsurprising; prefer simple inputs/outputs.
- Wrap ugly or overly-flexible dependencies behind a narrow adapter interface.
- Avoid method-chaining across multiple objects (Law of Demeter); pass what you need explicitly.
- Use SRP to decide boundaries: split units with different reasons to change.
- Keep one level of abstraction per function; do not mix orchestration with low-level parsing.

## Organization (one task at a time)
- Organize code so it is doing only one task at a time.
- Separate unrelated subproblems into helpers; isolate general-purpose code from project-specific code.
- When logic is unclear, write the steps in plain language first, then translate into code.
- Periodically reread your code from a fresh perspective; step back and scan the whole file for clarity.
- Stop refactoring when it is already easy to understand; do not refactor for its own sake.

## Less code (when it improves understanding)
- The most readable code is no code at all.
- Question requirements; avoid implementing features you won't need.
- Prefer standard libraries/tools over custom code when they reduce surface area and ambiguity.
- Remove dead code; do not keep commented-out code as a "future option".

## Robustness (fail early, be explicit at boundaries)
- Validate and normalize inputs at the boundary; keep core logic operating on clean data.
- Fail early and noisily when continuing would hide errors or corrupt state.
- Prefer explicit error paths over implicit "best effort" behavior when correctness matters.

## Metrics (use as signals)
- Use metrics as signals (nesting depth, function length, cyclomatic complexity, duplication, churn) to decide where to simplify, not to "game" numbers.

## Tests (treat test code as product code)
- Test code should be readable so that other coders are comfortable changing or adding tests.
- Make tests easy to read and change: clear names, clear arrangement, and actionable failure messages.
- Choose the simplest inputs that fully exercise behavior, including edge cases.
- Prefer clean and simple test values that still get the job done.
- Prefer clean, simple test values over "realistic" but noisy ones unless realism is the point.
- Avoid brittle tests that encode implementation details instead of behavior.

## Agent checklist (use in PRs/reviews)
- Goal: can you explain intent in one sentence and find the main path quickly?
- Names: specific, unambiguous, and encode key constraints (units/range/state)?
- Comments: explain "why" and "what's tricky" rather than narrating code?
- Structure: one job per function/module; shallow indentation; one abstraction level per function?
- Coupling: SRP/DRY/YAGNI applied only where they reduce complexity; Law of Demeter violations avoided?
- Extensibility: are stable paths open for extension but closed to risky modification (OCP), with new behavior added behind explicit seams?
- Boundaries: inputs validated/normalized; errors explicit; no hidden side effects in conditionals?
- Tests: readable, simplest meaningful inputs, failures are diagnostic, behavior-focused (not brittle)?
