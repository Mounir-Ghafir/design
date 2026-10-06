---
name: working-memory
title: Working Memory — Design Rules
description: Rules for making the UI act as the user's external memory — keeping task-relevant information visible and carried across steps so users never have to hold it in their heads. Load when designing multi-step flows, forms, comparison tasks, shopping/carts, navigation, state preservation, or reviewing a UX for memory burden.
applies_when: [multi-step flows, forms, comparison, shopping and carts, navigation, state preservation, ux review]
priority: supporting
rules: 15
---

# Working Memory — Design Rules

## Core principle

Working memory is a small, limited-capacity scratchpad (buffer) that temporarily holds and manipulates information needed to complete the current task. When a task requires holding more than it can fit, users dump needed items, work harder to recover them, take longer, and make mistakes. The UI should be the user's **external memory**: hold and display task-relevant information so users never have to commit it to working memory or remember it from one step to the next.

High cognitive load usually means high working-memory burden; tasks that tax working memory feel hard. Working memory is closely related to — but distinct from — short-term memory.

## Rules

### WM-01 · The UI is the user's external memory
rule: Treat the interface as the user's external memory.
do: Keep every piece of task-relevant information visible in the UI so the user can glance at it instead of recalling it.
never: Ask users to commit information to memory that the system could show or hold.
because: External memory is any tool or UI feature that lets users explicitly save and access information needed during a task.

### WM-02 · Never make users hold information temporarily
rule: No step may require holding a fact, value, or selection for a later step.
do: Carry values, selections, and context over from screen to screen and display them where needed.
never: Require the user to memorize an intermediate result, code, or option to enter it later.

### WM-03 · Keep task-relevant information on screen
rule: Everything the current step needs must stay visible at that step.
do: Keep the source material, the comparison set, or the prior answer on screen next to the current decision.
never: Force scrolling back or switching screens mid-task to recover needed information.
because: The screen is a natural external memory — users recover a scrolled-off concept by re-reading it; on small screens the scratchpad is smaller and recovery costs more time.

### WM-04 · Preserve page state
rule: Preserve state across navigation and reloads.
do: Restore form data, filters, scroll position, and unsaved input.
never: Discard user input because the user navigated, reloaded, or reopened the page.

### WM-05 · Provide explicit external-memory tools for heavy tasks
rule: For inherently information-heavy tasks, provide a place to store and access the needed information.
do: Comparison tables, saved-item lists, carts, and review-before-submit summaries.
never: Leave users juggling alternatives purely in their heads with no scaffold.
because: Comparing options means keeping the candidates in mind; a table lines them up so they don't have to be remembered.

### WM-06 · Support the user's own memory aids
rule: Users create their own external memory — carts, open tabs, spreadsheets, notes.
do: Make saved items and carts persistent and comparable; let users "park" candidates in tabs or lists.
never: Silently expire or wipe saved candidates, or force a decision before the user is ready.

### WM-07 · Don't stack a second memory load on the task
rule: A side burden of held information degrades the main task.
do: Show the side value in the UI; don't require storing it while doing something else.
never: Ask users to remember digits or data while simultaneously performing another task.
because: In the source's dual-task experiments, people storing 1–6 digits while doing a second task performed worse as the digit load grew; 1–2 digits did not interfere.

### WM-08 · Design for variable capacity
rule: Assume your users have less working-memory capacity than your team.
do: Target the general audience, keep flows light, and validate with real users.
never: Approve a flow because it feels easy to the team.
because: Education and IQ correlate positively with working-memory capacity, age correlates negatively, and a general audience varies widely; many developers have large working memories.

### WM-09 · Co-locate related information
rule: Related information must live on the same screen as the decision it supports.
do: Put references, prerequisites, and comparisons next to where they are used.
never: Split interdependent information across screens with nothing bridging them.

### WM-10 · Mark progress in multi-step flows
rule: Multi-step processes must remind users where they are and what they've done.
do: Progress indicators, step status, summaries, and review-before-final-submit.
never: Rely on users remembering what they did in earlier steps.

### WM-11 · Recognition over recall
rule: Show what was previously seen or done rather than making users recall it.
do: Visually differentiate visited links, show breadcrumbs, re-display previously entered values.
never: Require users to remember where they've been or what they last typed.

### WM-12 · Support the task with a scratchpad
rule: If a task is inherently hard, supply a virtual scratchpad — don't change the task.
do: Provide pen-and-paper equivalents: notes fields, saved working lists, printable/downloadable summaries.
never: Strip or hide needed information to make the screen look lighter.

### WM-13 · Offload from the system first
rule: Never require the user to supply or re-enter data the system already holds.
do: Smart defaults, autofill, and carried-over values.
never: Show an empty field for information the app already knows.
because: Overlaps cognitive-load.md CL-05; load this skill when the question is memory-holding, that one for overall load reduction.

### WM-14 · Forgetfulness is a design flaw
rule: When users forget information between steps, fix the UI, not the user.
do: Audit every point where the user must hold more than the buffer can fit and add external memory there.
never: Treat forgetting as user laziness or reply with added instructions instead of removing the hold.
because: Users forget because the interface requires more working memory than their brains can hold.

### WM-15 · Hold only what is necessary and relevant
rule: Whatever a step asks the user to keep in mind must be necessary and relevant to that step.
do: Trim what a screen demands users hold; keep strain off the buffer by showing instead of storing.
never: Display information at a task step just because it exists.

## Hard numbers

| Figure | Value (verbatim from source) | Note |
|---|---|---|
| Working-memory capacity (source summary) | **4–7 chunks** at any given moment | From the article's own takeaways; no study detail given |
| Chunk persistence (source summary) | each chunk **fades after 20–30 seconds** | From the article's own takeaways; no study detail given |
| Digits held in dual-task experiment | **1 to 6** digits | More stored digits ⇒ worse performance on the second task |
| Digits that did not interfere | **1–2** digits | Second-task performance did not suffer at this load |
| Short-term memory capacity | ~**7 chunks** ("magical number 7") | Source credits Miller, 1958 — short-term memory, not working memory |
| Mobile comprehension time penalty vs desktop | unknown: true | Source states "more time" with no magnitude |
| Empirical detail (sample sizes, effect sizes) | unknown: true | Source is a conceptual practitioner article |

## Decision procedure

Trace the task and find every point where the user must hold information:

1. **Carried items** — for each step, list what the user must bring forward: remembered values, prior steps, comparison candidates, choices.
2. **Offload** — for each carried item ask: can the system show it, store it, or carry it? If yes, do it (WM-01, WM-02).
3. **Visibility** — is all task-relevant information on the current screen, without scroll-back or a second tab (WM-03)?
4. **State** — do form data, filters, scroll, and unsaved input survive navigation and reloads (WM-04)?
5. **Scaffolds** — for inherently heavy tasks, add compare/save/review tools; respect user-made carts and tab-parked lists (WM-05, WM-06).
6. **Progression** — do multi-step flows show progress and a review-before-submit (WM-10)?
7. **Audience** — re-check with a low-capacity lens: small screens, older or distracted users, never just your team (WM-08).

## Anti-patterns

- Requiring users to memorize a value entered on page 1 to use on page 3.
- Wiping form data, filters, or scroll position on reload.
- Multi-option decisions with no comparison table or saved-candidate list.
- Multi-step flow with no progress indicator and no review step.
- Decision on one screen while the needed information sits on another.
- Empty fields for information the system already knows.
- Silently expiring or wiping a saved cart, wishlist, or parked list of candidates.

## Review checklist

- [ ] No step asks the user to hold information the UI could carry
- [ ] All task-relevant information visible at the point of use (no scroll-back or shuttling)
- [ ] Form data, filters, scroll position, and unsaved input survive navigation/reload
- [ ] External-memory tools present for heavy tasks (compare, save, review)
- [ ] User-made aids — carts, tabs, lists, notes — supported and persistent
- [ ] Related information co-located with the decision it supports
- [ ] Multi-step flows show progress and review-before-submit
- [ ] Recognition cues: visited links, breadcrumbs, previously entered values
- [ ] Defaults/autofill used instead of blank known fields
- [ ] Validated with general users, not just the team

## Caveats

- Sibling scope: cognitive-load.md owns the load model and general load reduction (its CL-05 overlaps WM-13); millers-law.md owns the 7 ± 2 capacity debates; chunking.md owns grouping data for entry; progressive-disclosure.md owns sequencing and reveal-on-need — load those for those jobs, this file for memory-holding and state continuity.
- The source is an NN/g practitioner article, not a controlled study. Its only empirical description is the Baddeley & Hitch dual-task digit experiments, reported as a direction (more digits ⇒ worse second-task performance) with no sample sizes or effect sizes.
- The capacity and duration figures (4–7 chunks; 20–30 seconds) come from the article's summary takeaways; the underlying study-level evidence is unknown.
- The source dates Miller's observation to 1958 (verbatim); the canonical paper is from 1956 (see millers-law skill), and the ~7-chunk figure is about short-term memory, not working memory.
- Check these caveats before defending any rule in review.