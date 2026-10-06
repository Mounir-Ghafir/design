---
name: law-of-similarity
title: Law of Similarity — Design Rules
description: Rules for using shared visual traits — colour, shape, size, orientation, movement — to declare what belongs together and what shares a function. Load when styling a set of components, marking links and navigation, choosing a primary action, building grids and lists, separating content types, or when a screen reads flat and everything looks equally important.
applies_when: [component styling, links and navigation, buttons and actions, icons and badges, grids and lists, typography hierarchy, content types and ads, ux review]
priority: supporting
rules: 17
---

# Law of Similarity — Design Rules

## Core principle

The eye perceives similar elements as a complete picture, shape, or group — **even if those elements are separated**.

```
one shared trait + any distance  →  one perceived group  (this law's edge over proximity)
no distinguishing trait          →  flat set of peers
two similar but unrelated items →  a relationship falsely signalled
```

Traits that carry the signal: colour, shape, size, orientation, movement — plus font treatment and texture. Elements that look alike are read as related, so they are assumed to share a common meaning or functionality.

## Rules

### LSM-01 · Similarity crosses distance
rule: A shared visual trait binds elements into one group even when they are physically separated.
do: Unite distant elements with one common trait instead of dragging them together spatially; one visible trait is enough — items need not be identical.
never: Assume proximity is the only way to declare a group.
because: The principle differs from other grouping laws in that the shared characteristic can unite elements despite a distributed placement.

### LSM-02 · Colour is the strongest similarity trait
rule: Shared colour unites elements of different types and stands out more prominently than other traits such as shape.
do: Use a single colour to bind otherwise different element types into one group.
never: Expect shape or size alone to hold a mixed-type group together.

### LSM-03 · Reserve the link colour for links only
rule: Treat the interactive colour as a category marker, not decoration.
do: Style every clickable element with the one link colour; leave body text in the default text colour.
never: Apply link colour to keywords, non-clickable headings, or nearby icons that are not clickable.
because: Users perceive everything sharing that characteristic as related and working the same way.

### LSM-04 · Differentiate links and navigation from normal text
rule: Links and navigation systems must be visually distinct from ordinary body text.
do: Differentiate links by colour and usually by shape as well, and make them stand out.
never: Let an inline link look like the paragraph around it.
because: Many users will typically consider a link to be any text that is blue and underlined.

### LSM-05 · Apply one interactive cue consistently
rule: Repeat the same marker beside every element that shares a function.
do: Place the same arrow icon beside each clickable element instead of relying on colour alone, so items still read as functionally similar even when their font treatment differs.
never: Signal one function with colour here, an arrow there, and an underline elsewhere.

### LSM-06 · Same colour on buttons reads as same importance
rule: Buttons that share a colour are perceived as sharing a level of importance.
do: Reserve a separate colour for the primary call to action so it stands out among secondary buttons.
never: Style Cancel, Submit, and Attach in one accent colour and expect one of them to read as primary.

### LSM-07 · One icon per function, unique shape per category
rule: A repeated icon means a repeated function; near-identical icons falsely claim a relationship.
do: Reuse one icon for elements that behave the same; give every distinct category a distinguishable icon.
never: Give two different categories the same or a very similar icon.
because: When elements share a shape, users assume they are the same and overlook the accompanying labels and small text.

### LSM-08 · Give list indicators distinct shapes
rule: Two badges in the same list are only distinguishable if at least one trait differs.
do: Give each indicator a unique shape, then add colour or an inner icon on top of it.
never: Let two status badges share both shape and colour and rely on their text alone.
because: Indicators that appear too similar take longer to scan — the shared shape would make them appear too similar and slow users down.

### LSM-09 · Same size means same prominence
rule: Consistently sized elements are read as one group at one level of importance.
do: Use one size for every instance of an element type; consistent use creates a hierarchy that is legible at a glance.
never: Let items of the same type drift between two sizes.

### LSM-10 · Break size or shape to mark a different content type
rule: A change of size or shape removes an element from the group around it.
do: Scale promotions or editorial units away from the surrounding item size to signal "a different kind of content".
never: Size a collection promo the same as the individual items around it.

### LSM-11 · Never style real content like an ad
rule: Content sized and shaped like the promotions beside it will be read as a promotion.
do: Differentiate genuine content from right-rail advertising by size or shape.
never: Drop a tutorial or article block into an ad slot at ad dimensions.
because: In the source's study, several participants completely missed a how-to video in the right rail because it was sized exactly like the display ads surrounding it.

### LSM-12 · A uniform grid carries no function
rule: A grid or list of identical objects signals only that there is more than one object, of the same type, of equal importance.
do: Add separate cues for clickability, destination, and persistence, and set the group's form apart from the material surrounding it.
never: Assume a neat grid communicates that its items are clickable, or let list rows share the styling of the body copy they sit inside.
because: A wireframe of identical boxes communicates nothing else, so function has to be stated separately; similarity also lets the group present itself as a set of a different kind from its surroundings.

### LSM-13 · Similarity flattens hierarchy — break it to pull focus
rule: When everything shares a trait, everything reads as an equal peer; the one exception is what gets seen.
do: Build the uniform group first, then break at least one trait — size, weight, colour — on the element that must win, typically a call to action.
never: Expect hierarchy to survive when every element matches on every trait, or let every element match and ask the user to find the important one.
because: If all text looked the same, the rule of similarity would have it perceived as equal — as peers in a flat system — but the law is usable from both sides, so breaking it deliberately draws the eye.

### LSM-14 · Typographic roles must be visually distinct
rule: Every text role needs its own treatment: headings, body, lists, pull quotes, headers.
do: Separate a headline from its paragraphs by size, weight, and spacing; set lists apart by indentation and segmentation; box and italicise quotes; run headers in a different font, colour, or size.
never: Ship a solid block of undifferentiated text.
because: The differences in how text is treated — the breaking of similarity — function as visual language, separately from the meaning of the words.

### LSM-15 · Every state is a deliberate exception
rule: Each state of a component must be distinguishable from that component's other states.
do: Signal a state by changing an existing trait — colour, fill, size, shape — on that component only.
never: Ship a state that is visually identical to the component's default.
because: Clear, consistently applied visual rules for each type of UI element are critical, because each interaction develops users' expectations for how other similar elements will function.

### LSM-16 · Keep the trait-to-function mapping stable
rule: One trait must always imply one behaviour.
do: Audit the interface so a user who learned one element can predict every element that looks like it.
never: Give a decorative icon the exact styling of the button beside it, or reuse an interactive treatment for something inert.

### LSM-17 · Expect proximity and common region to overrule you
rule: Where a shared trait conflicts with a shared enclosure or tight spacing, the location cues usually win.
do: Make the two agree — put elements that share a trait inside the same region and space.
never: Expect a colour match to hold a group together against a stronger enclosure or a much closer neighbour.
because: Similarity is not necessarily the strongest grouping principle — it is often overpowered by proximity or common region — though it is considered the most resilient.

## Hard numbers

| Constant | Value | Note |
|---|---|---|
| Original Gestalt grouping categories | **5** — Proximity, Similarity, Continuity, Closure, Connectedness | Common region added to the list later; similarity also called Invariance |
| Shared traits needed for a group | **1** visible trait | Items need not be identical |
| Colour/shape/size named as traits | **3** core, plus orientation, movement, font treatment, texture | Orientation and movement come from the summary takeaways |
| Colour-grid demonstrations | **4-by-3** grids of circles and triangles, read as columns or rows by colour | Perception illustrations, not test results |
| Pencil-and-paper experiment | **about 10** circles, **5–6** triangles, **about 3** dots | Self-run illustration; the dots are spotted first because dots are points, the shapes are made of lines |
| Promotion scale contrast | **double the size** of an individual product listing | The source's worked example of a different content type |
| Origins as cited | **1910** Wertheimer's flashing-lights observation; Wertheimer **1880–1943**; Köhler **1929**; Koffka **1935**; Metzger **1936** | Cited with no titles, venues, or findings |
| Adoption period claimed | "over the last twenty years" | Source statement, undated, uncounted |
| Contrast ratios, colour values, effect sizes, sample sizes | unknown: true | Source states none |

Quantitative data in the source: **none**. No contrast ratios, no colour values, no effect sizes, no sample sizes — every claim is qualitative and illustrated with figures.

## Decision procedure

1. **Name the groups** — list the element types on the screen and what relationship each set is claiming.
2. **Assign one trait per type** — colour, shape, size, orientation, movement, or font treatment. One trait each, applied everywhere.
3. **Check the exceptions** — for each element that must not belong to its group, confirm at least one trait actually differs.
4. **Check the interactive set** — is the link colour reserved, is one cue used consistently, is the primary action distinguished from secondary buttons?
5. **Check the grid and list** — what do these identical objects fail to communicate (clickability, destination, persistence)?
6. **Check the boundaries** — content and advertising, list and page, CTA and its row.
7. **Greyscale** — read the layout without words; everything the same is one group, whether or not that was intended.

## Anti-patterns

- Body text, links, and headings all in one treatment.
- Primary and secondary buttons in the same accent colour.
- Link colour applied to a non-clickable keyword or decorative icon.
- Two categories sharing one icon, or two badges sharing shape and colour.
- A how-to, article, or promo sized exactly like the ads around it.
- A uniform grid of identical boxes with no cue that anything is clickable.

## Review checklist

- [ ] Every element type has one signature trait, applied consistently
- [ ] Related elements grouped across distance where a shared trait can do the job
- [ ] Links and navigation clearly distinguishable from normal text
- [ ] Interactive colour reserved for genuinely interactive elements; one interactive cue used consistently
- [ ] Primary action separated from secondary actions by more than position
- [ ] No two unrelated categories share an icon, shape, or badge styling
- [ ] One size per element type; different content types a different size or shape
- [ ] Real content never styled to match surrounding advertising
- [ ] Grids and lists state clickability, destination, and persistence separately
- [ ] The element that must win differs from its group on at least one trait; states differ from the default
- [ ] Similarity and proximity/common-region cues agree; no group held together by colour against a stronger enclosure

## Caveats

- The source contains **no quantitative data**: no contrast ratios, no colour values, no effect sizes, no sample sizes, no measured scan or find times — `unknown: true`. Every rule here is a qualitative perceptual claim illustrated with figures. Any numeric threshold for "how similar is similar enough" is absent from this source.
- **Precedence**: the source does state one relation, recorded in LSM-17 — similarity "isn't necessarily the strongest grouping principle as it is often overpowered by proximity or common region", while being "the most resilient"; visually similar items may also simultaneously belong to location-based groupings. That is the only precedence claim it makes *about similarity*, and it carries no data. Discussing other laws rather than similarity, it separately calls uniform connectedness "the strongest" cue of relatedness and past experience "perhaps the weakest" principle, dominated by any other — sibling-law claims, defaults not measurements.
- **Interaction states**: the source never enumerates hover, active, focus, or disabled treatments. LSM-15 is derived from its statement that clear, consistently applied visual rules for each type of UI element are critical because each interaction builds expectations, plus its link-colour reservation — not from a state specification: `unknown: true`.
- The source's evidence is practitioner reporting: named product screenshots, one self-run pencil-and-paper exercise, a study on list indicators cited with no counts or figures, and a video-viewing study in which "several participants" missed an element — participant count and result size both `unknown: true`.
- **Provenance**: the five Gestalt grouping laws each have their own skill in this folder — `law-of-proximity.md`, `law-of-common-region.md`, `law-of-uniform-connectedness.md`, `law-of-pragnanz.md`. This file covers similarity only; do not restate their rules. The source also names several wider Gestalt ideas with no treatment here — closure, continuation, figure/ground, symmetry and order, common fate, parallelism, focal points, past experience — and past experience is explicitly stated to be the weakest and individually variable, so it is not a design lever.