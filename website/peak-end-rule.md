---
name: peak-end-rule
title: Peak-End Rule — Design Rules
description: Rules for shaping how an experience is *remembered*, by engineering its peak and its ending instead of its average. A psychology concept the source calls closely related to Cognitive Bias. Load when designing or reviewing the peak or ending of a journey, completion and confirmation screens, error and outage states, progress indicators, publish/send moments, waits and queues, customer-service interactions, or deciding how to measure satisfaction.
applies_when: [journey mapping, completion and confirmation, error and outage states, progress indicators, onboarding and first-run, customer service, waits and queues, pricing and promotions, satisfaction measurement, ux review]
priority: supporting
rules: 20
---

# Peak-End Rule — Design Rules

## Core principle

People judge an experience largely by how they felt at its **peak** and at its **end** — not by the sum or average of every moment in between. Memories are snapshots, and the recall is a biased, incomplete record. Optimise remembered quality, not experienced quality — including what people go on to *tell other people*.

```
peak = the most affectively intense moment  ─┐
end  = the feeling in the final moments      ─┴─→ averaged → remembered quality
duration of everything between them          →  barely registers ("duration neglect")
```

## Rules

### PER-01 · Judge the journey by its peak and end
rule: Evaluate a design by its most intense moment and its final moments, not by its average or total quality.
do: Score every journey on two points only — worst/best moment, and the last thing that happens.
never: Accept "it's fine on average" as evidence the experience works.
because: The peak and the end are averaged in memory and dominate the verdict; the rest is retained but not used.

### PER-02 · Locate the two moments before you design anything
rule: Name the peak and the end explicitly for each journey before making decisions.
do: Walk the timeline and write down the single most intense point and the literal last screen/step.
never: Start design work on a flow whose ending you have not decided.
because: You cannot optimise a moment you have not identified.

### PER-03 · Find where your product is most valuable
rule: Identify the moments when your product is most helpful, valuable, or entertaining — that is where your peak already lives.
do: Ask what emotional payoffs exist in a normal session: does it answer a hard question, remove a tedious step, cost less, or simply amuse?
never: Assume the peak is the paywall, the upsell, or the most-used feature.
because: The most valuable moment is the one already capable of carrying the memory.

### PER-04 · Make the peak positive on purpose
rule: Engineer a strong positive peak rather than hoping one occurs.
do: Add meaningful interaction, good news, a reward, or a moment of competence at the emotional high point.
never: Let the most intense moment of the journey be an accidental one.
because: Whatever is most intense defines the memory — positive or negative.

### PER-05 · Spend disproportionate effort on the end
rule: Give the ending more design effort than the ending's share of screen time or duration.
do: Budget the most polish per pixel for the final screen: illustration, motion, tone, microcopy.
never: Treat the last screen as an afterthought because the task is already "done".
because: Retrospective evaluation is dominated by the feeling at the end.

### PER-06 · Make the end feel finished
rule: The ending must acknowledge, confirm, and close.
do: Confirm what was accomplished, name the result, thank the user, and stop (Duolingo, TurboTax, Mailchimp's post-send confirmation).
never: End on a form field, a spinner, a bare status line, or a bare "Done".
because: The last impression is the lasting impression; an unresolved end reads as a failure state.

### PER-07 · Do not hold the user past the end
rule: Let the journey terminate. Do not extend it with hooks, upsells, or exit traps.
do: Offer an explicit next step and a clear way out, then release the user.
never: Fire an exit-intent discount pop-up or "please don't go" interruption.
because: Exit traps convert a positive ending into a memorable irritation.

### PER-08 · Assume a negative peak outweighs a good end
rule: Weight the removal of a bad moment at least as heavily as the addition of a good one.
do: Prioritise eliminating confusion, frustration, and error states over adding delight, given equal effort.
never: Use a strong ending to justify a rough middle.
because: People recall negative experiences more vividly than positive ones — the negativity bias.

### PER-09 · Remove the friction that creates the peak
rule: The negative peak is usually a known, cheap-to-remove defect.
do: Kill hover-closes, moving targets, hidden menus, forced repopulation of forms, and multi-level navigation (see CL-07, CL-14, CL-17).
never: Let a user-escape-the-menu problem persist "because the ending is good".
because: One frustrating peak recolours the whole product — including the brand.

### PER-10 · Never add pain to improve a memory
rule: Do not lengthen, complicate, or degrade an experience for the sake of a better remembered ending.
do: If a gentler ending requires extra pain, reduce the pain instead.
never: Add a step, delay, or error so the resolution feels earned.
because: Patients would not accept extra pain purely to improve a future memory; your users won't either.

### PER-11 · Let discomfort fade gradually
rule: When an unpleasant phase is unavoidable, taper it rather than cutting it off.
do: Take the peak intensity down in steps toward the end; end a hard effort by dropping to lower intensity.
never: End a hard session at full intensity.
because: Gradual relief is remembered more positively than abrupt relief — and it is safer.

### PER-12 · Accelerate progress into the finish
rule: Let a progress indicator speed up toward the end.
do: Weight remaining progress so the bar visibly accelerates as the task completes.
never: Keep progress linear and flat all the way to 100%.
because: An accelerating indicator makes the process judge as faster than an identical constant-speed one.

### PER-13 · Unmet expectations cost more than slow service
rule: A satisfied ending discounted by a broken expectation still reads as a bad experience.
do: Under-promise and over-deliver; never let the estimated wait, delivery, or duration be missed at the end.
never: Let the final moments contradict the estimate you set at the start.
because: Real-time experience that fails expectations is discounted after the fact.

### PER-14 · Design the ending for errors and outages
rule: Outages and dead ends are ends too, and unexpected ones are strongly memorised.
do: Explain what happened, give a realistic estimate of resolution, and never blame the user.
never: Show an error that demands urgent action the user cannot take (e.g. "unavailable — try again later" styled as critical).

### PER-15 · Average quality is a poor predictor of remembered quality
rule: Do not use average satisfaction or mean step time as the target metric.
do: Measure the ending and the peak: final-step completion, end-of-session sentiment, post-task recall.
never: Optimise a mean score while the end is broken.
because: Duration has essentially no effect on retrospective ratings — duration neglect.

### PER-16 · A weak ending is not fixed by adding more
rule: Adding a mildly pleasant extra at the end can *reduce* remembered satisfaction.
do: Delete trailing low-value content rather than stacking a bonus onto it.
never: Append a "and one more thing!" to a good experience.
because: Recipients who got one highly-rated item liked it more than those who got it plus a worse one; same result with a chocolate bar vs bar + bubble gum.

### PER-17 · Only journeys with a definite end are covered
rule: The rule applies only where the experience has a definite beginning and end.
do: Identify the closing boundary explicitly for flow-based journeys (checkout, filing, publish, wait, support contact).
never: Expect peak-end reasoning to predict ongoing, looping, or habitual use (inboxes, feeds, daily actives).
because: Without an end there is no end to weight — and day-long experiences are reported not to follow the rule.

### PER-18 · Ask retrospectively, not live
rule: Test the memory, not the moment.
do: After the session, ask how the experience was overall and which part stands out; also ask about the ending's shape.
never: Validate a weak ending using in-the-moment satisfaction ratings.

### PER-19 · Expect the peak to fade and the end to over-weight
rule: Assume the peak's influence decays and the ending's grows over time.
do: Re-check long-lived journeys (onboarding, subscription life) after weeks, not just in session.
never: Treat a session-1 measurement as permanent.
because: Peak effects fade faster than end effects, and episodic memory shifts toward semantic memory.

### PER-20 · Treat ending manipulation as an ethics call
rule: Deliberately distorting the end to flatter the memory is a product decision, not a design detail.
do: Ask what the user would think if they saw the mechanism; ship it only if the answer is "that's fair".
never: Use inflated estimates, manufactured relief, or celebratory screens that misstate what happened.
because: The rule is also described as a bias businesses use to "shape, and sometimes manipulate" — Disney's boards at all 12 parks show a 45 min wait as 50, then land 5 min under; AI at scale amplifies that risk.

## Hard numbers

| Constant | Value | Note |
|---|---|---|
| 1993 cold-pressor trials | **14 °C for 60 s** vs **14 °C for 60 s + 30 s warmed to 15 °C** | Kahneman, Fredrickson, Schreiber & Redelmeier, "When More Pain Is Preferred to Less: Adding a Better End", *Psychological Science* 4(6), 401–405 |
| Preference for the longer trial | **80%** of participants chose the 90 s version | Reported in a secondary write-up of the 1993 study; figures (57 °F / 59 °F) as given there |
| Colonoscopy extension | Scope left in place **3 extra minutes**, not moved, no inflation or suction | Kahneman, Redelmeier & Katz; long-procedure group rated it less unpleasant and was more likely to return |
| Sample sizes, effect sizes, means, significance | unknown: true | Not stated anywhere in the source — studies report direction only |
| Duration effect | "**no effect whatsoever** on the ratings of total pain"; elsewhere "**extremely slight**" | Duration neglect, per Kahneman 2012 p. 380 as quoted |
| Peak vs end share of remembered quality | unknown: true | Source defines recall as the *average* of the most intense moment and the feeling at the end — it reports **no percentage split**, and no 70% figure |
| Procedure-length example | Same procedure, **8 min vs 24 min**; the shorter was rated worse | Kahneman (2012) as recounted in the source |
| Pizza buffet study | **$4** vs **$8**: $4 → peak and last slice predict rating; $8 → first slice does | Price moderates the rule |
| Uber Express POOL cancellations | Direction only (rate reduced) — **no percentage given** | unknown: true |
| Reference price model | Weighted average of the **highest observed price** and the **most recent price** | Judged the most plausible of four reference-price models |
| Counter-evidence | **40 students**, VR film, extended peak scene → **no** effect | Digital/VR transfer not confirmed |

## Decision procedure

1. **Bounds** — does it have a definite start and end? If not, stop; this rule does not apply (PER-17).
2. **Map** — list phases, actions, and where emotion spikes on the journey-map emotional line.
3. **Peak** — name the most intense moment. Is it positive? If it is a known friction defect, remove it (PER-09).
4. **End** — name the literal last step. Does it confirm, celebrate, and release (PER-06, PER-07)? Does the final phase taper rather than stop abruptly, and does any progress indicator accelerate (PER-11, PER-12)?
5. **Fail paths** — design the outage, error, and abandon endings as deliberately as the happy one (PER-14).
6. **Measure** — replace average scores with retrospective and end-of-journey measures (PER-15, PER-18).

## Anti-patterns

- Optimising mean satisfaction while the ending is broken.
- Adding a trailing "one more thing" to a good flow.
- Exit-intent discount pop-ups on a positive ending.
- Using a warm sign-off to paper over a confusing session.
- Extending a journey with an experience that is painful for a better memory.
- Error states that demand urgent action the user cannot take.
- Measuring only step 1, and never revisiting the journey weeks later.
- Applying peak-end reasoning to an always-on product with no end.

## Review checklist

- [ ] Journey has a defined beginning and end
- [ ] Peak moment identified, positive, and amplified where the product is most valuable
- [ ] End confirms, acknowledges, and releases
- [ ] No upsell or exit trap after the end
- [ ] Final phase tapers; no abrupt full-intensity finish; progress accelerates toward completion
- [ ] Estimates and expectations not broken at the end
- [ ] Error, outage, and abandon endings designed, not defaulted
- [ ] No known friction defect left as a live negative peak
- [ ] No extra pain or delay added purely to flatter the memory
- [ ] Success measured retrospectively, not by averages

## Caveats

- The foundational evidence is **laboratory pain and cold-water immersion** plus retrospective ratings of clinical procedures. Its application to product UX is an **inference** drawn by the source's authors, not a tested result.
- The source reports **no sample sizes, effect sizes, means, or significance tests** for any study it summarises, and the "80%" figure appears in a secondary summary rather than the 1993 paper. The **peak-vs-end contribution percentage is not reported anywhere** — the rule is described only as an average of the two.
- The accelerating-progress-indicator finding is cited to "the HCI literature" with **no specific study** in the source; treat it as unattributed.
- The source's own **counter-evidence** should temper confidence: a 40-student VR study found no peak-end effect, and retrospective evaluations of day-long experiences (e.g. hotel stays) are reported **not** to follow the rule.
- Applicability is **conditional**: it holds when an experience has definite beginning and end periods, and is moderated by price (restaurants), self-restraint (eating), expectations, and recall goals.
- The rule is **contested** — described as "not an outstandingly good predictor" by one study in the source, and peak influence is said to fade over time. The claim that memory later shifts to over-weighting the end is flagged as needing citation *in the source itself*.
- The source frames this as a **cognitive bias closely related to Cognitive Bias** generally, and notes the rule is deliberately leveraged to "shape, and sometimes manipulate" experience. See `cognitive-bias.md` for the practitioner-side discipline; over-reliance on AI systems can amplify these biases at scale.
- `response-time-progress-feedback.md` covers perceived performance *during* waits and loads; this file governs how the wait is *remembered*. The end-of-journey rules (PER-05, PER-06, PER-11, PER-12, PER-14) overlap with completion and confirmation-screen design.
