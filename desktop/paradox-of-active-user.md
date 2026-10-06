---
name: paradox-of-active-user
title: Paradox of the Active User — Onboarding Design Rules
description: Rules for onboarding and in-product guidance aimed at users who start using the product immediately instead of reading manuals or tours. Load when designing onboarding, product tours, tooltips, empty states, feature gating, first-run experience, or deciding whether to block users before they can act.
applies_when: [onboarding, product tours, in-product guidance, tooltips, empty states, feature discovery, first-run experience]
priority: supporting
rules: 7
---

# Paradox of the Active User — Onboarding Design Rules

## Core principle

Defined by Mary Beth Rosson and John Carroll in 1987, in *Interfacing Thought: Cognitive Aspects of Human-Computer Interaction*: **users never read manuals but start using the software immediately**. New users were not reading the supplied manuals and would just get started, even if it meant hitting errors and running into roadblocks.

They are motivated to get their immediate task done. They don't care about the system as such and don't want to spend time up front on getting established, set up, or going through learning packages.

The paradox: users *would* save time in the long term by investing in setup and learning — but that is not how people behave. So do not build for an idealized, rational user. Design for the way users actually behave.

## Rules

### PAU-01 · Never block the product behind a tour
rule: Users must be able to start using the product immediately.
do: Make the product fully usable on first open; put guidance where the user is already working.
never: Require clicking through sequential overlays or information screens before any interaction is possible.

### PAU-02 · Put guidance throughout, never up front
rule: Guidance must be accessible throughout the product experience, not delivered before it.
do: Attach hints to the elements, screens, and states where the need actually appears.
never: Front-load documentation, learning packages, or an intro deck and call it onboarding.

### PAU-03 · Guidance must fit any path the user takes
rule: Active users arrive by unpredictable routes; guidance must help them no matter which path they choose.
do: Make hints reachable from every entry point, at the point of need.
never: Assume one canonical path through setup and withhold guidance off it.

### PAU-04 · Ship lightweight in-product hints
rule: In-product elements such as tooltips are the default guidance mechanism.
do: Provide helpful information in a contextually relevant way — right information at just the right time, aiding discoverability of new features.
never: Put guidance behind a separate page, help centre, or mandatory modal.
because: Users learn through a process of discovery; lightweight, low-friction hints fit that.

### PAU-05 · Onboard progressively
rule: Gradually build the user's familiarity with the platform instead of delivering all information at once.
do: Let users explore and learn features at a comfortable speed, instilling confidence as they go.
never: Overwhelm users with information all at once.

### PAU-06 · Hide everything but the core feature
rule: Show only the one capability the new user needs; reveal more as each one is learned.
do: Slack hid all features except the messaging input, then used Slackbot to engage users and prompt them to learn messaging in a risk-free way, progressively introducing additional features as each was learned.
never: Drop a new user into a fully featured app after a few onboarding slides.
because: We learn by building on each previous step — revealing features at the right time adapts users to complex workflows and feature sets without feeling overwhelmed.

### PAU-07 · Offer a risk-free 'get started' template
rule: A dedicated checklist is valid guidance that does not interrupt use.
do: Notion provided an easy-to-follow checklist guiding beginners through core features in a risk-free environment, letting them explore at their own pace and revisit it whenever needed.
never: Make onboarding so overwhelming that users face an endless amount of possibilities.
because: An unobtrusive, revisitable template aligns with how active users behave and still enables them to actively learn by using the app.

## Hard numbers

| Constant | Value | Note |
|---|---|---|
| Term first defined | **1987** | Rosson & Carroll, *Interfacing Thought: Cognitive Aspects of Human-Computer Interaction* |
| Underlying observation | **early 1980s** | Nielsen: user studies at the IBM User Interface Institute |
| Replications | "many other studies" | Count not given — `unknown: true` |
| Effect size, sample size, manual-reading rate | **unknown: true** | None reported; the finding is observational |

## Decision procedure

When a new user opens your product:

1. **Entry** — can they act on real data in the first screen, or must they dismiss something first? (PAU-01)
2. **Guidance location** — is help available where the work happens, or only up front? (PAU-02, PAU-03)
3. **Friction** — is every hint lightweight and dismissible, or does it demand reading before proceeding? (PAU-04)
4. **Volume** — how many features are visible at once? (PAU-05, PAU-06)
5. **Safety** — can they practise without risking anything real? (PAU-06, PAU-07)
6. **Return** — is there a checklist they can come back to? (PAU-07)

## Anti-patterns

- A product tour of sequential overlays before any first interaction.
- An intro slide deck standing in for in-product guidance.
- A fully featured surface on first run, with nothing hidden.
- Coach marks or modals that must be read through before the product responds.
- A one-shot setup wizard that leaves no revisitable artifact.
- Designing for the rational user who reads documentation first.

## Review checklist

- [ ] Product usable immediately; no blocking tour
- [ ] Guidance embedded throughout the experience, not up front
- [ ] Hints reachable from any entry path
- [ ] Lightweight, contextual in-product hints on new features
- [ ] Visible feature count ramps up as each feature is learned
- [ ] New users can practise risk-free
- [ ] A revisitable 'get started' checklist exists
- [ ] Familiarity built gradually; nothing delivered all at once

## Caveats

- The evidence is **observational user studies** from the early 1980s / 1987. No effect sizes, sample sizes, or measured rates of manual-reading behaviour are given — `unknown: true`. Trust the direction of the advice; the magnitudes are unquantified.
- **Date discrepancy, unresolved:** the term is credited to a 1987 publication, while Nielsen dates the underlying observation to user studies at the IBM User Interface Institute in the *early 1980s*. The source states both and does not reconcile them.
- Ethical framing in the source: do not build for an idealized, rational user, because real humans are irrational. Stretched to justify removing onboarding entirely, it inverts the principle.
- Resolution of that tension: guidance must exist — just not as a blocking tour. Progressive onboarding (PAU-05), in-product hints (PAU-04), and a 'get started' template (PAU-07) are all guidance.
- `progressive-disclosure.md` covers revealing complexity in stages; the mobile hub skill covers onboarding screens (3–5, skippable).