---
name: mobile-app-design
title: Mobile App Design — Design Rules
description: Rules for designing iOS, Android, and cross-platform apps. Load when scoping features, choosing a navigation model, sizing touch targets, building a visual system, specifying dark mode or accessibility, setting performance and offline targets, designing onboarding, or adding AI features.
applies_when: [app concept and scoping, information architecture and navigation, touch targets and gestures, visual system and typography, dark mode, platform conventions, accessibility, performance and offline, onboarding, ai features]
priority: hub
rules: 23
---

# Mobile App Design — Design Rules

## Core principle

Every screen must answer four questions: **Where am I? What can I do here? Where can I go? Can I trust this?** Keep it clear, keep it steady, focus on what matters. Clarity outranks decoration; familiar native components beat clever novelty.

```
platform  = HIG / Material floor     → never design below it
cognition = read + remember + decide → cut what you added (cognitive-load skill)
context   = thumbs, glare, one hand, bad signal → design for it
```

## Rules

### MAD-01 · Answer the design-mission questions on every screen
rule: Every screen lets the user answer: Where am I? What can I do here? Where can I go? Can I trust this?
do: Make location, available actions, navigation, and system state visible without scrolling or guessing.
never: Ship a screen where the user cannot tell what it does or how to leave it.
because: The interface must feel reliable and steady.

### MAD-02 · Work the 5 Elements of UX bottom-up
rule: Finish Strategy → Scope → Structure → Skeleton → Surface in order; planes overlap in practice.
do: Write goals and user needs, then features, then IA and flows, then wireframes, then visual design.
never: Start with colour and type before strategy, scope, and structure are written down.

### MAD-03 · Every feature must serve the primary goal
rule: If a feature does not support a user task or improve the experience, defer it.
do: Rank with MoSCoW (must / should / could / won't have); cut v1 down to an MVP.
never: Ship feature bloat at v1 because it happened to be buildable.

### MAD-04 · Design mobile-first
rule: Get core functionality solid on the smallest screen, then progressively enhance.
do: Add columns, extra information, and larger elements only as space allows; respect safe areas and orientation changes.
never: Design the tablet layout and squeeze it onto a phone.

### MAD-05 · Size touch targets to the platform, not the legal floor
rule: 44×44 pt on iOS, 48×48 dp on Android, 60×60 pt on visionOS; leave 8–12 pt between interactive elements.
do: Treat 24×24 CSS px (WCAG 2.2 AA) as the legal/accessibility floor only.
never: Design to the 24 px WCAG figure.
because: Targets below ~44 px have reported error rates 3× higher than properly sized ones.

### MAD-06 · Put primary actions in the thumb zone
rule: Primary actions and essential elements belong within easy thumb reach.
do: Optimise layouts for both left- and right-handed users; test one-handed use.
never: Put the primary action in a top corner that needs a grip change or two hands.

### MAD-07 · Every gesture needs a visible tap alternative
rule: Every swipe or pinch has a tap-based fallback.
do: Place the equivalent button beside the swipe action.
never: Ship gesture-only interactions.

### MAD-08 · Respond to every touch
rule: Every tap, swipe, or gesture must produce a visible — and where critical, haptic — response.
do: Use background-colour change, scale, animation, or haptics.
never: Leave an interaction visually silent.

### MAD-09 · One primary action per screen
rule: Every screen has one clear primary action, and it is the most prominent element on screen.
do: Demote competing CTAs visually; spend the accent colour only on the primary action.
never: Highlight everything — when everything is highlighted, nothing stands out.
because: Multiple competing actions on one screen is choice overload plus cognitive load.

### MAD-10 · Build hierarchy from spacing and whitespace
rule: Order the screen with size/weight, colour/contrast, spacing/grouping, type scale, and white space.
do: Use a consistent 8 px spacing scale (8, 16, 24, 32) with no arbitrary values; isolate CTAs with extra space; validate by squinting.
never: Rely on decoration to create hierarchy.

### MAD-11 · Never hardcode font sizes
rule: Use system text styles (Dynamic Type); text must scale to 200% without breaking layout or functionality.
do: Use one or two fonts; make headers 1.5–2× body size and bolder; build emphasis with opacity (100% primary / 60% secondary / 40% tertiary).
never: Hardcode font sizes.

### MAD-12 · Keep the palette small; never rely on colour alone
rule: Palette = one brand colour + one complement + neutrals; add labels, shape, or text cues to every colour signal.
do: Use built-in system colours so light/dark adapt automatically; add a subtle scrim behind text on busy images and re-check contrast.
never: Communicate status by colour alone.

### MAD-13 · Support dark mode — never just invert it
rule: Support system-wide dark mode. Default to the OS setting; allow an in-app override.
do: Use off-white `#E0E0E0` on dark gray `#121212`; show elevation with lighter surface colours (shadows vanish on dark); ship alternate image/logo assets; keep 4.5:1 / 3:1 contrast.
never: Just invert the light-mode colours — pure white on pure black causes halation (affects roughly 50% of people with uncorrected astigmatism).

### MAD-14 · Follow the platform's design language
rule: iOS → Apple HIG. Android → Material Design 3. Cross-platform → choose one as the primary design language and adapt key patterns (navigation, gestures, typography) for the other.
do: Use native, platform-standard components; HIG and M3 are free and continuously updated.
never: Over-customize standard components or invent an interaction for a solved problem.
because: Platform fidelity is muscle memory; ignoring it makes an app feel foreign.

### MAD-15 · Use each platform's native navigation convention
rule: iOS: tab bar + swipe-back gesture (e.g. subtle fade). Android: bottom navigation bar + system/hardware back action (e.g. Material-aligned slide).
do: Adapt the same logical flow per platform rather than shipping one UI to both.
never: Ship a swipe-only back path on Android, or a hardware-button back model on iOS.

### MAD-16 · Keep primary actions two taps from home
rule: Primary actions must be no more than two taps from the home screen.
do: Limit the bottom tab bar to 3–5 tabs with universally recognizable icons plus text labels; use stack navigation for linear flows; use drawers only for secondary destinations.
never: Hide a key function in a secondary menu, place main actions away from where users need them, or switch navigation patterns between screens.

### MAD-17 · Treat accessibility as a legal requirement
rule: Accessibility is a foundational requirement from day one, not a retrofit — ethical and legal.
do: Label every interactive element for VoiceOver (iOS) and TalkBack (Android), provide alt text, respect Reduce Motion, prefer accessibility-first component libraries, and test manually — automated scanners are a starting point only.
never: Ship without manual VoiceOver/TalkBack testing, or rely on colour alone to convey meaning.
because: The European Accessibility Act has been in force across all 27 EU member states since 28 June 2025.

### MAD-18 · Meet the contrast minimums in every mode
rule: 4.5:1 for normal text, 3:1 for large text — in light mode and dark mode.
do: Verify with a contrast checker; offer high-contrast dark mode for low-vision users; check readability in tough lighting.
never: Approve a palette you have not measured.

### MAD-19 · Never show a blank screen
rule: Speed is a design decision. Never show a blank screen. Target LCP < 2.5 s.
do: Lazy-load below-the-fold content, code-split the initial bundle, bundle API calls, cache aggressively, use WebP (20–30% smaller), and show skeleton screens or progress indicators.
never: Leave a silent wait or a white screen while data loads.

### MAD-20 · Degrade gracefully offline
rule: Never show an endless spinner or a freeze on network loss. Either work offline via caching or transparently limit features until connectivity returns.
do: Cache data, queue offline mutations and send them on reconnect without an error dialog, show an offline status banner, disable connection-dependent features.
never: Assume connectivity on a subway, in an elevator, or in a rural area.

### MAD-21 · Limit onboarding to 3–5 skippable screens
rule: Keep the primary tour to 3–5 screens and always offer skip.
do: Demonstrate value immediately (first interactive action, free intro session); show a rationale screen before the OS permission prompt; turn empty states into contextual onboarding with a CTA; reveal advanced features gradually; A/B test the flow.
never: Gate value behind registration or fire generic OS permission pop-ups with no context.
because: Poor onboarding is a primary cause of uninstalls. Retention metrics named in source: Day 1 and Day 7 only.

### MAD-22 · Test before you build
rule: Prototype → user test → iterate, before writing code.
do: Walk the fidelity ladder (paper → wireframes → interactive → production A/B); ~5 users find ~85% of usability issues; run usability, accessibility, performance, compatibility, and QA tests; keep analytics and crash reporting live from day one; profile on real devices, not simulators only; meet store metadata, privacy-policy, and screenshot requirements.
never: Skip user testing until after launch — that is when mistakes are most expensive.

### MAD-23 · Design AI features for trust and control
rule: Never rely solely on AI. Every AI feature ships with trust signals, human override controls, and progressive AI disclosure.
do: Explain outputs (short explanation first, depth on demand), state capabilities and limitations so trust is calibrated, allow verification and editing, add guardrails, bias mitigation, human-in-the-loop review, and recovery from mistakes; onboard users to the feature; human-review AI-generated layouts, code, personas, microcopy, and accessibility fixes.
never: Trust AI output without validation — it can perpetuate bias and stereotypes — or ship a feature that cannot be explained, verified, or overridden.

## Hard numbers

| Constant | Value | Note |
|---|---|---|
| Touch target, iOS | **44×44 pt** (≈ 59 px) | HIG baseline |
| Touch target, Android | **48×48 dp** | Material baseline |
| Touch target, WCAG 2.2 AA | **24×24 CSS px** | Legal/accessibility floor; not a design target |
| Touch target, visionOS | **60×60 pt** | Spatial input is less precise |
| Gap between interactive elements | **8–12 pt** | Prevents accidental taps |
| Spacing scale | **8, 16, 24, 32** (8-pt grid) | No arbitrary margins/padding |
| Fonts / sizes per screen | **1–2 fonts, 2–3 sizes** | Type scale stays small |
| Text scaling ceiling | **200%** without breaking | Dynamic Type / system text styles |
| Opacity hierarchy | **100% / 60% / 40%** | Primary / secondary / tertiary text |
| Contrast, normal / large text | **4.5:1 / 3:1** | Same in dark mode |
| Dark-mode text on background | **`#E0E0E0` on `#121212`** | Avoids halation |
| Taps from home to primary action | **≤ 2** | |
| Bottom tab count | **3–5**, icons + labels | |
| Onboarding screens | **3–5**, skippable | |
| LCP | **< 2.5 s** | Primary loading metric |
| EAA | In force **28 June 2025**, 27 EU states | |
| EN 301 549 v4.1.0 | Expected final **Q3 2026** | References WCAG 2.2 — implement now |
| EAA penalties | **€75,000–€100,000** per violation | Country-dependent, reported |
| OLED power saving (dark mode) | **14–58%** | Source-reported |

Source-reported figures (directional, not audited): first impression forms in ~**50 ms**, ~**94%** design-driven; OLED dark mode cuts power **14–58%**; **49%** of professionals feel confident using AI tools. Web-origin performance figures (e.g. 20% sales per 1 s of delay, $1→$100 UX ROI) are **not app-specific** — do not apply them to apps.

## Decision procedure

Work in this order when designing a screen, feature, or app:

1. **Mission** — can the user answer all four design-mission questions here? If not, fix that first (MAD-01).
2. **Plane** — which 5 Elements plane is unresolved? Finish it before starting the plane above it (MAD-02).
3. **Scope** — does every feature serve the primary goal? Apply MoSCoW; defer the rest (MAD-03).
4. **Structure** — is the primary action ≤ 2 taps from home, in one navigation model, in the thumb zone (MAD-06, MAD-16)?
5. **Touch** — does every target clear 44 pt / 48 dp with 8–12 pt gaps, and does every gesture have a tap fallback (MAD-05, MAD-07)?
6. **Visual system** — does one primary action dominate under the squint test, on the 8-pt grid, with 1–2 fonts (MAD-09, MAD-10, MAD-11)?
7. **Access & modes** — 4.5:1 / 3:1 contrast, 200% text, screen-reader labels, Reduce Motion, dark mode without inversion (MAD-12, MAD-13, MAD-17, MAD-18).
8. **Delivery** — loading states, offline behaviour, real-device profiling, prototype tested with ~5 users (MAD-19, MAD-20, MAD-22).

## Anti-patterns

- Switching navigation patterns between screens — screens feel like different apps.
- Gesture-only interactions with no visible tap alternative.
- Hardcoded font sizes — breaks Dynamic Type.
- Pure white on pure black "dark mode" — halation.
- Blank screens and silent waits while loading; endless spinner when the network drops.
- Highlighting everything, so nothing stands out.
- Key functions buried in a secondary menu.
- Generic OS permission pop-ups with no rationale.
- Feature bloat at v1 instead of an MVP.

## Review checklist

- [ ] Every screen answers: where am I, what can I do, where can I go, can I trust this
- [ ] 5 Elements worked in order; every feature ties to the primary goal (MoSCoW applied)
- [ ] Designed mobile-first; smallest screen carries core functionality
- [ ] Targets ≥ 44×44 pt / 48×48 dp / 60×60 pt visionOS; ≥ 8–12 pt apart
- [ ] Primary actions in the thumb zone, ≤ 2 taps from home; every gesture has a tap alternative; every interaction has visual/haptic feedback
- [ ] One primary action per screen; 8-pt spacing scale; 1–2 fonts; 2–3 sizes; system text styles; scales to 200% without breakage; passes the squint test
- [ ] Native, platform-standard components; correct per-platform nav and back convention
- [ ] Contrast 4.5:1 / 3:1 in light and dark; colour never the sole signal
- [ ] VoiceOver and TalkBack labels on all interactive elements; alt text; Reduce Motion respected; tested manually
- [ ] Dark mode follows the OS with in-app override; `#E0E0E0` on `#121212`; alternate assets; lighter surfaces for elevation
- [ ] LCP < 2.5 s; no blank screens; lazy loading, code splitting, WebP; offline cache/queue/banner designed
- [ ] Onboarding 3–5 skippable screens; contextual permission rationale; empty states guide the first action
- [ ] Prototyped and tested with ~5 users; analytics + crash reporting from day one; profiled on real devices
- [ ] AI features (if any) carry trust signals, override controls, progressive disclosure, stated limitations
- [ ] Push notifications value-based, time-zone aware, user-customisable; store metadata, privacy policy, screenshots met

## Caveats

- Every percentage and dollar figure in the reference (53% leave after > 3 s, 82% prefer dark mode, up to 35% engagement lift, $1 → $100 UX ROI, 5 users → ~85% of issues) is **source-reported and unaudited**; the source itself instructs treating them as directional. Several originate in web/e-commerce research with applicability to native apps **unverified**.
- Material Design 3 Expressive figures ("up to 4× faster" element identification, "up to 87%" preference, 46 studies / 18,000+ participants) are **vendor-reported and not independently verified**. M3 Expressive, Apple Liquid Glass (mid-2025), M3 Expressive type roles, and the 2026 "AI skills" list are **version-sensitive** — re-verify against current platform docs.
- **WCAG version conflict:** the stated target is WCAG 2.2 Level AA, but some UI libraries still cite WCAG 2.1 AA. Target 2.2.
- **Touch-target tension:** the 24×24 CSS px AA floor is legally sufficient but below both platform minimums. The source resolves this in favour of 44 pt / 48 dp — do not treat the WCAG floor as a design target.
- **Forward-looking:** EN 301 549 v4.1.0 (expected Q3 2026), Dutch "spring 2026" audits, and French EAA enforcement signals were pending at source writing. EAA penalties are country-dependent and reported, not a legal citation.
- Universal Design (Centre for Excellence in Universal Design) and Design Thinking (Tim Brown, IDEO) are frameworks, not measurements; Fitts's, Hick's, Jakob's and Miller's Laws are absent from the source's referenced-laws list. Marked **unknown** there and not inferable: US ADA/Section 508 detail, quantified offline targets (sync latency, cache TTL, storage budgets), a formal design-token schema, i18n guidance, monetization patterns, and any Fitts's-law treatment.
- Vendor-reported figures are source-reported and not independently verified. Check the caveats above before citing a number.
