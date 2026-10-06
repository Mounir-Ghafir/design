---
name: code-structure
title: Code Structure — Module and Package Rules
description: Rules for arranging and grouping code elements — variables, functions, classes, modules, files, packages — with operational coupling/cohesion diagnostics and the stated trade-offs of package-by-layer, package-by-feature, and hexagonal structure. Load when creating or splitting a module or package, laying out a project, moving code between files, or reviewing architecture.
applies_when: [module organisation, package layout, file organisation, project directory structure, coupling, cohesion, hexagonal architecture, refactoring, architecture review]
priority: supporting
rules: 17
---

# Code Structure — Module and Package Rules

## Core principle

Code structure is how you arrange and group your code elements. Group so that everything inside a module is related to one purpose, and modules depend on each other only through well-defined interfaces:

```
cohesion = degree to which classes within a module are related to one another  → MAXIMISE
coupling = degree of dependence between different modules                       → MINIMISE
```

Aim for high cohesion and loose coupling between modules; the source claims their combination results in high readability and maintainability.

## Rules

### CS-01 · Package by feature, not by role
rule: Organise packages around features or functionalities, not technical roles.
do: Group all components of one feature — controller, service, repository, domain classes — in a single package (e.g. `user/`, `order/`, `product/`).
never: Split one feature's classes across top-level `controllers/`, `services/`, `repositories/` packages.
because: The stated benefits of package by feature: high cohesion, low coupling, strong encapsulation (classes can be package-private), high modularity (easy to break into a microservice later), less cross-package navigation, promotes Domain Driven Design.

### CS-02 · Package by Layer is a trade-off, not a default
rule: If you inherit a layer-structured codebase, name its layers and accept its stated costs; do not choose it for new code.
do: Recognise the typical layers — Presentation (user interactions, UI, controllers, views), Service (business logic, provides data to presentation), Domain (entities), Data Access (persistence/retrieval to/from database), Infrastructure (logging, configuration, security, cross-cutting concerns).
never: Make layer the primary packaging axis of a new project.
because: The stated disadvantages: low cohesion (unrelated classes grouped into the same package), high coupling, poor encapsapsulation (most classes are public because other layers need them), low modularity (difficult to break down into a microservice later), poor maintainability (classes scattered — hard to find the class you are looking for), and it promotes Database Driven Design rather than Domain Driven Design.

### CS-03 · Detect low cohesion
rule: Flag a module as low cohesion when its classes are loosely related, carry unrelated responsibilities, or lack a clear purpose.
do: Ask "what single purpose does this package serve?" — high cohesion means classes within it are closely related and share a common, well-defined purpose. If you cannot state it in one phrase, split the package and move each straggler to the package that owns its purpose.
never: Group unrelated classes because they were created at the same time or live in the same layer.
because: Cohesion describes how focused a piece of software is, and is very related to the Single Responsibility Principle.

### CS-04 · Detect high coupling
rule: Flag high coupling when one module depends on another's workings — a class made `public` only so a distant package can reach it, a change to one feature forcing edits across several packages, or a module reaching past a well-defined interface into another module's details.
do: Cut the dependency by exposing an interface (hiding implementation details, exposing only essential functionality), or by moving the code to where it belongs.
never: Widen an access modifier or copy code purely to finish an import.
because: Loose coupling is considered a sign of a well-structured system and good design; combined with high cohesion it results in high readability and maintainability.

### CS-05 · Hexagonal root holds exactly three packages
rule: The root package contains only `core`, `adapters`, and `config` (plus the application entry class).
do: Keep sub-packages beneath these three — `core` may hold sub-packages of domain logic; `adapters` may organise per individual adapter or by technology.
never: Add a fourth top-level package such as `service`, `repository`, or `util`.

### CS-06 · Enforce the dependency direction
rule: Dependencies point inward only — root may depend on all other packages; `config` may depend on `core` and `adapters`; `adapters` may depend on `core` but not on `config`; `core` may not depend on any of the other packages.
do: Treat core as the package that depends on nothing; check imports against this table in review.
never: Let an adapter import `config`, or `core` import anything from `adapters` or `config`.

### CS-07 · Ports declared in core, implemented in adapters
rule: Ports are interfaces defined by the core; adapters are their implementations.
do: Declare service, repository, and external-dependency interfaces in `core`; place all adapter implementations in `adapters`; keep configuration classes in `config`, which exists to connect the different components together.
never: Put an adapter implementation or a configuration class inside `core`.

### CS-08 · Keep the core free of external details
rule: The core is the heart of the application — its business logic must run without a UI or a database, independent of external details such as databases, user interfaces, and external services.
do: Drive the core from primary actors (a webhook, a UI request, a test script) and reach secondary actors — a Repository (e.g. a database) or a Recipient (e.g. a message queue) — only through ports.
never: Open a database connection, render a UI, or call an external service from core code.
because: The pattern's stated payoff is isolation of concerns, making the system easier to test, maintain, and evolve; the source attributes it to Dr. Alistair Cockburn, 2005.

### CS-09 · Smallest container that fits
rule: Encapsulate reusable code blocks in functions; model objects and behaviors in classes; group related functions and classes in modules; store modules and other resources in files; form a package from multiple related modules when code is complex, high risk, or reusable between projects.
do: Keep every piece of logic in exactly one place; separate code into logical units that perform specific tasks or represent specific concepts.
never: Create a class or package with no related neighbour — grouping requires related elements.

### CS-10 · Refactor structure, never behaviour
rule: Refactoring improves code structure without changing its functionality.
do: Extract variables, functions, classes, or modules to reduce repetition; rename to make elements meaningful and consistent; move code between locations or files to improve cohesion and reduce coupling; simplify expressions, conditions, loops, or statements.
never: Bundle a behaviour change into a restructuring change.

### CS-11 · Follow the language and framework standard
rule: Adhere to the standards and best practices of your language and framework — PEP 8 for Python, PSR for PHP.
do: Use one consistent indentation convention — four spaces for Python, two spaces for JavaScript.
never: Mix conventions within a single project.

### CS-12 · Keep the project structure clean
rule: Each project lives in its own folder with a descriptive name, separating raw data, documentation, source code (`src/`), and results.
do: Use the stated layout — `README.md`, `requirements.txt`, `data/`, `docs/`, `results/`, `src/` — and keep code used by multiple projects in its own separate folder.
never: Mix operational input/output folders into the code base, or duplicate shared code across project folders.

### CS-13 · Filenames that locate and order files
rule: One filename convention, applied consistently above all else.
do: Short, descriptive, human-readable names; no spaces — underscores or dashes; dates as YYYY-MM-DD largest unit first (2020-10-15_data_input); zero-padded numbers reflecting the expected number of files (001, not 1); numeric prefixes where ordering is logical (001_introduction, 002_methodology, 003_results).
never: Use day-first dates, spaces, or unpadded numbers in filenames.

### CS-14 · Raw data is read-only
rule: Never alter raw data — treat it as read-only and keep an immutable store for it.
do: Run cleaning on a copy of the raw data, so you can document which cleaning decisions have been made; separate operational input/output folders from the code base.
never: Overwrite a raw input file in place.

### CS-15 · Outputs are disposable
rule: You must be able to delete any output and regenerate it easily by re-running your pipeline.
do: Delete and regenerate outputs frequently while developing — if you fear deleting a result, you lack confidence in reproducing it.
never: Keep an output you cannot regenerate.

### CS-16 · Structure work as a DAG, run it end to end
rule: Model the project as a Directed Acyclic Graph — start from input data, finish with outputs, and in between no lines that link backwards.
do: Run scripts from end to end so code executes in the same order each time in a clean environment.
never: Depend on variables or objects left over from a previous run — a common source of errors.

### CS-17 · Reuse one project template
rule: Keep structure consistent across projects so team members can quickly orient themselves.
do: Start new projects from a project template (cookiecutter-style) that lays out the standard folders, documentation, and test directories.
never: Invent a new folder layout for every project.

## Hard numbers

| Constant | Value | Note |
|---|---|---|
| Module/package size, file count, dependency count thresholds | `unknown: true` | The source gives no numeric limit for any of these — no rule of thumb stated |
| Indentation | 4 spaces Python, 2 spaces JavaScript | Stated convention (CS-11) |
| Filename padding | `001` not `1` | Zeros reflect the expected number of files |
| Date format | YYYY-MM-DD, largest unit first | `2020-10-15_data_input`, not `15-10-2020` |
| Typical layered structure | 5 named layers | presentation, service, domain, data access, infrastructure |
| Hexagonal root packages | 3 (`core`, `adapters`, `config`) | plus the application entry class |
| Hexagonal pattern origin | Dr. Alistair Cockburn, 2005 | As stated in the source |

## Decision procedure

When adding or reorganising code, work in this order:

1. **Axis** — name the feature this code belongs to; put it in that feature's package (CS-01).
2. **Purpose** — state the target package's single purpose in one phrase (CS-03).
3. **Dependency** — list what must become public and which packages must change for this to work (CS-04).
4. **Direction** — confirm `core` still depends on nothing and adapters never import `config` (CS-06).
5. **Container** — pick the smallest unit that fits: function → class → module → file → package (CS-09).
6. **Hygiene** — raw inputs untouched, outputs regenerable, pipeline runs end to end from a clean environment (CS-14–CS-16).
7. **Convention** — language standard, filenames, and project template all match (CS-11, CS-13, CS-17).

## Anti-patterns

- `controllers/`, `services/`, `repositories/` as top-level packages holding unrelated features.
- A class set to `public` only because another layer needs it.
- One package holding unrelated classes with no stated purpose.
- `core` importing config, an adapter, a database, or a UI.
- A fourth top-level package beside `core`/`adapters`/`config`.
- Database tables driving the design instead of domain entities.
- Raw input edited in place; a result file that cannot be regenerated.
- A pipeline step that needs variables left over from a previous run.
- Shared helpers copied into several project folders.
- A fresh folder layout invented for every project.

## Review checklist

- [ ] Every package has one stated, well-defined purpose (CS-03)
- [ ] A feature's controller, service, repository, and domain classes sit together (CS-01)
- [ ] No class is public solely for another package's benefit (CS-04)
- [ ] Dependencies follow the core/adapters/config table; core depends on nothing (CS-06)
- [ ] Ports declared in core, implementations in adapters, wiring in config (CS-07)
- [ ] Core has no database, UI, or external-service calls (CS-08)
- [ ] Raw data untouched; every output regenerable (CS-14, CS-15)
- [ ] Pipeline runs end to end in a clean environment (CS-16)
- [ ] `data/`, `docs/`, `results/`, `src/` separated; shared code in its own folder (CS-12)
- [ ] Filenames consistent, dated YYYY-MM-DD, zero-padded (CS-13)
- [ ] Language/framework standard followed (CS-11)
- [ ] Structure matches the team's project template (CS-17)

## Caveats

- Siblings: this file covers module/package/file organisation; `clean-code.md` covers naming and readability; `solid.md` and `single-responsibility-principle.md` cover object and class-level design (cohesion is stated to be very related to the SRP).
- These are engineering conventions, not findings: the source supplies **no empirical evidence** — no measured coupling effects, no defect correlations, no sample sizes, no study citations; evidence for the coupling/cohesion and package-style claims: `unknown: true`.
- The claimed benefits and disadvantages of package-by-layer, package-by-feature, and hexagonal architecture are the source author's assertions, not measurements.
- Numeric thresholds for module size, file count, and dependency count are absent from the source: `unknown: true` — do not quote a rule of thumb as sourced.
- Dropped as out of scope: the "how to test" material (unit/integration/system/regression and frameworks), the general best-practices article (naming, comments, Git, security, performance, linters, AI assistants), and the learning-resources/promotional sections.
