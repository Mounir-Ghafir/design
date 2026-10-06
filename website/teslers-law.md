---
name: teslers-law
title: Tesler's Law (Conservation of Complexity) — Design Rules
description: Rules for deciding where irreducible complexity lives — in the user or in the system. Load when simplifying an interface, choosing what to automate or default, deciding whether engineering time is worth removing user friction, estimating the value or cost of complexity, cutting features, or reviewing UX.
applies_when: [simplification, feature planning, automation decisions, settings and defaults, cost-benefit analysis, complexity review, ux review]
priority: core
rules: 13
---

# Tesler's Law (Conservation of Complexity) — Design Rules

## Core principle

Every process has a core of complexity that **cannot be designed away** — it can only be moved: into the user interface or into the workflows of designers and developers. Your job is to decide **where it lives**, not to pretend it is gone.

```
irreducible complexity  = the core that must stay → borne by someone
the only question       = who bears it: the user, or the system
your job                = absorb as much as you can; leave users only what is inherently theirs
```

History, stated exactly: **Larry Tesler** (1945–2020, computer scientist specialising in human-computer interaction; worked at Xerox, Apple, Amazon, Yahoo!; co-creator of copy-and-paste) formulated the law in the **mid-1980s while at Xerox PARC**, where he helped develop the "language of interaction design". He later joined **Apple**, worked on the **MacApp** object-oriented framework, and created the law to sell interface standards to Apple management and independent software vendors — and, above all, to reduce complexity for customers. Tesler's own words: "every application must have an inherent amount of irreducible complexity. The only question is who will have to deal with it."

## Rules

### TL-01 · Complexity is conserved, not removed
rule: For any system there is an amount of complexity that cannot be reduced — you only choose where it lives.
do: Treat every design change as a transfer of complexity, never a deletion.
never: Claim a redesign "removed" complexity you actually pushed elsewhere.
because: What leaves the UI lands in your development team's workflows.

### TL-02 · Assign every complexity a bearer
rule: Every irreducible complexity must be explicitly borne by the user or by the system.
do: Name the bearer for each complex step: a user action or a mechanism your team builds.
never: Leave complexity unassigned — unassigned complexity defaults to the user.
because: The only question the law asks is who will have to deal with it.

### TL-03 · Lift as much burden from users as you can
rule: Deal with inherent complexity during design and development so the burden leaves the user.
do: Pre-fill, suggest, automate, and default anything the user should not have to reproduce.
never: Ship complexity the team could absorb just because the interface still works.
because: A modern email client pre-populates the sender and suggests recipients — the sender/recipient complexity is absorbed, not gone.

### TL-04 · Leave users only what is inherently theirs
rule: The user bears complexity inherent to their own task; the system bears what can be implemented or automated.
do: Keep the decisions only the user can make (intent, choices, knowledge); move everything representable in software to the system.
never: Require the user to supply or remember what the system already knows.
because: An email still needs a stated recipient; the "from" field can be filled automatically.

### TL-05 · Delete complexity by deleting features
rule: The one way to remove complexity entirely is to remove the feature that carries it.
do: Cut low-value features outright — they add interface clutter.
never: Treat feature removal as the only lever; within a kept feature, complexity only transfers.
because: Clutter makes users hunt for what they need, reduces efficiency, and increases perceived difficulty.

### TL-06 · Stop at the point of abstraction
rule: Take care not to simplify interfaces to the point of abstraction.
do: Stop simplifying where a "simple" surface starts hiding necessary information or control the user still needs.
never: Trade usability and clarity for a cleaner-looking screen.
because: An interface simplified past usefulness produces confusion exactly where it looks easiest.

### TL-07 · Cost the trade with user-time arithmetic
rule: Decide whether the system should absorb complexity by estimating the value or cost to users.
do: Multiply frequency per week × active users per week × value or cost per encounter; use any timeframe that fits (week, year, lifetime).
never: Decide the system/user trade on engineering convenience alone.
because: Tesler: "unless you have a sustainable monopoly position, the customer's time has to be more important to you than your own."

### TL-08 · Smart defaults come with absorbing complexity
rule: When the system handles complexity, the system chooses — so its defaults must be smart.
do: Invest in correct, editable defaults; treat them as a core part of the feature.
never: Automate a decision the system will get wrong more often than the user would.
because: Bad defaults ruin a simplified product — when the system decides wrong, the user blames the product.

### TL-09 · Absorbed complexity costs engineering and maintenance
rule: Complexity shifted to the system is real work: build it up front and maintain it.
do: Budget engineering effort and ongoing maintenance for every complexity you automate.
never: Assume automation is free because the user no longer sees it.
because: A checkout-free store removes friction for the shopper; the machine-learning, computer-vision, and AI complexity is paid for by the team that makes it work.

### TL-10 · Amortise the cost with standards
rule: Absorb complexity once, then reuse it.
do: Encapsulate repeated mechanisms in shared libraries and interface standards.
never: Pay the engineering price per product for complexity you could build once.
because: Tesler's original (economic) argument: standards and consistency reduce time to market and code size — benefiting users and developers.

### TL-11 · Don't design for an idealized, rational user
rule: Real users are not rational optimisers.
do: Design for people who start using the product immediately and behave irrationally in real life.
never: Justify a design on the assumption users will read the manual or follow the intended path.
because: The paradox of the active user: users skip manuals and start using software, even into errors.

### TL-12 · Admit your complexity bias
rule: You naturally favour complex solutions; treat that preference as a warning signal.
do: When a solution feels intricate, suspect you don't yet understand the problem; deepen understanding through observation and experience.
never: Pick complexity because it reads as intelligent, thorough, or expert.
because: A 1989 Farris & Revlin hypothesis experiment showed most people adopt complicated rules when a simple one fits; more assumptions means greater chance of failure.

### TL-13 · Guidance belongs in the context of use
rule: Users who still bear operational complexity need in-context help.
do: Embed guidance — e.g. tooltips with helpful information — where the user is working, reachable from any path.
never: Rely on manuals or out-of-context documentation to carry the load you abstracted away.
because: Guidance must fit the context of use to help active new users no matter which path they take.

## Hard numbers

| Quantity | Value | Note |
|---|---|---|
| Key formula | encounters/week × active users/week × value-or-cost per encounter | method for costing a complexity trade-off |
| Worked example (verbatim) | 3 × 1,000,000 × 0.5 min = 1,500,000 s = 25,000 min = 416 h ≈ just over 17 days (per week) | per-week user time returned |
| Decision rule | "unless you have a sustainable monopoly, the customer's time has to be more important to you than your own" | Tesler, via Saffer interview |
| Sanity check (source) | 1,000,000 users × 1 wasted minute/day vs 1 engineer-week to remove it | "you are penalizing the user to make the engineer's job easier" |
| Irreducible core | "every application must have an inherent amount of irreducible complexity" | Tesler's postulate, not a measurement |
| Origins | Mid-1980s, Xerox PARC; formalised at Apple on MacApp | Tesler 1945–2020, co-creator of copy-and-paste |
| Measured complexity, effect sizes, sample sizes | None — `unknown: true` | The law is asserted, not empirically tested |

## Decision procedure

1. **Inventory** — list every step and every decision in the process (TL-01).
2. **Classify** — separate necessary task complexity from complexity your design added (TL-04).
3. **Delete** — cut low-value features outright; their complexity leaves entirely (TL-05).
4. **Assign** — for what remains, name the bearer: user or system (TL-02, TL-03).
5. **Cost** — estimate user time value: frequency × users × unit value (TL-07).
6. **Prepare the system** — if the system bears it: smart defaults, engineering budget, maintenance (TL-08, TL-09).
7. **Reuse** — can the mechanism be built once and shared via standards? (TL-10).
8. **Clarity check** — is the interface past the point of abstraction, and is guidance in context? (TL-06, TL-13).
9. **Self-check** — is the solution's remaining complexity a bias artifact, not a requirement? (TL-12).

## Anti-patterns

- Simplification to the point of abstraction — a clean UI that hides necessary information or control.
- Claiming you "removed" complexity that was silently pushed onto users.
- Absorbing complexity while shipping wrong defaults.
- Automating without an engineering and maintenance budget.
- Re-asking the user for what the system already knows.
- Keeping low-value feature clutter because removing it feels risky.
- Designing for the rational user who reads the manual first.
- Deciding the system/user trade on engineering convenience alone, without estimating user cost.
- Choosing an elaborate solution you selected mainly because of complexity bias.

## Review checklist

- [ ] Irreducible core of the process identified and named
- [ ] Every remaining complexity has a named bearer (user or system)
- [ ] Users bear only complexity that is inherently theirs
- [ ] Low-value features deleted rather than re-skinned
- [ ] User-time value formula run before moving complexity
- [ ] Defaults smart wherever the system decides
- [ ] Engineering effort and maintenance budgeted for absorbed complexity
- [ ] Repeated mechanisms shared via standards, not rebuilt per product
- [ ] Simplification has not crossed into the point of abstraction
- [ ] Guidance available in the context of use
- [ ] Complexity-bias check passed on the chosen solution

## Caveats

- **No empirical evidence.** The source presents conservation of complexity as an assertion/prediction about systems (Tesler "postulated" it), not a measured physical law: no measured complexity values, no effect sizes, no sample sizes — `unknown: true`. The `Hard numbers` are the source's illustrative arithmetic and definitions, not measurements. The only empirical study the source cites is the **1989 Farris & Revlin** experiment supporting the *related* complexity bias; its sample size is not given.
- **Honest framing while designing:** "conservation of complexity" is an observation/assertion about where work lands, not a conserved quantity that can be measured in a design review.
- **Siblings (one line):** `progressive-disclosure.md` covers the *sequencing* technique (records it has NO empirical validation) — this file answers the *conservation* question of where complexity lives; `cognitive-load.md` covers removing extraneous load, including its CL-03 simplicity-must-not-cost-clarity caveat; `paradox-of-active-user.md` covers the active-user paradox named in the source.
- The worked cost-benefit arithmetic (TL-07) is a decision aid, so use it to compare options — not as evidence about any specific system.