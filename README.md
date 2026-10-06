---
name: ux-design-skills
title: UI/UX Design Skills
description: Rule set an AI agent loads to design and review interfaces and write front-end code. 44 unique skills in three platform folders — mobile/, website/, desktop/ — with the 39 platform-neutral skills duplicated into every folder so an agent loads only the folder it needs. 685 rules total, with evidence limits recorded per file.
---

# UI/UX Design Skills

43 self-contained rule files, organised into three platform folders. Each file is a skill an agent loads, applies, and checks against. No rule file points at another for its evidence — every file stands alone.

## Layout

```
mobile/   41 files   2 mobile-specific + 39 shared   634 rules
website/  41 files   2 website-specific + 39 shared  623 rules
desktop/  40 files   1 desktop-specific + 39 shared  608 rules
```

- The **shared** 39 skills (laws, memory and attention effects, Gestalt principles, and the code skills) apply to every platform and are **duplicated byte-for-byte into all three folders** — on disk that is 122 files, 44 unique skills.
- Because the folders are self-contained, an agent scoped to a folder never reads another platform's skills.

## How to use

1. Decide the platform: mobile app, website, or desktop app.
2. Load **every file in that folder only** — `mobile/`, `website/`, or `desktop/`. Do not read the other two folders.
3. Follow each skill's `## Rules`, then verify with its `## Review checklist`.
4. Read the `## Caveats` before defending a rule in review — several are weaker than they look.

Folder anchors (load first, they are the broadest files in their folder):

| Folder | Anchor | Role |
|---|---|---|
| `mobile/` | `mobile-app-design.md` | hub — the only `hub`-priority file in the set |
| `website/` | `website-design.md` | core — look-and-feel; `responsive-web-design.md` is the layout/technique layer |
| `desktop/` | `desktop-app-design.md` | core — Windows app rules |

## Priorities

| Priority | Meaning | Count |
|---|---|---|
| `hub` | Always load for mobile work | 1 |
| `core` | Load for most interface design work | 11 |
| `supporting` | Load when the task touches it | 32 |

## Platform-specific skills

Present in exactly one folder.

| Skill | Folder | Load when | Rules | Priority |
|---|---|---|---|---|
| `mobile-app-design.md` | `mobile/` | Any mobile app work — scoping, IA, targets, visual system, dark mode, accessibility, performance, onboarding, AI features | 23 | hub |
| `mobile-commerce-ui-patterns.md` | `mobile/` | Product pages, checkout, paywalls, pricing, order tracking, category screens | 21 | supporting |
| `website-design.md` | `website/` | Any web screen — consistency, hierarchy, white space, nav, CTAs, mobile, speed, accessibility | 15 | core |
| `responsive-web-design.md` | `website/` | Responsive layouts, breakpoints, fluid grids, media queries, mobile-first, viewport meta tag, responsive media and typography | 18 | core |
| `desktop-app-design.md` | `desktop/` | Windows/desktop apps — keyboard-first, window behaviour, input modalities | 18 | supporting |

## Shared skills

Copied into `mobile/`, `website/`, and `desktop/` — load the copy in your folder.

### UI/UX laws, effects, and components

| Skill | Load when | Rules | Priority |
|---|---|---|---|
| `cognitive-load.md` | Layout, forms, onboarding, simplifying a cluttered UI, UX review | 22 | core |
| `color-palette.md` | Building a brand/design-system palette — base, neutral and semantic families, shade and tint scales, the 60-30-10 distribution, WCAG contrast, colour-vision-deficiency checks, role-based naming, design tokens | 21 | core |
| `law-of-proximity.md` | Spacing, grouping, list and form layout — elements near each other read as related | 20 | core |
| `peak-end-rule.md` | Journey-level design — what users remember from an experience | 20 | supporting |
| `fitts-law-touch-targets.md` | Touch target sizing, spacing, reachability, thumb zone, menus | 19 | core |
| `choice-overload.md` | Too many options, filters, defaults, recommender logic, feature creep | 18 | core |
| `response-time-progress-feedback.md` | Latency budgets, loading states, progress indicators, perceived speed | 18 | core |
| `teslers-law.md` | Deciding where irreducible complexity lives — system vs user | 13 | core |
| `progressive-disclosure.md` | Revealing complexity in stages, secondary screens, wizards | 15 | core |
| `chunking.md` | Long strings, long text, forms, card grouping, menu sizing | 14 | core |
| `hicks-law.md` | Decision time, option complexity, breaking a complex task into steps | 17 | supporting |
| `law-of-similarity.md` | Signalling interactivity and state with colour, shape, size, orientation | 17 | supporting |
| `law-of-uniform-connectedness.md` | Connecting related items with lines, frames, containers, timelines | 17 | supporting |
| `cards.md` | Card components — anatomy, image, elevation, what belongs inside vs out | 16 | supporting |
| `law-of-pragnanz.md` | Simplifying complex compositions; closure, symmetry, figure/ground | 16 | supporting |
| `law-of-common-region.md` | Grouping with borders, backgrounds, containers | 16 | supporting |
| `pagination.md` | Choosing pagination vs infinite scroll vs load-more; URL/back/accessibility behaviour | 15 | supporting |
| `postels-law.md` | Liberal input acceptance, conservative output; input tolerance and normalisation | 15 | supporting |
| `working-memory.md` | Using the UI as the user's external memory; never making users hold state | 15 | supporting |
| `mental-model.md` | Matching a user's expectations; deciding whether to break a convention | 15 | supporting |
| `pareto-principle.md` | Prioritising features and where to invest design effort | 15 | supporting |
| `jakobs-law.md` | Following established conventions; when innovation is worth its cost | 15 | supporting |
| `selective-attention.md` | Banner blindness and change blindness — guiding attention, cueing changes | 14 | supporting |
| `von-restorff-effect.md` | Making one thing distinctive — and why only one | 14 | supporting |
| `occams-razor.md` | Deciding what to remove, and knowing when to stop removing | 14 | supporting |
| `cognitive-bias.md` | Framing, anchoring, defaults, reviewing your own decisions | 14 | supporting |
| `flow.md` | Matching task difficulty to user skill; eliminating hesitation | 14 | supporting |
| `goal-gradient-effect.md` | Progress indicators, motivation to finish a multi-step flow | 13 | supporting |
| `zeigarnik-effect.md` | Useful incompleteness, endowed progress, content-discovery signifiers | 13 | supporting |
| `serial-position-effect.md` | Where items sit in a list — first and last are remembered best | 12 | supporting |
| `aesthetic-usability-effect.md` | Running usability tests where participants say "it looks great" | 10 | supporting |
| `millers-law.md` | Working-memory limits, and why 7 ± 2 is not a design constraint | 9 | supporting |
| `paradox-of-active-user.md` | Onboarding design — in-context guidance over blocking product tours | 7 | supporting |
| `parkinsons-law.md` | Task inflation in forms; autofill and expected duration | 7 | supporting |

### Engineering/code skills

| Skill | Load when | Rules | Priority |
|---|---|---|---|
| `clean-code.md` | Writing or reviewing code — naming, readability, small units, comments, tests | 22 | supporting |
| `code-structure.md` | Organising modules — coupling vs cohesion, package by layer vs feature vs component | 17 | supporting |
| `less-is-more.md` | When to accept more code for performance — and when minimalism wins | 16 | supporting |
| `solid.md` | All five SOLID principles — detection and fix for each violation | 12 | supporting |
| `single-responsibility-principle.md` | The "one reason to change" rule, with the "and" diagnostic question | 13 | supporting |

## Maintenance note

Shared skills live in **three byte-identical copies**, one per folder. When editing a shared file, apply the edit to all three copies — or edit one and re-copy. The platform-specific files exist in exactly one folder and need no duplication.

## Conventions

Every skill uses the same structure:

- **`## Core principle`** — the mental model, short.
- **`## Rules`** — the operative content. Each rule is `### XX-NN · Title` with `rule:` (the invariant), `do:` (the action), `never:` (the prohibited move), and often `because:`.
- **`## Hard numbers`** — exact values only. Never rounded, never approximated.
- **`## Decision procedure`** — ordered steps to work through when something feels wrong. This is what makes the skill actionable rather than a list to memorise.
- **`## Anti-patterns`** — moves that look reasonable and are wrong.
- **`## Review checklist`** — `- [ ]` items for a final pass.
- **`## Caveats`** — what the evidence does **not** support.

Rule IDs are stable and citable (`CL-07`, `FT-02`, `LPX-11`, `PER-03`). Cite them in review comments so feedback points at a rule rather than an opinion.

## Known overlaps

Several skills legitimately cover adjacent ground. Load one, not all.

- `cognitive-load`, `millers-law`, `chunking`, `working-memory` — effort, memory limits, chunking, external memory. `millers-law` is the narrow one: the 7 ± 2 figure and why it is not a design constraint.
- `choice-overload` and `hicks-law` — both about option count. Different effects: satisfaction vs decision time. They are **not** the same finding and the sources do not establish a shared mechanism.
- `progressive-disclosure`, `teslers-law` and `pareto-principle` — what to hide, where complexity must live, and what the long tail is worth.
- `goal-gradient-effect` and `zeigarnik-effect` — artificial progress. The endowed-progress car-wash experiment (`zeigarnik`) IS goal-gradient evidence; one file owns the theory, the other owns the experiment and the design levers.
- `von-restorff-effect`, `serial-position-effect`, `selective-attention`, `peak-end-rule` — three different reasons an item or moment is remembered (distinctiveness, position, attention, peak/end). Keep them separate.
- `cognitive-load` CL-04, `jakobs-law`, `mental-model` — familiar patterns, from three angles: reduce load, follow convention, match the model.
- `cards`, `pagination`, `mobile-commerce-ui-patterns` — the component, the navigation pattern, and the commerce screens that use both. `mobile-commerce-ui-patterns` lives only in `mobile/`.
- `color-palette`, `cognitive-load`, `choice-overload`, `cards`, `von-restorff-effect` — the palette is the constraint that prevents load problems: too many shades → choice paralysis (`choice-overload`), a hard-to-use system → load (`cognitive-load`), colour-coded hierarchy and state on surfaces (`cards`), and the accent colour as the single distinctive thing (`von-restorff-effect`).
- `website-design`, `desktop-app-design`, `mobile-app-design` — the same job on three platforms. Overlap is intentional; platform numbers live in each file and are not interchangeable. Each lives only in its own folder.
- `website-design`, `responsive-web-design` — look-and-feel vs the layout/technique layer. `responsive-web-design` owns breakpoints, fluid grids, and the viewport; `website-design` owns the visual decisions those rules carry. Both live only in `website/`.
- `solid` and `single-responsibility-principle` — SRP is the first of the five; `solid` is the overview, the SRP file is the deep-dive.
- `clean-code`, `code-structure`, `less-is-more`, `postels-law` — naming/readability, module organisation, performance-vs-simplicity, and input tolerance.

## What this set does not know

Read these before treating a rule as a finding.

- **Some techniques have no empirical validation.** `progressive-disclosure` states this before its own rules: no empirical evidence exists (Carroll & Rosson 1997); it is practitioner convention. `parkinsons-law` is an organisational observation about clerical work, and its UX application is inference. `pareto-principle` — the 80/20 split is a rule of thumb, not a measurement. `teslers-law` — "conservation of complexity" is a postulate, not a measured law. `flow`, `goal-gradient-effect`, `paradox-of-active-user`, `mental-model`, `jakobs-law`, `occams-razor`, `postels-law`, `cards`, `pagination`, `selective-attention`, `serial-position-effect`, `working-memory`, `color-palette` and the five Gestalt skills supply no effect sizes or sample sizes; their `## Hard numbers` sections say so with `unknown: true`. The verified mechanics in `responsive-web-design` (viewport default width, relative-unit reflow, zoomability of fluid type) are browser specification behaviour, not usability measurements — its two published statistics (>60% mobile traffic, 74% revisit) are source-reported marketing figures.
- **One skill is paywalled and truncated.** `parkinsons-law` — the source article stops at line 33. Its `## Caveats` records exactly where.
- **One skill is not research.** `mobile-commerce-ui-patterns` derives from UI/UX tutorial-video commentary. Six of eight source videos are unattributed. Lower confidence than everything else here.
- **`von-restorff-effect` has no attribution.** The source never mentions Hedwig von Restorff, the 1933 experiment, or any study; the file says so plainly and does not import the classic figures.
- **Working-memory capacity estimates genuinely disagree.** 7 ± 2 vs 4 ± 1 vs 3. `chunking` records the dispute rather than picking a winner.
- **Statistics are source-reported and directional.** None are audited. Vendor and platform figures (Microsoft's Windows guidance, Wix's web-practice figures, Apple/Material numbers) are not independently verified, and `desktop-app-design` / `website-design` caveat that their vendors steer toward their own platforms.
- **Where a `## Caveats` entry says unresolved, it is unresolved in the source too.** These are recorded, not resolved: the empirical status of choice overload, whether aesthetics changes actual performance, whether Fitts's Law transfers from mouse to touch, constant vs variable response time, which Gestalt principle wins when they conflict (common-region and uniform-connectedness both claim to overpower the others), and the 4.5:1 vs 4:1 contrast-ratio discrepancy inside `website-design`'s own source. Decide these with local testing, and record your decision.