---
name: flow
title: Flow — Design Rules
description: Rules for producing a state of full immersion, energized focus and control by matching challenge to skill, answering every action instantly, and removing hesitation and distraction. Load when tuning difficulty, designing a repeat task or expert workflow, writing onboarding, adding focus or mastery mechanics, deciding where to simplify, or reviewing an experience people find either frustrating or boring.
applies_when: [difficulty tuning, repeat tasks, expert workflows, onboarding, focus modes, mastery and gamification, efficiency, ux review]
priority: supporting
rules: 14
---

# Flow — Design Rules

## Core principle

Flow is the state where a person is fully immersed in an activity with energized focus, full involvement, a sense of total control, and enjoyment of the process. It is not a visual style. It is the *result* of a balance the design controls, and of the interface never making the user hesitate.

```
challenge > skill  → anxiety, worry, heightened frustration  → raise SKILL
skill > challenge  → relaxed, bored, apathetic               → raise CHALLENGE

hesitation is the flow killer:
every action → instant visible feedback → next action already obvious
```

## Rules

### FLW-01 · Balance challenge against skill
rule: Tune the perceived difficulty of the task to the user's current skill.
do: Rate challenge and skill separately for each step of the core task; plan the first 15 minutes and steady-state use separately, since the balance drifts as the user improves.
never: Ship one fixed difficulty for the whole user base, or assume the level that suits your power-user tester suits everyone.

### FLW-02 · Too hard? Raise the skill, don't lower the task
rule: When challenge exceeds skill, close the skill gap first.
do: 1:1 onboarding, in-context teaching, progressive disclosure, sensible defaults, guardrails, undo, and visible sub-goals.
never: Delete features or dumb down the interface just to make failure less visible; simplicity is not the same as avoiding complexity.

### FLW-03 · Too easy? Raise the challenge
rule: When skill exceeds challenge, add difficulty deliberately. This is the counterintuitive move.
do: Set a stretch goal ("hit Inbox Zero without ever touching your mouse"); add mastery levels, deeper modes, advanced capability, more meaningful choices.
never: Add busywork, fake scarcity, or points as a stand-in for real challenge.

### FLW-04 · Make the next action obvious
rule: The user must always know what to do next and how to do it.
do: Keep the primary function visible and limit alternative actions so one path stays dominant.
never: Hide the next action behind a menu, a search, or a decision.
because: Hesitation is the flow killer.

### FLW-05 · Never make the user decide after every action
rule: When an action completes, put the next unit of work in front of them automatically.
do: Archive → the next item is already on screen; finish a record → the next record loads. Process one at a time.
never: Bounce the user back to an inbox, index, or landing page after every item.
because: The decision itself, repeated every single time, is what destroys flow.

### FLW-06 · Feedback on every action, instantly and visibly
rule: Every action returns a response the user perceives as immediate.
do: Treat 100 ms as the point where an action feels instant; acknowledge presses before any network work; show the state change.
never: Leave an action visually silent until a whole batch completes.

### FLW-07 · Show the result while it is being made
rule: The user must watch progress toward the goal continuously, not learn the outcome at the end.
do: Live preview while editing; per-item upload progress; a running count of what is done and what remains.
never: Submit everything, then reveal an error screen or a confirmation page.

### FLW-08 · Remove avoidable transitions and mental cost
rule: A committed user should never have to navigate, or think, in order to keep working.
do: Replace pagination with continuous loading; keep secondary actions in place below the item, without losing position; take intent in one step ("later today", not day/month/year/hour/minute selectors).
never: Require a click to reach the next page of the same list, or expose your data model as a form the user must complete.

### FLW-09 · Strip temporal and visual distraction
rule: Remove everything that invites the user to leave the task.
do: Run the removal test on every element — "if I had to remove just one thing, what would it be?" — then run it again. Keep the inbox, the next item, and new-content lists off screen mid-task.
never: Show what is next alongside what is being worked on.
because: Fast response kills temporal distraction; visual distraction is what's left to design away.

### FLW-10 · Set clear goals: one overarching, plus increments
rule: State the overall goal and the smaller goals that advance it.
do: Describe the product in plain, down-to-earth language; give realistic worked examples of use instead of a feature list.
never: Leave the user to infer what the product is for or how each feature would be used.

### FLW-11 · Make content and features discoverable, in context
rule: Once the user is at full efficiency, keep discovery available so boredom doesn't set in.
do: Surface newly created or most-popular content; place a feature's entry point in the context where the user is most likely to try it.
never: Turn discovery into an interruption in the middle of a running task — place it between sessions.

### FLW-12 · Match the mental model; friction accumulates
rule: The design must fit the user's model of the task, and every break in the smooth path must be removed.
do: Test the interrupted path deliberately; when the flow is broken, the experience is momentarily broken, so fix each break.
never: Treat a single friction event as cosmetic.

### FLW-13 · Flow is context-specific
rule: Decide explicitly where flow belongs. Not every screen should produce it.
do: Put flow on the repeatable task; let users blow through the home page on the way to what they came for. Short flow is valid flow.
never: Treat a home page, marketing page, or confirmation screen as a flow surface.

### FLW-14 · Measure flow by observation
rule: Flow will not show up in analytics, and surveys report what people want you to know.
do: Watch users work. Signs: they stop talking about *how* they are doing it, ask no how-to questions, are hard to interrupt, and later report feeling energized, productive, or gratified.
never: Declare flow achieved because session length, engagement, or a satisfaction score rose.

## Hard numbers

| Constant | Value | Note |
|---|---|---|
| Coinage | 1975 | Mihály Csíkszentmihályi; the concept is claimed to have existed for thousands of years under other names |
| Instant-response threshold | **100 ms** | Where an action starts to feel instant; slower invites distraction |
| Case-study response time | ≤ 100 ms originally → **< 32 ms** now | Vendor-reported email render in one product; not a general target |
| Productivity claim | **5× / 5-fold** | Asserted in the source with no study, sample, or effect size cited |
| Conditions checklist | 5 conditions | Know what to do next; know how to do it; no distractions; clear immediate feedback; high perceived challenge *and* skill — all seen above |
| First-use checkpoint | **first 15 minutes** | Ask what these should feel like, and what comes after |

## Decision procedure

When a repeat task feels frustrating or dull, work in this order:

1. **Place** — name the exact step or session where flow should occur. If you can't, you have no flow target (FLW-13).
2. **Rate challenge** — how hard is this to the intended user at their current skill? Challenge above skill shows up as errors, re-reads, backtracking, help-seeking, abandonment.
3. **Rate skill** — what does the user already know here? Skill above challenge shows up as fast completion, skimming, tab-switching, low return.
4. **Balance, too hard** — raise skill: onboarding, in-context teaching, defaults, guardrails, undo, visible sub-goals (FLW-02). Only lower the difficulty if the task itself is wrong.
5. **Balance, too easy** — raise challenge: stretch goal, mastery levels, deeper modes, meaningful choice (FLW-03). Not busywork.
6. **Clear the path** — verify each action answers instantly and visibly, the next action is obvious, there is nothing to navigate through, and nothing invites a mid-task detour (FLW-04 – FLW-09).
7. **Verify by watching** — observe a real session for the FLW-14 signs rather than asking about satisfaction.

## Anti-patterns

- Redesigning for simplicity until there is no challenge left.
- Treating delight, animation, or polish as the engagement strategy.
- A home page or browse experience designed as a flow surface.
- One difficulty setting for the entire user base.
- A batch confirmation, or a return to the list, after every completed action.
- Flow assessed only through analytics or satisfaction surveys.

## Review checklist

- [ ] Flow surfaces named explicitly
- [ ] Challenge rated against the intended user's skill; first 15 minutes and steady state treated separately
- [ ] Too-hard problems raise skill rather than delete the task
- [ ] Too-easy problems raise challenge deliberately
- [ ] Next action obvious at every point; alternative actions limited
- [ ] No decision required after each completed action
- [ ] Instant visible feedback on every action; progress and result visible while the work is made
- [ ] No avoidable transitions: pagination, back-to-list, lost position, field-by-field entry
- [ ] Removal test run; inbox / next item hidden during the task
- [ ] Goal stated with realistic examples; discovery available in context between tasks
- [ ] Flow signs observed in real sessions

## Caveats

- `response-time-progress-feedback.md` covers latency and progress feedback in depth; `cognitive-load.md` covers reducing effort. This skill is about matching challenge to skill — the other two reduce the load *around* the task.
- Flow is not an appropriate goal for every context, and not every step of a flow needs to create flow.
- These rules come from three overlapping practitioner articles. No controlled studies, sample sizes, or effect sizes are recorded anywhere in the source; the quantitative claims are a single latency threshold, one vendor's response time, and an unsourced 5× productivity figure.
- The claim that breaks in flow weigh more heavily than frictionless moments is stated without magnitude or evidence.
- The neuroscience framing (prefrontal downregulation, "transient hypofrontality") is asserted without citation.
- The five-condition list traces to Csikszentmihályi, Abuhamdeh & Nakamura, "Flow", in *Handbook of Competence and Motivation* (Guildford Press, 2005). The Gallup CE11 assessment is named as an option for subjective measurement; no threshold or scoring guidance is given.