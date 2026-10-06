---
name: response-time-progress-feedback
title: Response Time & Progress Feedback — Design Rules
description: Rules for how fast a system must answer, and for telling the user what is happening during the wait. Load when designing loading states, spinners, progress bars, skeleton screens, long or background operations, uploads and exports, multi-step flows, latency budgets, error recovery, or reviewing a slow interface.
applies_when: [loading states, progress indicators, spinners and skeletons, async and background tasks, latency budgets, long-running operations, multi-step flows, error recovery, ux review]
priority: core
rules: 18
---

# Response Time & Progress Feedback — Design Rules

## Core principle

Response time is not one number. Acceptable delay depends on **what** the response is to, on **closure** (how complete the task already feels), and on whether feedback proves the system is working. Make the fast path faster; when you cannot be fast, prove liveness, then free the user.

```
0.1 s  felt instant   →  1 s  thought uninterrupted   →  2 s  continuity, only after closure
10 s   attention holds →  15 s  discontinuity: the wait becomes a separate episode
```

Faster responses raise productivity **more than proportionally** — the gains accelerate below one second.

## Rules

### RT-01 · Direct manipulation must be felt, not seen
rule: Every tap, key, drag and draw responds in ≤ 0.1 s.
do: Press states, ripples, echoed characters (≤ 0.1–0.2 s), haptics; drawing with no perceived variability.
never: Block a local press on a network round trip before acknowledging it.
because: Below ~0.1 s the response is absorbed into the physical action; past it, hand and eye desynchronise.

### RT-02 · 400 ms is the flow-of-thought line
rule: Anything inside a train of thought gets feedback within **~400 ms** (the Doherty threshold).
do: Target ≤ 400 ms for navigation transitions, list updates, validation, taps that fetch.
never: Spend a thought-interrupting wait on an interaction the user could have driven instantly.
because: Users hold a sequence of actions in short-term memory; delay disrupts it and forces a rethink.

### RT-03 · Scanning and paging stay under a second
rule: Next-page and next-screen loads feel instant (≤ ~1 s); while scanning, 0.5 s is already long.
do: Prefetch the next page or chunk during reading; virtualise long lists; keep scroll jank at zero.
never: Make someone wait for a page turn just to see the page.
because: A scanner should be able to skip ten pages as fast as one.

### RT-04 · Past ~2 s, wait only at a closure point
rule: Delays beyond ~2 s are acceptable only after the user perceives task or subtask closure.
do: Queue long work at a natural pause — after submit, after a saved step, on navigation; report errors ~2–4 s after the user finishes their thought (on blur), not mid-entry.
never: Stall the middle of a form, scroll or edit with an unprompted wait.
because: Greater closure permits longer delay; mid-thought interruption costs more than the wait.

### RT-05 · Between 5 and 10 s, prove liveness
rule: Long enough to worry, short enough to wait — show that work is happening.
do: Busy or progress feedback; keep the page and the user's place visible instead of blanking it.
never: Swap loaded content for a full-screen spinner the instant a fetch starts.
because: Novices assume a crash without feedback; experts need an estimate to plan parallel work.

### RT-06 · The 15-second discontinuity ends the conversation
rule: At ~15 s the wait stops being a pause in a task and becomes a separate episode — free the user.
do: Move the work to the background, notify on completion, let them leave and come back.
never: Hold anyone captive in a blocking spinner for a minute.
because: Captivity past 15 s demoralises: work pace and motivation fall.

### RT-07 · Signal 1 — the system is busy working
rule: Acknowledge immediately: heard, accepted, understood, working — one signal can carry all four.
do: Press state → spinner → determinate bar; name what is running.
never: Leave the UI silent after submit.
because: A response also feeds back on continuity of thought, and proves the command was not lost.

### RT-08 · Signal 2 — the system needs you
rule: When input is required, say precisely what is needed and put the user where to supply it.
do: Name the missing field or decision, focus it, keep everything already entered.
never: A generic "invalid input" toast that leaves the user hunting for the cause.
because: An unspecified demand is a second, longer wait after the first one.

### RT-09 · Signal 3 — the task is accomplished
rule: Completion must be unmistakable and must unblock the next step.
do: Confirm where the user is looking, reveal the result, offer the next action.
never: A silent state change that needs a screen re-read to detect.
because: The completion signal *is* the closure the user was waiting for.

### RT-10 · Signal 4 — the system has failed
rule: On failure, stop the indicator, say what happened, and keep the user's work.
do: Clear error naming the cause, a retry path, preserved state, and how long recovery will take.
never: Let a progress bar freeze or crawl after the process died — it reads as a hang.
because: A stalled indicator is only meaningful if stalls are real; false liveness destroys the crash signal.

### RT-11 · Show progress graphically, not numerically
rule: A filling graphic beats a number when an exact value isn't required.
do: Bar or thermometer that fills; it implies approximation, which is honest, and fits small spaces.
never: Make a bare "47%" the primary progress display.
because: Users assimilate graphics faster than text, and exact completion times are rarely knowable.

### RT-12 · Progress must be real
rule: Show a percentage only for genuinely countable work, and let the indicator reflect real state.
do: Linear work (upload, download, install, export, compile) → graphical percent done, optionally time remaining; unknown duration (pipelines, remote calls, multi-pass jobs) → indeterminate spinner or skeleton, driven by real milestones.
never: Invent a total to justify a percentage, animate "activity" that outlives the work, or show a countdown you cannot honour.
because: Approximation is acceptable, fiction is not — and a time estimate only helps when it is credible.

### RT-13 · Never start a user at 0%
rule: Do not open a flow the user has partly completed at zero progress.
do: Give an artificial head start; credit finished steps on the first render.
never: A progress meter that begins at 0% on step 2 of 3.
because: Goal-gradient logic: motivation rises with perceived proximity to the goal; starting at zero reads as standing still.

### RT-14 · Don't make users pay twice for a failure
rule: Recovery time is part of the failure's cost; minimise it and restore state.
do: Autosave drafts, forms, carts; restore the last query, index or model parameters; state the recovery wait immediately; target ~15 s, or failing that under 5 minutes.
never: Make someone re-enter work the system already had.
because: Lost work demoralises and produces an irrational sense of personal failure.

### RT-15 · Make waits feel shorter — without making them longer
rule: Improve perceived performance: optimistic UI, skeletons, prefetch, partial results, useful occupation.
do: Render the expected result and reconcile; stream multi-item results progressively; label the loading regions.
never: Substitute animation work for speed work.
because: With an indicator, users watched the screen and noticed answers; without one they looked around the room.

### RT-16 · Never buy perceived value with an artificial delay
rule: Adding delay to "build trust" is unsupported by evidence and cuts against continuity.
do: If you pace anything deliberately, keep it short, transparent and off the path of a blocked task.
never: Slow a fast operation because delay is claimed to increase perceived value or trust.
because: It is a summary takeaway with no study behind it, and it contradicts Miller's continuity and morale rules.

### RT-17 · Spec a nominal value and a tolerance
rule: Every response-time requirement needs a target, a tolerance, and a response type.
do: Name the response type, the nominal value, and the range a user cannot detect; re-validate on your own tasks.
never: Ship a bare "the API must be fast".
because: Miller's specification principle — and his per-topic values are explicitly his best calculated guesses.

### RT-18 · Don't promise a constant time you can't hold
rule: Prefer predictable timing where you can deliver it; variable is not automatically worse.
do: When variability is real (network, cache, load), pair it with progress feedback; keep variance inside a plausible band.
never: Assume "constant is better" as a law — the replication failed to support it.
because: Prior work favoured constant times (L. H. Miller 1977; Carbonell 1968; Weisberg 1984); Myers found pr = 0.2046, and non-significance is not equivalence.

## Hard numbers

| Tier / figure | Time or value | What it means | Note |
|---|---|---|---|
| Instant / direct manipulation | **≤ 0.1 s** | Felt instant — part of the physical action | Keystroke echo ≤ 0.1–0.2 s; tracing with no perceived variability |
| Doherty threshold | **400 ms** | Flow of thought uninterrupted; neither side waits on the other | Popularised figure; see Caveats on provenance |
| Scanning / paging | **~1 s** | Next page feels instant | 0.5 s is already long mid-scan |
| Conversational | **~2 s** (up to ~3–4 s complex) | Thought continuity maintained | Beyond 2 s only after closure |
| Tolerable with feedback | **~5–10 s** | Attention stretches — needs liveness signals | Status inquiry may relax to 7–10 s |
| Attention limit → discontinuity | **~10 s** attention holds; **~15 s** it breaks | Beyond ~10 s → background progress or status; at 15 s the wait becomes a separate episode, users abandon or lose the thread | 15 s = Miller Postscript 1; the 10 s bound is a low-confidence snippet |
| Percent-done | No time threshold given | Show percent done **only when duration is computable** | The source justifies percent-done by computability, not by elapsed time. No "show a percentage after N seconds" rule is stated (`unknown: true`) |
| Thadhani (programmers) | 3.0 s → ~180 tph; 0.3 s → **371 tph** (+106%) | Gains accelerate below 1 s | Productivity rises more than proportionally |
| Poughkeepsie forecasters | SRT ≥ 5 s → **99 tph**; sub-second → **336 tph** | Administrative work benefits too | Brief states "339%" — reads as 339% *of baseline* (≈ +239%); flagged in source |
| Lab tolerance (indirect) | ~16% at 2–4 s; **<10%** at 0.6–0.8 s; 20–30% at 6–30 s | How much variation users cannot detect | Careful stimuli, full attention; real tasks may exceed it |
| Myers 1985 | **86.1%** liked progress indicators; pr = **0.0006** vs none | Progress feedback is preferred | n = 48; waits 10 s constant, 1–17 s variable (mean 8.601 s) |
| Constant vs variable | pr = **0.2046** (n.s.); no-progress subset 0.1497 | No evidence of preference | Non-significance ≠ equivalence |

### Field evidence (case figures, not thresholds)

Reported per-study outcomes. Use as precedent for why speed pays, not as design targets.

| Case | Before | After | Reported change |
|---|---|---|---|
| Thadhani (programmers) | 3.0 s SRT → ~180 tph | 0.3 s → **371 tph** | **+106%**; a 2.7 s cut saves **10.3 s** of user time per transaction |
| Poughkeepsie forecasters | SRT ≥ 5 s → **99 tph** | sub-second → **336 tph** | Brief's "339%" reads as 339% *of baseline* (≈ +239%), flagged in source |
| Lab C (source-reported) | — | SRT 6 s → 0.25 s | Time per task fell ~**6 min (20%)** |
| Lab D | **36 min** | **23.5 min** at SRT 0.6 → 0.25 s | **35%** saved; 3.6 min per operation |
| Scaled service | **~300** concurrent users, 80% of txns ≤ 0.5 s, ~95,000 tasks/month | grew to ~400 users (projected **908,000** transactions) | SRT degradation to ~4 s avg raised task time **32 → 48 min (+50%)**, adding **22,500** extra hours/month |

## Decision procedure

When a wait is in play, work in this order:

1. **Classify** — which response type is this? Direct manipulation, in-thought action, closure-bound work, or long-running job? The tier follows from the type.
2. **Budget** — set a nominal value *and* a tolerance (RT-17). Write it into the spec, not into a wish.
3. **Instant path** — anything under ~0.1 s gets unconditional local feedback (RT-01); audit for network round trips hiding behind a local press.
4. **Acknowledge** — every accepted command emits all four messages (RT-07) before any long work starts.
5. **Indicator** — computable total → graphical percent done; unknown total → indeterminate liveness (RT-11, RT-12).
6. **Honesty check** — can this indicator stall, and does it stop on failure? A bar that keeps moving after a dead process is worse than silence (RT-10, RT-12).
7. **Escape hatch** — over ~15 s, background the job, notify, preserve state, and say how long recovery or the job will take (RT-06, RT-14).
8. **Verify** — measure real latency and attention drift on your own tasks; these thresholds are guidance, not law.

## Anti-patterns

- A full-screen spinner replacing content that was already on screen.
- A fake percentage on work whose total nobody knows; a bar that keeps moving after the process died.
- A blocking spinner on a 3-minute job with no notification and no state preservation.
- Onboarding progress that starts at 0% on a flow already underway.
- Validation errors that redraw the field under a fast typist.
- A visible countdown that outlasts its own estimate.
- Artificial pacing added to make a fast operation feel "substantial".

## Review checklist

- [ ] Every tap, key and drag responds within ~0.1 s
- [ ] In-thought interactions target ~400 ms; nothing exceeds ~2 s without closure or feedback
- [ ] Page turns, scrolling and scanning stay under ~1 s perceived
- [ ] Every accepted command shows heard / accepted / understood / working
- [ ] Long operations show progress — determinate if computable, indeterminate if not
- [ ] Multi-step operations show step-level and overall progress, and never start at 0%
- [ ] Indicators reflect real state; stalls and failures are detectable
- [ ] Operations beyond ~15 s run in the background, notify on completion, and are leaveable
- [ ] Time remaining shown only where estimable
- [ ] Failures state the cause, the retry path, the expected recovery time, and restore state
- [ ] Error notices land at natural pauses, not mid-entry
- [ ] Response-time specs carry nominal values, tolerances and response types
- [ ] Thresholds validated against real tasks on real devices

## Caveats

- **The 400 ms figure is popularised, not isolated.** The 1982 IBM brief's own data emphasises *sub-second* response and reports points at 0.25, 0.3, 0.5, 0.6 and 1.0 s; the specific "400 ms" and the "addicting" language come from summary/popularising sources. Treat it as a widely cited target, not a settled law.
- **Miller's numbers are estimates, and the tolerance data are laboratory/indirect.** He calls his 17 per-topic values his "best calculated guesses", to be verified in extended studies; the categories are not exhaustive, permissible ranges of variation are uncited for most values, and one topic (dynamic-model manipulation) offers **no estimates at all** — "not even guesses". His time-perception tolerances come from careful stimuli with full attention and may be exceeded substantially in real tasks. Do not present per-topic tolerances as validated.
- **"Later Research Signals" are explicitly low confidence** — ResearchGate citation snippets, unverified. That includes the Nielsen 10-second attention bound, the agentic/VR/LLM latency snippets and the declining-rate progress-bar result. Treat as pointers, not evidence.
- **Unresolved conflicts, recorded not decided:** progress bars "regardless of accuracy" vs. the indicator's role as a crash signal and approximate completion estimate; "purposeful delay increases perceived value and trust" (labelled unsupported, and against Miller's continuity/morale rules); constant vs. variable timing (prior findings vs. Myers pr = 0.2046 — non-significance is *not* equivalence).
- **Small, dated evidence.** Myers: 48 subjects, mostly CS graduate students, waits of 10 s constant or 1–17 s variable, ~40 minutes each, first-version order effect pr = 0.0025. All field data are 1960s–80s mainframe and terminal systems, so directional findings travel but exact thresholds need re-validating for mobile and web.
- **No elapsed-time trigger for percent-done or for backgrounding work is stated in this reference.** It ties percent-done to computable duration, and its free-the-user rule starts at 15 s. Widely quoted Nielsen-style thresholds (percentage at ~60 s, background-and-notify at ~1 hr) are **not** in this source — do not attribute them to it.
- **Goal-gradient (RT-13) is a design heuristic here**; the frequently repeated claim that time-remaining displays increase stress is *not* stated in this reference — treat that as judgement, not finding.
- Three different Millers appear in this literature (George 1956, Robert 1968, Lawrence 1977); sources alternate Thadhani/Thadani; the raw PDFs contain OCR errors.
- Conflicts and evidence limits are recorded above. Check them before defending a rule in review.