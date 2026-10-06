---
name: von-restorff-effect
title: Von Restorff Effect — Design Rules
description: Rules for making the one element that matters — the key action, primary CTA, error, or warning — visually distinctive so it is remembered. Load when choosing what to emphasise, designing a CTA, styling alerts and security messages, highlighting a price or offer, or when a screen feels visually loud.
applies_when: [primary action, cta design, alerts and errors, pricing, security warnings, emphasis, hierarchy, accessibility review]
priority: supporting
rules: 14
---

# Von Restorff Effect — Design Rules

## Core principle

The Von Restorff effect (also called the **Isolation Effect**) predicts that when multiple similar objects are present, the one that differs from the rest is most likely to be remembered — and it is afforded more weighting than its peers.

Make important information or key actions visually distinctive. But make only **one** thing stand out, with restraint, and never let the difference rest on colour or motion alone.

## Rules

### VRE-01 · Give the one element that matters its difference
rule: When multiple similar objects are present, the one that differs from the rest is most likely to be remembered.
do: Decide the single element every user must notice — the key action or critical information — and make it differ from its peers.
never: Let the most important element look identical to the rest of its group.
because: Sameness hides an element inside its group; difference is what draws recall to it.

### VRE-02 · Break it out by colour, shape, position, size, or texture
rule: Items that stand out from their peers by colour, shape, position, size, and texture are more memorable.
do: Pick one visible property that cleanly separates the chosen element; motion is an extra channel with its own check (VRE-09).
never: Use two weak half-changes where one clear difference would isolate the item.
because: The isolation is perceptual; a half-measure leaves the item visually inside the group.

### VRE-03 · One standout per view
rule: Only one element per view gets the difference.
do: Confirm no second element competes for the treatment; reduce every other candidate toward its group's baseline.
never: Make two or more elements stand out on the same screen.
because: If everything stands out, nothing is remembered as different. Emphasis is comparative.

### VRE-04 · The primary CTA differs from ordinary actions
rule: The main call-to-action must look different from the rest of the action buttons.
do: Give the primary CTA its own colour, shape, position, or size so it reads as distinct from a plain action button.
never: Style the primary CTA identically to secondary buttons.
because: This is the standard UI application of the effect — the reason CTAs look different from every other button.

### VRE-05 · The standout must stay legible and understood
rule: The isolated element must be understood, not just noticed.
do: Make what the CTA does clear at the moment it stands out and keep it recognisable across the app.
never: Trade clarity for spectacle — an ambiguous standout wastes the effect.
because: Users need to differentiate a simple action from the CTA and remember the CTA's purpose through use.

### VRE-06 · Restrain emphasis — elements compete
rule: Use restraint when placing emphasis on visual elements.
do: Treat emphasis as scarce; every extra emphatic element steals weight from the isolated one.
never: Add emphasis "to be safe" on several elements.
because: Emphatic elements compete with one another, and the difference — the whole mechanism — dissolves.

### VRE-07 · Salient elements must not read as ads
rule: Keep the standout inside the visual register of a product UI.
do: Scale contrast and decoration to the level a product, not a banner ad, would use.
never: Amplify so far that the isolated item is mistaken for an advertisement and tuned out.
because: A salient item that reads as an ad loses both trust and attention.

### VRE-08 · Never rely on colour alone
rule: Colour must not be the only signal of contrast.
do: Pair the colour difference with shape, size, position, or texture so the distinction survives without colour.
never: Encode "this is the important one" in colour alone.
because: Relying exclusively on colour excludes users with a colour vision deficiency or low vision.

### VRE-09 · Motion contrast needs a sensitivity check
rule: Motion is a legitimate contrast channel — use it cautiously.
do: Consider users with motion sensitivity whenever motion communicates contrast; provide a reduced-motion alternative.
never: Animate the standout by default for everyone.
because: Motion as a contrast cue is unsafe for a real share of users.

### VRE-10 · Delete or de-emphasise the competitors
rule: The isolated element needs a quieter field around it.
do: Cut decorative flourishes and secondary emphasis that point at anything other than the chosen element.
never: Leave competing highlights standing once the standout is chosen.
because: Recall of the isolated item depends on the homogeneity of the elements around it (see VRE-03).

### VRE-11 · The standout must keep hierarchy and integrity
rule: Difference strengthens the chosen element within the existing visual system.
do: Make the isolated element a step up in the same system of type, colour, and spacing.
never: Break the grid or restyle surrounding elements to create the contrast.
because: Distinctiveness that respects the system reads as priority; arbitrary difference reads as noise.

### VRE-12 · Remember the sibling: position (serial position effect)
rule: First and last items of a list or string are best recalled; items in the middle suffer the worst recall.
do: When choices are serial, place the most important actions at the ends — apps moved from hamburger menus to top/bottom bar navigation with key actions to the right or left for this reason.
never: Bury the most important action in the middle of a menu or list.
because: Position-based recall is a distinct sibling mechanism, not a substitute for distinctiveness.

### VRE-13 · Keep the treatment consistent (patterns aid recall)
rule: The same role gets the same distinctive treatment across the product.
do: Use one consistent style for primary CTAs, another for destructive or error states, another for warnings.
never: Hand the standout to a different element on each screen.
because: Consistent patterns are easier to recognise and learn; the standout then telegraphs its role by its form.

### VRE-14 · Spend the difference on what matters
rule: Reserve the isolated treatment for information or actions whose loss costs the user.
do: Before emphasising, ask what the user would be harmed by missing.
never: Spend the effect on promotional or low-value content while errors and security warnings use standard styling.
because: If the difference is wasted on trivia, the effect is spent and the genuinely important item is remembered no better than its peers.

## Hard numbers

| Constant | Value | Note |
|---|---|---|
| Recall advantage of the isolated item | `unknown: true` | Source gives no recall percentages for the effect |
| Original experiment details | `unknown: true` | Source names no experiment, researcher, or year |
| Recall after **3 days** for orally-presented information | **10%** | Source's figure from its Picture Superiority Effect example (a sibling effect, not the Von Restorff effect) |
| Serial position recall figures | `unknown: true` | Source states primacy/recency > middle qualitatively; no figures |

## Decision procedure

When a screen needs a focal point, work in this order:

1. **Find the one** — which element, if missed, costs the user most? That gets the treatment.
2. **Check homogeneity** — the rest of the group must look alike; delete or de-emphasise competitors (VRE-10).
3. **Pick the channel** — colour, shape, position, size, or texture: one clear difference (VRE-02, VRE-08).
4. **Verify the role** — the difference matches the element's job, matches the pattern used elsewhere (VRE-13), and keeps hierarchy intact (VRE-11).
5. **Rate the volume** — does it still read as product UI rather than an ad (VRE-07)? Is restraint intact (VRE-06)?
6. **Check motion and colour** — reduced-motion path for animated contrast (VRE-09); redundant non-colour cues for colour-deficient and low-vision users (VRE-08).
7. **Count the standouts** — if more than one element stands out, renegotiate until one remains (VRE-03).

## Anti-patterns

- Two or more emphasised elements on one view.
- Primary CTA styled the same as the secondary buttons.
- Colour-only emphasis, excluding colour-deficient and low-vision users.
- Emphasis so loud the element reads as an advertisement.
- Pulsing or animated standout with no reduced-motion path.
- Standout spent on promotional content while errors and warnings look standard.
- Arbitrary difference that breaks the grid or style system.

## Review checklist

- [ ] Exactly one element per view differs from its group
- [ ] The chosen element is the one whose loss costs the user most
- [ ] Difference is a single clear channel among colour, shape, position, size, texture
- [ ] Not colour-only; redundant cues exist
- [ ] Primary CTA is distinct from all other actions and its purpose is legible
- [ ] Emphasis restrained; nothing competes; nothing reads as an ad
- [ ] Motion contrast has a reduced-motion alternative
- [ ] Standout preserves grid, hierarchy, and system integrity
- [ ] Same role uses the same treatment across screens
- [ ] Important serial choices are placed at the ends (worst recall sits in the middle)

## Caveats

- The source (a 2017 UX article by Andri Budzinskiy) is **exposition, not an empirical study**: it reports no original-experiment details, dates, sample sizes, or effect sizes for the Von Restorff effect; the researcher attribution and classic figures are absent and marked `unknown: true` above.
- Scope/siblings: the same source treats serial position (VRE-12) and cognitive load; selective attention is closely related to the Von Restorff effect — see `selective-attention.md`, `serial-position-effect.md`, and `cognitive-load.md` (CL-10); attention and decision biases live in `cognitive-bias.md`.
- Most of the raw scraped file was unrelated pasted journal text (superior pattern processing; working memory and attention); all of it was dropped.