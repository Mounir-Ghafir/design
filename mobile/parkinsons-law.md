---
name: parkinsons-law
title: Parkinson's Law — Design Rules
description: Rules for capping how long a task may take so it cannot inflate to fill the time available. Load when building checkout, booking, signup or any timed flow, when adding a step or a field, when setting a duration or delivery promise, or when a form feels slower than users expect.
applies_when: [checkout, booking, signup, forms and flows, task duration, deadlines, scope control, reducing steps]
priority: supporting
rules: 7
source_status: paywalled-truncated
---

# Parkinson's Law — Design Rules

## Core principle

Any task will inflate until all of the available time is spent.

```
inflation = available time you hand the task − time the task actually needs
```

## Rules

### PL-01 · Cap the task at what users expect
rule: Limit the time a task takes to complete to what users expect it will take.
do: Take the expected duration as the target, then hold every part of the flow to that number.
never: Ship a flow slower than the duration users already assume.
because: Takeaway 1 of the source. The expectation is the budget, not a ceiling to exceed.

### PL-02 · Underrunning the expectation is the win
rule: Reduce the actual duration to below the expected duration.
do: Cut latency, fields and clicks until real completion time lands under the expected one.
never: Reinvest the saved seconds as licence to add a step, a field, or an upsell.
because: Takeaway 2 of the source. Since work expands to fill time available, removing available time is the only reliable brake.

### PL-03 · Autofill the critical fields
rule: Use features such as autofill to save user time when collecting critical information in forms.
do: Pre-fill known values, offer completions, and keep purchases, bookings and similar functions quick to finish.
never: Show an empty field the system already knows the value of.
because: Takeaway 3 of the source. Each remaining keystroke is time left for the task to inflate into.

### PL-04 · Re-entry is inflation you authored
rule: Never make the user supply the same information twice.
do: Carry values across steps, screens and sessions; re-display them for confirmation instead of re-typing.
never: Re-ask for a name, address, card or account detail already given in this flow.
because: INFERENCE. Mapped from the source's "Officials make work for each other" — no UI data in the source supports it.

### PL-05 · Needless fields, steps and dialogs are where inflation lands
rule: Ship no field, step, option or dialog the user did not ask for.
do: Default every optional choice; collapse secondary inputs behind an explicit reveal; inline confirmations.
never: Present a blank optional input on the critical path, or gate an unambiguous primary action behind a modal.
because: INFERENCE. The source's inflation claim is about staff and committee work, not about form fields or dialogs.

### PL-06 · Publish the deadline, then hold it
rule: State the duration you expect a task to take and treat it as a hard budget.
do: Apply deliberate time pressure — the source notes last-minute work yields far more in that hour than usual.
never: Quote a duration the flow was not built to meet, then add work to it.
because: Constraints are the source article's own thesis: "Why Constraints Are The Best Thing You Can Work With".

### PL-07 · Set the budget before the design exists
rule: Fix the duration and the field list before building, not after.
do: Write the target duration into the spec, then review every addition against it.
never: Let scope grow once the budget has been committed.
because: Staff grew 5–7% per year "irrespective of any variation in the amount of work (if any) to be done" — growth does not check the budget.

## Hard numbers

| Constant | Value | Note |
|---|---|---|
| Organisational finding | Staff rose **5–7% per year** | "irrespective of any variation in the amount of work (if any) to be done" |
| Committee size | Inefficient above "between 19.9 and 22.4"; optimal between **three** and **20** | Source's conjecture, marked `[citation needed]` |
| UI time budget, effect size, sample size | **unknown: true** | Nothing measured anywhere in the source |

## Decision procedure

1. **Expectation** — establish what duration users already assume. That is the budget (PL-01).
2. **Fields** — cross out every input the task does not strictly require; autofill the rest (PL-03, PL-05).
3. **Repeat entry** — remove anything re-asked or re-typed (PL-04).
4. **Steps, dialogs, underrun** — count taps, inline confirmations, delete modals; cut until actual time is below expected time, then refuse to reinvest the difference (PL-02, PL-05).

## Anti-patterns

- A flow that ships slower than its own stated duration.
- An empty field the system could fill, or a modal on an unambiguous primary action.
- Scope added after the time budget was quoted.

## Review checklist

- [ ] Target duration written down and derived from user expectation
- [ ] Every field is autofilled or strictly required by the task; no value re-entered
- [ ] Steps and dialogs counted; measured duration below the expected duration
- [ ] No step added since the duration was quoted

## Caveats

- **The source is paywalled and truncated.** Louis Chew, "Parkinson's Law: Why Constraints Are The Best Thing You Can Work With", 4 min read, May 13, 2017. The body stops at "Create an account to read the full story." (source line 33), directly after the bullet "Doing work at the last minute makes you more productive…" under the heading "The Long Arm Of The Law". Whatever the article argued after that point is unavailable and has not been reconstructed. Source lines 35–100 are an appended Wikipedia entry on the 1955 essay, not the article itself.
- **Nothing here is measured.** No effect sizes, no sample sizes, no observed UI completion times → `unknown: true`. The original is also not a law about human task duration: it is an organisational-behaviour observation about British civil-service clerical work — headcount, minutes, memoranda, committees.
- **The UX application is an inference the source makes.** Moving from "work fills its allotted time" to "users finish forms faster than expected" is asserted, not measured. PL-04 and PL-05 are my mapping of the organisational claim onto interface elements, flagged as inference in each block.
- The 1955 essay's main subject is the *organisational* finding (public-administration headcount grows regardless of work); the time-expansion line appears there only as a "commonplace observation", and its 1955 personal wording includes "so as to" where Chew's article prints it without. The source's Stock-Sanford, Asimov and "Data expands to fill the space available for storage" corollaries are explicitly facetious and concern deadline pressure and storage; only the time-pressure idea is used (PL-06).
- Historical figures in the source, recorded so they are not lost despite carrying no interface meaning: Council of the Crown 29, rising to 50 before 1600; Lords of the King's Council (1257) fewer than 10, growing to 172 and then ceasing to meet; Privy Council fewer than 10, rising to 47 in 1679; Cabinet Council 1715 at eight members, rising to 20 by 1725; Cabinet ~1740 at five members, 23 in 1939, 18 in 1954, 27 in 2025. The source states eight "is not supported by observation" — no cabinet in its dataset had that size.
- Cross-links: `cognitive-load.md` CL-05 covers offloading memory via defaults and autofill; `response-time-progress-feedback.md` covers setting time budgets. Neither was used as a source here.