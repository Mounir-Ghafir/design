---
name: zeigarnik-effect
title: Zeigarnik Effect — Design Rules
description: Rules for using the Zeigarnik effect (unfinished tasks hold attention and pull users back) and the endowed-progress head start. Load when designing onboarding, progress bars, task lists, loyalty or reward flows, content queues with partial completion, resumable states, and return-engagement mechanics.
applies_when: [onboarding, progress bars, task lists, checklists, loyalty and rewards, content discovery, resumable states, retention, return engagement]
priority: supporting
rules: 13
---

# Zeigarnik Effect — Design Rules

## Core principle

People remember uncompleted or interrupted tasks better than completed ones (observed by Bluma Zeigarnik in 1927, in a waiter who recalled unpaid orders but forgot them once everyone paid). Starting a task establishes a task-specific tension (Lewin's field theory) that keeps relevant information accessible; completing the task relieves that tension, and interruption prevents the relief.

Design's job: create *useful* incompleteness — visible, resumable, honest — and give users a head start (endowed progress), never manufactured anxiety.

## Rules

### ZE-01 · Start 'in progress', not unstarted
rule: Present a new task as already begun.
do: Reframe stage labels so the first step counts as progress — 'Signing in' should read as step 1, not step 0.
never: Show a fresh flow that reads as a blank, unstarted slate.
because: An interrupted or already-started action carries a strong push to complete; a pristine blank carries none.

### ZE-02 · Give users a head start
rule: Endow users with visible progress toward a goal (endowed progress effect).
do: Pre-stamp, pre-credit, or pre-fill part of the path; the tested head start is 2 of 10 slots (20%). Example: TGI Fridays grants a free appetiser for joining its rewards program (1 point per US dollar spent).
never: Start every progress counter at 0%.
because: Artificial advancement creates the illusion of less effort remaining, and completion rises with it (see Hard numbers).

### ZE-03 · Head starts must stay honest
rule: Granted progress must be real, uniform, and explained.
do: Give every user the same head start and make the source of the credit legible.
never: Falsify progress, or grant head starts selectively to some users.
because: The effect rides on perceived partial completion; discovered deception destroys trust and the effect with it.

### ZE-04 · Interruption must signal benefit, not brokenness
rule: Make incomplete states look deliberate and valuable.
do: Frame partial states as 'not yet done' progress toward an obvious reward.
never: Present an interrupted state as an error, dead end, or broken feature.
because: Task tension motivates only while the finish line stays visible and reachable; broken-looking states drive abandonment.

### ZE-05 · Show progress explicitly
rule: Display exactly where the user is and what remains.
do: Use task counters and percentages, e.g. '6/69 challenges solved' and '81% complete' (HackerRank).
never: Track a task invisibly with no completion status at all.
because: A clear indication of progress is a direct motivator for task completion.

### ZE-06 · Visualise the finish line
rule: Represent the goal externally so it is easy to picture.
do: Use a progress bar that states what is done, where the user is, and what the next step is; LinkedIn shows profile completeness and prompts concrete next actions like 'Add Profile Picture'.
never: Show a progress state with no named next action.
because: As people approach a goal, external representations that ease visualising the goal enhance goal pursuit (Cheema and Bagchi).

### ZE-07 · Leave a 'not yet done' remainder
rule: Break consumed content into smaller parts with a visible remainder.
do: Chop long content into digestible portions the reader is 'not yet done' with.
never: Serve content in one complete blob with no continuation signal.
because: A visible remainder keeps the task in mind and promotes further consumption.

### ZE-08 · Don't hand over all value up front
rule: Withhold part of the value at the start.
do: Leave the deeper content incomplete at the beginning — an email header ending in an ellipsis, not a full stop.
never: Disclose all value of a material before the user has engaged it.
because: The natural desire to complete a task pulls the reader into the deeper content.

### ZE-09 · Make interruption resumable
rule: Interrupted tasks must resurface somewhere the user can continue.
do: Persist the partial state — saved carts, drafts, partially-consumed content — with an obvious 'continue where you left off' path; reminder or streak patterns may point back to it.
never: Let abandonment erase or reset the partial state without a trace.
because: Unfinished tasks intrude on the mind until closed, so a clear resume path converts that tension into a return visit (the cliffhanger pattern).

### ZE-10 · Apply where users drift off
rule: Place completion pressure at the points where users already abandon.
do: Find flow segments where users tend to drift off (onboarding checklists, loyalty cards, reward programs) and make partial progress visible there.
never: Apply the effect to tasks that hold no remaining value for the user.
because: Applied where users drift, it improves engagement, retention, onboarding, and task completion; applied everywhere it becomes noise.

### ZE-11 · Plan the post-completion moment
rule: Design the action a user is likely and mentally free to take right after finishing.
do: Queue the natural next move for the moment of completion — offer what the user is more willing and able to do post-task.
never: Treat 'done' as the end of the experience with no next step designed.
because: Right after completion the tension is relieved and the user is available for follow-up actions they would otherwise not take.

### ZE-12 · Make the final stretch feel short
rule: Keep the remaining gap visibly small as the goal approaches.
do: Reinforce how much is *left* rather than how far the user has come, and keep the last steps effortless.
never: Add new requirements or hidden work near the finish line.
because: People are motivated by how much is left, not how far they've reached; the closer the goal, the faster the approach (see goal-gradient-effect.md).

### ZE-13 · Never manufacture anxiety
rule: The tension you create must correspond to real, freely-reachable user value.
do: Pair every incomplete state with a clear, reachable completion and the freedom to walk away.
never: Manufacture urgency — fake expiry, false interruption, nagging notifications, progress that decays — to force completion.
because: Interruption designed to 'trick' users (as the practitioner sources admit) becomes a dark pattern once the tension no longer matches a real benefit.

## Hard numbers

| Figure | Value | Note |
|---|---|---|
| Endowed-progress comparison | Head start: **2 of 10 slots pre-stamped (20%)** vs **8 slots, 0 stamped (0%)** | Groups A/B, loyalty-card car wash; both needed **8 purchases** |
| Completion with head start | **34% redeemed** | Group A (experimental) |
| Completion, control | **19% redeemed** | Group B (control) |
| Experiment identity | Nunes & Dreze (2006), 'The Endowed Progress Effect: How Artificial Advancement Increases Effort' | Free car wash after 8 purchases |
| Sample size / effect size | `unknown: true` | Source gives redemption percentages only |
| Original waiter study | 1927; paper 'On Finished and Unfinished Tasks' / Über das Behalten von erledigten und unerledigten Handlungen, Psychologische Forschung | Bluma Zeigarnik (1901–1988); N and method `unknown: true` |
| Coffee loyalty example | Free 10th coffee after 9 paid | Digital stamp card (goal-gradient evidence; see sibling) |

## Decision procedure

When adding a Zeigarnik-style mechanic, work in this order:

1. **Value first** — confirm real user value remains unfinished. No real value, no tension (ZE-13).
2. **Start already begun** — reframe the flow so step 1 counts as progress (ZE-01).
3. **Endow honestly** — any head start is uniform, explained, and universal; never start at 0% (ZE-02, ZE-03).
4. **Name the state** — show exact progress, percent done, and the next step (ZE-05, ZE-06).
5. **Signal benefit** — partial states must read as deliberate progress, not breakage (ZE-04).
6. **Make it resumable** — persisting partial states with a clear continue path (ZE-09).
7. **Design the finish** — plan the final stretch and the post-completion move (ZE-11, ZE-12).
8. **Audit the ethics** — if the tension could read as anxiety or a trap, remove it (ZE-13).

## Anti-patterns

- Every counter starting at 0%, or a flow that reads as unstarted.
- Falsified progress or moving the goalposts as the user nears the end.
- Interrupted states that resemble errors or dead ends.
- Missing completion status or hidden progress (ZE-05 / ZE-06 ignored).
- All value disclosed up front — nothing left to discover.
- Abandoned carts, drafts, or content that vanish, erasing the interrupted task.
- Artificial urgency: fake expiry timers, countdown anxiety, nagging notifications, decaying streaks.
- Completion pressure applied to tasks with no remaining value to the user.

## Review checklist

- [ ] Every flow starts 'in progress' or with an honest endowment, never a blank 0%
- [ ] Progress is visible: where the user is, what's done, what's next
- [ ] Head starts are uniform, explained, and honest
- [ ] Partial states read as deliberate progress, not brokenness
- [ ] All interrupted states are resumable (carts, drafts, content) with a continue path
- [ ] Deeper content is withheld for discovery; no full-value dump
- [ ] Content is chunked with a visible 'not yet done' remainder
- [ ] The final stretch is short and free of new requirements
- [ ] The post-completion next action is designed
- [ ] No manufactured urgency, fake interruption, or anxiety-driven pressure

## Caveats

- Source is practitioner writing (Canvs Editorial, Nov 2020; Abhishek Chakraborty, Sep 2017; and a compiled reference card) — bylines, Medium subscribe blocks, image credits, and share prompts stripped; not a peer-reviewed treatment. Original waiter study detail: source reports only the 1927 attribution and paper title (N and method `unknown: true`); the endowed-progress experiment preserves only the redemption percentages (34% vs 19%) with sample sizes and effect sizes `unknown: true` (a McKinney 1935 citation also appears without detail). Overlaps with **goal-gradient-effect.md** (Hull/theory; the endowed-progress experiment IS goal-gradient evidence — cross-reference, don't duplicate), **response-time-progress-feedback.md** (percent-done indicators from a latency angle), and **progressive-disclosure.md** (staged reveal).
