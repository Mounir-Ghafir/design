---
name: serial-position-effect
title: Serial Position Effect — Design Rules
description: Rules for ordering lists, menus, navigation, carousels, landing pages, wizard steps, and data-entry sequences so the items users must remember sit where memory is strongest — the beginning (primacy) and the end (recency), with the least important items in the middle. Load when ordering any sequence, designing a flow's ending, or reviewing recall-heavy UI.
applies_when: [list ordering, navigation, menus, carousels, landing pages, wizards and flows, forms, settings, surveys, ux review]
priority: supporting
rules: 12
---

# Serial Position Effect — Design Rules

## Core principle

Users remember the FIRST and LAST items in a series best; the middle is where recall fails. The first item is rehearsed alone and stored into long-term memory (primacy); the last item is still held in working memory (recency); middle items must be rehearsed alongside everything before them and are least often stored.

```
first items   → remembered best  (primacy — long-term memory encoding)
last items    → remembered best  (recency — still in short-term/working memory)
middle items  → remembered worst (stored least frequently in either memory)
```

Position is a memory decision: what the item must survive for, and when the user will act on it, decide where it goes.

## Rules

### SPE-01 · Start with the most important item
rule: Open every list, menu, page, and flow with the item the user must remember.
do: Put the most important item first and give the sequence a strong opening.
never: Let the key item drift toward the middle.
because: The first item is rehearsed by itself and transferred to long-term memory, giving it a recall advantage (primacy effect).

### SPE-02 · Reserve the middle for the least important items
rule: Assign the weakest recall position to the items that matter least.
do: Place expendable details in the middle, between a strong beginning and a strong end.
never: Put a must-remember item in the middle of a list.
because: Middle items are stored less frequently in both long-term and working memory; recall degrades the nearer an item sits to the centre.

### SPE-03 · Strong start, strong finish
rule: Design the end of every sequence to be memorable — a call to action, summary, confirmation, or recap.
do: End landing pages with CTAs, close workflows with a confirm/recap step, restate key points at the end of long content.
never: Let a sequence trail off into a trivial detail or dead end.
because: The final item is still held in working memory (recency effect) — it is what remains when the user walks away.

### SPE-04 · Match placement to decision timing
rule: Choose first-vs-last placement from when the user will act on the information.
do: If the decision happens some time after exposure (>30 seconds), put the most important item first; if the decision is immediate, put the most important item last.
never: Pick placement without asking when the user decides.
because: Primacy survives a delay; recency is only there while the item is still in working memory. A sales page leads with the main benefit and saves persuasive extras like "free shipping" or "5% cashback" for the end — a visitor who leaves early still remembers the core benefit.

### SPE-05 · System-paced content keeps the payoff last
rule: When the user does not control the pace (video, audio), present the most important item last.
do: Structure time-driven content to build toward its key point.
never: Front-load the key point in content the user cannot pause or re-read.
because: Without self-paced rehearsal, early items fail to reach long-term memory; recency is the position that survives.

### SPE-06 · Anchor key navigation far left and far right
rule: Put primary navigation destinations at the far left and far right of a menu or tab bar.
do: Anchor core destinations ("Home", "Profile") at the edges; let secondary items sit toward the middle.
never: Hide primary navigation in the middle of a nav bar.
because: Edge positions are the ends of the sequence, where recall is strongest — the pattern seen in popular iOS tab bars that place "Home" left and "Profile" right.

### SPE-07 · Keep task-relevant information on screen
rule: Retain the information a task needs inside the interface instead of taxing the user's memory.
do: Show page numbers, rulers, grids, and reference data alongside the working area.
never: Expect users to hold task context in their head that the interface could display.
because: Recalling costs effort; recognition-based on-screen information reduces strain on limited attention and memory.

### SPE-08 · Add cues that trigger recognition and recall
rule: Include perceptual cues in the interface so users recognise or recall state without effort.
do: Tie sounds to cause and effect; add maps, speedometers, and status indicators.
never: Make users remember interface state a cue could communicate.

### SPE-09 · Face the user with fewer than five items at a time
rule: Keep the number of items presented at once below five.
do: Break long lists, menus, and flows into steps so the user faces fewer than five items at any one time within the dialogue.
never: Force a long list to be held in short-term memory at once.
because: Short-term memory maintains only a handful of items at one time (see Hard numbers).

### SPE-10 · Keep state visible across a workflow
rule: Never make the user accumulate and recall selections across steps unaided.
do: Show applied filters, cart contents, sort order, and progress at every step, or offer a simple way to retrieve this information.
never: Let earlier steps' choices vanish from view.
because: Recall of earlier-presented items is degraded by everything that happens between presentation and later use.

### SPE-11 · Randomise positions in choice lists
rule: Shuffle list positions so ordering cannot bias a choice.
do: Randomise option order for each voter or each presentation of a choice set.
never: Use a fixed order when the choice is being measured.
because: Primacy and recency add a systematic margin of error to choices from long lists; randomising nullifies it.

### SPE-12 · Plan for interruption: primacy survives, recency does not
rule: If a distraction or delay separates presentation from recall, put must-remember items first.
do: Assume recency is lost when a distractor task or a gap intervenes before the user acts; anchor critical content at the start.
never: Depend on end-of-sequence placement when the user will be interrupted or decide later.
because: In interference tests, primacy survived a 30-second distractor task while recency disappeared (Glanzer & Cunitz, 1966).

## Hard numbers

| Constant | Value | Note |
|---|---|---|
| Interference gap that eliminates recency | 30-second distractor task | Recency gone, primacy survived (Glanzer & Cunitz, 1966) |
| Decision-timing threshold | 30 seconds | Decide later → lead with the key item; decide immediately → end with it |
| Short-term memory capacity | three to four chunks | Glanzer & Cunitz (1966) conclusion |
| Operational presentation cap | fewer than 5 items at one time | Source's guidance; "up to around five items" held in short-term memory |
| Pacing effect | rapid presentation removes primacy; slower presentation improves recall | Glenberg et al. (1980) |
| Recall percentages / effect sizes | unknown: true | Source states none — do not fill in classic figures |

## Decision procedure

1. **Audit** — list every menu, list, carousel, wizard, and data-entry sequence; tag items by importance.
2. **Timing** — when will the user act? Delayed (>30 s) → most important first (SPE-01, SPE-04); immediately → most important last (SPE-04).
3. **Middle** — only the least-important items sit in the middle (SPE-02).
4. **End** — the sequence closes on a CTA, summary, confirmation, or recap (SPE-03).
5. **Interruption** — if a distractor or delay intervenes before recall, build on primacy (SPE-12).
6. **Pacing** — system-paced (video/audio)? Put the payoff last (SPE-05).
7. **Navigation** — anchor key destinations far left and far right (SPE-06).
8. **Load** — fewer than five items at a time; task info and cues on screen (SPE-07–SPE-10).
9. **Bias** — randomise positions whenever the choice is measured (SPE-11).

## Anti-patterns

- Most important item buried in the middle of a long list.
- Landing page that ends without a call to action or recap.
- Primary navigation (Home, Profile) sitting in the middle of a tab bar.
- Long single-screen lists that exceed short-term memory.
- Fixed option order in surveys or ranked choices.
- End-dependent placement when users will be interrupted or decide later.
- Auto-advancing critical content with no pause for rehearsal.

## Review checklist

- [ ] Every sequence has a strong opening, a deliberate middle, and a designed ending
- [ ] Most important item first when the decision is delayed
- [ ] Most important item last when the decision is immediate
- [ ] Least important items confined to the middle
- [ ] Ends deliver a CTA, summary, confirmation, or recap
- [ ] System-paced content builds toward its key point
- [ ] Key navigation anchored far left and far right
- [ ] Fewer than five items presented at any one time
- [ ] Task-relevant information and cues retained on screen
- [ ] Survey/choice positions randomised
- [ ] Critical items placed where recall survives interruption

## Caveats

- The source is secondary commentary. It references the classic memory research — Glenberg et al. (1980), Glanzer and Cunitz (1966) — but reports no recall percentages or effect sizes; those figures are `unknown: true` here, do not import them.
- The article is internally loose about capacity: "three to four chunks" (Glanzer & Cunitz) vs "up to around five items"; both are recorded as stated — the 5-item cap is a design heuristic, not a measured limit.
- Sibling skills: `peak-end-rule.md` covers the "end dominates memory" effect, `von-restorff-effect.md` the isolation effect, `chunking.md` memory grouping — this skill is specifically about POSITION within a sequence.
- The effect governs *recall / remembering*, not attention or scanning; it does not predict where the eye lands.
- Long series strain attention regardless of position — prefer breaking them up (SPE-09).