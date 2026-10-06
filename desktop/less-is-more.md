---
name: less-is-more
title: Less Is More — And When It Fails
description: Rules for deciding when concise code and minimal UI are the right answer, and when to pay for more complexity. Load when choosing an algorithm, defending extra code in review, stripping or simplifying a UI, cutting features, or slimming process.
applies_when: [algorithm choice, performance trade-offs, code review, simplification, ui minimalism, feature cuts, process design, tech stack]
priority: supporting
rules: 16
---

# Less Is More — And When It Fails

## Core principle

Conciseness and minimalism are defaults, not laws. Buy complexity only when a stated requirement — performance, scale, task completion — pays for it. Never go minimal at the user's expense.

```
simple by default      → clarity, fewer bugs, lower maintenance, faster load, less cognitive load
complexity when earned → a named requirement: speed, scale, guaranteed bounds
never minimal here     → necessary information, feedback, accessibility, task completion
```

## Rules

### LIM-01 · Simplicity is the default, not the goal
rule: Ship the simplest implementation that meets the requirement; complexity must be bought with a named reason.
do: Start plain; write the requirement (latency, dataset size, traffic) down before adding code.
never: Add cleverness speculatively "for scale later".
because: Simpler software is easier to understand, maintain and extend, has fewer bugs, costs less, and needs less processing power. That is why it is the default — not proof it always wins.

### LIM-02 · Buy complexity when performance demands it
rule: Accept more code when a verbose algorithm materially beats a simple one.
do: Choose divide-and-conquer (partition, then recurse) over repeatedly rescanning the whole collection when inputs are large.
never: Defend the shortest implementation when it is also the slow one.
because: The source's C comparison: Bubble Sort is under 15 lines yet does ~100 million comparisons and swaps on 10,000 elements; QuickSort is over 30 lines yet does ~100,000 operations — about 1,000 times fewer.

### LIM-03 · Gate the trade-off on input scale
rule: Prefer the simple algorithm for small inputs; let complexity earn its place on large ones.
do: Keep the straightforward version below 100 elements, where the source calls performance differences negligible; justify complexity for systems processing millions of records.
never: Rewrite a hot path that only ever handles tiny inputs.

### LIM-04 · Judge by growth rate, not line count
rule: Evaluate code by how its work grows, not by how long it reads.
do: Reject O(n²) approaches for large datasets in favour of average-case O(n log n) where the source states it.
never: Keep nested full-array scans because they read clearly.
because: At 10,000 elements the gap the source reports is ~100 million operations versus ~100,000 — a per-line judgement would choose wrong every time.

### LIM-05 · Every extra line must encode an optimization
rule: Complexity buys only measurable wins — fewer comparisons, a guaranteed bound, cached work.
do: Name the win behind each added construct: recursive partitioning, median-of-three pivot selection, LRU eviction, red-black trees' guaranteed logarithmic complexity.
never: Add abstraction or indirection that no execution path exercises.

### LIM-06 · Pay the defect tax that clever code owes
rule: The more intricate the implementation, the more explicitly you must test and defend it.
do: Check off-by-one boundaries, switch recursion to iteration for small subarrays, and guard worst-case O(n²) with randomized pivot selection; prefer proven hybrids such as C's qsort.
never: Ship recursive pointer code without considering off-by-one mistakes or stack overflows.

### LIM-07 · Fix the root cause, don't layer over it
rule: Attack the slow thing itself before adding a covering layer.
do: Optimise the slow SQL query instead of standing up a caching layer; prefer fewer components — the source's claim is that fewer parts make the system less fragile.
never: Cover a slow path with a cache and inherit its edge cases and unpredictable behaviour.

### LIM-08 · Keep stack, process, and feature set minimal
rule: Minimise infrastructure, process, and feature count, not just lines.
do: Fit the development process on a single A4 page or into an elevator pitch; drop features whose upkeep exceeds their value (the source dropped an optional paywall over weekly invoice and support hours).
never: Add a policy, rule, or process for every problem — Nygard's "grandiosity" quickly loses touch with reality and bottlenecks the teams doing the work.

### LIM-09 · Keep only content that helps the task
rule: Show only the essential part of the feature; make every element deliberate and useful.
do: Remove elements that do not help the user perform the task — extra text, unnecessary animation, decorative effects.
never: Ship content that is present only because it was easy to add.

### LIM-10 · Cut choices, not tasks
rule: Hick's Law — decision time rises with the number and complexity of choices.
do: Reduce the functions offered on a page so users are not overwhelmed into abandoning the task; remove redundant steps.
never: Present every variant simultaneously "to be safe".
because: Too many options overwhelm a user into quitting the task they were attempting; fewer choices and fewer steps are also cheaper to keep.

### LIM-11 · Let space, contrast, and typography do the work
rule: Replace ornament with emphasis.
do: Use negative space to highlight content, high contrast to pull attention to the main element, bold typography to emphasise it, and a limited, uniform colour palette; keep fonts and icons to a minimum (flat design).
never: Add decoration where emphasis is needed.

### LIM-12 · Order content by importance
rule: Distribution is hierarchical — most important at the top, less important at the bottom.
do: Focus the page on its main element, cut excessive text, and keep navigation simple and convenient.
never: Bury the primary action beneath secondary content.

### LIM-13 · Ship only functional animation
rule: Animation and imagery must serve a function, not a mood.
do: Keep photos and illustrations uncrowded — the source warns a crowded illustration reverses the design's effect.
never: Add animation for its own sake.

### LIM-14 · Never hide necessary information
rule: Minimalism must not make required things hard to find.
do: Run the first-time-user test: can a new user complete their primary tasks with no guidance?
never: Make users hunt for navigation, search, contact, or settings behind a clean visual veneer — that is confusion, not minimalism.

### LIM-15 · Never cut feedback or accessibility for looks
rule: Removing feedback is not minimalism; failing accessibility is not design.
do: Keep confirmations, state changes, loading states, and error messages — precisely the feedback users need; meet WCAG contrast requirements.
never: Use low-contrast grey text on white for elegance, or ship a submit button that gives no confirmation.

### LIM-16 · Removal is the harder direction
rule: Removing an element while preserving task completion requires deeper understanding than adding one.
do: Validate that the task still works after every cut; treat minimalism as a functional test, not an aesthetic pose.
never: Strip features, hints, or labels to make a mock-up look clean.

## Hard numbers

| Item | Source figure (verbatim) |
|---|---|
| Bubble Sort | typically less than 15 lines; worst-case and average time complexity O(n²); at 10,000 elements, approximately 100 million comparisons and swaps |
| QuickSort | more than 30 lines; average-case time complexity O(n log n); at 10,000 elements, on the order of 100,000 operations — about 1,000 times fewer than Bubble Sort; worst-case O(n²), mitigated through randomized pivot selection; logarithmic depth of recursion |
| Small-input cutoff | fewer than 100 elements — performance differences are negligible |
| Large-input justification | systems processing millions of records |
| Red-black trees | operations with guaranteed logarithmic complexity |
| Measured performance data | unknown: true — neither main article reports timings, benchmarks, sample sizes, or effect sizes |

A third fragment in the scrape claims: Forrester — a well-designed UI can raise conversion by up to 200 percent, better UX by up to 400 percent; Google Core Web Vitals — pages loading under two seconds have bounce rates approximately 9 percent lower than five seconds; Baymard — the average e-commerce site could improve conversion by 35 percent through better checkout design alone. No sample sizes, effect sizes, or study parameters are given for any of these.

## Decision procedure

1. **Requirement** — is there a stated performance, scale, or task-completion requirement? If none, stop at simple (LIM-01).
2. **Growth** — estimate input size and check how the simple version scales (LIM-04).
3. **Price** — write down what each extra line buys (LIM-05) and what it costs in defects and upkeep (LIM-06, LIM-08).
4. **Root cause** — fix the underlying slow or complex thing rather than layering over it (LIM-07).
5. **UI cut test** — remove only what does not serve the task (LIM-09–LIM-13), then run the first-time-user test (LIM-14).
6. **Floor** — never remove necessary information, feedback, or accessibility (LIM-14, LIM-15).

## Anti-patterns

- Nested full-array scans over large data because the code "reads clearly".
- Rewriting a path whose inputs never exceed 100 elements.
- Abstraction layers no execution path exercises.
- A caching layer hiding a query that should have been optimised.
- A new policy or process for every problem encountered.
- Hiding navigation or labels to make a screen look clean.
- Low-contrast grey text chosen for elegance.
- Animation or ornament with no state to communicate.

## Review checklist

- [ ] Simple version first; a named requirement justifies any added complexity
- [ ] Growth rate checked against expected input size
- [ ] Each extra line maps to a stated optimization
- [ ] Defect risks of the clever parts tested (off-by-one, recursion depth, worst case)
- [ ] Root cause fixed, not covered by a new layer
- [ ] Stack, process, and feature count still minimal
- [ ] Every UI element helps the user perform the task
- [ ] Content ordered by importance; choices and steps reduced
- [ ] Feedback, labels, and WCAG contrast intact
- [ ] First-time users can find everything and finish unaided

## Caveats

- Two unrelated articles by different authors: **A** (software engineering — the "paradox" QuickSort piece plus the minimal-platform/process piece) supplies LIM-01–LIM-08; **B** (Key Lime Interactive, "Minimalism and a UX Design Strategy") supplies LIM-09–LIM-13. The scrape also carries further unrelated fragments (an agency marketing post, two short listicles, a slow-design post); LIM-14–LIM-16 come from the agency fragment — the rest were dropped.
- Measured performance data: **Article A gives only theoretical/complexity analysis plus asserted operation counts** — no benchmark method, timings, sample sizes, or effect sizes: unknown: true. **Article B gives no measured data at all** (it references Hick's Law without parameters): unknown: true.
- Sibling coverage: `clean-code.md` handles naming and readability; `occams-razor.md` handles removing UI elements; `cognitive-load.md` CL-02/CL-03 cover delete-before-you-optimise and the "simplicity must not cost clarity" caveat. This file's distinct contribution is the counter to naive minimalism — complexity that is earned, and minimalism that fails.
