---
name: occams-razor
title: Occam's Razor — Design Rules
description: Rules for cutting a design down to only what earns its place, and for knowing when to stop cutting. Load when simplifying a screen or flow, reviewing your own work, deciding whether a feature or element is necessary, choosing between a simple and an elaborate solution, or writing copy.
applies_when: [simplification, feature scope, ui review, navigation, forms and flows, copy and language, design critique, trade-off decisions]
priority: supporting
rules: 14
---

# Occam's Razor — Design Rules

## Core principle

Among competing hypotheses that predict equally well, the one with the fewest assumptions should be selected.

```
HYPOTHESIS   = an explanation of why something happens
RAZOR        = when two explanations predict equally well, prefer the one assuming less

DESIGN MOVE  = entities must not be multiplied beyond necessity
```

This is a **logical** principle for ranking explanations, not an empirical finding about users. It works best as a working model for reaching an initial conclusion before full information is available.

## Rules

### OR-01 · Start simple, add only on demand
rule: Begin from the simplest design that satisfies the requirement; add complexity only when a named need forces it.
do: Ship the stripped version first; never multiply entities beyond necessity; record every later addition with the reason it was necessary.
never: Add a feature, animation, second nav pattern, or option to fix a failure you cannot name.
because: The best method for reducing complexity is to avoid it in the first place.

### OR-02 · Ask the minimum-UI question for every element
rule: Every element must pass this test: what is the minimum amount of UI that lets the content be found and effectively communicate itself?
do: Run the test element by element; anything that fails is a removal candidate.
never: Keep an element because it looks deliberate or intentional.
because: Detail added on the assumption that it enhances experience often distracts and confuses instead.

### OR-03 · Edit ruthlessly
rule: Cut every element and pattern that has no meaning or provides no value.
do: Replace any element for which a simpler equivalent exists; hold your own work to a critique.
never: Retain an element because it is familiar, liked, or already built.
because: Perfection is achieved not when there is nothing more to add, but when there is nothing left to take away.

### OR-04 · Test the removal, never estimate it
rule: Every proposed cut must be verified against overall function, not judged by feel.
do: Remove the element, then check: task still completable? message still communicated? A-to-B still traversable? Restore exactly what fails.
never: Delete an element on the reasoning that "it can't be that important".
because: Removing as many elements as possible is only valid without compromising the overall function.

### OR-05 · Removing an element is not removing a requirement
rule: The razor prunes implementation. It never prunes what the product is required to do.
do: Before each cut, ask whether the element fulfils a stated requirement or is a redundant extra.
never: Remove an affordance, label, state, or feedback to make a screen look cleaner.
because: A dropped requirement is a scope decision, not a simplification; only the extra is removable complexity.

### OR-06 · Sort necessary from accidental complexity
rule: Classify each part as necessary (the user or domain genuinely requires it) or accidental (it exists for a reason nobody can state).
do: Accidental becomes a removal candidate; necessary stays, however complex it looks.
never: Cut something you have not classified.
because: Without the classification, "simple" is just an opinion about how the screen looks.

### OR-07 · Stop only at zero remaining cuts
rule: The design is complete when no additional item can be removed.
do: Re-run the removal test until a complete pass produces zero cuts; that is the stopping condition.
never: Call the work done while a removable item survives a full pass.
because: Consider completion only when no additional items can be removed.

### OR-08 · Overrule your own complexity bias
rule: Do not credit an option for being elaborate; complexity is not evidence of quality.
do: Produce the simplest option that satisfies the requirement, then compare against the elaborate one.
never: Choose the harder option because "that will never work" on the simple one.
because: Complexity bias is the flight response — the more impenetrable the solution, the less you must understand.

### OR-09 · Chaos is not complexity
rule: Before pruning an irregular pattern, decide whether it has order or is merely unpredictable.
do: Treat unexplained irregularity as something to investigate, not as clutter to strip.
never: Remove an element only because you cannot articulate why it works.
because: Mistaking chaos for complexity invents an order and predictability that is not warranted.

### OR-10 · Simplify copy, keep specialist meaning
rule: Remove jargon that has plain substitutes; keep a precise term its own audience already uses.
do: Rewrite everyday copy as briefly as possible so the widest audience can be reached.
never: Simplify language for people who use the technical term correctly.
because: Jargon works as a shortcut only when all parties involved know the code.

### OR-11 · Simplicity is not the target
rule: Aim at the level of complexity that keeps people engaged, not the lowest level reachable.
do: Keep the parts that carry meaning or provide value; expect expert users to need more of it.
never: Flatten a product until it is boring and uneventful.
because: Too simple and we are bored, too complex and we are confused, and the ideal level moves as expertise grows.

### OR-12 · Simplification must not cost clarity
rule: A simpler design that is harder to understand or harder to traverse is a failed simplification.
do: Test with a non-designer and with an older or low-vision user; keep whatever they need.
never: Ship a striking design that compromises the clarity of the message or the ease of getting from A to B.
because: A good design should not compromise the strength of the structure or block the route through it.

### OR-13 · Evidence outranks simplicity
rule: Simplicity selects between equally-supported options; it never substitutes for evidence.
do: Back the simpler option with evidence or label it explicitly provisional; confirm the base rate for rare or novel cases.
never: Argue "it's simpler" as the entire justification for an important or risky decision.
because: Think horses, not zebras — unless you are on the African savannah; new data also legitimately allows more complexity.

### OR-14 · Use it alongside other models, never alone
rule: The razor shortens reasoning; critical thinking still does the work.
do: Pair it with fundamental error distribution, Hanlon's razor, confirmation bias, availability, and hindsight bias.
never: Apply it without checking your own confirmation bias.
because: Mental models tend to interlock and work best in conjunction.

## Hard numbers

| Constant | Value | Note |
|---|---|---|
| Removing an element | **Test, never estimate** | The source gives no removal count, ratio, or threshold |
| Benefit of a simpler interface | **unknown: true** | No effect size, sample size, study, author, venue, or date |
| Preferred level of complexity | **unknown: true** | Attributed to "psychologists" with no citation; stated to rise with expertise |
| 37signals (the source's only worked example) | **Three-person web design consulting firm in 1999; three million worldwide users; 16 employees** | Business scale, not evidence about users |

## Decision procedure

1. **State the requirement** — one sentence the screen or flow must accomplish. Everything not serving it is a candidate.
2. **Ask the minimum-UI question** — per element: what is the least UI that lets the content be found and communicate itself?
3. **Classify** — necessary (user or domain requires it) or accidental (nobody can say why it is there).
4. **Propose one cut** — a single element per pass, decoration first, structure last.
5. **Test the removal** — task completable? message communicated? A to B traversable? usable by an older or low-vision user? Restore exactly what fails.
6. **Log what survived** — write down the assumption that justified each remaining complex part; that note is your review trigger.
7. **Repeat to zero** — keep going until a complete pass returns no cuts. That, and only that, is completion.
8. **Audit your own bias** — was complexity rewarded rather than tested? Is the residual pattern ordered, or chaos you are reading as design?

## Anti-patterns

- Adding animations, an offscreen nav, or another option to "enhance" an experience with no named failure behind it.
- Treating a dropped requirement as removable complexity, or deleting an element you never tested.
- Declaring the work done while a removable item survives a full pass.
- Choosing the elaborate option because the simple one "will never work".
- Simplifying jargon for everyone, or precision for specialists.
- Running the razor alone on a high-stakes, rare, or novel decision.

## Review checklist

- [ ] Requirement stated in a single sentence
- [ ] Every element answers the minimum-UI question and is classified necessary vs accidental
- [ ] Every cut tested against function, not estimated
- [ ] Task completable, message communicated, A to B still traversable
- [ ] Checked with a non-designer and with an older or low-vision user
- [ ] No requirement or affordance removed to make a screen look clean
- [ ] Retained complexity carries a written justification and a review trigger
- [ ] A full removal pass returns zero cuts
- [ ] Simplest option built and compared against the elaborate one
- [ ] Residual irregularity is ordered, not chaos read as design
- [ ] Copy plain for the general audience, precise for specialists

## Caveats

- The source contains **no quantitative data** — no effect sizes, sample sizes, studies, authors, venues, or dates. All such figures are `unknown: true`; the 37signals numbers are business scale, not evidence.
- Occam's razor is a **logical principle, not an empirical finding about users**. Nothing here shows that a simpler UI is faster, clearer, or preferred; for that, use `cognitive-load.md` and `chunking.md`.
- **"Fewest assumptions" ranks explanations, not design decisions.** It chooses between models of the world that predict equally well; using it to justify shipping the visually simplest option is a category error — the option set and the hypothesis set are different sets.
- The source states plainly that **the simplest model is sometimes not the correct one**: the world contains things that "don't seem necessary to any physical processes" yet exist. Simplicity raises the probability of being right; it never establishes it.
- The default only holds when the two options **predict equally well**. For high-stakes, rare, or novel situations, verify the base rate instead of assuming it.
- **Simplicity still costs work.** It is easier to falsify but not free, and a conclusion resting on simplicity alone needs empirical backing — "simple is as simple does".
- **Too much simplicity is a failure mode**: people prefer a middle level of complexity, and the preferred level rises with expertise (attribution uncited, `unknown: true`).
- **Watch for confirmation bias while applying it** — the moon-landing example shows the same razor used to justify either side of a claim.
- A designer's own ease is not the target: pros **impose constraints deliberately** to produce a better product. Constraint is a design choice, not a regression.
- `cognitive-load.md` covers removing extraneous cognitive load; its CL-03 covers "simplicity must not cost clarity", the caveat this file leans on hardest (OR-12).