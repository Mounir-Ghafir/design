---
name: solid
title: SOLID — Object Design Rules
description: Rules for applying the five SOLID principles when designing classes, interfaces, and modules; reviewing object-oriented code; refactoring a class with mixed duties; or deciding where a new behaviour belongs.
applies_when: [class design, interface design, code review, refactoring, god classes, switch statements, inheritance, interface splitting, dependency injection]
priority: supporting
rules: 12
---

# SOLID — Object Design Rules

## Core principle

Code gets fragile where change concentrates. SOLID is five tests for where the next change will land — each names a structural question you can ask of a class, function, or module before you write or accept it.

Each rule below gives a detection question and its fix: when the answer exposes a violation, apply the fix rather than reasoning around it.

```
S ingle responsibility → one reason to change per class
O pen/Closed            → add behaviour by adding code, not editing it
L iskov substitution    → a subtype drops in wherever the base is used
I nterface segregation  → many small interfaces, not one general one
D ependency inversion   → both layers depend on abstractions
```

## Rules

### SOL-01 · One reason to change
rule: A class, module, or function has one, and only one, reason to change.
do: State its single responsibility in one sentence and name the class after it (BookPrinter, BookSaver, InventoryManager).
never: Let one class hold data, print it, and persist it.
because: The source's stated payoffs: fewer test cases per class, fewer dependencies (lower coupling), and smaller organised classes that are easier to search than monolithic ones.

### SOL-02 · Detect and split mixed duties
rule: Ask of every class: "List the separate reasons this file gets edited." More than one → split it.
do: Extract each extra duty into its own collaborator and call it — Book becomes Book + BookSaver + BookPrinter.
never: Fix a god class by moving the offending methods into private helpers of the same class.
because: Persistence, output, and domain data change for different reasons; split, a save-format change can no longer break the domain object.

### SOL-03 · Add behaviour by adding code
rule: Classes, modules, and functions are open for extension and closed for modification.
do: Add a new subtype or class rather than editing a working one; the source's one exception is fixing a bug in existing code.
never: Reopen a shipped class to bolt on a new variant.
because: Editing working code is where new bugs in an otherwise happy application come from; extending leaves existing behaviour untouched.

### SOL-04 · Kill type-dispatch chains
rule: Ask: "To support a new type, do I edit this method?" If yes, OCP is violated.
do: Replace `switch` / `if type ==` chains with one interface and one class per type (Notification, SpeedRate, PaymentProcessor); callers depend on the interface.
never: Add another `case` for a new variant — the source says using a switch makes an OCP violation very likely.
because: Adding push notifications or PayPal then means writing new code, not reopening code that already works.

### SOL-05 · Subtypes must be drop-in replacements
rule: If A is a subtype of B, replacing B with A must not disrupt the behaviour of the program.
do: Keep every guarantee the base type makes; code written against the base must run unchanged with any subtype.
never: Publish a subtype that cannot honour a base-class method.
because: LSP (Barbara Liskov, 1987, paper co-authored with Jeannette Wing) is what lets callers trust the declared type instead of probing concrete types.

### SOL-06 · Never stub an override into nonsense
rule: Ask of every override: "Does this do what the base contract promises, or does it throw / print an error?"
do: Move the contested capability into its own interface (Flyer, Swimmer, an engine-less Car shape) and let only fit classes implement it.
never: Override with `throw new AssertionError(...)`, `console.error(...)`, or an empty body while keeping the subtype relation (ElectricCar.turnOnEngine, Penguin.fly, RobotWorker.eat, Fish.fly).
because: A caller holding the base type hits the exception at runtime — the source's blatant-violation case.

### SOL-07 · Don't let a subtype rewrite inherited invariants
rule: A subtype must not silently change the base class's expected post-conditions.
do: Before inheriting, check each override preserves the base's guarantees; if it cannot, share an abstraction instead of extending.
never: Ship a Square whose setWidth also sets height, then pass it anywhere a Rectangle is expected.
because: Substituting it makes results diverge from what Rectangle-relying code assumes — setting one dimension changes both.

### SOL-08 · No client depends on methods it doesn't use
rule: Clients should not be forced to depend on methods they do not use.
do: Ask of every interface, "Does every implementor need every method?" Split into small client-specific ones (BearCleaner / BearFeeder / BearPetter, Workable / Eatable, per-diet menu interfaces).
never: Ship one general-purpose interface covering all clients.
because: The source compares it to component frameworks: you bring in only the pieces you need, so each implementor carries just the methods relevant to it.

### SOL-09 · Find segregation violations by their stubs
rule: An implementation with an empty, throwing, or error-logging method body is an ISP violation in disguise.
do: Split the fat surface (Animal → Flyer + Swimmer; Worker → Workable + Eatable) so each class implements only what it needs.
never: Keep a method that makes no sense for the implementor just to satisfy the type checker.
because: Forced stubs become runtime errors and lie about what the class can do.

### SOL-10 · Both layers depend on abstractions
rule: High-level modules must not depend on low-level modules; both depend on abstractions, and abstractions must not depend on details — details depend on abstractions.
do: Name the seam as an interface (Logger, Keyboard, IVersionControl) and have the concrete details implement it.
never: Let a high-level class name a low-level concrete type in its fields, parameters, or imports.
because: Decoupled modules then change independently — swapping a file logger for a database logger stops touching UserService.

### SOL-11 · Find DIP violations at the `new` keyword
rule: Ask: "Where does this class call `new Concrete()` or accept a concrete parameter?" That is the coupling point.
do: Inject the abstraction through the constructor (dependency injection) so the concrete implementation is chosen outside the class.
never: Construct your own collaborators inside the class that uses them (Windows98Machine builds its own Monitor and StandardKeyboard with `new`).
because: Concrete construction inside the class makes it hard to test and locks you in; injection keeps implementations swappable.

### SOL-12 · Expect more classes, not fewer
rule: Applying SOLID raises class count — accept that cost deliberately.
do: Extract confidently and name each new class after the responsibility you extracted.
never: Merge distinct responsibilities back into one class to keep the file or line count down.
because: The source states these principles can result in a very large codebase; the aim is making changes without major issues, not minimal class count.

## Hard numbers

| Constant | Value | Note |
|---|---|---|
| Principles | **5** | Single Responsibility, Open/Closed, Liskov Substitution, Interface Segregation, Dependency Inversion |
| Origin | Robert C. Martin, **2000** paper "Design Principles and Design Patterns" | SOLID acronym credited to Michael Feathers |
| Liskov substitution origin | Barbara Liskov, **1987**, paper co-authored with Jeannette Wing | |
| Switch/OCP heuristic | switch usage → "**very likely**" OCP violation | No quantified figure given |
| Measured effect on defects or maintenance cost | `unknown: true` | Source states no studies, sample sizes, or effect sizes |

## Decision procedure

When a design or a review feels off, work in order:

1. **Name** — state the class's single job in one sentence. A second, unrelated job → split (SOL-01, SOL-02).
2. **Growth** — ask how a new type gets added. By editing this code → restructure now (SOL-03, SOL-04).
3. **Contract** — for every subtype, check it honours the base promises and no override throws or stubs (SOL-05–SOL-07).
4. **Surface** — for every interface, check each implementor needs every method (SOL-08, SOL-09).
5. **Seams** — find `new Concrete()` calls and concrete type names in high-level code; inject abstractions instead (SOL-10, SOL-11).
6. **Cost** — count the new classes and accept them if each has one sentence-long job (SOL-12).

## Anti-patterns

- God class that stores, prints, saves, and logs.
- `switch`/type-flag chain extended once per new variant.
- Subtype override that throws "I don't have an engine" / "Penguins cannot fly."
- Fat interface whose every implementor stubs the methods it doesn't want.
- A Square forced into Rectangle-shaped code, changing both dimensions on one setter.
- High-level service constructing its own low-level collaborators with `new`.
- Responsibility-splitting undone to keep the file count small.
- One class that stores data, sends emails, and logs actions — one duty added per feature.
- Subtype inheriting a contract method but never supplying its own behaviour, silently returning the base's generic result.

## Review checklist

- [ ] Each class has one stated reason to change (SOL-01)
- [ ] Extra duties live in named collaborator classes (SOL-02)
- [ ] New behaviour arrives as new code, not edits to working code (SOL-03)
- [ ] No switch/type-flag dispatch on an extension point (SOL-04)
- [ ] Every subtype is a drop-in replacement for its base (SOL-05)
- [ ] No override throws, logs an error, or no-ops its contract (SOL-06, SOL-09)
- [ ] Interfaces split to what each client actually uses (SOL-08)
- [ ] Subclass overrides preserve the base's post-conditions (SOL-07)
- [ ] Persistence and output extracted out of the domain object (SOL-02)
- [ ] Collaborators injected as abstractions, never constructed internally (SOL-11)
- [ ] High-level code names no low-level concrete type (SOL-10)

## Caveats

- These are engineering conventions and heuristics, not laws. Empirical evidence `unknown: true` — the source reports no measured defect rates, maintenance-cost studies, sample sizes, or effect sizes.
- The source's "Further reading" link lists gave titles and links only, no evidence.
- The source is Java-flavoured (with JavaScript and C++ retellings); language-specific examples are illustrative — the principles are stated as language- and framework-agnostic.
- The scraped file retells each principle several times with overlapping, occasionally inconsistent examples (Square/Rectangle appears as both sanctioned pattern and violation); these rules follow the invariant statements, not every example.
- Siblings: `single-responsibility-principle.md` holds the full SRP deep-dive (this file stays at overview depth); `clean-code.md` and `code-structure.md` cover naming, style, and layout in the same folder.
