---
name: law-of-uniform-connectedness
title: Law of Uniform Connectedness — Design Rules
description: Rules for using an explicit visual tie — colour, line, arrow, frame or shape — to declare that elements belong together, and for laying related items on a line, curve or grid so continuation carries the meaning. Load when joining items into a unit, showing context or ownership, building steppers, timelines, breadcrumbs, process UI, tabbed panels, dashboards or charts, or when a layout reads as unrelated parts.
applies_when: [grouping and layout, flows and steppers, timelines, navigation and breadcrumbs, tabs and panels, process UI, dashboards, data visualisation, ux review]
priority: supporting
rules: 17
---

# Law of Uniform Connectedness — Design Rules

## Core principle

Elements that are visually connected are perceived as more related than elements with no connection. Connection makes a group read as a unit instead of a pile of separate things — and it can carry meaning no label could.

```
colour / line / frame / shape  →  one perceived unit
line or curve of items          →  perceived as related by continuation
no cue, however close           →  no relationship expressed
two or three cues for one link  →  noise; use the least amount possible
```

The source calls connectedness **the strongest** cue suggesting relatedness, and says the effect holds even when it contradicts proximity and similarity. Treat that as a working default, not a measurement — see Caveats.

## Rules

### LUC-01 · Connectedness is a declaration of relationship
rule: Any element joined to another by a shared visual property is read as related to it.
do: Name the relationship first, then pick the cue that expresses it.
never: Place two elements near each other and let the reader guess what the tie means.

### LUC-02 · Connect with colour, line, frame or shape
rule: Group things of like nature with one of the four connecting devices.
do: Enclose them in a frame or coloured rectangle, share one colour, run one line through them, or bind them in a single shape.
never: Rely on a heading or a colon to carry a grouping no visual cue supports.

### LUC-03 · The connecting line does not have to touch
rule: A line's proximity to an element is enough to bind them.
do: Route connectors close to their targets and let them pass, running cleanly between neighbours.
never: Extend a hairline to meet every shape it labels.
because: The source states plainly that lines need not touch for the connection to be perceived.

### LUC-04 · An enclosure makes items a single unit
rule: Anything inside one border, panel or background is read as a unit; anything outside is read as separate.
do: Put same-nature functions in one frame — login, sign up, forgotten password.
never: Put an unrelated item inside a group because the box was already drawn.
because: Nothing inside an enclosure needs further justification to be seen as related.

### LUC-05 · Enclosure is how you show context across a gap
rule: When related things sit apart, connect them rather than moving them together.
do: Enclose a tab link together with the page copy it governs; wrap an orphaned control and its label in one frame.
never: Break the tie between an element and the content it controls.
because: Context is the stated purpose of connectedness in web design.

### LUC-06 · A shared convention links a list
rule: One repeated visual convention is a connection.
do: Give every item in a set the same bullet shape, the same colour, or one numbering system — Roman or Arabic — carried end to end.
never: Number three of seven steps, or swap the marker halfway down a list.

### LUC-07 · Connect actions to the content they produce
rule: The strongest use of connection is a visible tie between an action and its result.
do: Ask which elements you want the user to group, then tie exactly those.
never: Leave the user to assume a control produced the panel now on screen.

### LUC-08 · Make the group read as chunks, not items
rule: Grouping's job is to replace a long list of individual elements with a few legible units.
do: Bound each group of controls so function and purpose are readable before any label is.
never: Ship a dense field of controls that can only be parsed one at a time.

### LUC-09 · Put related items on a line or curve
rule: Elements arranged on a line or curve are perceived as related to each other.
do: Lay the components of one relationship along one straight line or one continuous curve.
never: Scatter the members of a series at unrelated positions on the canvas.
because: Anything off the line reads as less associated with the set.

### LUC-10 · Aligned arrays carry category context
rule: Items in a consistent run belong to the label that heads the run.
do: Place each set of thumbnails along one horizontal line directly beneath its own category heading.
never: Let a run of items cross a category boundary.

### LUC-11 · A grid is context even with no visible structure
rule: A clear alignment makes association legible when the items share nothing else.
do: Build a vertical grid and let it define the categories for you.
never: Compensate for missing structure with prose.

### LUC-12 · Build continuation into flow UI
rule: Multi-step UI needs a visible path from step to step.
do: Number the steps, or draw arrows or a flow chart linking them; use a funnel shape to show progress toward the end.
never: Present an unordered stack of steps with no indication of where the user is in the run.

### LUC-13 · Let the eye follow a route
rule: Users follow paths instinctively — route them where you want them to go.
do: Carry the eye along the intended sequence with an unbroken run of connected elements.
never: Break the path between two consecutive steps and let them hunt for the way on.
because: The eye is accustomed to marking out and following pathways, so following them is free.

### LUC-14 · Continuation runs through negative space
rule: The eye draws a connecting line across the gaps in your layout, not only across the content.
do: Trace the implied line and check what it passes over; it must not cut through unrelated material.
never: Assume whitespace is empty — it is part of the line the eye follows.

### LUC-15 · Show the crossing, not the segments
rule: Where lines or curves meet, people see continuous paths, not a pile of fragments.
do: Design crossings so each path reads through the intersection as one line.
never: Let a junction read as several disconnected stubs meeting at a point.
because: We continue our perception of shapes beyond their ending points.

### LUC-16 · Use one cue per relationship
rule: Apply the fewest principles that establish the grouping; prefer efficient fundamentals over heavy-handed styling.
do: Let connectedness do the work rather than stacking proximity, similarity and enclosure on the same pair.
never: Signal one relationship three different ways at once.

### LUC-17 · Remove cue devices that restate a tie
rule: A connection line or frame that adds nothing beyond the relationship already visible is noise.
do: Audit for redundant borders and connectors after grouping is settled; keep the design elegant and invisible.
never: Ship connector lines and frames whose only effect is to be noticed.
because: Derived from the source's instruction to use the least amount possible and not employ three principles when one will do — it never states a removal test explicitly.

## Hard numbers

| Constant | Value | Note |
|---|---|---|
| Original Gestalt grouping categories | **5** — Proximity, Similarity, Continuity, Closure, Connectedness | Source's own list |
| Gestalt origin | **1910** — Max Wertheimer's railroad-crossing lights | Historical attribution, not a result |
| Connectedness pairing demo | **2** squares + **2** circles read as **2** related pairs | Perception demo, not a test result |
| Sketch demos | **6** dots → **2** groups of **3**; **3** broken lines → **3** lines, not **6** segments | Self-run pencil exercises, not test results |
| Strength vs other cues; connector distance | unknown: true | Asserted as strongest with no ratio; only "need not touch" is stated, no distance given |

Quantitative data in the source: **none.** No effect sizes, no sample sizes, no measured cue-strength ratios, no px/rem or geometry figures. Every claim is qualitative and illustrated with figures or self-run sketches.

## Decision procedure

1. **Name the ties** — list the elements that must read as one unit and what the relationship is. If you cannot name it, do not connect them.
2. **Pick one device** — colour, line/arrow, frame, or shared numbering/bullet. One relationship, one cue (LUC-16).
3. **Draw it** — enclose the group, route the connector clear of unrelated content, and check the line need not touch (LUC-03).
4. **Check what the line crosses** — trace the implied path through negative space; it must not pass through foreign content (LUC-14).
5. **Read the chunks** — can you name each unit's purpose before reading any label (LUC-08)?
6. **Check alignment and sequence** — does every series sit on a line, curve or grid with no item crossing a boundary (LUC-09 – LUC-11), and does every step, breadcrumb and flow show its place and its next step (LUC-12, LUC-13)?
7. **Strip the rest** — remove borders and connectors that only restate a tie (LUC-17). It should read as if it had no rules.

## Anti-patterns

- A dashed connector between two things that were already adjacent.
- Card inside card inside card.
- A connecting line routed through unrelated content to reach its target.
- Individually bordered chips in a row that is meant to read as one list, or numbered steps with nothing joining them.
- Chart points plotted off the line or curve that expresses their relationship.
- Three cues at once — colour, border and line — for one relationship.
- A thick, styled connector the eye snags on while scanning the content it links.

## Review checklist

- [ ] Every element that must read as a unit is joined by colour, line, frame or shape
- [ ] Connector lines route clear of unrelated content; not forced to touch their targets
- [ ] Enclosures contain only what belongs together
- [ ] Exactly one cue per relationship; no cue doing nothing
- [ ] Shared bullet, colour or numbering carried consistently across every item it links
- [ ] Flow UI shows a continuous path — numbered steps, arrows or funnel; context or ownership visible wherever related content sits apart
- [ ] Series sit on a line, curve or grid; no category boundary crossed
- [ ] Nothing connected that isn't related; nothing related left unconnected
- [ ] Grayscale/zoom-out pass: groups still legible, borders still quiet

## Caveats

- The source contains **no quantitative data** — no effect sizes, sample sizes, measured accuracy or scan times, no ratios between cues. All of it is `unknown: true`. Evidence is argument plus figures and pencil-and-paper sketches the authors ask readers to run themselves; no controlled experiment is cited for any rule here. Its illustrations are the 747 cockpit dashboard, Google search result borders, speech vs thought bubbles, and graph and portfolio layouts.
- **The "strongest cue" claim is present**, stated three ways in one article ("the strongest of the Gestalt Principles concerned with relatedness"; "of all the principles suggesting objects are related, uniform connectedness is the strongest"; "there is only one principle of perception that is more powerful than proximity"), and echoed in a second article saying the grouping effect "works even when it contradicts other Gestalt principles, such as proximity and similarity." It is **single-source in framing and completely unquantified** — no data supports it. The same corpus also says symmetry "takes precedence over proximity" and past experience is "perhaps the weakest" principle. Use precedence as a default for tie-breaks only.
- Every precedence claim here is qualified "all else being equal" (Palmer) — it holds only where competing cues are otherwise equal.
- **Scope:** this file's source also covers Proximity, which has its own skill — `law-of-proximity.md`. Do not restate its rules. Continuation / Good Continuation is folded in here (LUC-09 – LUC-15) because the source treats it as part of the same set and it operates through the same connecting devices. Sibling Gestalt skills, not duplicated here: `law-of-similarity.md`, `law-of-common-region.md`, `law-of-pragnanz.md`.
- LUC-17 is **derived**, not stated: the source gives "use the least amount possible" and "don't employ three of them when one will do", but no test for removing a redundant cue device.
- The source's own closing summary block **mislabels two principles**, calling proximity "also known as Emergence" and similarity "also known as Invariance", while its own body text defines emergence and invariance separately. Do not reuse those aliases.
