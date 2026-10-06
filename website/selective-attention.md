---
name: selective-attention
title: Selective Attention — Design Rules
description: Rules for designing within the limits of users' selective attention. Users filter a screen down to goal-relevant stimuli, so content that looks like, sits near, or lives in an ad spot gets ignored (banner blindness), and changes lacking strong cues — or competing with other changes — go unseen (change blindness). Load when styling content, placing content near or among ads, animating, signalling interface changes, or reviewing UX.
applies_when: [ad-adjacent layout, content styling, banner design, animations, change signalling, notifications, mobile ui, ux review]
priority: supporting
rules: 14
---

# Selective Attention — Design Rules

## Core principle

Selective attention is the process of focusing on only a subset of the stimuli in the environment, usually those related to our goals. Attention is limited in capacity and duration: users do not perceive most of what a screen contains and will not stop filtering because you wish they would. The designer's job is to guide attention — prevent overwhelm, keep users from being distracted, and help them find the relevant information or action. Never fight the filter; design within it.

## Rules

### SAT-01 · Recognise attention as a filter
rule: Users do not perceive the page; they attend only to stimuli related to their current goal.
do: Guide attention with placement, contrast, and motion; put goal-relevant information where the user's eyes already are.
never: Assume anything is "seen" just because it is on screen and looks important to you.
because: Within a flood of sensory input most detail is filtered out without awareness; the user focusing elsewhere will overlook even large, prominent elements.

### SAT-02 · Never style content to look like an ad
rule: Legitimate content must not carry ad signals — ad-like placement, visual treatment, or proximity to promotions.
do: Choose colours, type, backgrounds, and layout consistent with the site's content conventions.
never: Make content stand out with ad-like treatment (fancy formatting, coloured box, animation) to "increase salience" — it often has the opposite effect.
because: Users have learned to ignore page elements they perceive, correctly or incorrectly, as ads; ad-like visual treatment such as animation is a recognised ad trait.

### SAT-03 · Keep important content out of ad-dedicated locations
rule: Do not rely on positions users have learned are ads — the top of the page or the right rail.
do: With real users, test that important content placed in the top banner or right rail is actually seen.
never: Put the primary answer only in the top banner or right rail and call it done.
because: Ad-specific placement is a learned ad signal; some participants skipped past an ad at the top of Google's own results even though its design was far from a traditional banner.

### SAT-04 · Never mix content and ads in one visual section
rule: Content and ads must occupy distinct visual sections.
do: If a section contains a promotion, treat the whole section as poisoned and move legitimate content elsewhere.
never: Sandwich helpful content between or beside sponsored items in the same region.
because: The Gestalt law of proximity groups nearby items as one unit; once the information scent says "ads", users stop scanning the rest. A participant judged the right rail ads from one sponsored story and never returned, though it held useful craft videos.

### SAT-05 · Respect the hot-potato effect
rule: One unwanted item makes users abandon an area — on that page, other pages, and other sites.
do: Assume users who classify a section as ads will not fixate there again anywhere.
never: Reuse a poisoned layout on deeper pages and expect users to re-check it.
because: The hot-potato scanning pattern: users gaze at an item they are not interested in, look away, and avoid it thereafter — a defence mechanism rooted in the availability bias.

### SAT-06 · Watch for faux ads on mobile
rule: On small screens, anything that stands out from its immediate context may be taken for an ad.
do: Keep big images, graphics, and standout elements visually continuous with the surrounding content.
never: Justify an element with "it matches the page" — on mobile only the immediately visible context counts.
because: Little of the page is visible at once and inline ads are large in proportion to the screen, so users scroll past anything ad-like (faux ads) without inspection, even valuable content.

### SAT-07 · Movement is the native cue for change
rule: A change is noticeable only when movement — or another strong cue — points to it.
do: Signal every change the user must see with motion or a strong visual cue.
never: Present a change as a silent static swap with nothing drawing the eye.
because: Peripheral vision detects movement, then central vision inspects the source. When that cue is weak or absent, change blindness occurs — and it is robust even when observers are warned a change may happen.

### SAT-08 · Make one change at a time
rule: Do not run competing changes simultaneously.
do: Sequence changes, or merge simultaneous changes into one coordinated event.
never: Update a second element while a first change should command attention.
because: When two changes compete, one wins the eye movement and that saccade blocks detection of the other. In an Android app, a search icon quietly replaced a top-right button while the menu opened, and users never noticed the swap.

### SAT-09 · Group simultaneous changes in one region
rule: Everything that changes at once should appear in the same screen region.
do: Collocate concurrently updating elements so one motion highlights them all.
never: Update two far-apart regions at the same time and expect both to be seen.

### SAT-10 · Present the change where the user is looking
rule: The response to a user action must be visible at the locus of that action.
do: Place the outcome next to the control that triggered it (e.g., a text field beside the search icon).
never: Update a far corner of the screen on user action and expect it to register.
because: The user's eyes follow the element that responds; surrounding elements are expected to stay unchanged, so changes spread across regions — even a nearby button swap — are missed.

### SAT-11 · Use animation sparingly for change
rule: Animation signals change; too many competing animations dilute the signal.
do: Animate the change you want noticed; still or dim other motion (heroes, carousels, moving backgrounds).
never: Let irrelevant animation run while an important update appears near it.
because: Competing motion splits attention and prevents the eye from reaching the change.

### SAT-12 · Dim what did not change
rule: Attract attention to a change by de-emphasising the areas that stay static.
do: Dim, blur, or shade non-changing regions and highlight only what changed.
never: Give the changed and unchanged states equal visual weight.
because: A big block of contrasting colour appearing in a corner shifts the page's "shadow profile" and is far easier to detect than a subtly blending element.

### SAT-13 · Anchor floating elements to the gaze and contrast
rule: Elements that appear while scrolling must land in the user's focus area with contrasting colours.
do: Place Back-to-Top-style controls toward the bottom of the page; choose colours that stand apart from the page.
never: Pop a semi-persistent bar in page-matching colours at the top of the screen mid-scroll.
because: Page scrolling masks the bar's own movement, and blending into the page's palette virtually guarantees it goes unseen.

### SAT-14 · Verify perception with real users
rule: "Obvious to me" is not "seen by the user".
do: Run usability tests (eye tracking where available) to confirm important content and changes are perceived.
never: Ship on the strength of your own certainty about what users will notice.
because: Designers know what to look for, where it will appear, when, and what it means — users do not.

## Hard numbers

| Fact | Value | Note |
|---|---|---|
| Banner-blindness participants, top/right-rail ads | **26 users** | same task page with ads in the top banner and right rail; text was read, ads almost ignored |
| Banner-blindness participants, inline promo | **26 users** | blue rectangle promo embedded in text was totally ignored |
| Right-rail attention (Andes-hikes study) | **1 of 132 = 0.8%** of content-area fixations, in a right rail spanning **25%** of the content area | page total 148 fixations, 132 in content area; fixations were **33 times** fewer than the rail's size warranted |
| Change-detection alternations (flicker experiments) | **20 or 40 alternations** for many participants | picture shown about **half a second**, display blank **a fraction of a second**; mid-1990s experiments |
| Banner blindness documented | **1997** (usability testing) → **2007** (major eyetracking study) → across **3 decades** | reconfirmed by a recent major eyetracking study |

Figures the source does not state (`unknown: true`):
- Prevalence rate — share of users who exhibit banner blindness: `unknown: true`.
- Sample sizes / participant counts in the change-detection flicker experiments: `unknown: true`.
- Participant count for the Google SERP ad-skipping observation: `unknown: true`.
- Participant counts for the mobile gaze studies (inline ads, faux ads): `unknown: true`.

## Decision procedure

When content or a change goes unperceived, audit in this order:

1. **Position** — is the content in an ad-dedicated spot (top, right rail) or the same visual section as a promo? Move it or test it (SAT-03, SAT-04).
2. **Style** — does it carry ad-like treatment (box, fancy formatting, animation)? Restyle to content conventions (SAT-02, SAT-06).
3. **Changes** — list every simultaneous change. Sequence them, or group them into one region (SAT-08, SAT-09).
4. **Cue** — is each change motion-cued at the locus of the user's action, with no competing animation? (SAT-07, SAT-10, SAT-11).
5. **Contrast** — do floating/transient elements contrast and land in the user's line of sight? Are unchanged areas dimmed? (SAT-12, SAT-13).
6. **Audience** — confirm with real users that the content and the change are actually perceived (SAT-14).

## Anti-patterns

- Content styled to "stand out" with ad-like visuals — the opposite of salience.
- Helpful content sharing the right rail or top banner with sponsored items.
- A search field or icon replacing another control while a menu opens elsewhere.
- Two simultaneous changes at opposite ends of the screen.
- Semi-persistent bars or floating buttons in page-matching colours appearing mid-scroll.
- An animated hero or carousel running while an important update appears near it.
- Silent static updates with no motion, dimming, or cue of any kind.

## Review checklist

- [ ] No content styled to look like an ad; no ad-like animation on content
- [ ] No content and ads sharing one visual section
- [ ] Important content not stranded in the top banner or right rail without testing
- [ ] Simultaneous changes sequenced, or grouped into one screen region
- [ ] Each important change carries a strong cue at the user's locus of attention
- [ ] No competing animations; unchanged areas de-emphasised
- [ ] Floating elements contrast with the page and appear within the user's focus area
- [ ] Mobile pass: standout elements cannot be mistaken for faux ads
- [ ] Real-user testing confirms important content and changes are perceived

## Caveats

- The title overstates this file's breadth: the source body is dominated by two selective-attention failure modes — banner blindness and change blindness — not the full psychology of attention.
- Selective attention is closely related to the Von Restorff Effect; the isolation principle itself lives in sibling skill `von-restorff-effect.md`, and change signalling connects to `cognitive-load.md` (CL-16 immediate feedback) — do not duplicate those here.
- The 0.8% / 33× figures come from a single user's gaze path in one study; the 26-participant studies report qualitative outcomes (ads got little attention), not prevalence rates.
- These are NN/g field observations rather than tightly controlled experiments; treat the mechanisms as robust and the magnitudes as sketchy. Banner blindness has, however, been documented across 3 decades.
- The mobile rule for search is relaxed: the source notes a magnifier icon is fairly discoverable on mobile when no search box is shown, but the field should still appear next to the icon when tapped.