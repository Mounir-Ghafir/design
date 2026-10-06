---
name: clean-code
title: Clean Code — Naming, Readability and Local Discipline
description: Rules for writing code a teammate can read, understand and change — names, small functions, comments, layout, objects, tests and local refactoring. Load when writing or reviewing a function or class, choosing a name, tidying a module, or reviewing AI-generated code.
applies_when: [naming, functions, comments, formatting, code layout, readability, refactoring, tests, code review, code smells]
priority: supporting
rules: 22
---

# Clean Code — Naming, Readability and Local Discipline

## Core principle

Clean code is code every member of the team can read, understand and change — not code that obeys a checklist. You spend far more time reading code than writing it, so optimise each line for the next reader, and prefer a real fix over a tidy-looking ritual.

## Rules

**General rules**
### CC-01 · Conventions and simplicity
rule: Follow standard conventions, and keep it simple stupid — simpler is always better.
do: Apply the community style guide (PEP 8 for Python — snake_case, spaces over tabs; Google JavaScript Style Guide; Java — camelCase, four spaces, opening brace on the same line; JavaScript — two spaces, camelCase functions, snake_case object properties) plus your team's additions.
never: Invent a house style, or add abstraction for a future that may never come.

### CC-02 · Leave it cleaner; fix root causes
rule: Boy Scout rule — leave the campground cleaner than you found it — and always find the root cause of a problem.
do: Tidy the code you touch while you are in it; trace every bug to its origin before patching it.
never: Walk away from the mess you passed through, or bandage a symptom.

**Design rules**
### CC-03 · Configuration stays high and few
rule: Keep configurable data at high levels of the call stack, and prevent over-configurability.
do: Pass values down from the layer that owns them; leave stable facts hard-coded.
never: Thread configuration through every layer, or expose knobs nobody uses.

### CC-04 · Polymorphism over branching
rule: Prefer polymorphism to if/else or switch/case.
do: Move type-dependent behaviour into implementations; extract a long or nested conditional into a function named for what it decides (e.g. get_discount_rate).
never: Grow a switch that must be edited every time a new type appears.

### CC-05 · Isolate threads; inject and know only direct dependencies
rule: Separate multi-threading code; use dependency injection; follow the Law of Demeter — a class should know only its direct dependencies.
do: Concentrate threads and locking in one module, take collaborators from outside, and call only methods on objects you were handed.
never: Reach through chains (a.getB().getC().doIt()), or new-up collaborators inside the class that needs them.

**Understandability tips**
### CC-06 · Consistency and explanatory variables
rule: Do all similar things the same way, and name intermediate results.
do: Keep one pattern per concept in a file; introduce explanatory variables instead of leaving an expression to be decoded.
never: Write two variants of the same idea side by side.

### CC-07 · Boundary conditions centralised; value objects over primitives
rule: Encapsulate boundary conditions in one place, and prefer dedicated value objects to primitive types.
do: Collect edge and off-by-one handling into a single function; wrap meaningful primitives (UserId, Money) instead of passing bare numbers and strings.
never: Scatter index arithmetic through a method, or overload one int with three meanings.

### CC-08 · No logical dependency; no negative conditionals
rule: Never write a method that works only because of something else in the same class, and avoid negative conditionals.
do: Test each condition positively, and make a method's result depend on its own inputs.
never: Depend on call order inside the class, or wrap a check in `if (!flag)`.

**Names rules**
### CC-09 · Names reveal intent
rule: Choose descriptive and unambiguous names that say why the thing exists, what it does and how it is used.
do: Rename until the name needs no comment; rename an existing name whenever the code reads better afterwards.
never: Ship a name that only works with a comment explaining it.

### CC-10 · Meaningful, pronounceable, searchable
rule: Make meaningful distinctions, use pronounceable names, and use searchable names.
do: Name real concepts (elapsed_days, user_id) so you can say them out loud to a colleague and find them with search.
never: Number series (data1, data2), single letters, or an inline literal that IDE search cannot find.

### CC-11 · Constants for magic numbers
rule: Replace magic numbers with named constants.
do: Name the value for its purpose (TEN_PERCENT_DISCOUNT = 0.1) so a change is a one-line edit in one place.
never: Repeat a bare literal across the code, or explain it with a trailing comment.

### CC-12 · No encodings in names
rule: Avoid encodings — don't append prefixes, type information, suffixes or abbreviations.
do: Let context and the type system carry the kind; spell words out in full.
never: Type prefixes, interface/manager suffixes on every name, or abbreviations like `hp`.

**Functions rules**
### CC-13 · One thing, small, well named
rule: A function does one thing, does it well and does only that — and it is small.
do: Split functions that do several jobs; cap nesting at 2 levels of indentation (start at 3 if you must, but set a limit); give the function and its arguments descriptive names.
never: One body that validates, calculates and formats.

### CC-14 · Few arguments, no flag arguments
rule: Prefer fewer arguments, and never use flag arguments.
do: Keep to 2 arguments unless you have a good reason; split a flagged function into independent methods the caller can invoke directly.
never: A boolean parameter that decides what the function does.

### CC-15 · No side effects
rule: Functions have no side effects.
do: Make the output depend only on the inputs and return the change.
never: A function that also mutates unrelated state it was not asked to touch.

**Comments rules**
### CC-16 · Explain yourself in code first
rule: The truth is in the code — explain intent, clarification and consequences, never mechanics.
do: Fix a bad name or extract a named function instead of commenting; delete commented-out code (version control remembers), closing-brace comments, bylines and obvious noise.
never: A redundant comment restating the function name, or a comment propping up an unreadable expression.

### CC-17 · Comment only when code cannot speak
rule: Keep comments where only a comment can carry the reason.
do: Comment legal notices, TODOs, warnings of consequences, non-obvious decisions and mandated public API contracts (Javadoc).
never: Mandate comments on every private function, or delete a hard-won explanation because "clean code needs no comments".

**Source code structure**
### CC-18 · Vertical layout
rule: Separate concepts vertically; keep related code vertically dense and close.
do: Declare variables next to their usage; keep dependent functions and similar functions close; place functions in downward flow.
never: Make the reader jump up and down the file to follow one idea.

### CC-19 · Lines and whitespace
rule: Keep lines short, don't use horizontal alignment, don't break indentation, and use white space to associate related things and disassociate weakly related things.
do: Indent consistently; group related statements with blank lines and separate unrelated ones.
never: Pad arguments into columns, or mix unrelated logic in one block.

**Objects and data structures**
### CC-20 · Objects keep their insides inside
rule: Hide internal structure, prefer data structures, and avoid hybrid structures (half object, half data); objects should be small.
do: Keep one responsibility and a small number of instance variables; a base class should know nothing about its derivatives; prefer many small functions over passing code in to select a behaviour, and prefer non-static methods to static ones.
never: Expose getters for every field, or build a type that is half behaviour and half raw data.

**Tests**
### CC-21 · Tests are fast, isolated specifications
rule: Every test is readable, fast, independent and repeatable, with one assert per test.
do: Name the behaviour being asserted; make each test stand alone and rerunnable in any order.
never: A test that needs another test to pass, or a bundle of unrelated assertions.

**Code smells**
### CC-22 · Smell, then refactor
rule: Treat rigidity (small change cascades), fragility (one change breaks many places), immobility (code cannot be reused), needless complexity, needless repetition and opacity (hard to understand) as refactoring triggers.
do: Refactor only when it solves a real problem now — restructuring without changing external behaviour, with tests green and IDE refactoring tools.
never: Refactor working code to satisfy an aesthetic or an arbitrary line target.

## Hard numbers

| Item | Value | Note |
|---|---|---|
| Reading vs writing time | **"well over 10 to 1"** | quoted in the source; no citation given |
| Indentation depth | **no more than 2 levels** | source allows starting at 3, but demands a limit |
| Function arguments | **2 recommended** | beyond 2 you need "a good reason" |
| Function line length | contested: **"4 to 5 lines"** | attributed to Robert C. Martin, criticised in the same source |
| Line length, file length, duplication threshold | `unknown: true` | source says only "keep lines short" and objects "should be small" |

## Decision procedure

1. **Names** — read every name aloud: does it reveal intent with no comment?
2. **Units** — each function one thing, ≤ 2 indentation levels, ≤ 2 arguments, no flags, no side effects.
3. **Branches** — extract or polymorphise any switch that grows with types and any deep conditional.
4. **Layout** — related code adjacent and declared near use; whitespace does the grouping.
5. **Comments** — delete restatements, noise and commented-out code; keep only why, warnings, legal, TODO.
6. **Refactor** — only for a real problem right now, with tests green and IDE refactoring tools.

## Anti-patterns

- Noise: commented-out code, closing-brace comments, bylines, comments that restate the name, horizontal alignment padding.
- Magic numbers and abbreviations that need a comment to be understood.
- Flag arguments, side effects, and logical dependency on call order.
- A switch edited for every new type; a base class that knows its subclasses.
- Refactoring working code to hit an arbitrary line target; hard-coded secrets in AI-generated code.

## Review checklist

- [ ] Language style guide followed; no invented house style
- [ ] Names intention-revealing, pronounceable, searchable; no prefixes or abbreviations; magic numbers named; boundary logic in one place
- [ ] Each function: one thing, ≤ 2 indentation levels, ≤ 2 arguments, no flags, no side effects
- [ ] Comments explain why only; nothing commented out; no redundant noise
- [ ] Related code adjacent, lines short, indentation unbroken, whitespace grouping
- [ ] Tests: one assert each, readable, fast, independent, repeatable
- [ ] AI-generated code checked for long methods, duplicated logic, stray structure, hard-coded secrets and insecure dependencies

## Caveats

- These are conventions and heuristics, not empirical findings: the source gives no defect rates, maintenance-cost figures, readability studies, sample sizes or effect sizes — `unknown: true`.
- The source is a scrape of several disagreeing pieces: one prescribes DRY, another (attributing Sandi Metz) says "duplication is far cheaper than the wrong abstraction". Default to the simpler version; abstract only when the duplication actually costs you.
- No line-length or file-length limit is stated anywhere in the source — `unknown: true`. The "4 to 5 lines" target is contradicted within the source itself. An uncited claim of a 13-hour AWS outage caused by an internal AI coding tool appears there too; treat as unverified.
- Siblings: `solid.md` (five SOLID principles), `single-responsibility-principle.md` (SRP deep-dive) and `code-structure.md` (module/package organisation) — load those for that ground; this file covers naming, readability, small units and local discipline only.
