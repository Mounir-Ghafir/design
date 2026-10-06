---
name: cards
title: Cards — Design Rules
description: Rules for designing UI cards — when a card is the right container, what belongs inside it, how content is ordered and truncated, whole-card clicking and states, imagery, shadows, typography, spacing, and animation. Load when building card grids, dashboards, product/article/profile listings, or reviewing card-based layouts.
applies_when: [card design, card grids, dashboards, product listings, media feeds, profile cards, cards vs lists, hover states, content containers, ui review]
priority: supporting
rules: 16
---

# Cards — Design Rules

## Core principle

A card is a flexible-size, visually distinct, clickable container that groups information about one subject — one card, one concept — and acts as an entry point to detail rather than the detail itself.

```
card = browse or compare one item  → image-led, short, whole-card click, opens detail
list = scan order or hierarchy     → compact rows; titles matter more than visuals
```

## Rules

### CRD-01 · One card, one concept
rule: All content inside a card relates to exactly one idea, item, or subject.
do: Split heterogeneous items into separate cards; let the card boundary (border, shared background) show what is related inside and what is not.
never: Put two topics inside one border — users then wonder whether the content is related at all.

### CRD-02 · Choose the pattern before you style it
rule: Cards are for browsing; lists are for order, hierarchy, and title-scanning.
do: Use cards when users browse or compare options side by side; switch to a list for ordered data, repetitive content, long titles, and data-heavy screens where scanning speed beats visuals.
never: Build an order-sensitive, data-heavy screen out of cards just because cards look modern.
because: Cards are less hierarchical and take more space than list rows, so the wrong choice costs scannability on exactly the screens that need it most.

### CRD-03 · The card is an entry point, not the destination
rule: A card is short and links onward to the full details.
do: Show a digestible summary first and reveal the rest when the card is opened; keep supporting body text short and truncate it with three dots (…) to signal there is more.
never: Fill a card until it grows too wide or too long and stops reading as a card.

### CRD-04 · Order content by priority
rule: Structure every card as header → body → footer, each step lower in priority.
do: Header carries the title or most important information (optionally a small icon or image); body carries the primary content with readable typography and white space; footer carries action links and metadata.
never: Bury the title under body copy, or place the primary action above the thing it acts on.

### CRD-05 · Make the whole card clickable when it has one action
rule: Follow Fitts's Law — any part of the card is the hit target, not just the text link or image.
do: Make the card itself the entry point when a single action is attached; the larger touch zone improves usability on touchscreens and with a mouse.
never: Ship a card whose body is inert and whose only target is a small link.
because: The bigger target lowers interaction cost and cuts cognitive load, encouraging users to engage with the content effortlessly.

### CRD-06 · Signal clickability and design every state
rule: If it is clickable it must look clickable; if it can change state the change must be designed.
do: On hover use a subtle colour change or shadow plus a pointer cursor (a faint border also works); design hover, active, focus, empty, loading, and error states, with sufficient contrast for accessibility.
never: Leave users unsure whether a card is interactive, or ship a card with no empty or loading treatment.

### CRD-07 · Keep actions few and place them predictably
rule: A single card must not be overloaded with actions.
do: Put primary actions ("Add to Cart", "Buy Now") in a row at the bottom of the card for alignment and accessibility, with supplemental actions (wishlist, share) beside them; move extras into an overflow menu — the kebab menu belongs in the upper right corner, where left-to-right, top-to-bottom scanning ends.
never: Scatter competing buttons across the card, or hide the primary action behind an overflow menu.

### CRD-08 · Build hierarchy with colour and size
rule: Highlight what matters and subdue what does not — inside the card exactly as across the page.
do: Title outranks preview; the primary button ("Learn More") outranks secondary ones (favourite, save); emphasise priority content with a larger font or more central placement.
never: Give everything equal emphasis — when all of it is highlighted, none of it feels important.

### CRD-09 · Images carry the card
rule: Treat the image as the main attention grabber and keep it clean and consistent.
do: Keep one defined visual style across a grid; use high-DPI images so they do not pixelate; use transparent-background images where the card surface shows through; use quality media, since blurry or grainy images break trust.
never: Mix random image styles across a grid, or let low-resolution media carry a vital message.

### CRD-10 · Text over images must clear contrast
rule: Labels over images or video need foreground-versus-background contrast that low-vision users can read.
do: Hold a contrast ratio of 4.5:1 — place a darker cover over the image and adjust its transparency so the image stays visible and the text stays legible.
never: Drop dark text straight onto an unpredictable photograph.

### CRD-11 · One shadow, one light source
rule: Shadows and gradients exist to make the card feel like a physical object, not to decorate every element.
do: Use a slight drop shadow as the depth cue and signifier that the whole card is clickable (a border or subtle grey shading works too); keep the light direction consistent.
never: Cast shadow at all corners and sides — that ruins the physical-object illusion — or pile extra shadows onto media, buttons, and icons inside an already elevated card.

### CRD-12 · Typography does the talking
rule: Design every card for maximum readability.
do: Use simple, easy-to-read typefaces on a solid colour background with sufficient contrast; for most card projects a single typeface is enough; a sans-serif typeface in normal weight works for card body copy.
never: Set body text over a busy background, or stack several typefaces into one small container.

### CRD-13 · Let spacing, not lines, divide
rule: White space and typography create separation inside a card.
do: Keep a uniform distance between content and card edges; group related elements and actions close together; use subtle dividers or varying text sizes only when you must; leave enough space around cards in a grid so users can focus.
never: Draw horizontal dividers between elements inside a card — they are rarely helpful and eat space — or run cards flush together unless zero-gap is deliberate.

### CRD-14 · Size cards to the device and to the emphasis
rule: Adapt card shape, size, and column count to the viewport and to what deserves attention.
do: Square cards on mobile, rectangular cards on web; fewer columns on mobile screens; either align cards to a uniform size so focus stays on the content, or enlarge selected cards to draw attention.
never: Reuse one desktop grid geometry unchanged on a phone.

### CRD-15 · Animate with restraint
rule: Motion orients users and links card states; it does not decorate.
do: One animated feature — or a video in place of the main image — per card; use visual hints to show how functionality works, hover feedback to acknowledge interaction and reveal options (tag, reply, delete), and a zoom transition from thumbnail to detail that keeps users feeling in context.
never: Stack many animated or interactive elements on a card, or scroll content inside a single card — it reads as confusing.

### CRD-16 · Define the container
rule: A card needs a clear boundary to read as related content.
do: Fix the container decisions up front — fixed or responsive width, fixed or content-driven height, appropriate inner padding, a background typically white or light shades, a subtle shadow or border for depth, and rounded edges.
never: Leave a "card" with no boundary, so users cannot tell which items belong together.

## Hard numbers

| Spec | Value | Note |
|---|---|---|
| Text-over-image contrast | **4.5:1** | Dark cover over image, transparency adjusted |
| Body-text truncation | **three dots (…)** | Keep supporting text short first |
| Typefaces per card project | **1** ("a single typeface is enough") | Sans-serif, normal weight for body copy |
| Card sections | **3** — header, body, footer | Footer only if needed |
| Animation budget | **1** animated feature, or a video instead of the main image | |
| Task-card actions | **2** (e.g. mark complete, edit) | More → overflow menu |
| Device shapes | Square = mobile, rectangular = web; mobile = fewer columns | No column counts given |
| Kebab menu position | Upper right corner of the card | Matches L→R, top→bottom scan end |
| Corner radius, padding, shadow offset/blur, aspect ratio, grid gap, hover timing | unknown: true | Source says "round the edges", "subtle shadow", "appropriate padding" with no values |

## Decision procedure

When you are about to lay out cards, work in this order:

1. **Purpose** — state the card's one job (summarise, prompt action, navigate). One concept only (CRD-01).
2. **Pattern** — is this browsing/comparison or ordered, title-heavy, data-heavy scanning? Card or list (CRD-02).
3. **Content** — keep only the digestible summary; push detail behind the open, truncate with … (CRD-03).
4. **Order** — header (title) → body (primary) → footer (actions, metadata); confirm colour and size hierarchy (CRD-04, CRD-08).
5. **Interaction** — one action? whole card clickable, signalled by shadow/hover/pointer. Several? bottom action row plus overflow (CRD-05, CRD-06, CRD-07).
6. **States** — hover, active, focus, empty, loading, error; 4.5:1 for any text over media (CRD-06, CRD-10).
7. **Restraint** — one typeface, one shadow direction, one animation, no inner dividers, no inner-element shadows (CRD-11, CRD-12, CRD-13, CRD-15).

## Anti-patterns

- Two topics inside one card border.
- Cards used for an ordered, title-scanning, or data-heavy list.
- A long card that no longer looks like a card; a wall of body text with no truncation.
- Inert card body whose only target is a small text link; no hover/clickability cue.
- Low-contrast text over a photo.
- Shadows on every side of the card, plus shadows on its buttons and icons.
- Horizontal dividers slicing up the inside of a card.
- Many animated elements, or scrolling inside a single card.
- Desktop card geometry copied unchanged onto mobile.
- Primary action buried in an overflow menu.

## Review checklist

- [ ] One concept per card; distinct topics in separate cards
- [ ] Card vs list chosen for browsing vs ordered scanning
- [ ] Content short; body truncated with …; labels bite-sized (no slang, no redundant punctuation)
- [ ] Header → body → footer priority order; title > preview, primary button > secondary
- [ ] Whole card clickable when there is one action; click signalled (shadow, hover, pointer, faint border)
- [ ] Actions in a bottom row; overflow/kebab in the upper right; not overloaded
- [ ] 4.5:1 for text over images; body text on a solid background
- [ ] Single typeface, sans-serif normal-weight body; consistent margins; dividers used sparingly
- [ ] One shadow direction; no extra shadows on inner elements; container visibly defined, edges rounded
- [ ] Empty, loading, error, hover, active, focus states present
- [ ] High-DPI, stylistically consistent images; card size and column count adapted per device

## Caveats

- This is practitioner advice from two design articles (Medium), not research: no usability results, conversion data, sample sizes, or effect sizes are reported anywhere in the source — measured evidence: `unknown: true`.
- The source claims "studies confirm that images elevate design" and that cards have "better scrolling rates" than lists, but cites no study, sample, or number — `unknown: true`.
- Agency case studies and promotional figures in the source were dropped as marketing, not evidence.
- Scope: `cognitive-load.md` covers grouping and layout; the mobile commerce patterns skill uses cards for product listings on commerce screens — defer cross-component grouping and layout trade-offs to those.
