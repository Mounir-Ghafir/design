---
name: color-palette
title: Color Palette — Design Rules
description: Rules for building a color palette for a design system — base, neutral, and semantic families, shade and tint scales, the 60-30-10 distribution, WCAG contrast, color-vision-deficiency checks, role-based naming, and design tokens. Load when creating or revising a brand palette, setting up a design system's color, defining status and state colors, or reviewing the accessibility of colour usage.
applies_when: [color palette, design tokens, brand colors, design system setup, accent and secondary colors, state colors, dark mode theming, color contrast, accessibility review, visual hierarchy]
priority: core
rules: 21
---

# Color Palette — Design Rules

## Core principle

A palette is a discipline of restraint: a few base hues, full lightness scales per hue, clear semantic families, and contrast verified on the pairs you actually render — named by role, not by code. If two colors fight, the palette is wrong, not the design.

```
brand      = 1–2 hues the product is recognised by      → dominant + accent
neutral    = grey scale for text, borders, backgrounds  → tinted, never pure black/white
semantic   = success / warning / danger / info          → one colour per meaning, everywhere
```

## Rules

### CP-01 · Start with one dominant color
rule: The palette begins with a single color that appears most often in the UI and is strongest associated with the brand.
do: Choose that one color first (e.g. Netflix red, Spotify green, Meta blue), then derive everything else from it.
never: Pick five colours you like and work backwards to a brand.
because: The dominant color guides users toward key points of the UI and is the anchor every harmony, scale, and token builds on.

### CP-02 · Align to brand, audience, and culture
rule: The palette must fit the brand's personality, the audience's expectations, and the culture(s) the product serves.
do: Extract primary and secondary colours from brand guidelines when they exist; research users' needs and emotional expectations first; verify cultural meaning before locking a colour.
never: Choose colours on taste alone, or assume a colour's meaning transfers across cultures (money is red in China, green in the USA).
because: Colour meaning varies by culture, and there is little real research proving a universal emotional effect; brand fit and audience perception decide whether a palette is appropriate.

### CP-03 · Choose a color harmony first
rule: Select a colour scheme — monochromatic, analogous, complementary, split-complementary, triadic, tetradic, or square — before picking individual colours.
do: Derive all palette hues from the chosen harmony; start with monochromatic or analogous (easiest to balance) and use complementary or split-complementary for attention contrast.
never: Combine unrelated colours with no dominant hue.
because: Harmonies are the template a palette is built from; the more hues you introduce, the harder it is to balance and enforce visual hierarchy.

### CP-04 · Keep the palette small
rule: Few base hues — typically 5–7 — carry a whole UI, even when the shipped set holds 50–80 values.
do: Limit your first pass to about three colours; for the full system count 1–2 brand colours, 1 accent, a neutral scale, and 4 semantic colours.
never: Give every component its own colour.
because: Fewer colours reinforce visual hierarchy because there is less competing for attention — the cereal-aisle problem is the failure mode.

### CP-05 · Plan base, neutral, and semantic families
rule: Structure the palette into brand (primary/secondary), semantic/status, and neutral families.
do: Separate status colours (green success, yellow/amber warning, red error/destructive, blue informational) from brand colours, and keep neutrals (text, borders, backgrounds) as their own scale.
never: Use a brand colour for warnings or a status colour for brand elements.
because: Semantic colours carry fixed meaning that must be consistent everywhere; mixing families breaks both brand and status communication.

### CP-06 · Build a full shade and tint scale per base
rule: Every base colour gets a full scale of lighter tints and darker shades for backgrounds, borders, hovers, and text.
do: Generate roughly 9–10 steps per hue (e.g. 50, 100, 200 … 900); the lightest values become backgrounds and hover states, the mid-range the primary interactive colour, the darkest text and high-contrast borders.
never: Add shades one-off per screen as needs appear.
because: A complete scale supplies every needed state without a new colour decision per component, keeping the palette "easy to modify" and ready for theming.

### CP-07 · Keep shade scales compact
rule: Ship only the shades you actually use — typically 6–10 per colour and around 10 for the neutrals.
do: Start small and trim ruthlessly; add a shade only when a real use case appears.
never: Generate a maximal scale "just to be safe".
because: More shades mean more choices and more maintenance, and leave designers with decision paralysis when they build screens.

### CP-08 · Stay inside the usable lightness band
rule: Keep shade lightness between about 95 (lightest) and 30 (darkest).
do: Use the lightest shades for tinted backgrounds and the darkest for text; test shades on an example UI (a few fields, buttons, and boxes).
never: Go lighter than 95 — colours become barely distinguishable — or rely on shades darker than 30 — saturated colours lose saturation rapidly.
because: This is practitioner guidance from the mobile/hued sources; a lightness range of 95 to 30 is reported as the sweet spot. `unknown: true` — not a measurement.

### CP-09 · Shift hue as shades darken
rule: Do not hold hue constant across a lightness scale; shift it as shades darken so the dark end stays vibrant.
do: For yellow, slowly decrease hue toward orange and red as lightness falls so the dark versions stay rich instead of muddy; experiment with hue curves per colour.
never: Darken every colour along one fixed in-hue path.
because: With lightness fixed, the nice yellow turns muddy fast; a hue shift keeps the result vibrant.

### CP-10 · Set saturation last
rule: Decide lightness and hue first; choose saturation only after them.
do: Reserve full saturation for what draws attention — an accent or active element — and keep surfaces, text, and neutrals low in saturation.
never: Saturate a whole palette or many adjacent elements at once.
because: Too many saturated colours together overwhelm users, and saturation is what draws attention — using it everywhere makes nothing stand out.

### CP-11 · Neutralize with tinted grays, not absolute black or white
rule: Build neutrals from the primary hue at low saturation, and avoid absolute black and white.
do: Use tinted greys (the brand hue at low saturation) for backgrounds and text so they harmonise with the palette; pick a slightly cool or warm grey rather than a dead neutral.
never: Use pure black on pure white as surface/text combinations, or a pure grayscale with no relationship to the palette.
because: Pure grayscale doesn't exist in nature and looks unnatural; absolute white and black strain the eyes from their extreme contrast.

### CP-12 · Follow the 60-30-10 distribution
rule: Use roughly 60% dominant, 30% secondary, 10% accent colour.
do: Make the dominant share the background or surface (usually a neutral or muted brand tint, as in Apple News's white/light-gray + blue + pink), the secondary share cards/sidebars/secondary buttons, and the 10% the CTAs, active states, and links — the brand colour's heaviest lifting.
never: Spread the accent colour evenly across the interface, or make the dominant surface a loud saturated hue.
because: The ratio creates visual balance and keeps the accent where it must draw the eye.

### CP-13 · Define state colors up front
rule: Define state colours — active, focus, negative, positive, notice — before components use them.
do: Pair each state to a named colour: active can match the brand colour, focus a shade of blue, negative red, positive green, notice yellow or orange; attach each to its message so users grasp the meaning.
never: Invent a new colour the first time a new state appears in a component.
because: States are consistent signals; predefined colours keep error, notice, and success meaning identical across the whole product.

### CP-14 · Meet the contrast thresholds
rule: Every text/background and active UI component pair must pass the WCAG contrast thresholds for its use.
do: Test normal text at ≥ 4.5:1, large text at ≥ 3:1, and active UI components and graphical objects (icons, graphs) at ≥ 3:1; use a contrast checker (WebAIM, Coolors, accessible-colors.com); remember the lighter colour is 4.5 times lighter when a ratio is 4.5:1.
never: Rely on eyeballing contrast, or approve a brand palette never verified on the pairs you actually render.
because: Contrast decides readability for people with low vision and under poor lighting; low-contrast palettes fail exactly those users. Grey buttons can also read as disabled even when intended otherwise.

### CP-15 · Never encode information in color alone
rule: Any meaning carried by colour must also be conveyed by text, icon, pattern, shape, or size.
do: Add an icon and error text to red validation, labels or pattern fills to chart series, and text to status badges; test your design in grayscale.
never: Make colour the only difference between a valid and an invalid field, between two chart series, or between any two states.
because: Colour-alone information is WCAG 1.4.1 non-compliance and fails users with colour vision deficiency.

### CP-16 · Simulate color vision deficiency
rule: Check every palette under colour-vision-deficiency simulation before shipping.
do: Use Color Oracle, Coblis, Sim Daltonism, or Chrome DevTools "Emulate vision deficiencies"; test red/green pairs specifically.
never: Call a palette accessible without a simulation pass.
because: 1 in 12 men and 1 in 200 women have some colour vision deficiency and about 99% of those are red-green; pairs that look distinct to you can collapse for them.

### CP-17 · Name colors by role, not by code
rule: Give every colour a descriptive, role-based name instead of its hex code.
do: Use function names — primary, secondary, success, warning, danger, neutral — and labels like "Primary Blue" and "Accent Orange".
never: Reference colours by hex code in conversation, docs, or components.
because: Nobody should have to remember whether the success colour is emerald or lime; role names make the palette usable across teams.

### CP-18 · Number the shade scale
rule: Name shades with a numbered scale based on lightness, not stacked adjectives.
do: Number steps from lightest to darkest (e.g. 0 = white to 1000 = black, or 50/100/200 … 900), and insert missing steps as numbers — Primary 350 sits between Primary 300 and Primary 400.
never: Use adjective ladders ("Primary lighter", "Primary lighter-ish") that force renames when you insert a shade.
because: A numbered scale lets you expand the palette without renaming existing shades.

### CP-19 · Ship the palette as design tokens
rule: Publish the palette as named design tokens used everywhere, not as hex values scattered in code.
do: Define tokens such as `color-primary-blue` or `color-error-text`; use semantic names (`color-surface-primary`, not `color-white`) so themes can swap values; generate the necessary CSS variables or SCSS tokens.
never: Hard-code hex values directly in components, or keep design and code on different values.
because: Tokens make a value change propagate across the entire system and are the mechanism that keeps hand-built and generated UIs on brand.

### CP-20 · Document centrally and keep usage consistent
rule: Store the palette and its usage rules in one central, documented location everyone can access.
do: Categorise colours (base, accent, state) in a palette library; write usage guidelines; keep the same colour for the same role on every screen, and the same interactive colour for every call to action.
never: Let the palette live in one designer's head or get recreated per feature.
because: Centralised documentation prevents miscommunication and drift; consistency is how users learn what a colour means in the product.

### CP-21 · Test in context and iterate
rule: Validate the palette on real components, on light and dark backgrounds, and with real users — then iterate.
do: Apply it to a dashboard, form, and settings page; check hover/click states and overlays (e.g. 50% transparency); look at colours on light and dark backgrounds; review on multiple screens and under varying lighting; run A/B tests and gather feedback.
never: Approve a palette from swatches alone, or ship it without checking components in real use.
because: Colours change on real surfaces — contrast, legibility, and perceived state only show up in context, and iteration is how a palette stops vibrating (think a green logo on an orange background) and starts working.

## Hard numbers

| Value | Meaning |
|---|---|
| ≥ 4.5:1 | WCAG AA contrast requirement, normal text (all sources) |
| ≥ 3:1 | WCAG AA contrast requirement, large text (Atmos: ">120% larger than body text") (all sources) |
| ≥ 3:1 | WCAG AA contrast requirement, active UI components and graphical objects such as icons and graphs (Atmos, UXPin) |
| no requirement | images, inactive UI components, purely decorative elements (Atmos) |
| 7:1 / 4.5:1 | WCAG AAA requirements for normal / large text (Figr source only) |
| 4.5:1 | stated to mean the lighter colour is 4.5 times lighter than the darker (Figma source) |
| 60% / 30% / 10% | dominant / secondary / accent usage (IxDF, Figma, NN/g, UXPin) |
| 9–10 steps | full lightness scale per hue, e.g. 50, 100, 200 … 900 (UXPin) |
| 6–10 per colour, ~10 for neutrals | typical shipped shade counts (Atmos) |
| 8–10 steps | typical neutral/grey scale (UXPin) |
| 5–7 base hues → 50–80 values | typical full palette composition (UXPin FAQ) |
| 95 → 30 | reported usable lightness range (Atmos) |
| 0 or 360 = red, 120 = green, 240 = blue | hue degrees on the HSL wheel (IxDF) |
| 120° apart | triadic colour spacing (NN/g) |
| hueRotate 0–360, opacity 0–1 | loop parameters for generating palettes in Framer (Multani, InVision) |
| Overlay 50% black / Normal 50% white / Normal 50% black | filter layers that respectively increase saturation, lighten, darken (Multani, InVision) |
| 50% | example overlay transparency so content stays visible underneath (Figr) |
| 2.2 billion | people with some kind of vision impairment (WHO estimate, cited by Atmos) |
| 1 in 12 men / 1 in 200 women | colour vision deficiency prevalence (Atmos); UXPin gives the same as ~8% of men and ~0.5% of women |
| ~99% | of colour-blind people have red-green colour blindness (Atmos) |
| #1F6AE3 / #FF5733 | Figr's example "Primary Blue" / "Accent Orange" hexes |
| #003A70 / #A0C4FF | Figr's example base blue / lighter blue for backgrounds |
| `color-primary-blue`, `color-error-text`, `color-surface-primary` | example token names (Figr, UXPin) |
| > 60% | of people accept or reject new products based on colour — appears only in the promotional "read next" blurb of the UI Color Palette 2026 article, not in the article itself; `unknown: true` |
| 8.6× | faster design-to-prototype cycles claimed by UXPin when combining Forge with a defined component library — vendor marketing figure, no methodology; `unknown: true` |

## Decision procedure

1. Confirm the brand and audience context; extract existing brand colours from brand guidelines (CP-01, CP-02).
2. Pick one dominant base hue, then a colour harmony, and derive 1–2 secondary/accent hues from it (CP-03, CP-04).
3. Structure the set into brand, neutral, and semantic families; define state colours (CP-05, CP-13).
4. Generate a full ~9–10 step lightness scale per base colour, then trim to the ~6–10 shades you actually use (CP-06, CP-07, CP-18).
5. Hold lightness inside the 95–30 band; shift hue on the dark shades; set saturation last (CP-08, CP-09, CP-10).
6. Replace pure blacks/whites and dead neutrals with tinted greys built from the brand hue (CP-11).
7. Allocate colour 60-30-10 across dominant, secondary, and accent (CP-12).
8. Verify every text/background and active UI pair against the contrast thresholds, then run a colour-vision-deficiency simulation (CP-14, CP-15, CP-16).
9. Name colours by role, number the shade scale, ship the palette as design tokens, and document it centrally (CP-17, CP-18, CP-19, CP-20).
10. Apply to real screens — dashboard, form, settings — test states and overlays on light and dark backgrounds, then A/B test and iterate (CP-21).

## Anti-patterns

- **A palette chosen by personal taste** — no harmony, no brand anchor, no audience or cultural check.
- **Every component its own colour** — the cereal-aisle effect; nothing is distinguishable by hierarchy.
- **A maximal 30–40 step scale "to be safe"** — more choices, more maintenance, decision paralysis.
- **Pure black on pure white everywhere** — harsh contrast that strains the eyes; violates the tinted-grey guidance.
- **Colour-only states** — a red field with no icon or message, or chart series distinguished only by hue.
- **A status colour that flips meaning** — red for success here, warning there.
- **Hex codes in docs and code** — `#1F6AE3` instead of `primary-blue`; nobody remembers what it means.
- **Adjective shade ladders** — "Primary lighter", "Primary lighter-ish", renamed every time a step is inserted.
- **Approving a palette from swatches** — never seen on a button, a hover state, an overlay, or dark mode.
- **A brand colour doing duty as a warning colour** — highlights, warnings, and errors all converging on one hue.

## Review checklist

- [ ] One dominant brand colour chosen first; brand guidelines followed where they exist.
- [ ] A colour harmony is chosen and named; all hues derive from it.
- [ ] Palette limited to ~5–7 base hues; semantic family covers success/warning/danger/info; state colours defined.
- [ ] Each base has a numbered shade/tint scale, trimmed to what is actually used (~6–10 shades).
- [ ] Lightness band respected (≈95–30); hue shifted on the dark shades.
- [ ] Neutrals are tinted greys, not absolute black/white.
- [ ] 60-30-10 distribution holds on the real screens, accent reserved for CTAs, active states, and links.
- [ ] All text/background pairs pass ≥ 4.5:1 (normal) and ≥ 3:1 (large text and active UI components); AAA claimed only where 7:1 / 4.5:1 hold.
- [ ] No meaning is conveyed by colour alone (WCAG 1.4.1).
- [ ] Colour-vision-deficiency simulation passed (Color Oracle, Coblis, Sim Daltonism, or DevTools).
- [ ] Colours named by role, shade scales numbered, shipped as design tokens, documented centrally.
- [ ] Tested on real components, light and dark backgrounds, overlays, multiple screens and lighting, and with users; then iterated.

## Caveats

- The raw source is a concatenation of **seven unrelated documents**: Figr Identity's "Creating a Color Palette for Your Design System" (2024; an advertisement for Figr Identity), Interaction Design Foundation's "UI Color Palette 2026" by Mads Soegaard, Patrick Multani's "11 Tips For Building Great Color Palettes" (InVision, 2017), Atmos's "How to create the best UI color palette" by Ondrej Pesicka (2022, updated 2023; an advertisement for Atmos), Figma's "Types of color palettes" (an advertisement for Figma), Nielsen Norman Group's "Using Color to Enhance Your Design" by Kelley Gordon (2021), and UXPin's "How to Choose a Color Palette for UI Design" (2026; an advertisement for UXPin). The concatenation means the same claim sometimes appears in several sources without a shared study.
- **Conflict recorded, unresolved — shade numbering:** Atmos says number shades from 0 (white) to 1000 (black), while UXPin describes a 9–10 step scale starting at 50 (e.g. 50, 100, 200 … 900). Both are recorded; neither reconciles the other.
- **Conflict recorded, unresolved — large-text definition:** Atmos defines large text as ">120% larger than body text", which is not WCAG's official definition (18 pt / 24 px, or 14 pt / 18.66 px bold). The discrepancy is source-reported, not resolved here.
- **Conflict recorded, unresolved — WCAG version:** sources cite WCAG 2.0 (Figr), AA thresholds (Atmos), and WCAG 2.2 (UXPin). The ratios agree (4.5:1 / 3:1), but the versions differ and are recorded as stated.
- **Vendor steering:** four of the seven sources promote a specific product (Figr Identity, Atmos, Figma, UXPin). Framework, automation, and performance claims — including the "8.6× faster" figure — are promotion, not independent findings.
- **Almost nothing here is measured.** No source supplies controlled usability studies, sample sizes, or effect sizes for the palette claims: the 95–30 lightness range, hue shifting, "6–10 shades", the 60-30-10 distribution, saturation guidance, and cultural colour meanings are practitioner guidance. `unknown: true` applies to all of them. NN/g is explicit that there is little real research proving a universal effect of a particular colour on emotions, and that a colour's meaning varies by culture.
- The two statistics flagged in the Hard numbers table — the > 60% accept/reject claim and the 8.6× claim — come respectively from a promotional "read next" blurb and a vendor's marketing, with no methodology attached.
- Sibling coverage: `cognitive-load.md` owns effort and choice reduction (a palette that is hard to use is a load problem); `choice-overload.md` owns the decision-paralysis mechanism overgrown palettes trigger; `cards.md` owns surface anatomy where colour encodes elevation and state; `von-restorff-effect.md` owns making the accent colour distinctive — and why only one; `fitts-law-touch-targets.md` owns the focus-visible interaction states whose colours this file defines. The platform hubs — the mobile hub skill, the website design skill, and the desktop app design skill — own where each platform applies these colours.