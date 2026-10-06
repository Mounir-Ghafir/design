---
name: mobile-commerce-ui-patterns
title: Mobile Commerce UI — Design Rules
description: Rules for mobile product pages, pricing, paywalls, search and post-purchase so shopping feels safe and quick. Load when designing or reviewing an e-commerce or marketplace screen, a product or category page, a cart / booking / checkout flow, a trial or subscription paywall, order tracking, or navigation for a shopping app.
applies_when: [product pages, category screens, cart and checkout, booking flows, paywalls and trials, pricing display, order tracking, search, forms and input, bottom navigation, commerce ux review]
evidence_class: practitioner-video-commentary
priority: supporting
rules: 21
---

# Mobile Commerce UI — Design Rules

## Core principle

Every element on a screen asks the user a question. A commerce screen converts when its questions are cheap to answer.

```
decision load = choices still left to the user
doubt load    = what the screen leaves unresolved (cost, timing, quality)
risk load     = what feels irreversible (signup, card, cancellation)
```

## Rules

### MC-01 · Make product imagery predictable and legible
rule: Every product image must be interchangeable, and legible under any overlay.
do: Standardise framing, scale, and background so tiles sit cleanly in the grid; give overlay icons a subtle container or outline.
never: Float an icon on an uncontrolled photo, or mix aspect ratios and crop styles in one row.

### MC-02 · Align everything to a layout grid
rule: Text, buttons, and images snap to one grid that sets all margins and spacing.
do: Use white space to group related content; keep gaps small enough to hold the page flow together.
never: Position elements by eye, or open huge gaps that disconnect the page.

### MC-03 · Let type and colour support the product
rule: Soft natural colour, one clean font family, hierarchy from size, weight, and line height.
do: Increase line height on paragraph text; rank content with weight and scale, not extra colours.
never: Add a second font, or a saturated palette that competes with the product.

### MC-04 · Delete redundant labels
rule: Remove labels that repeat what the layout already communicates.
do: Drop "Price:" above an obviously priced number; trust alignment to signal what a value is.
never: Add a word the user could delete without losing meaning.

### MC-05 · Put trust and cost at the point of decision
rule: Ratings and the total price sit where the decision is made, not below the fold.
do: Pair title with rating, count, and a review link; put the total on the Add to Cart button.
never: Make users scroll to judge quality, or do arithmetic to learn what they will pay.

### MC-06 · Keep the buy path adjacent, preset, and always reachable
rule: Quantity sits beside Add to Cart, common amounts are one tap, and the action follows the scroll.
do: Stepper next to the button plus preset chips (500 g, 1 kg); fix both in a sticky bottom bar above the home indicator; scroll long detail in a card under a sticky image so the product stays in view.
never: Hide quantity in a separate sheet, make users type it, or pin the only buy control to the top of the page.

### MC-07 · Smart defaults *(decision fatigue — named, uncited)*
rule: Pre-fill the most common answer; users rarely change a default.
do: Default the modal choice, the common variant, the nearest size.
never: Open a form with every field blank and every choice handed to the user.

### MC-08 · Goal gradient *(named, uncited)*
rule: Never start a user at 0% progress.
do: Give an artificial head start so the first step already reads as movement.
never: Begin onboarding on an empty screen with a 0-of-N counter.

### MC-09 · Reciprocity *(named, uncited)*
rule: Deliver something useful before asking for anything.
do: Offer a sample, a free report, or a genuinely usable preview ahead of the signup wall.
never: Demand registration before value exists.

### MC-10 · IKEA effect *(named, uncited)*
rule: What the user builds or configures is valued more than what is handed to them.
do: Let them choose, assemble, or personalise before the paywall appears.
never: Put the paywall in front of the first real investment of effort.

### MC-11 · Loss aversion *(named, uncited)*
rule: Frame the upgrade around what stands to be lost, not only what is gained.
do: Name the forfeited benefit, the deadline, or the price rise that follows.
never: Sell purely on added features with nothing at stake.

### MC-12 · Contrast effect *(named, uncited)*
rule: Judgements are relative to whatever was just seen.
do: Place a high-value anchor first so a later cost reads as a small, reasonable addition.
never: Show an unanchored price in isolation and expect it to look modest.

### MC-13 · Sell safety, not a subscription
rule: "Start my free trial" beats "Subscribe" because it names a reversible step.
do: Frame the primary action as starting, not as agreeing to recurring billing.
never: Make the first button of a trial flow read like a contract.

### MC-14 · Make the commitment legible *(transparency bias — named, uncited)*
rule: State what happens next, including when the first charge lands.
do: Timeline of Today / Day 5 / Day 7, an explicit promise of a reminder before billing, and copy like "Start in two taps".
never: Leave the user to infer when they get charged or how long it takes.

### MC-15 · One number, then reframe it
rule: Show a single price. Never show a range.
do: One figure, then context that changes the comparison — "2 minutes away", "includes taxes and fees".
never: Display "$13 to $17"; users anchor to the highest number and stall.

### MC-16 · Transport, don't inform
rule: A booking screen should let users picture themselves at the destination.
do: High-quality imagery, sensory titles ("steps from the sand"), total price including taxes and fees, free cancellation stated upfront beside a shield icon.
never: Ship a form-like screen that lists facts and leaves the anxiety in.

### MC-17 · Post-purchase is part of the purchase
rule: Order tracking is a conversion surface, not a status page.
do: Visual timeline, proactive updates at each state, humanising detail such as courier photos.
never: Leave the user with a spinner, an order number, and no news.

### MC-18 · Category screens must be scannable
rule: One imagery style, a logical layout, a hierarchy that reads in one pass.
do: Unified image treatment; balanced, colour-coded grouping across the grid.
never: Wade users through a cluttered mix of inconsistent stock photos.

### MC-19 · Never ship a blank search bar
rule: An empty search field gives a user with no query nothing to act on.
do: Offer recent searches, popular items, or personalised suggestions beneath the field.
never: Present search as a bare input and a keyboard.

### MC-20 · Match the input control to the task
rule: Choose the control from the task's frequency and precision demands.
do: Slider or scroll wheel for one-time, low-precision, non-critical setup (height, weight, age); text field or stepper for frequent, precise, or repetitive entry (logging food quantities).
never: Use a slider for repetitive logging — it turns slow and fiddly.

### MC-21 · Bottom navigation carries only core destinations
rule: 3–5 tabs, all high-frequency, all thumb-sized, all unmistakably marked.
do: Home, Search, Add/Create, Messages, Profile; tap areas ≥44 × 44 px; active tab differs by two signals (outline → filled plus colour or weight); one icon style; brand palette only; bar above the home indicator, separated by a subtle border or shadow.
never: Put Help, Log out, or legal pages in the bar, colour each tab uniquely, or ship a target under 44 × 44 px.
because: Source asserts these thresholds with no standard; use `fitts-law-touch-targets.md` for the values.

## Hard numbers

| Constant | Value | Note |
|---|---|---|
| Bottom-nav tab count | **3–5** | Asserted, no standard cited; source also flags ">6" as over-limit (unresolved) |
| Minimum tap target | **≥44 × 44 px** | Unattributed; research-backed values live in `fitts-law-touch-targets.md` |
| Measured conversion effects | **None** | No studies, sample sizes, effect sizes, or metrics appear anywhere in the source |

## Decision procedure

1. **Question test** — name the question each element asks the user; answer it in the design or cut the element.
2. **Trust and cost** — can quality and total price be judged at the moment of decision without scrolling (MC-05)?
3. **Buy path** — is Add to Cart reachable, with quantity and total, at any scroll position (MC-06)?
4. **Friction** — count choices left open, doubts left unresolved, costs left hidden (MC-07, MC-14, MC-15).
5. **Legibility** — grid alignment, one type family, overlays that survive every product image (MC-01, MC-02, MC-03).
6. **Claim check** — treat every effect in this file as a hypothesis; instrument it locally (see Caveats).

## Anti-patterns

- Blank search bar shipped as-is.
- Price displayed as a range.
- Buy control pinned to the top, out of thumb reach, with quantity in a separate sheet.
- Signup wall in front of any delivered value or any user investment.
- Billing date implied rather than stated, or a Log out / Help / legal page in the bottom bar.

## Review checklist

- [ ] Product images interchangeable; overlay icons legible on every one
- [ ] One layout grid governs margins, spacing, and alignment
- [ ] One font family; hierarchy from size, weight, line height; soft natural palette; redundant "price" labels removed
- [ ] Rating and review count beside the product title
- [ ] Total price on the Add to Cart button
- [ ] Quantity adjacent to the button with presets; sticky bottom bar; detail scrolls with the product in view
- [ ] One price number; totals include taxes and fees; cancellation stated upfront
- [ ] Blank search replaced with recents, popular items, or personalised suggestions
- [ ] Input control matched to frequency and precision of entry
- [ ] Bottom nav: 3–5 core tabs, ≥44×44 px targets, two-signal active state, above home indicator
- [ ] Claims measured locally, never assumed from this file

## Caveats

- **Provenance is tutorial-video commentary, not research.** Every rule here comes from spoken commentary in UI/UX tutorial videos. No studies, sample sizes, effect sizes, standards citations, or user-research methods appear anywhere in the source. Confidence is **materially lower** than the research-based skills in this folder — `cognitive-load.md`, `choice-overload.md`, `chunking.md`, `fitts-law-touch-targets.md` — which should be preferred wherever they overlap.
- **Named effects are uncited here.** Goal gradient (MC-08), IKEA effect (MC-10), loss aversion (MC-11), reciprocity (MC-09), contrast effect (MC-12), transparency bias (MC-14), and decision fatigue (MC-07) are named flatly with zero references. Their research counterparts live in `cognitive-bias.md`, `choice-overload.md`, and `cognitive-load.md`. **Never cite this file as the evidence for them.**
- **One comparative claim is presenter opinion.** Loss aversion is called "a significantly stronger psychological motivator" than gain framing, with no effect size or basis. Any quantitative version of that is invented.
- **Mostly unattributed.** 6 of the 8 source videos are unnamed; only "uxpeak" and "UI/UX Playbook" appear, with no titles, URLs, publish dates, or speaker credentials.
- **The product-page source over-promises.** A video announces 15 UX/UI fixes; only 10 are enumerated. Items 11–15 are unknown and may not exist.
- **Unresolved source conflicts.** The tab over-limit is stated as both "more than five" and "more than six"; identical items carry different timestamps across the source's restatements (timestamps exist in the reference and are dropped here as provenance noise). Neither is reconciled.
- **Thresholds are asserted without a standard.** 44 × 44 px and 3–5 tabs carry no platform or standards attribution in the source; the research-backed values are in `fitts-law-touch-targets.md` and `mobile-app-design.md`.
- **One unverified anecdote.** "Showing actual content previews significantly increased conversion" is a creator's own account with no baseline, figure, period, or method. It supports no number in this file.
- **Prioritisation is derived.** Which lever wins in a conflict, and any ordering across areas, is an inference from reading the sources together — not a source claim.