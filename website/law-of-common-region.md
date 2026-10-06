---
name: law-of-common-region
title: Law of Common Region — Design Rules
description: Rules for using an area with a clearly defined boundary to make related elements read as a group. Load when deciding where to draw borders, cards, panels or tinted backgrounds, when whitespace cannot carry a grouping, when grouping cues conflict, when structuring page chrome or tables, or when a layout is starting to look cluttered.
applies_when: [grouping and layout, cards and containers, borders and backgrounds, navigation shell, tables and comparison views, page sections, ux review]
priority: supporting
rules: 16
---

# Law of Common Region — Design Rules

## Core principle

Elements tend to be perceived into groups if they share an area with a clearly defined boundary. Items inside a boundary are assumed to share a characteristic or functionality; everything outside it reads as separate.

```
conflicting cues  →  the boundary WINS over proximity and similarity
boundary over-used →  clutter, false floors, abandoned scroll
```

Provenance: one of the Gestalt **laws of grouping**, first proposed by Gestalt psychologists to explain that humans naturally perceive objects as organised patterns — a disposition the source names **Prägnanz**. The original set (first half of the twentieth century) covered proximity, similarity and closure; later research at the end of the twentieth century added more. Of the set, common region is "perhaps the most relevant for UX."

## Rules

### LCR-01 · Give every related group a defined boundary
rule: Any set of elements that serves one purpose must sit inside a clearly defined boundary.
do: Cards, bordered panels, tinted background blocks, outlined wells.
never: Leave a set of related elements floating in undifferentiated space.
because: Items within a boundary are perceived as a group and assumed to share some common characteristic or functionality.

### LCR-02 · Border or background — pick one, not both
rule: A border and a background fill are interchangeable ways to create the region; choose per group.
do: Border for a floating unit (card, list item); background for a full-bleed section (header, footer, sidebar).
never: Stack a heavy border, a tinted fill and a shadow around the same group.
because: Adding a border around an element or group is an easy way to create common region — so is defining a background behind it.

### LCR-03 · Separate chrome from content
rule: The persistent UI shell gets its own region so structure is legible before the user reads anything.
do: Give the header, the left navigation panel and the footer distinguishing backgrounds or borders.
never: Let navigation sit on the same surface as the content it navigates.

### LCR-04 · Fixed and sticky headers must be visually detached
rule: Anything that stays while content scrolls behind it needs an explicit boundary.
do: Background colour or clear border on the header so scrolling content passes behind a known edge.
never: Rely on scroll position alone to tell the user where the header ends.

### LCR-05 · One region for a whole footer link set
rule: Enclose all footer links in a single unifying background so they read as one group.
do: One tinted block covering navigation, legal and meta links.
never: Scatter footer links across the page background with dividers only.

### LCR-06 · Put labels inside the region of what they label
rule: A label and the content it controls share one boundary.
do: Accordion/tab heading inside the same panel as its content; card title inside the card.
never: Place a section label outside the region it introduces.
because: Displaying a tab or accordion label within the same boundary as its associated content visually connects the two areas and establishes their relationship.

### LCR-07 · Bind captions to their media
rule: An image and its caption belong in one region.
do: Wrap figure plus caption in a single bounded block, separate from surrounding body copy.
never: Float a caption in the text stream, detached from its image.
because: An image is often grouped with its caption within a boundary to ensure their relationship is clear, and to separate them from the rest of the article content.

### LCR-08 · Region beats proximity and similarity
rule: When a boundary and a spacing or shape cue disagree, the boundary wins — trust the container over the gap.
do: If proximity or similarity is producing the wrong grouping, enclose the correct group rather than re-spacing it.
never: Assume tighter spacing will eventually override an enclosing boundary.
because: A clear boundary is a strong visual cue that can overpower other grouping principles such as proximity or similarity.

### LCR-09 · Use a region to hold mixed element types
rule: Container any group whose members differ in kind, not just in spacing.
do: One card per item when icon, title, byline and rating sit together.
never: Assume similarity will hold a heterogeneous group together on its own.

### LCR-10 · Add the region when the whitespace is immovable
rule: If spacing cannot be adjusted — fixed grid, wrapping titles, variable content — draw the boundary instead.
do: Card layout around repeated items whose heights shift with wrapped text.
never: Ship a repeating block where the user must guess which label belongs to which item.
because: Large gaps between elements belonging to one recipe made it difficult to tell which byline and rating were related to which; enclosing the content in a border fixed it.

### LCR-11 · One shape for every repeated sibling
rule: Give each instance of a repeated unit the same bounded shape.
do: Card per search result, per list item, per settings row; consistent inset and padding.
never: Outline only the first instance, or only the instances that happen to match in height.

### LCR-12 · Nest regions to express hierarchy
rule: A region may sit inside another region to show sub-grouping.
do: Outer region for app chrome; internal rules or lighter regions for search, workspaces, and channels.
never: Flatten sub-groups to the same visual level as the whole.

### LCR-13 · Two axes need two different cues
rule: A structure grouped on both rows and columns requires a different device per axis.
do: Zebra row backgrounds for horizontal runs; whitespace or a vertical border between columns.
never: Try to make one set of boxes signal row membership and column membership at once.
because: In a comparison table both the column (each product or service) and the row (each characteristic) must be distinguished; zebra stripes unite horizontal elements while whitespace or another border separates each column.

### LCR-14 · Whitespace first — add a border only when it earns its place
rule: Try to group with spacing alone before adding any boundary.
do: Ask: is the border necessary to understand the grouping? Can whitespace do it? Were users confused in testing when the boundary was absent?
never: Box a set in an abundance of caution — proximity is usually enough.
because: Using whitespace alone reduces visual complexity; borders added out of caution produce busy, cluttered designs.

### LCR-15 · Never let a region read as the end of the page
rule: A full-width region that changes colour or gains a border can act as a false floor.
do: Keep full-width colour blocks off the main scroll path, or make clear they are a section within the same page.
never: Close a long scrolling list with a full-width bordered or contrasting block.
because: Segmenting a page into distinct sections can create false floors and prevent users from scrolling further, because they think they have hit the end — especially when borders span the full width of the screen.

### LCR-16 · No container without a relationship
rule: Every boundary must encode a real grouping.
do: Delete any border or tinted box that carries no relationship; re-add spacing instead.
never: Add a coloured box "to add structure" with no group behind it.
because: Too many borders and coloured boxes that exist purely for decoration add clutter to the interface.

## Hard numbers

| Constant | Value | Note |
|---|---|---|
| Categories in the Gestalt grouping set | **5** — Proximity, Similarity, Continuity, Closure, Connectedness | The complete set, per the source's Origins section |
| Grouping-laws timeline | original set — proximity, similarity, closure — discovered in the first half of the twentieth century; further principles added at the end of the twentieth century | Later additions described only as "a few more grouping principles" |
| Rank among the set | "perhaps the most relevant for UX" | The source's own judgement, unquantified |
| Groups produced by borders, print-dialog example | **3** — where to print, what to print, how many to print | Boundaries disambiguate the numeral "1" as a page number on one side and a copy count on the other |
| Attribution in the reference material appended to the source file | common region principle proposed by Palmer (1992); element connectedness by Palmer & Rock (1994) | The article itself names no author for the principle |

Quantitative data in the source: **none**. No effect sizes, no sample sizes, no measured accuracy, time or scroll-drop figures — `unknown: true`. Every claim is qualitative and illustrated with figures.

## Decision procedure

1. **List the groups** — which sets of elements belong together and serve one purpose?
2. **Try whitespace** — can spacing alone carry each grouping? (LCR-14) If yes, stop. Add a boundary only where testing showed confusion without one.
3. **Contain** — for each group still unclear, pick border or background, one device only. (LCR-01, LCR-02)
4. **Check conflicts** — is proximity or similarity yielding a different grouping than the real relationship? Enclose; the region wins. (LCR-08)
5. **Immovable layout** — whitespace unavailable? Then card or panel every repeated unit consistently. (LCR-10, LCR-11)
6. **Structure pass** — are header, nav and footer in their own regions; is every label inside its content's region? (LCR-03 to LCR-07)
7. **Hierarchy** — sub-groups needing nesting, or a two-axis structure needing two cues? (LCR-12, LCR-13)
8. **Scroll pass** — does any full-width region read as the end of the page? (LCR-15)

## Anti-patterns

- Every list item boxed "to be safe".
- A filter menu with each category in its own bordered box when spacing already groups them.
- Full-width colour blocks that stop a scrolling page dead.
- Captions drifting away from their images; accordion or tab labels outside the panel they open.
- Containers on groups that share no characteristic, or border + tint + shadow stacked on one unit.
- Navigation sharing one surface with the content it navigates.

## Review checklist

- [ ] Every related group sits inside a clearly defined boundary
- [ ] One cue per group — border, background, or whitespace — never stacked
- [ ] No container exists purely for decoration
- [ ] Chrome (header, nav, footer) separated from content by its own region
- [ ] Sticky/fixed header visibly detached from scrolling content
- [ ] Labels placed inside the region of the content they label
- [ ] Captions bound to their media
- [ ] Conflicting proximity/similarity resolved with an explicit boundary
- [ ] Mixed-type and repeated units each carry a consistent container
- [ ] Sub-groups nested inside their parent region
- [ ] Two-axis structures use a different cue per axis
- [ ] No full-width region that could read as the end of the page
- [ ] Every border justified by observed confusion, not caution alone
- [ ] One pass done with boundaries removed to confirm which survive

## Caveats

- Gestalt grouping laws are perceptual-psychology principles described **qualitatively**. The source provides **no quantitative data** — effect sizes, sample sizes and measured rates of grouping are `unknown: true`.
- Every rule here is practitioner guidance argued from figures and worked examples, not from controlled experiments. Treat the precedence and clutter claims as strong defaults, not measurements.
- The source asserts that a clear boundary overpowers proximity and similarity; the research material appended to it also notes that predicting which principle wins remains an unresolved theoretical problem. Do not treat precedence as a guarantee.
- No source guidance exists for spacing amount, border weight or region colour — those are design-system decisions, not outputs of this principle.
- The full-width "false floor" problem is presented as a common failure mode with no measured drop-off in scrolling.
- Provenance: the five Gestalt principles each have their own skill in this folder — `law-of-proximity.md`, `law-of-similarity.md`, `law-of-uniform-connectedness.md`, `law-of-pragnanz.md`. This file covers only common region; do not restate their rules here.