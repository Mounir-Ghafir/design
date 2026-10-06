---
name: fitts-law-touch-targets
title: Fitts's Law & Touch Targets — Design Rules
description: Rules for sizing, spacing and placing interactive targets, and for thumb reach on touch. Load when building or reviewing buttons, icons, list rows, tabs, menus, forms or any tap interface, choosing target minimums, deciding where a control goes, or auditing mis-taps.
applies_when: [touch targets, buttons and controls, forms and CTAs, menus, navigation, mobile layout, spatial UI, accessibility audit, ux review]
priority: core
rules: 19
---

# Fitts's Law & Touch Targets — Design Rules

## Core principle

Time to acquire a target is a function of **distance divided by size** — logarithmically. Bigger and closer is faster and more accurate; smaller and farther is slower and more error-prone.

```
MT = a + b · log₂(D/W + 1)

MT = movement time          D = distance from the start point to the target centre
                             W = target width along the axis of motion
                             a = intercept          → empirical, per device / hand / user
                             b = slope (1/b ≈ throughput) → empirical, per device / hand / user
```

`a` and `b` depend on the input device, the hand and the user. Never carry mouse constants onto a finger. Use the law as a directional rule — bigger, closer, less crowded — not as a stopwatch.

Three structural cautions:

- **Log, not linear.** Twice as far is longer, not twice as long. Distance buys you logarithmically; size buys you much faster.
- **2D targets.** The formula is one-dimensional, along the direction of movement. Rectangular targets need **W and H treated separately** — for typical UI rectangles use the **smaller** of the two (MacKenzie & Buxton 1992). A 44 × 44 pt button is not "88 pt wide".
- **Constrained paths use the steering law.** Where geometry dictates the trajectory — hierarchical pull-downs, docked toolbars — the path narrows toward the target, an *inverted triangle*; model that with the steering law, not a free-pointing D/W ratio.

**Scepticism gate:** most classic mouse-era corollaries of this law do **not** transfer to touch. Size, spacing, proximity and consequence survive (FT-01…FT-08); the mouse's favourite tricks do not (FT-10, FT-14, FT-15, FT-19).

## Rules

### FT-01 · Platform minimums are floors, not targets
rule: Every interactive element meets its platform minimum; exceed it where the screen allows.
do: iOS **44 × 44 pt**, Material **48 × 48 dp**, visionOS **60 × 60 pt**, WCAG 2.2 AA floor **24 × 24 CSS px**.
never: Treat 24 × 24 CSS px as a design goal — it is the legal floor, below both platform minimums.

### FT-02 · Make the whole visible target live
rule: The entire visible region of an element responds, not just its icon or label.
do: Treat icon + text label as one target; make full link blocks and rows tappable.
never: Require the finger to land on a specific glyph inside a larger button.

### FT-03 · Space interactive elements apart
rule: Leave **8–12 pt** between interactive elements as a minimum.
do: Space small targets further apart than large ones; widen the gap where a mis-tap is costly.
never: Pack dense rows of small controls edge to edge.

### FT-04 · Invisible padding is not size
rule: Hidden hit area does not enlarge a target in the user's mind.
do: Enlarge the visible affordance itself, then extend the active area around it.
never: Shrink the icon and rely on transparent slop to catch the tap.

### FT-05 · Size by error rate, not by taste
rule: Derive target size from where the mis-tap rate levels off, in physical units.
do: Record real taps and misses; pick a capture rate (~95%) and size to it; verify in mm on device.
never: Quote a pixel rule without checking what the pixel physically is on that screen.

### FT-06 · Bigger is better only up to a point
rule: Oversized controls stop reading as controls; users aim at the icon or label, not the extent.
do: Size for the element's expected screen location; keep labels short and clear.
never: Inflate a primary button to fill a row just to make it "safe".

### FT-07 · Cluster controls that are used in sequence
rule: Consecutively used controls belong next to each other — close, but spaced.
do: Put Submit beside or just below the last form field; keep a sticky bottom action bar for long flows.
never: Park Save/Submit in a distant header, forcing long travel against the flow.

### FT-08 · Put controls where the finger already is
rule: Place targets near the user's most probable previous position.
do: Sequence: read → act in one region; keep the next action near the last one.
never: Assume you know where the finger is — on touch you do not (FT-13).

### FT-09 · Never small and far apart
rule: Small objects spread widely take the longest to acquire.
do: Enlarge the target or move it closer; usually both.
never: Ship a grid of small, widely separated controls as the primary navigation.

### FT-10 · Edges and corners are the *hardest* places to tap
rule: The mouse-era "magic edge / magic corner" advantage does **not** exist on touch.
do: Place larger targets near edges and corners; reserve corners for a few low-use menus and anchored actions.
never: Assume a corner-anchored control is easy to hit, or move a frequent action there for that reason.

### FT-11 · Centre for primary content
rule: Users prefer to view and touch the middle of the screen; they scroll content toward it.
do: Centre primary content; put secondary actions in top/bottom bars; put tertiary functions in corner menus.
never: Assume a top-left-first, desktop scanning order on a touch screen.

### FT-12 · Primary actions in the thumb zone — as a heuristic
rule: Put primary actions where a thumb comfortably reaches.
do: Anchor them low and central; support both left- and right-handed users symmetrically.
never: Cite the classic thumb-sweep chart as authoritative — the source flags it as incorrect.

### FT-13 · Design for every grip and both hands
rule: Grip is unknown, changes unconsciously, and cannot be self-reported.
do: Design for one-thumb, two-thumb, cradled, one-hand-plus-other-finger, and tablet holds; offer mirrored layouts.
never: Optimise for a single right-handed, one-handed, bottom-of-screen assumption.

### FT-14 · Use it directionally, then validate
rule: Bigger / closer / less crowded is a design heuristic, not a predictor.
do: Validate with real users in real contexts — walking, one-handed, distracted.
never: Present a computed Fitts index as a measured or predicted tap time.

### FT-15 · Menu options appear next to their trigger
rule: Options must open beside the label or handle that opened them.
do: Use a popover/context menu adjacent to the tapped item; order linear menus so the most-used sit nearest the handle, and centre the handle when usage is even.
never: Send options to a distant bottom sheet (a known anti-pattern in shipped mail clients).

### FT-16 · Keep menus short
rule: Long menus raise movement-time demands and are a documented failure mode.
do: Shorten, group, or move rarely used items behind a second level with a discoverable cue.
never: Ship a 20-item drop-down; long drop-downs and title menus impede.

### FT-17 · Do not default to radial menus
rule: Pie/radial menus are fast in theory — equal distances, large wedges — and slow in practice.
do: Consider them only for expert, repeated, screen-anchored sets; expect a learning curve.
never: Choose them because the equidistance maths is flattering; their value fades away from the cursor and direction/handedness biases appear.

### FT-18 · Separate destructive from primary; prefer undo
rule: Destructive controls must not sit beside the primary action.
do: Offer undo (toast/snackbar with undo); keep destructive and unrelated items far apart.
never: Place Delete or Cancel flush against the main CTA, or make "Are you sure?" the only recovery.

### FT-19 · Do not time out controls
rule: People live in the world and are distracted; short-lived UI fails them.
do: Keep controls available long enough; make re-summon obvious; provide a tap alternative for every gesture.
never: Let video-player or notification chrome vanish before a distracted user can react.

## Hard numbers

| Constant | Value | Note |
|---|---|---|
| Apple HIG minimum touch target | **44 × 44 pt** | iOS baseline; a floor, not a goal |
| Google Material minimum | **48 × 48 dp** | Android baseline |
| WCAG 2.2 Level AA floor | **24 × 24 CSS px** | Legal/accessibility floor — below both platform minimums |
| Apple visionOS minimum | **60 × 60 pt** | Spatial input is less precise |
| Spacing between interactive elements | **8–12 pt** | Increase where an accidental tap is costly |
| Observed tap-cluster sizes | **~7 mm / ~12 mm**, holding **~95%** of taps | **95%, not 100%.** ~7 mm = men's thumb reach and screen centre; ~12 mm = women's hands and screen corners. 2013–2017 capacitive era |
| Standard-derived sizes usually are | Where the error rate **levels off** | Not "as big as possible" |

## Decision procedure

1. **Classify the input.** Mouse/trackpad (the classic law largely applies) or finger/hand (most corollaries do not).
2. **Measure.** Audit every target against its platform minimum; flag anything under.
3. **Check the live region.** Icon + label, full link, full row — one target.
4. **Check the gaps.** 8–12 pt minimum; destructive and unrelated items much further apart.
5. **Check the path.** Is the CTA beside the last input? Do menu options open beside their trigger?
6. **Check the reach.** Primary action reachable by either hand and in more than one grip.
7. **Check the zone.** Primary content centred; nothing critical relying on an edge or corner being "easy".
8. **Check the consequence.** Undo available; destructive separated from primary.
9. **Validate.** Record taps and misses; size to a chosen capture rate; verify physical size on real devices.

## Anti-patterns

- Two competing actions inside one 44 pt button.
- Icon-only control with no label and no visible padding.
- Hit slop relied on in place of a visible target.
- Submit/Save stranded in a header on a long form.
- Options in a far bottom sheet instead of beside the trigger.
- Radial menu shipped as the default "Fitts-optimal" choice.
- Delete or Cancel flush against the primary CTA.
- "Are you sure?" as the only path back from a destructive action.
- Corner-anchored control assumed to be easy to reach.
- Auto-hiding controls that expire before a distracted user acts.
- Any quoted time-to-tap figure for touch.

## Review checklist

- [ ] Every target ≥ 44 × 44 pt (iOS) / 48 × 48 dp (Material) / 60 × 60 pt (visionOS); WCAG floor met
- [ ] Whole visible area of each target is active (icon + label, full link, full row)
- [ ] 8–12 pt minimum gaps; larger where a mis-tap is costly
- [ ] Destructive controls separated from primary; undo provided
- [ ] CTA adjacent to the last input, not in a distant header
- [ ] Menu options open beside their trigger; menus short and frequency-ordered
- [ ] Primary content centred; no critical action depending on an edge or corner
- [ ] Edge and corner targets are larger, not assumed easy
- [ ] Primary action reachable by either hand and in more than one grip
- [ ] Sizes verified in physical units on real target devices
- [ ] Tap and miss data collected; size justified against a stated capture rate

## Caveats

- **Hoober's central critique:** Fitts's Law as published is largely **not applicable to touch**. Touch results are predictable and repeatable but do not fit an existing model, so he publishes **guidelines, not formulas**.
- **No time-to-tap constants exist for touch.** None are published — values vary too widely with context. Do not invent them or reuse mouse `a`/`b`.
- **Mouse-era corollaries that do NOT transfer:** "bigger is always better"; "edges are infinitely deep / magic corners"; "the pixel under the pointer is the zero point"; "pop-ups are best". Treat each as suspect on touch.
- **Unresolved conflicts** (recorded, not silently decided): bigger-is-always-better vs only-as-big-as-needed; edges-are-fast vs edges-are-hardest-to-tap; Cancel/Submit adjacency vs destructive-action separation; confirm dialogs vs undo preference. Decide per product and note the trade-off taken.
- **Data age:** 1,300+ observed users, 2013–2017, capacitive phones of that era. Re-validate for foldables, larger phones and tablets.
- **The thumb-sweep chart is flagged as incorrect** — it assumes a one-handed grip with taps at the bottom.
- **Standards need scrutiny.** Platform minimums may follow platform convention as much as human factors; ISO's 22 × 22 mm reflects IR-grid kiosks; pixel rules are device-dependent.
- Fitts's law covers **rapid goal-directed pointing**, not continuous motion such as drawing.
- Conflicts and evidence limits are recorded above. Check them before defending a rule in review.
