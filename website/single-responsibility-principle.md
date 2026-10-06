---
name: single-responsibility-principle
title: Single Responsibility Principle — Design Rules
description: Rules for giving each class, function, or module one duty only. Load when designing a new class, refactoring a god class, deciding where a new behaviour belongs, reviewing code that mixes logic with persistence, or splitting a module or microservice.
applies_when: [class design, refactoring, code review, god classes, mixed duties, module boundaries, microservices, testability]
priority: supporting
rules: 13
---

# Single Responsibility Principle — Design Rules

## Core principle

Robert C. Martin describes it: "A class should have one, and only one, reason to change."

A responsibility is an axis of change: one reason a requirement would force you to edit this unit. Two responsibilities means two, independent reasons — and every change now risks breaking the duty you were not touching. Apply the principle to classes, functions, modules, and microservices alike.

## Rules

### SRP-01 · One reason to change
rule: Every class, function, and module has exactly one reason to change.
do: State the unit's responsibility in one sentence; name the unit after it.
never: Give a unit two duties and justify them as related.

### SRP-02 · Ask the responsibility question before you change anything
rule: Before adding a method or feature to existing code, ask: "What is the responsibility of your class/component/microservice?"
do: If your answer includes the word "and", you're most likely breaking the single responsibility principle — take a step back and rethink the approach.
never: Bolt new behaviour onto an existing class because it is the fastest path.
because: Extending existing code instead of writing a new class is the trap that accumulates responsibilities and makes the software progressively harder to maintain; the "and" in your answer is the audible symptom.

### SRP-03 · Treat every responsibility as an axis of change
rule: Identify the distinct responsibilities inside a unit before you accept it; each one is a potential axis of change.
do: List which requirement would force an edit to this unit; if two unrelated requirements both would, split it.
never: Assume responsibilities are independent just because they currently live together.

### SRP-04 · Optimise for explanation, not just compilation
rule: A unit with one responsibility must be explainable in one sentence.
do: Prefer units a new developer can understand and implement quickly — the source's stated benefit is fewer bugs and faster development speed.
never: Ship a class you cannot describe without the word "and".

### SRP-05 · Split mixed duties into one class per duty
rule: When a class handles two concerns, extract the second concern into its own class.
do: Example — `UserManager` holding user details *and* database writes splits into `User` (change email) plus `UserDataStorage` (save).
never: Keep domain logic and persistence in the same class (the source's `ProductReport` also splits into `ProductReportGenerator` and `ReportSaver`).

### SRP-06 · Apply SRP beyond classes
rule: The one-reason test applies to functions, modules, components, and microservices — not only classes.
do: Check the responsibility of every unit you create at any granularity.
never: Hide two responsibilities inside one "small" function or one service because the class-level rules were satisfied.

### SRP-07 · Mind the dependency blast radius
rule: A change to a multi-responsibility unit forces updates or recompiles in dependents that use only one of its duties.
do: Split widely depended-upon units first; each split shrinks the set of dependents touched by any one change.
never: Dismiss a violation as "not a big deal" because the class itself is small — count its dependents.

### SRP-08 · Keep persistence free of business logic, validation, and auth
rule: A data-access unit's only duty is managing persistence for its scope.
do: Follow the source's `JPA EntityManager` example — persist, update, remove, read the entities of the current persistence context, nothing else; it changes only when the general persistence concept changes.
never: Put business logic, validation, user authentication, or domain-model rules in a repository or entity manager.

### SRP-09 · Give mapping and conversion their own type
rule: Type conversion and mapping are a single, self-contained responsibility — give them a dedicated class.
do: Follow the source's `JPA AttributeConverter` example: a `DurationConverter` implements only the two conversion operations, so it is easy to understand and changes only if the mapping algorithm changes.
never: Embed data-type conversion inside the entity or the persistence logic it serves.

### SRP-10 · Extract, don't accumulate
rule: If a new requirement does not belong to the unit's one sentence, create a new unit for it.
do: Divide and conquer — split a class with more than one responsibility into smaller classes, each with its own.
never: Add a method to an existing class to avoid writing a new one.

### SRP-11 · Design each unit to be testable in isolation
rule: One responsibility per unit means one concern under test.
do: Verify you can test a unit's behaviour without setting up the other functionalities it would otherwise contain.
never: Write a test that must satisfy unrelated duties of the same class to exercise one of them.

### SRP-12 · Keep units reusable without dragging duties along
rule: A unit extracted for one duty should be usable in other contexts without importing your other duties.
do: Extract shared single-duty classes so callers take only the behaviour they need.
never: Reuse a grab-bag class and inherit its unrelated functionality.

### SRP-13 · Don't oversimplify
rule: SRP is a rule of balance, not an end in itself — "don't use it as your programming bible."
do: Find the right balance when defining responsibilities; use common sense alongside the principle.
never: Create classes with just one function, or many tiny classes whose injected dependencies make the code unreadable and confusing.

## Hard numbers

| Constant | Value | Note |
|---|---|---|
| Empirical evidence (defect rates, maintenance cost, sample sizes) | `unknown: true` | The source states no studies, numbers, or effect sizes — benefits are argued, not measured |
| Reasons to change per unit | 1 | Martin's definition, verbatim |
| Granularity the source applies it to | classes, functions, modules, components, microservices | Article 2 adds functions and modules explicitly |
| SOLID named by / acronym coined by | Robert C. Martin (Uncle Bob), around the 2000s / Michael Feathers | Context only; the other four principles are covered in `solid.md` |

## Decision procedure

1. **Ask** — "What is the responsibility of your class/component/microservice?" If the answer contains "and", stop (SRP-02).
2. **List axes** — name every requirement that would force an edit here (SRP-03).
3. **Split** — extract each extra axis into its own unit, domain logic separated from persistence (SRP-05, SRP-10).
4. **Check dependents** — split widely used units first; count what a change would ripple into (SRP-07).
5. **Re-test** — can the unit be explained in one sentence, tested alone, reused alone (SRP-04, SRP-11, SRP-12)?
6. **Stop** — if the result is a swarm of one-function classes, back off (SRP-13).

## Anti-patterns

- God class doing persistence, validation, and business logic at once.
- Extending an existing class because writing a new one feels slower.
- Domain entity that writes itself to the database.
- "Related" duties bundled under one name to avoid an extra file.
- Oversplitting into one-function classes that need many injected dependencies.
- A widely depended-upon utility class that everyone must recompile when anything changes.

## Review checklist

- [ ] One-sentence responsibility for every class, module, and service
- [ ] No "and" in that sentence
- [ ] Domain logic separated from persistence
- [ ] Validation, auth, and business rules outside data-access units
- [ ] Type conversion/mapping isolated in its own class
- [ ] Each unit testable without unrelated setup
- [ ] High-fan-in units checked first for mixed duties
- [ ] Not oversplit — responsibilities balanced, not atomised

## Caveats

- Sibling skills: `solid.md` is the overview covering all five SOLID principles; this file is the deep-dive on SRP alone and deliberately does not restate the other four principles' rules. `clean-code.md` and `code-structure.md` cover naming and layout concerns that overlap with, but are broader than, SRP.
- These are engineering conventions, not measured results: `unknown: true` — the source gives no defect rates, maintenance-cost studies, sample sizes, or effect sizes, only argued benefits ("easier to implement", "reduces the number of bugs", "improves development speed").
- "One reason to change" is genuinely ambiguous in practice; the source acknowledges SRP "sounds a lot easier than it often is" and handles it only via the "and" diagnostic plus an appeal to balance — it offers no formal test for when two duties are truly one responsibility.
