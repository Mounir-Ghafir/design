---
name: hicks-law
title: Hick's Law — Design Rules
description: Rules for cutting the time a user spends deciding by cutting the number and complexity of choices on screen. Load when a screen or flow offers too many options, when building navigation or landing pages, when splitting a long process into steps, writing onboarding, or reviewing a flow where users stall.
applies_when: [option lists, navigation, landing pages, forms and checkout, onboarding, menus, feature discovery, ux review]
priority: supporting
rules: 17
---

# Hick's Law — Design Rules

## Core principle

Decision time rises with the number **and** the complexity of choices.

```
RT = a + b log2 (n)
```

`RT` = reaction time, `n` = number of stimuli present. `a` and `b` are arbitrary measurable constants that depend on the task and its conditions. Hick and Hyman, 1952. Growth is logarithmic in `n`.

Two things that are easy to get wrong: removing options reduces decision time but does not remove the decision; and reducing count *and* complexity together is what moves `RT`.

## Rules

### HL-01 · Minimise options when response time is critical
rule: When the user must decide fast, keep visible options small — one to five is a good rule of thumb.
do: Apply it to critical-response surfaces: landing pages, quick actions, primary navigation.
never: Fan out fifteen equally prominent options where one tap must land correctly.
because: Stated as a rule of thumb, not a derived threshold.

### HL-02 · Count complexity, not just option count
rule: Complexity counts as much as quantity — fewer hard-to-compare options beat more easy ones.
do: Rate each option by how much the user must read, infer, or compare before choosing it.
never: Treat "12 options" as a number while ignoring that each one is dense, jargon-laden, or unscoped.
because: The principle names number *and* complexity; `n` alone does not.

### HL-03 · One decision per screen
rule: Rationalise presenting only part of a complex process at any one time.
do: Split a long checkout into e-mail/password, then cart details, then delivery information.
never: Show an entire payment process as one long, complex form.
because: Fewer options per screen makes completion more likely than mid-flow abandonment.

### HL-04 · Do not over-chunk
rule: Splitting into too many small steps causes drop-off before the goal is reached.
do: Merge adjacent steps that each asked for one trivial answer.
never: Turn one action into a ten-screen wizard "because it keeps options low".
because: The source is explicit that over-chunking drives abandonment too.

### HL-05 · Highlight the recommendation, and count distraction as a choice
rule: Mark the intended option so it stands out from the clutter; treat anything competing for attention as an added option.
do: Use visual weight and position for the recommendation; strip promo content, competing CTAs, and adjacent nav from a decision screen.
never: Offer options of equal perceived hierarchy, or leave a second goal on a screen whose only job is one decision.
because: Equal-weight options cause analysis paralysis; distractions act like extra choices and slow response time.

### HL-06 · Progressive onboarding for new users
rule: Teach the core action consequence-free, then reveal features as the user succeeds.
do: Hide everything except the single input needed; introduce the next capability only after the first is learned.
never: Drop a new user into a fully featured app after a few onboarding slides.
because: Slack's pattern: a bot prompts, one input is exposed, features follow.

### HL-07 · Never simplify into abstraction
rule: Simplify the choice, not the meaning behind it.
do: Keep the words users need to tell options apart; cut only the decoration around them.
never: Reduce a differentiated product line to unnamed, undifferentiated tiles.
because: Losing the meaning of a choice costs more than the decision time you saved.

### HL-08 · Group options into high-level categories
rule: Offer categories that expand on selection, not a flat list of every destination.
do: Model navigation as sections in a library. For very large volumes, break it into small, discrete clusters.
never: Expose direct links to every page in the product from one menu and rely on scrolling.
because: Flat access to every link turns a fast task — a last-minute present, a printer cartridge — into a scroll marathon.

### HL-09 · Card-sort before you sketch
rule: Derive groupings and category labels from users, not from the org chart.
do: Run open or closed card sorting (paper or tools such as Optimal Workshop) before sketching or wireframing.
never: Fix category names first and validate them afterwards.
because: Card sorting reveals the categories that actually make sense to users.

### HL-10 · Move complexity off the control, into the interface
rule: Keep the physical or on-surface control minimal; let the screen hold the complexity.
do: Progressive-disclose information through menus on the interface the user is already looking at.
never: Add buttons to a handheld remote to reach features that menus can present.
because: The Apple TV remote pattern — minimal controls, complexity organised on the TV interface.

### HL-11 · Minimise choices on the landing page
rule: The first screen is make-or-break: one goal, minimum content.
do: Lead with the primary or best-selling option and one well-placed image; organise the copy carefully.
never: Put the full catalogue, all filters, and secondary navigation on the landing page.

### HL-12 · Defer options until after commitment
rule: Remove options from the entry screen; add them once the user has committed.
do: Put refinement tools on the results page, not on the page asking for the query.
never: Offer filters before there is anything to filter.
because: Entry is for the single action; refinement comes after.

### HL-13 · Keep the original query visible
rule: Re-display the input the user committed to on every subsequent screen.
do: Keep the search term pinned at the top of the results page.
never: Make the user re-enter or recall what they already told you.
because: The more decisions being made, the less likely items set in working memory are quickly recalled.

### HL-14 · Preserve expert paths — complexity is sometimes unavoidable
rule: Minimise the decision-making process; do not attempt to eliminate it.
do: Keep the dense control set where the domain requires it, and simplify by organising rather than deleting.
never: Strip a professional tool to a consumer-app feature count because fewer buttons look cleaner.
because: A DSLR camera carries far more controls than a smartphone camera, and that is not a mistake.

### HL-15 · Know when not to apply it
rule: Hick's Law does not apply to decisions requiring extensive reading, research, or extended deliberation.
do: For comparing products, trip options, or menus, provide depth, detail, and comparison tools instead of fewer options.
never: Force a deliberative choice — booking a holiday, choosing a restaurant — into three opaque tiles.
because: For complex choices the prediction fails; it covers simple, quick decisions in the right context.

### HL-16 · Cap navigation depth
rule: A 2–3 way branch repeated down 10 levels is a defect.
do: Flatten depth first, then reduce the width of each branch.
never: Build a deep binary-choice tree where reaching the target needs 10 or more clicks.
because: Users abandon long before they reach the information they need.

### HL-17 · Measure the effect after launch
rule: Confirm it in metrics; do not assume the simplification worked.
do: Watch time on site (too little = left without deciding; too much = drifted off goal) and page views (too complex a navigation lowers them). Use eye-tracking heat maps to find where attention leaks and re-apply the law there.
never: Read a rising page-view count as success when it came from click depth.
because: Design decisions have to be confirmed against metrics.

## Hard numbers

| Constant | Value | Note |
|---|---|---|
| Formula | `RT = a + b log2 (n)` | The only form given. No `n+1` variant appears |
| Growth | Logarithmic in `n` | Stated, not fitted |
| `a`, `b` | Arbitrary, task- and condition-dependent | **No values given** — no 0.05, no 0.01 coefficient appears |
| Options when response time is critical | **1–5** | "A good rule of thumb", not an optimum |
| Navigation depth to avoid | 2–3 choices per level × **10 levels** | Also cited as 10+ clicks to target |
| Original work | Hick & Hyman, **1952** | British and American psychometric team |
| K.I.S.S. | Recognised in the **1960s**; U.S. Navy first; general industry use by the **1970s** | Echoes the law; not a measurement |

Not established by this source: any coefficient for `b`, any optimal option count, any confidence interval, any effect size — `unknown: true`.

## Decision procedure

1. **Quick or deliberative?** If it needs reading, research, or comparison, stop — HL-15 applies instead.
2. **Count options, then rate complexity** (HL-02). Count distractors as options (HL-05).
3. **Response time critical?** Hold to 1–5 visible options (HL-01).
4. **Too many to cut?** Card-sort the categories and labels, then expand categories on selection (HL-08, HL-09).
5. **Long process?** One decision per screen, then check you have not over-chunked (HL-03, HL-04).
6. **Complexity that can move?** Push it into the interface and progressively disclose (HL-10).
7. **Mark the recommendation** and remove equal-hierarchy rivals and distractors (HL-05).
8. **New user?** Expose one input, reveal features as each is learned (HL-06).
9. **Meaning lost?** Restore any label or distinction needed to tell options apart (HL-07).
10. **After launch:** time on site, page views, attention (HL-17).

## Anti-patterns

- Flat mega-menu exposing every destination at once.
- Equal-weight options with no recommendation.
- One long form where one decision per screen would do.
- Over-chunking a trivial action into a multi-screen wizard.
- Filters on the entry screen, before anything exists to filter.
- A 10-level binary-choice tree.
- Flattening a professional tool to a consumer feature count.
- Forcing a research-heavy choice into three tiles.
- Simplifying until the options are indistinguishable.
- Declaring the law satisfied without checking metrics.

## Review checklist

- [ ] Quick decision, or HL-15 treatment for a deliberative one?
- [ ] Option count recorded and each option rated for complexity
- [ ] 1–5 options on any critical-response surface
- [ ] Distractors counted as options and removed
- [ ] One recommended option highlighted and visually dominant
- [ ] Long flows split to one decision per screen, without over-chunking
- [ ] Options grouped by user-derived categories from card sorting
- [ ] Complexity moved into the interface, not onto the control surface
- [ ] Entry screen carries one goal; refinements deferred until after commitment
- [ ] Original query or input stays visible throughout the flow
- [ ] Labels still let users distinguish the options
- [ ] Expert and deliberative paths preserved
- [ ] Navigation depth under 10 levels, no 10+ click paths
- [ ] Time on site, page views, and attention checked after launch

## Caveats

- **Decision time is not satisfaction.** Hick's Law governs how long a decision takes. The separate claim that fewer options make users *happier* is contested and is covered in `choice-overload.md`; do not cite this law for it.
- Effort reduction, chunking, and working-memory limits belong to `cognitive-load.md`; progressive-disclosure mechanics belong to `progressive-disclosure.md`.
- This file rests on **one article**: practitioner guidance plus the 1952 citation. No re-analysis, no replication, no effect sizes.
- `a` and `b` are stated as arbitrary and task-dependent. No values, no optimal `n`, no intervals appear — do not quote a coefficient.
- The 1–5 range is explicitly a rule of thumb and applies only where response time is critical.
- Simplification overshoots in two directions: too many chunks (HL-04) and abstraction (HL-07). Both raise abandonment.
- The log form assumes independent, roughly binary choices in the right context; real interfaces present multi-attribute options the source does not model.
- Time-on-site and page-view counts are directional signals only. The source gives no target values.
- Response latency is a separate lever from decision count; the source cites the Doherty Threshold (<400ms) as adjacent work but does not tie it to `RT`.
