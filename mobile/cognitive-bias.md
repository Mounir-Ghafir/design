---
name: cognitive-bias
title: Cognitive Bias — Design Rules
description: Rules for spotting cognitive bias in the interfaces you build and in your own design decisions. Load when writing research findings, choosing a default, setting prices or tiers, framing a result, designing onboarding or progress, writing persuasive UI, or mediating a decision made from one number.
applies_when: [research reporting, decision framing, defaults and settings, pricing and tiers, onboarding and progress, persuasive UI, team critique, ux review]
priority: supporting
rules: 14
---

# Cognitive Bias — Design Rules

## Core principle

Biases are the predictable by-product of mental shortcuts. A shortcut is not automatically a defect — whether one is an error or an adaptive rule depends on the environment, and that argument is open. Shape the user's environment so the right shortcut is the easy one, and audit your own.

User side → design the environment (frames, defaults, anchors, exit paths). Practitioner side → impose structure (criteria, counts, disconfirmation, an opponent).

A **cognitive bias** is an error in thought processing; a **logical fallacy** is an error in argument structure. Users commit the first; reviewers argue the second.

## Rules

### BI-01 · Assume the designer is biased too
rule: Practitioners misread research, choose between alternatives, and argue in teams with the same shortcuts as users.
do: Write the decision criterion before reading the findings; get a non-owner to attack the direction.
never: Count your own preference, or your attachment to a solution you built, as evidence.
because: Biases are far easier to see in others than in yourself — the bias blind spot.

### BI-02 · Fix the criterion and the metric first
rule: Decide what would count as success, and which number you will read, before you collect anything.
do: Store the metric, threshold, and comparison condition with the research plan.
never: Choose the metric after the sessions are over.
because: A criterion written after the data is anchored to it.

### BI-03 · Report both frames, plus counts
rule: State every finding as success and as failure, with the raw number of people.
do: "16 of 20 found search; 4 of 20 did not" — plus the absolute number affected, never a rate alone.
never: Present the flattering frame and omit the sample size.
because: Identical facts framed oppositely gave 51% vs 39% support for a redesign (NN/g) — one experiment, not an established effect.

### BI-04 · Make someone argue the opposite frame
rule: The inverse frame gets stated out loud before the decision closes.
do: Flip success ↔ failure, price up ↔ price down, current users ↔ potential users; widen any narrowly-worded question.
never: Close a decision that has only ever been argued one way.
because: Narrow frames hide whole classes of benefit and cost.

### BI-05 · Small samples get counts and ranges
rule: Percentages from small samples manufacture precision and false debate.
do: Report counts, sample size, and a range; test significance before calling a difference real.
never: Turn 16/20 into "an 80% success rate" and carry it to a roadmap decision.
because: The source's own caution: at 16/20 the true rate may lie anywhere between 58% and 93% (95% CI).

### BI-06 · One vivid story is not a signal
rule: A single memorable failure outweighs a hundred ordinary successes in everyone's head.
do: Triangulate anecdotes with frequency and analytics; hunt the disconfirming case on purpose.
never: Redesign around one review, screenshot, or angry ticket; never file a readout of only confirming quotes.

### BI-07 · Defaults are decisions
rule: Status-quo bias makes the preselected option win more often than it deserves.
do: Make every default visible, changeable, and written from the user's side; name what it does.
never: Ship a default chosen for the business with no explanation.
because: Users keep the current state to avoid risk and loss — a default *is* the status quo.

### BI-08 · Set anchors and order deliberately
rule: The first number shown becomes the reference point; the way options are grouped or sequenced changes the choice.
do: Order tiers so the intended plan anchors sensibly; test alternatives together for comparison and apart for exploration.
never: Use a reference figure you would not defend if asked where it came from.
because: Adjustment from a starting value is incomplete, and grouping changes outcomes (distinction bias).

### BI-09 · Make every contrast honest
rule: Endowment, price relativity, and decoy effects only work when the alternatives are real.
do: Let users build or customise something before asking them to commit; keep a genuine mid-tier against the top tier.
never: Manufacture a decoy, an inflated "was" price, or a fake countdown.
because: Ownership raises perceived value — which is a fact about the designer's offer, not a fact about the user.

### BI-10 · Keep the exit cheap
rule: Loss aversion and sunk cost press users to stay inside something that no longer serves them.
do: Keep cancel, downgrade, delete, and data export obvious, cheap, and reversible.
never: Make getting a user's own data out harder than signing up.
because: Losses loom larger than equivalent gains, and past investment is not a reason to invest more.

### BI-11 · Complete the arc
rule: Effort rises as the finish nears, and memory keeps the peak and the ending — not the average.
do: Show remaining steps and progress; make the last step the easiest; rescue the worst moment in the flow.
never: End the flow on an upsell, a survey, or an error.

### BI-12 · Never judge usability by your own reaction
rule: You cannot un-know the product, and a handsome screen feels usable whatever its defects.
do: Run first-use tasks with people who have never seen it; judge completion and recovery, not your own ease.
never: Approve a UI because it felt obvious when you clicked through it.
because: Halo effect and the curse of knowledge inflate perceived usability — separate looks from function in every test.

### BI-13 · Users satisfice — and their shortcut may be right
rule: People take the first adequate option, use things the way they know, and quit after repeated failure.
do: Make the good-enough option genuinely good; surface capabilities where they are needed; fix the first failure point.
never: Design for exploration, optimisation, or persistence the task does not require.
because: Satisficing, functional fixedness, and learned helplessness cap what an interface can ask.

### BI-14 · Structure beats intention
rule: Checklists, accountability, and incentives move decisions; awareness and training do not.
do: Attach criteria to the review, name who decided, assign a devil's advocate, use an outside-view (reference-class) comparison.
never: Expect a workshop, a one-shot video, or averaging more opinions to cancel a bias out.
because: Biases are systematic, so crowd-averaging does not remove them; training effects are partial (29% reported, one source).

## Hard numbers

| Figure | Value | Note |
|---|---|---|
| NN/g framing experiment | 51% vs 39% support redesign | ~1,000 practitioners, p<0.0001; **single unreplicated experiment** — see Caveats |
| Small-sample range, 16/20 | 58%–93% (95% CI) | The source's own caution; applies to every rate you carry forward |
| Debiasing training | 29% reduction (awareness); medium–large to 3 months (videos/games) | Source-reported, not independently verified; partial transfer |

Working catalogue — biases that change a design decision:

| Bias | Effect on users | Design implication |
|---|---|---|
| Anchoring | First number becomes the reference; adjustment is insufficient | Set the anchor honestly; show the real comparison (BI-08) |
| Framing | Identical facts, opposite conclusions | Report both frames; use absolute counts (BI-03) |
| Choice overload | Too many or hard options stall the decision | Confirm preconditions first — see `choice-overload.md` |
| IKEA / endowment effect | What they've built or configured feels more valuable | Try-before-signup, guest mode, ask for the account at the save moment |
| Loss aversion | Losses loom larger than equal gains | Make stakes real and reversible; no fake urgency |
| Sunk cost | Past investment justifies more investment | Cheap exit, cheap migration, easy data export (BI-10) |
| Reciprocity | A free gift creates felt obligation | Give real value first; never buy consent with a token |
| Goal-gradient & Zeigarnik | Effort accelerates near the finish; unfinished tasks stay salient | Show progress and remaining steps; close every loop (BI-11) |
| Confirmation bias | Users seek and discount selectively | Let people filter by their own criteria; never pre-filter away dissent |
| Availability heuristic | Vivid, recent cases dominate | Counter one complaint with rates and frequency data (BI-06) |
| Halo effect | One positive trait colours every judgement | Test function separately from looks (BI-12) |
| Hindsight bias | Afterwards, outcomes seem predictable | Keep pre-mortems pre; don't credit a retrospective with foresight |
| Status-quo / default bias | Current state and preselected option win | Defaults visible, user-serving, changeable (BI-07) |
| Survivorship bias | Only the survivors and the actives are visible | Interview churned and lost users, not just retained ones |
| Representativeness & conjunction | Resemblance drives likelihood; a specific bundle looks more probable than its parts | Show distributions, never bundled-as-more-likely claims |
| WYSIATI | Coherence is substituted for evidence | Validate with behaviour and outcomes, not with how well it reads |
| Overconfidence effect (+ Dunning–Kruger) | Over-trust in own judgement, unrecognised incompetence | Prototype and test before building; never test with the team only |
| Optimism bias / planning fallacy | Own time and risk underestimated; no reference class | Quote ranges from comparable past projects (outside view) |
| Peak-end rule | Memory keeps the peak and the ending | Fix the worst moment and the last screen |
| Decoy & price-contrast effects | An adjacent option reframes the target's value | Only honest comparisons; keep a genuine mid-tier |
| Social proof & authority bias | "Others chose this" / "an expert says so" accepted uncritically | Show real counts and real sources; let users check them |
| Escalation of commitment | More investment to justify earlier investment | Pre-set review checkpoints and kill criteria; require the opposite case |
| Curse of knowledge | You cannot un-know the product | Never send insiders to first-use tests; describe the task, not the UI |
| Satisficing, fixedness & learned helplessness | First adequate option taken; things used one way only; repeated failure stops effort | Make the adequate option genuinely good; fix the first failure point (BI-13) |

## Decision procedure

1. **Frame it** — write the decision question verbatim; list who is inside the frame and who is outside.
2. **Flip it** — restate it as the opposite frame; if the recommendation changes, the frame is deciding, not the evidence.
3. **Criterion** — check what would count as evidence was written before the data existed.
4. **Counts** — absolute numbers, sample size, and the gaps you do not know.
5. **Disconfirm and name the mechanism** — what would have to be true for the other recommendation to be right, and which bias is driving this (default, anchor, frame, loss, availability, or a shortcut that is simply correct here)?
6. **Exit and ethics** — is the user better off, and can they reverse it?

## Anti-patterns

- A small-sample percentage driving a roadmap decision.
- A pre-framed question presented as the only option.
- A default chosen for the business, unexplained.
- A redesign triggered by one vivid complaint.
- Decoy tiers, inflated "was" prices, fake scarcity.
- Export, cancel, or delete buried or made harder than signup.

## Review checklist

- [ ] Decision question written before the data; metric and threshold fixed
- [ ] Finding stated in both frames, with counts and sample size
- [ ] Question restated in reverse or from another viewpoint
- [ ] Disconfirming evidence actively sought; known gaps listed
- [ ] Defaults, anchors, and option order chosen deliberately and explained
- [ ] No manufactured contrast: decoy, false "was" price, fake scarcity
- [ ] Exit paths obvious and reversible
- [ ] Tested with first-time users, not insiders

## Caveats

- **The framing result is not established.** 51% vs 39% (~1,000 practitioners, p<0.0001) is one experiment, on one decision, source-reported, with no replication, meta-analytic, or cross-domain evidence. Treat it as unresolved; the source's own small-sample caution applies to any rate you carry forward.
- **The rationality debate is open.** Defect framing (Kahneman/Tversky) vs ecological rationality (Gigerenzer), with a Haselton & Buss middle position — bias toward the least costly error — and Berthet's critique that much of the literature is vignette-based with low ecological validity. Take no side: validate the effect in your context before treating a shortcut as a defect.
- **Individual training transfers only marginally.** One-shot videos and games reported medium-to-large reductions sustained to three months across six biases; awareness/feedback training reported 29%. All source-reported, not independently verified.
- **The locus of debiasing is unresolved** in the source: individual training and institutional/structural countermeasures are presented side by side. Structural levers are the safe default because the errors are systematic.
- **Speed-critical decisions are not bias.** Where timeliness beats accuracy, the shortcut is doing its job; don't over-correct.
- **Persuasion and manipulation are not separable by technique.** Loss aversion and framing can make a product humane or harmful; judge the pattern, not the mechanism.
- The catalogue is a working subset, not exhaustive, and carries no effect sizes the source does not state.
- Related: `choice-overload.md` (option count), `cognitive-load.md` (working-memory limits).
