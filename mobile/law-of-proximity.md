---
name: law-of-proximity
title: Law of Proximity — Design Rules
description: Rules for using the distance between elements to declare what belongs together. Load when laying out a page or screen, spacing list items, building a form, separating navigation from actions, clustering content into sections, or when grouping reads wrongly.
applies_when: [grouping and layout, lists and tables, forms, navigation, page sections, whitespace, responsive layout, ux review]
priority: core
rules: 20
---

# Law of Proximity — Design Rules

## Core principle

Objects that are near, or proximate to each other, tend to be grouped together. The eye builds a relationship between elements of the same design — and then judges what they share.

```
within-group gap  <  between-group gap   →  two groups
every gap equal                          →  one group, every item equal
one unbounded cluster                    →  no structure at all
```

## Rules

### LPX-01 · Proximity declares a relationship
rule: Placing two elements next to each other is a claim that they belong together.
do: Move related elements adjacent before reaching for a border, a colour or a heading.
never: Position two elements side by side with no relationship to express.
because: Proximity is the primary visual cue that describes information architecture to the brain.

### LPX-02 · Close proximity implies shared function
rule: Elements read as one group are assumed to share functionality or traits.
do: Verify the grouping you drew is the grouping the relationship actually implies.
never: Let two functionally different controls fall inside the same visual cluster.

### LPX-03 · Proximity organises information faster than content can
rule: Let distance do the organising work the user would otherwise have to do.
do: Space so the structure is legible at a glance, before a single word is read.
never: Make the user infer hierarchy from wording alone.

### LPX-04 · Inside-group gaps must be smaller than between-group gaps
rule: Items in a group must be nearer to each other than to anything outside it.
do: Set within-item spacing, then set group separation larger — the source's own sketch put the group gap at roughly 3–4× the within-group gap.
never: Use one spacing value for a flat run of items *and* for the gap after it.

### LPX-05 · Uniform spacing asserts equal importance
rule: Equally spaced, equally aligned items read as one group of equals.
do: Break the uniformity at the item that outranks its siblings.
never: Space every row identically and then add emphasis some other way.

### LPX-06 · Unenclosed elements need more space, not less
rule: An element without a boundary needs more room around it.
do: Add outer space to unenclosed sidebar items and inline widgets so they still scan as separate features.
never: Remove a widget's frame and tighten its spacing in the same change.
because: Without edges from a surrounding shape, unenclosed widgets need more space to be scanned separately yet understood as functionally similar.

### LPX-07 · Whitespace is the enclosure — vary it
rule: Use varying amounts of whitespace to either unite elements or separate them.
do: Widen one gap and tighten the rest; the widened gap is the group boundary.
never: Let every gap in a layout share one value.
because: Proximity is similar to common region but uses space as the enclosure.

### LPX-08 · Don't stack or cluster every element
rule: Full-bleed, edge-to-edge rows defeat grouping.
do: Break long runs into bounded clusters with real space between them.
never: Apply a narrow-first stack unchanged at every breakpoint.
because: Full-bleed elements occupy more of the person's visual field; the more rows there are, the more the brain moves back and forth between scanning and reading.

### LPX-09 · Every cluster must match a real relationship
rule: A group that means nothing camouflages the items inside it.
do: Group genuinely related actions — Previous and Next belong together.
never: Park the one outlier action inside a row of unrelated buttons.

### LPX-10 · Bind labels to their fields
rule: A label and its field form one unit.
do: Use a minimal gap between a top-aligned label and its field, and a larger margin before the next label–field pair.
never: Space a label from its field exactly as far as the fields are from each other.

### LPX-11 · Chunk forms into meaningful groups
rule: Break long forms into groups the user already recognises.
do: Split 12 fields into 3 chunks of 4 — only where the split is real, such as shipping versus billing.
never: Chunk a form along lines you invented for visual balance.

### LPX-12 · Bind each heading to its own section
rule: Section text sits closer to its own heading than to the preceding section.
do: Put the space above a heading and below its section; keep the gap to the previous section wider.
never: Let a heading drift toward the text it does not introduce.
because: Whitespace around a well-designed heading signals which paragraphs it belongs to; changing the subject means starting a new paragraph.

### LPX-13 · Put instructions beside what they describe
rule: An instruction belongs next to the thing it tells the user how to use.
do: Anchor hints, labels and empty-state prompts to their target element.
never: Drop usage instructions in a distant corner, or over a busy background.

### LPX-14 · Keep actions inside the user's focal area
rule: Task-focused users attend to one region — put what they need inside it.
do: Place primary actions, their alternatives and their instructions in one focal block.
never: Hide an escape hatch in a corner far from the main calls to action.
because: "Tunnel vision" — users selectively attend to part of the screen and miss things in plain sight because they sit outside that area.

### LPX-15 · Re-audit grouping at every breakpoint, and relocate rather than merge
rule: Grouping must survive resizing, not just the widest layout.
do: Re-check relationships where columns stack; keep comparison sets adjacent at all widths; shift an item out of a shared line when the gap cannot survive.
never: Compress a gap until two groups read as one.
because: Scaling down can shrink the space between elements or push them apart, destroying grouping relationships.

### LPX-16 · Don't over-group
rule: Cramming items together destroys the cue you were aiming for.
do: Keep groups small enough that each item's spacing stays distinct.
never: Squeeze so many items into one block that the layout becomes noisy and crowded.
because: Group too many items too closely and the proximity of each becomes so indistinct that the design loses meaning.

### LPX-17 · When spacing can't carry a group, use a connection cue
rule: A shared container or connector overrides spacing.
do: Put the items in one menu or frame, or give them a shared bullet, colour or numbering system.
never: Tighten spacing repeatedly hoping it will beat an explicit connection.
because: Connectedness works even when it contradicts proximity and similarity, and is described as the strongest cue suggesting relatedness.

### LPX-18 · Use continuation to hold a path through the layout
rule: Lay elements on a line or curve so the eye connects them without being told to.
do: Align content along a shared axis; carry process steps with numbering, arrows or a funnel shape.
never: Scatter the steps of one flow so no path reads through them.
because: The eye follows lines, curves or sequences of shapes through both positive and negative space — it sees a line and a curve crossing, not four separate segments.

### LPX-19 · Isolate the one action you want
rule: An item that differs from its neighbours is the one that gets remembered.
do: Make the primary CTA visually distinct from the other buttons in its group; put the most important nav destinations at the extremes of the bar.
never: Let the action you most need clicked sit in a run of identical buttons.

### LPX-20 · Re-check grouping after the design drifts
rule: Aesthetic choices break systems down as a process unfolds — verify grouping on work you are already satisfied with.
do: Greyscale the layout and confirm each cluster still says what you meant.
never: Assume a grouping that held at kickoff still holds at delivery.

## Hard numbers

| Constant | Value | Note |
|---|---|---|
| Within-group vs between-group gap | ~**3–4×** the within-group gap | Ratio from the source's sketch exercise, not a measured threshold |
| Form chunking comparison | **12 fields** as one group vs **3 groups of 4** | Illustrative, and only valid if the split is meaningful |
| Gestalt perception demo | **72 circles** read as **36** + **3 × 12** | Perception demo, not a test result |
| Original Gestalt grouping categories | **5** — Proximity, Similarity, Continuity, Closure, Connectedness | Common region added to the list later |
| Spacing values, tokens, effect sizes, sample sizes | unknown: true | Source states no measurement unit and no data |

Quantitative data in the source: **none**. No effect sizes, no sample sizes, no measured scan rates, no px/rem/padding figures. Its only numbers are the illustrations above.

## Decision procedure

1. **List the groups** — which elements belong together, and what the relationship is. If you cannot name it, do not group them.
2. **Space** — set the within-group gap first, then a larger gap between groups; vary at least one value.
3. **Check the enclosure** — unenclosed items need more surrounding space than enclosed ones.
4. **Read it without words, then check collisions** — greyscale it: do the clusters still read, is anything unrelated inside a group, are related items stranded apart?
5. **Check the focal area** — primary actions, their alternatives and their instructions all inside the region users attend to?
6. **Re-run at every breakpoint** — stacking changes gaps; relocate rather than compress. Then re-check the grouping survived late-stage visual changes.

## Anti-patterns

- A flat list where the one item that outranks the rest gets identical spacing.
- One giant cluster holding every element on the screen.
- The primary action sitting in a row of identical secondary buttons.
- A skip / guest-access link parked in a corner far from the main calls to action.
- Form labels spaced from their fields exactly as far as the fields sit from each other.

## Review checklist

- [ ] Every cluster corresponds to a named relationship; no unrelated item inside one
- [ ] Within-group gaps visibly smaller than between-group gaps, and not all gaps equal
- [ ] No single cluster swallowing the screen; full-bleed rows broken into bounded clusters
- [ ] Labels tight to their fields; each heading tight to its own section
- [ ] Primary action distinct from its neighbours and inside the focal area, instructions adjacent to their targets
- [ ] Grouping re-checked at every breakpoint; nothing merged to fit
- [ ] Nothing left fragmentary or full-bleed by a narrow-first stack
- [ ] Greyscale pass done on the final layout

## Caveats

- No quantitative data appears anywhere in the source — no effect sizes, sample sizes, measured scan rates or spacing measurements. Its "mobile-usability studies" are cited with no participant count and no result: `unknown: true`.
- The source *does* state precedence between conflicting grouping cues, without supporting data: proximity "can overpower competing visual cues such as similarity of color or shape"; connectedness "works even when it contradicts other Gestalt principles" and is "the strongest" of the cues suggesting relatedness; symmetry "takes precedence over proximity"; past experience is "perhaps the weakest" principle and is dominated by any other. These are single-source qualitative claims, and the framing is "all else being equal" — so precedence holds only where the competing cues are equal. Use them as defaults, not measurements.
- Cross-skill context, not this source: `law-of-common-region.md` records that a drawn boundary overpowers proximity and similarity. This source says proximity uses space *as* the enclosure and never ranks itself against a drawn border.
- Provenance: the five Gestalt grouping laws each have their own skill in this folder — `law-of-similarity.md`, `law-of-common-region.md`, `law-of-uniform-connectedness.md`, `law-of-pragnanz.md`. This file covers proximity only; do not restate theirs.
- Everything here is practitioner argument illustrated with figures and worked examples, not controlled experiments, and no rule is attached to user-testing evidence. The source's own verification advice is to check the integrity of the grouping against work you are otherwise satisfied with visually. No spacing tokens, unit values or padding figures are given — any widely-cited numeric threshold for proximity is absent from this source: `unknown: true`.
