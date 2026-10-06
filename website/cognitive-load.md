---
name: cognitive-load
title: Cognitive Load — Design Rules
description: Rules for minimising the mental effort a user spends understanding and operating an interface. Load when laying out a screen, building a form or flow, writing onboarding, simplifying a cluttered UI, choosing what to show, or reviewing UX.
applies_when: [screen layout, forms and flows, onboarding, navigation, settings, simplification, ux review]
priority: core
rules: 22
---

# Cognitive Load — Design Rules

## Core principle

Working memory is small and cannot be upgraded. Reduce the load your design *adds*; never remove the load the *task* requires.

```
intrinsic load   = difficulty of the task itself     → manage by chunking/sequencing
extraneous load  = difficulty caused by your design → REMOVE. This is your job.
germane load     = effort invested in learning       → encourage, don't optimise away
```

## Rules

### CL-01 · One primary action per screen
rule: Every screen has exactly one primary action.
do: Make it visually dominant — filled button, largest target, strongest contrast.
never: Two competing primary buttons.
because: Competing priorities force a decision the user never asked to make.

### CL-02 · Delete before you optimise
rule: Remove elements that do not serve the user's goal.
do: Cut redundant links, irrelevant images, decorative flourishes, excessive colour.
never: Assume a UI element is needed because it exists.
because: Only *overuse* backfires; meaningful imagery and typography are valuable.

### CL-03 · Simplicity must not cost clarity
rule: Simplify layout, never meaning.
do: If a simplification makes the interface harder to interpret, revert it.
never: Hide a required action to make a screen look cleaner.

### CL-04 · Build on patterns users already know
rule: Reuse labels, layouts, and gestures users have met elsewhere.
do: Brand-tint familiar patterns rather than redesigning them.
never: Invent a new interaction for a solved problem.

### CL-05 · Offload memory to the system
rule: Never require the user to remember or re-enter information the system can supply.
do: Smart defaults (editable), autofill, re-display previously entered values, OS sign-in/biometrics.
never: Show an empty field the app already knows the answer to.

### CL-06 · Minimise choices
rule: Fewer visible options = less decision time.
do: Remove redundant options; group the rest under meaningful categories.
never: Present every variant simultaneously "to be safe".

### CL-07 · Show choices as a complete group
rule: A visible subset must not imply it is the whole set.
do: When you split options into groups, signal that other groups exist.
never: Show 3 of 12 filters with no indication the other 9 exist.

### CL-08 · Hidden menus need discoverability cues
rule: Hiding options reduces discoverability; pay it back.
do: Pair hidden menus with visible entry points, or use out-of-the-way links to the same content.
never: Hide a frequently used action in a secondary menu.

### CL-09 · Readability over decoration
rule: Typography should be pleasant, appropriate, and easy to read.
do: Design should feel "relatively invisible".
never: Use a font style that carries no unique meaning.

### CL-10 · Icons need labels unless universal
rule: Only these work alone: print, close, play/pause, reply, share.
do: Pair every other icon with a text label.
never: Ship an icon-only control for a novel action.

### CL-11 · Consistency is a load reducer
rule: Same colours, typography, icons, and layouts everywhere.
do: Define design tokens and a style guide; audit across devices.
never: Let one screen diverge from the pattern.

### CL-12 · Tailor to the most vulnerable users
rule: Design first for novices, children, seniors, and users under stress.
do: Support Dynamic Type, high contrast, reduced motion, and layout preferences.
never: Size text for the average developer with a large monitor.

### CL-13 · Show only what this screen is for
rule: Every screen has one purpose.
do: Ask: what is the primary purpose, what can be removed, what is redundant?
never: Put secondary content on a primary screen — move it to its own screen or menu.

### CL-14 · Remove steps
rule: Every extra step is a drop-off point.
do: Map the flow, delete no-value steps, minimise taps.
never: Gate value behind registration or extra clicks before the user has seen anything.

### CL-15 · Never split attention
rule: Related elements must be adjacent.
do: Group by function; use grid alignment; separate groups with subtle lines or spacing.
never: Put a label on the left and its input on the right of a wide layout.

### CL-16 · Immediate feedback on every interaction
rule: Every tap, hover, and submit must produce a visible response.
do: State changes, confirmations, loading indicators, skeleton screens, haptics.
never: Leave an interaction visually silent.

### CL-17 · Chunk long content and long forms
rule: Break long text and long input flows into units.
do: Short paragraphs, clear headings, bold keywords, bullets, summary; multi-step forms with a progress marker.
never: Present one wall of text or a 30-field form on one screen.

### CL-18 · Mix content types
rule: Harmonise text, images, video, and infographics.
do: Use visual weight to guide the eye.
never: Fill a screen with a single undifferentiated content type.

### CL-19 · Balance visual weight
rule: Use symmetry or intentional constructive asymmetry.
do: Align to a grid so structure is instantly legible.
never: Place elements at arbitrary positions.

### CL-20 · Remove lag
rule: Delay is extraneous load.
do: Optimise perceived speed: skeleton screens, optimistic UI, progressive rendering.
never: Ship a blank screen while waiting.

### CL-21 · Put focus where the action is
rule: Start the cursor/focus in the primary field.
do: Auto-focus the field the user almost certainly wants (e.g. a search box).
never: Leave focus on the body or on a decorative element on load.
because: Micro-interactions compound. Each one removed is one less pause.

### CL-22 · Don't judge ease of use by your own comfort
rule: Your capacity is not the user's.
do: Test with novices, seniors, and distracted users.
never: Approve a UI because it feels obvious to you — high-capacity people overestimate ease (see CL-12).

## Hard numbers

| Constant | Value | Note |
|---|---|---|
| Working memory capacity | ~7 ± 2 units | 1956 figure; see CHUNKING skill for the disputed estimates |
| Practical chunk target | **3–6 items (4 ± 1)** | Memory and data-entry strings only |
| Menu item caps | **No limit from Miller** | Menus are recognition-based; all options stay visible |
| Perceived load limits | ~10–15 seconds attention, then re-orient cost rises sharply | Not a design target |

## Decision procedure

When a screen feels heavy, work in this order:

1. **Purpose** — state the screen's single job. Anything not serving it is a candidate for removal.
2. **Steps** — list every step to complete the task. Delete the ones with no value.
3. **Choices** — count visible options. Remove redundancy; group the remainder.
4. **Memory** — find every place the user must read, remember, or decide what the system already knows.
5. **Attention** — check nothing related is separated (CL-15) and nothing competes for focus.
6. **Feedback** — verify every interaction responds immediately (CL-16).
7. **Audience** — re-check at senior / novice / stressed settings.

## Anti-patterns

- Registration wall before any value is shown.
- Cursor in the wrong field on first load.
- Hidden filters with no signal that more exist.
- Two primary CTAs on one screen.
- Decorative imagery crowding out controls.
- Inconsistency between screens of the same product.
- Blank/silent waits.

## Review checklist

- [ ] One clear purpose per screen
- [ ] Exactly one primary action
- [ ] Every element serves the user's goal
- [ ] Familiar patterns and standard labels
- [ ] Icons labelled unless universal
- [ ] Choices minimised, grouped, and signalled as complete
- [ ] Long content chunked; long forms stepped with progress
- [ ] Related elements adjacent
- [ ] Defaults/autofill used instead of blank fields
- [ ] Immediate feedback everywhere; loading states present
- [ ] Consistent colour, type, spacing, link styles; no typos
- [ ] Onboarding for non-obvious features
- [ ] Accessible and personalisable (seniors, children, disabled users)
- [ ] Flow audited for unnecessary steps

## Caveats

- The three-load additivity model is **contested**; types likely influence each other rather than summing.
- Physiological load measures work in labs and **do not reliably transfer** to real use.
- In **learning** contexts, some effortful processing is beneficial ("desirable difficulty"). Remove extraneous load; retain productive struggle. Do not build a no-effort learning flow.
- Many of these rules are practitioner heuristics, not controlled experimental results.
- Contested definitions and evidence limits are recorded above. Check them before defending a rule in review.