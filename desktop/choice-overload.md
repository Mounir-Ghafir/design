---
name: choice-overload
title: Choice Overload — Design Rules
description: Rules for keeping the number and difficulty of presented options inside the range where people still decide. Load when building option lists, menus, plan or tier pickers, filters, settings, recommendations, scoping features, or reviewing a screen that feels indecisive.
applies_when: [option lists and menus, pricing and plan tiers, filters and search, settings, recommendations, product scoping, feature triage, ux review]
priority: core
rules: 18
---

# Choice Overload — Design Rules

## Core principle

Too many options degrades the decision and the mood — but the effect is **conditional, not universal**, and both too few and too many underperform. Aim for the peak, not the floor.

```
none            → very low satisfaction; no comparator (single-choice aversion)
sweet spot      → highest satisfaction; less regret, faster decisions   ← target
beyond the peak → attention draws, then decisions stall; regret rises
```

Peak position: **unknown** — no source quantifies it. Never substitute a made-up number.

## Rules

### CO-01 · Confirm the preconditions before blaming overload
rule: Overload needs all three: no clear prior preference, no clearly dominant option, low familiarity.
do: Check all three before redesigning; if a winner exists or users already know what they want, look elsewhere.
never: Attribute abandonment to option count when one option is obviously best.
because: With a prior preference or a dominant option, option count barely moves decision quality or satisfaction.

### CO-02 · Variety and complexity are different problems
rule: Number of options is *variety* (wanted when browsing); difficulty comparing them is *complexity* (hurts when choosing).
do: Show breadth on discovery surfaces; make comparison cheap at the moment of choice.
never: Cut variety from a browse surface to fix a comparison problem.
because: Purchase is two steps — select an assortment, then choose within it — and each step wants the opposite of the other.

### CO-03 · Aim for the peak, not the floor
rule: Satisfaction is an inverted U; very few and very many both underperform.
do: Retain enough real alternatives to compare against; cut only clear redundancy.
never: Collapse a set to one option.
because: Single-choice aversion (Mochon) and the decoy effect (3 options beat 2) show that removing all comparators degrades the decision.

### CO-04 · Never invent an option-count limit
rule: No numeric optimum exists anywhere in the evidence base.
do: Derive the count for your product by testing option counts against time-on-task and conversion.
never: Quote "7 options", "3–5 options", or any fixed cap as a finding.

### CO-05 · Nudge, don't delete
rule: Manage overwhelm with choice architecture — organize, group, highlight, recommend.
do: Keep the catalogue; change what is visible, what leads, and how it is grouped.
never: Remove options to "help" users unless they asked you to.
because: Users want content organized and curated, not deleted — but deletion argues the same goal from the other side. Record the tension; do not resolve it by dogma.

### CO-06 · Filter first, then choose
rule: Narrowing tools come before the moment of choice, not after it.
do: Search, filters, sort, category entry points above the list.
never: Make users scroll an entire set to reach something comparable.
because: The purchase is staged — select an assortment, then choose within it.

### CO-07 · Recommend, curate, and spotlight
rule: Decide what appears at this moment and what leads it.
do: Featured item, recommended plan, personalized rows from history, prominent placement of the good option.
never: Give every option equal visual weight and call it neutral.

### CO-08 · Make comparison possible side by side
rule: If users must compare, let them compare directly.
do: Aligned attribute tables for tiers and plans; shared axes for products.
never: Force comparison across tabs, pages, or from memory.
because: Complexity — not count — is the negative side of an assortment, and it lives in the comparison.

### CO-09 · Set the default; offer second-order decisions
rule: A sensible default and a saved routine both cut future choice cost.
do: Preselect a plan, mark a recommended option, let users set a standing preference.
never: Make users re-decide a settled question on every visit.
because: Fatigue pushes people onto defaults, and a second-order decision buys off all the later ones.

### CO-10 · Move the decision earlier
rule: The choice is cheapest before the user arrives at it.
do: Order ahead, saved routines, a short menu before the counter.
never: Put a wide-set, high-stakes decision at the moment of arrival.
because: NN/g soda fountains — 100+ flavours, multi-level menus — turned a sub-10-second task into more than a minute (>500% inflation); families with children and elderly users gave up and left.

### CO-11 · "No decision" stays available
rule: Under pressure many people prefer no choice at all; that is a valid path, not a failure.
do: Offer skip, defer, "not now", save-for-later, and a visible exit at every choice point.
never: Block progress or the exit until a choice is made.

### CO-12 · Commitment and time set tolerance
rule: People who already paid tolerate inefficiency; people on a phone delete.
do: Assume low commitment and low time on web/mobile; assume more tolerance after purchase.
never: Port a counter-ordering experience into an uncommitted browse context unchanged.
because: Large sets feel harder under time pressure and yield more regret; more time makes large sets more enjoyable.

### CO-13 · Choosing for others reverses the effect
rule: Proxy decision-makers tolerate more options, not fewer.
do: When someone is choosing for another person, do not aggressively narrow the set.
never: Apply self-choice rules unchanged to gift, group, or delegated purchasing.
because: Polman reports the effect reverses for proxy decision-makers; the regulatory-focus mechanism behind it is unverified (`[citation needed]` upstream).

### CO-14 · Maximizers regret; satisficers take the first acceptable option
rule: The paradox hits maximizers hardest; satisficers stop at the first good-enough option.
do: Anticipate regret — show why this option is right, add confidence cues, expose settled defaults.
never: Build a flow that lets a maximizer reopen a decision they already made.
because: Maximizers also carry the largest opportunity cost, and more options make it larger.

### CO-15 · Charge every feature its full cost
rule: Each added feature costs decisions, explanation, and error risk — plus maintenance and support load.
do: Keep a running total per feature: cognitive cost, error risk, maintenance, support burden.
never: Add a marginal feature to an already satisfactory solution ("featuritis").
because: Features compound in the mental model and crowd screens so the target option is harder to notice.

### CO-16 · Don't over-feature a simple need
rule: If the task is trivial, the interface should be too.
do: Match capability to task; strip customization nobody pays for.
never: Subject the majority to complexity to satisfy a few enthusiasts.
because: The same feature set is beloved where customization is the value and commitment is high, and hated where it isn't — context decides, not count alone.

### CO-17 · Measure time-on-task, not stated appeal
rule: Breadth attracts; behaviour decides.
do: Watch time-on-task, errors, abandonment, and post-choice regret; test option counts against each other.
never: Accept "looks great" or survey appeal as proof that a larger set works.
because: People enjoy large choice sets while regretting them — stated appeal and outcome pull apart.

### CO-18 · Cite this as conditional evidence, never as law
rule: The empirical status is contested and average effects are weak.
do: State the preconditions whenever you invoke the paradox; name the counter-evidence.
never: Present the effect as settled, or quote a "proven" conversion lift.
because: Critics — including meta-analytic work arguing the effects are small and average out — dispute the base, and the original studies have been questioned. The source does not name these critics. Unresolved.

## Hard numbers

| Constant | Value | Note |
|---|---|---|
| Iyengar & Lepper jam display (2001) | **24 vs 6** varieties | More shoppers stopped at the 24-display; the 6-display bought more. Purchase rates, sample sizes, and replication status are **not recorded** in the source (`unknown: true`) — do not quote a rate |
| 401(k) participation (Iyengar, Jiang & Huberman, 2004) | ~**800,000** records; **−up to 2%** participation per **+10 funds** | 2 funds peaked at **75%**; 59 funds fell to as low as **60%**; fewer than 10 funds clearly beat more |
| Cafeteria choice-architecture study | 2 years; visibility + accessibility of healthy food raised healthy sales | Direction only — no author, venue, or effect size (`unknown: true`) |
| Soda fountain (NN/g, Loranger, 2015) | **100+** flavours; **<10 s** normal task vs **>1 min** on the machine (**>500%**) | Observational, not controlled |
| Optimal option count | **None established** | The inverted-U peak and Schwartz's "magic number" are never quantified |
| Hick's Law | Decision time rises with option count | Related but distinct — see the cognitive-load skill for load-side work |

## Decision procedure

1. **Preconditions** — no prior preference, no dominant option, low familiarity? If any fails, option count is probably not your problem.
2. **Stage** — is this browsing (variety) or choosing (complexity)? Fix the failure that matches the stage.
3. **Inventory** — list visible options; mark near-duplicates as the first removal candidates, never comparators.
4. **Compare cost** — can users compare on shared axes side by side? If not, that is the overload, not the count.
5. **Narrowing** — are search, filters, and grouping available before the choice point?
6. **Default and exit** — is there a visible default, featured option, or recommendation, and can the user decline or defer without deciding?
7. **Context** — commitment, time pressure, expertise, choosing for someone else? Re-check before cutting anything.
8. **Measure** — time-on-task, errors, abandonment, regret. Iterate the count; never assume a target.

## Anti-patterns

- A fixed "max N options" rule justified by the paradox.
- Deleting options users might want instead of organizing them.
- A single-option screen with no comparator, or scroll-to-compare lists with no side-by-side view.
- 100+ flavour customization on a task that takes seconds.
- Equal visual weight everywhere, no default, and a blocked exit.
- Cutting browse variety to solve a comparison problem.
- Citing the jam study as proof rather than as conditional evidence.

## Review checklist

- [ ] Preconditions checked before attributing failure to overload
- [ ] Option count justified for its stage (browse vs choose)
- [ ] Near-duplicates removed; real comparators retained
- [ ] Side-by-side comparison available where comparison is required
- [ ] Search, filter, and grouping available before the choice point
- [ ] A visible default, featured option, or recommendation
- [ ] Nudging preferred over deleting options; skip, defer, and exit available
- [ ] Presentation matched to stage: imagery to browse, concise copy to choose
- [ ] Guidance and defaults present for complex or high-stakes decisions
- [ ] Marginal features and advanced settings deferred or hidden
- [ ] Context checked: commitment, time, expertise, proxy decision-maker
- [ ] Time-on-task measured, not stated appeal
- [ ] Effect described as conditional; no invented option-count number quoted

## Caveats

- **Unresolved conflict — empirical status.** Critics, including Scheibehenne et al.'s meta-analytic work arguing the effects are small and average out, dispute the base, and the original studies have been questioned. The source presents both sides with no adjudication. Treat the effect as conditional; never present it as settled.
- **No magic number.** The inverted-U peak and Schwartz's "magic number" are never quantified anywhere in the source — `unknown: true`. Never quote 7 options or 3–5 options from this file.
- **Jam study.** The 24 vs 6 conditions are source-reported. The reference records **no purchase-rate figures, sample sizes, or replication status** for it — `unknown: true`. Do not quote purchase percentages from this skill.
- **Missing figures.** Cafeteria study: two-year duration and direction only, no author, venue, or effect size. Soda-fountain and dating-app accounts (NN/g, Loranger) are illustrative, not controlled. Both `unknown: true`.
- **Polman's regulatory-focus mechanism.** Carries an upstream `[citation needed]` tag; only the reversal itself is asserted.
- **Variety vs complexity.** Resolved only by the two-stage model, not by a single rule; the source gives no guidance for sets that are large *and* varied at both stages at once.
- **Miller's ~7** is a 1956 memory figure, not an option-count rule for recognition-based menus.
- **Hick's Law** (decision time rises with option count) is related but distinct — for load-side option-count work, use the cognitive-load skill.
- Many countermeasures here are practitioner heuristics, not controlled results.
- Conflicts and evidence limits are recorded above. Check them before defending a rule in review.