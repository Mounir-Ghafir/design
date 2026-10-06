---
name: law-of-pragnanz
title: Law of Prägnanz — Design Rules
description: Rules for reducing a composition to the simplest form the eye can hold, and for deciding when extra complexity is earned. Load when simplifying a layout, cutting visual detail, designing a mark or icon, judging whether a composition reads at a glance, or reviewing hierarchy.
applies_when: [figure simplification, layout and composition, logo and icon design, wireframing, visual hierarchy, design review]
priority: supporting
rules: 16
---

# Law of Prägnanz — Design Rules

## Core principle

People perceive and interpret ambiguous or complex images as the simplest form possible, because that is the interpretation requiring the least cognitive effort.

```
simple_reading = the interpretation needing the fewest distinct parts to hold together
```

The eye prefers things that are simple, clear and ordered — they are safer, take less time to process, and present fewer surprises. The human eye finds simplicity and order in complex shapes because that prevents being overwhelmed with information.

Origin: in **1910** Max Wertheimer watched lights flashing on and off at a railroad crossing, like bulbs encircling a movie-theatre marquee, and saw a single light travelling bulb to bulb. The lights do not move. That observation produced the Gestalt descriptive principles.

## Rules

### LP-01 · Resolve every composition to its simplest form
rule: Reduce the composition to the fewest elements that still read as one coherent whole.
do: Ask what the eye takes in at a glance without resolving competing interpretations.
never: Ship a layout that needs a second look to become legible.

### LP-02 · Prefer simple, clear and ordered forms
rule: Of two candidate treatments, choose the one that is simplest, clearest and most ordered.
do: Rank candidates by processing time they demand, then cut the most expensive first.
never: Add detail that conveys nothing.
because: Simple, clear and ordered things read as safer — they process faster and present fewer surprises.

### LP-03 · Simple figures are processed and remembered better
rule: Default to the simpler figure whenever both versions carry the same message.
do: Cut detail until the figure is instantly recognisable at its rendered size.
never: Keep ornament that survives only because nobody challenged it.
because: Research confirms people visually process and remember simple figures better than complex figures.

### LP-04 · Collapse convolution into one unified shape
rule: Transform a convoluted shape into a single, unified shape by removing extraneous detail.
do: Remove internal detail that does not change what the shape *is*.
never: Leave marks that force the eye to reconcile competing contours.

### LP-05 · Name the simpler reading before you ship
rule: Decide explicitly which of two possible readings of the same layout is the simpler one.
do: Three distinct objects often beat one complex object; elsewhere one object beats three. Pick deliberately.
never: Leave the reduction to the viewer.
because: The eye always resolves toward the simplest reading. If that is not yours, yours loses.

### LP-06 · Design the outline, then let the eye fill the gaps
rule: Communicate the silhouette first and let the viewer complete it.
do: Identify the outline, match it to a form the viewer knows, then omit segments the eye will supply.
never: Omit so much that the viewer sees separate parts instead of a whole.
because: The whole is perceived before its parts, and the mind fills gaps to complete a familiar pattern.

### LP-07 · Shift perception in stages, never all at once
rule: Change what the viewer sees by strengthening one reading and weakening the original.
do: Find an alternative reading, build it up while you take the old one away.
never: Swap the original reading and the alternative in a single step.

### LP-08 · Keep forms recognisable across scale, rotation and viewpoint
rule: A form must stay identifiable after rotation, translation and scale.
do: Test the mark at favicon size and at large size before approving it.
never: Design a mark that only works at the size you first drew it.
because: Objects are recognised independent of rotation, translation and scale.

### LP-09 · Wireframe before style
rule: Wireframe the layout; the eye assembles the content blocks into a single page.
do: Place a wireframe of the new concept beside the current page — variances are visible without content.
never: Argue visual quality from a comp that has no agreed wireframe underneath it.

### LP-10 · Simplify until recognition breaks, then back off
rule: Simplify aggressively, then stop at the point where the message still reads correctly.
do: Test the simplified version on someone who has not seen the original.
never: Cut a label, a state, or a required meaning to make a screen look cleaner.
because: Under-communicating is the failure mode of over-simplifying. Simplicity must not cost clarity.

### LP-11 · Spend complexity where it carries a relation
rule: Extra visual complexity is justified only when it tells the viewer something.
do: Spend it on convention (red means stop; blue underlined means link), contrast, direction, enclosure.
never: Spend it on decoration that adds no relation, no hierarchy, no meaning.

### LP-12 · Every simple composition needs one focal point
rule: A simplified composition still needs one point of difference for the eye to catch.
do: Make one element differ in shape or colour; the surrounding elements supply the similarity it stands out from.
never: Flatten a composition until nothing is unlike anything else.
because: Focal points cannot be seen without similarity among the other elements, and attention is drawn to what is different.

### LP-13 · Closure — supply enough outline for a close match
rule: Give enough of the outline for the eye to complete the figure; do not give all of it.
do: Leave a gap the viewer can close from context; stop omitting when the parts stop reading as one shape.
never: Complete every outline, or omit so much that nothing closes.
because: Too much missing and the elements read as separate parts; too much given and closure never happens.

### LP-14 · Symmetry and order — build balance, not perfect mirroring
rule: Compose toward order around a centre; balance does not require perfect symmetry.
do: Use a symmetric structure to carry the eye quickly.
never: Break a symmetric structure for a reason weaker than variety.
because: Symmetry gives solidity and order, and takes precedence over proximity.

### LP-15 · Figure and ground — make the relationship stable
rule: The composition must resolve to one clear figure resting on one clear ground.
do: Stabilise it with size and contrast — the smaller of two overlapping objects reads as figure, convex over concave.
never: Leave figure and ground near-equal in density unless reversal is the intent.
because: The eye separates figure from ground first; the more stable it is, the more reliably you lead the viewer.

### LP-16 · Uniform connectedness — the strongest cue that two things belong together
rule: Connected elements are read as more related than unconnected ones, more strongly than by any other grouping cue.
do: Bind a pair with a line or connector; the line does not need to touch the elements.
never: Connect a pair that should read as separate.
because: The connection wins even when the connected elements differ in shape.

## Hard numbers

| Constant | Value | Note |
|---|---|---|
| Observation date | **1910** | Wertheimer's railroad-crossing / marquee lights; the only date in the source |
| Effect size for the simple-vs-complex advantage | **unknown: true** | Source asserts it; states no magnitude |
| Sample size, study, author, venue | **unknown: true** | No citation given for the processing/recall claim |
| Threshold defining "simple enough" | **No threshold stated** | "Simplest form possible" is qualitative in the source |

## Decision procedure

1. **One glance** — state what the composition says after a single look. If you cannot, it is not simple enough.
2. **List the parts** — count distinct elements, and the contours the eye must reconcile.
3. **Simplify in order** — internal detail, then contours and outlines, then competing focal points, then repetition, then decoration. Cut ornament last; never cut meaning.
4. **Name the reading** — write down the single shape or structure the eye resolves to. That is your message; change the shapes if it is not the intended one.
5. **Stop at recognition** — re-test after every cut and put back the one that breaks recognisability.
6. **Re-buy clarity deliberately** — reintroduce detail only where it carries a relation, a convention, a contrast, or a hierarchy.

## Anti-patterns

- A comp that needs a second look to become legible.
- Ornament surviving because nobody questioned it.
- Every element made identical, so nothing draws the eye.
- Outline omitted so far that the viewer sees parts, not a whole.
- Detail cut from a label or required meaning to make a screen look cleaner.
- Ambiguous figure/ground shipped by accident.
- A grouping cue used to bind elements that should read separately.

## Review checklist

- [ ] The composition reads correctly in one glance
- [ ] The shipped reading is the simpler one, and it is the intended one
- [ ] Outline and silhouette legible at final rendered size
- [ ] Rotation, scale and favicon test passed for any mark
- [ ] Wireframe agreed before styling
- [ ] Detail kept only where it carries a relation or a convention
- [ ] Simplification stopped before meaning was lost
- [ ] One clear focal point, with similarity in the surrounding elements
- [ ] Figure/ground stable; no accidental ambiguity
- [ ] Grouping cues point the way the content should group

## Caveats

- The source contains **no quantitative data** — no effect sizes, sample sizes, or measured recall advantage. All such figures are `unknown: true`.
- It claims "research confirms" that simple figures are processed and remembered better, but cites **no study, author, venue, or date**. Treat it as an unverified premise, not evidence.
- Gestalt principles are perceptual tendencies, not guarantees. Past experience and culture shift what counts as simplest, and the source calls past experience the weakest principle — any other principle dominates it.
- This file also covers Closure, Symmetry and Order, Figure/Ground and Uniform Connectedness, which each have dedicated coverage in this folder (`law-of-uniform-connectedness.md`, `law-of-common-region.md`); use those for depth rather than restating them here.
- "Simplest form possible" is qualitative in the source. There is no numeric threshold, so "simple enough" is argued per composition, not checked against a number.