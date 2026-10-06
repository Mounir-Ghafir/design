---
name: goal-gradient-effect
title: Goal-Gradient Effect — Design Rules
description: Rules for using perceived proximity to a goal to raise effort and completion. Load when designing onboarding, multi-step flows, progress meters, loyalty or reward programs, streaks and tiers, gamification, checkout and order tracking, activity tracking, or reviewing whether a flow gets abandoned before the end.
applies_when: [onboarding, multi-step flows, progress indicators, loyalty and rewards, streaks and tiers, gamification, checkout and orders, activity tracking, ux review]
priority: supporting
rules: 13
---

# Goal-Gradient Effect — Design Rules

## Core principle

The goal-gradient hypothesis: **the tendency to approach a goal increases with proximity to the goal.**

```
effort ↑     ╭──╮ ← last 100 m, the "mad dash"
            ╱    ╲
start ──────╯──────╯───→ distance to goal
```

Proposed by behaviourist **Clark L. Hull in 1932**. In his 1934 experiment, **rats in a straight alley ran progressively faster** as they moved from the starting box to the food: animals traversing a maze "will move at a progressively more rapid pace as the goal is approached."

Effort is therefore not fixed — it rises as the finish line comes into view. **Move the finish line, make progress visible, and never let the user stare at zero.**

## Rules

### GGE-01 · Never start a user at 0%
rule: Do not open a flow the user has already partly completed at zero progress.
do: Credit finished steps on first render — resumed flows, saved drafts, returning users.
never: Render a progress meter at 0% on step 2 of 3.
because: An article takeaway: providing *artificial progress* toward a goal helps ensure users are motivated to complete the task. Zero reads as standing still.

### GGE-02 · Invisible progress loses the user
rule: Every activity long enough to fatigue the user must show that they are moving toward a goal.
do: Persistent percent-done bar, step counter ("3 of 5"), milestone list, or badge bar.
never: Run a multi-step activity with no progress affordance.
because: "We'll likely give up if we cannot see that we are moving towards a goal." Visualising effort in the journey context is what stimulates goal-gradient behaviour.

### GGE-03 · Place milestones, not just a destination
rule: Break a long journey into visible intermediate goals.
do: Named stages, each with its own completion state, marked as it is cleared.
never: One undifferentiated bar for a 40-minute course or a 12-week programme.
because: Visual milestones increase goal-gradient behaviour in long and fatiguing journeys — "like tiny pieces of cheese in a maze", placed strategically along the route.

### GGE-04 · Show pending credit before it is confirmed
rule: Display work that is done but not yet scored or processed.
do: Auto-calculate potential points for ungraded answers beside earned totals; label them pending.
never: Hide earned-but-unconfirmed progress until a grader or batch returns.
because: A predicted scoring system lets participants anticipate future development and stay engaged (Interaction Design Foundation: milestone at a 70% pass, top 10% ranking, "best in class" at 100%).

### GGE-05 · Put the goal within reach
rule: Keep reward distance short enough that goal-gradient behaviour can appear at all.
do: Nearer thresholds, shorter cycles, next-tier-neighbouring tiers; break a distant self-set goal into nearer rungs — 52 books a year → 1 book a week → 25 pages a day.
never: Accept a single distant target with no nearer rung.
because: If the reward is perceived as too distant, individuals are less likely to show goal-gradient behaviour. Nearer rungs also prevent the procrastination tail — 35 books left for the last two months of the year.

### GGE-06 · Reward sooner, and reward more often
rule: Shorten the interval between effort and reward.
do: Nucor pays lower-level employees bonuses on **monthly** production — the end of the maze every **30 days**, not once per year.
never: Defer an award you could have paid the moment the work landed.
because: Far-away rewards are much less motivating than near-term ones ($1,000 a month beats $12,000 a year). The article claims the effect may be strong enough to get away with **less total reward by increasing its velocity** — no magnitude is given.

### GGE-07 · Progress must survive the session
rule: Treat progress state as persistent data, not screen decoration.
do: Store it server-side; show lifetime and cycle totals on open; carry tiers, streaks and partial work forward.
never: Reset the visible meter to zero when the user comes back.
because: Quicker movement toward a goal correlates with better retention and faster reengagement in a loyalty program.

### GGE-08 · Never let the meter sit at its new zero
rule: Pre-load the next goal the instant a reward is earned.
do: On completion, reveal the next threshold, tier or target in the same view; keep the meter moving forward.
never: Let a user reach 100% and then meet an empty bar with no stated next goal.
because: **Post-reward resetting**: customers who accelerated toward their first reward slowed down when they began work toward their second.

### GGE-09 · Make difficulty adjustable or the gradient collapses
rule: Let the user change the pace so the goal stays reachable.
do: Flexible plans, scalable targets, adjustable set size or daily volume, easy/normal/hard.
never: A fixed target the user visibly cannot keep up with.
because: When training becomes too difficult, people are at risk of diminishing their goal-gradient behaviour; struggling to keep up will likely demolish it.

### GGE-10 · Vary the target, and make the path worth taking
rule: Refresh the challenge across the journey, and make the repeated activity itself rewarding.
do: New challenges at each stage; bonus events and Point Boosters that temporarily accelerate progress toward a voucher (Morrison's More); bonus stars (Starbucks); tracked order states from preparation to delivery (Domino's).
never: One static threshold and a bare end-of-year prize carrying a boring repeat action.
because: Different challenges keep people invested, tangible bonus events speed them up toward the reward, and "the thrill of the hunt" makes a fun activity one people return to.

### GGE-11 · Track the activity, and give it an audience
rule: Show the ongoing record, per session and cumulatively, and let others see it.
do: Activity history, run summaries, countdowns to an upcoming event, in-session progress bars; kudos and comments on completed activity.
never: Show only an end-of-period total, or a progress display with no audience.
because: Social features can have a positive effect — community-led motivation builds confidence and accelerates efforts toward larger challenges (Strava).

### GGE-12 · Escalate the signal as the target approaches
rule: Increase salience in proportion to proximity.
do: Rising tone frequency, accelerating tick, motion that converges, copy that intensifies near the goal.
never: Flat, low-grade animation carried unchanged from first step to last.
because: In *Aliens* (1986) the motion tracker's dot closing on a small target, with pulsating sounds increasing in frequency, built anticipation and raised viewers' heart rates. Illustration, not a study.

### GGE-13 · One gradient across the whole flow
rule: Treat a multi-step flow as a single continuous gradient from entry to completion.
do: Keep one scale, unit and denominator; carry the same indicator across steps; land exactly on 100% when the task is done.
never: Re-base, re-unit or restart the scale between steps.
because: Splitting the flow destroys the perceived distance-to-goal that every step depends on.

## Hard numbers

| Constant | Value | Note |
|---|---|---|
| Hypothesis proposed | **1932**, Clark L. Hull | Behaviourist; the original proposal |
| Foundational experiment | **1934**, Hull — rats in a straight alley | Ran progressively faster from starting box to food |
| Animal research since | Anderson **1933**; Brown **1948**; review: Heilizer **1977** | Investigated extensively **with animals** |
| Human evidence | **2006**, Kivetz, Urminsky & Zheng, "The Goal-Gradient Hypothesis Resurrected" | Field experiments in reward programs — **no effect sizes, no sample sizes (`unknown: true`)** |
| Reward distance | **$1,000/month** vs **$12,000/year**; **$1,000/month for 5 years** vs **$90,000 in 5 years** | Illustrative contrasts, not measured results |
| Payout cadence | **Monthly** (Nucor: end of the maze every **30 days**, not once per year) | Real example of shortening effort→reward delay |
| Self-set goals | **52 books/year** → 1 book/week → 25 pages/day; **35 books** left for the last two months | Personal-goal illustration |
| Milestone examples | **70%** pass, top **10%** ranking, **100%** "best in class" | Interaction Design Foundation course tracking |
| Percent-done | Myers **1985**, CHI | Preference for progress indicators shown; constant-vs-variable-time replication **not statistically significant**. Statistics live in `response-time-progress-feedback.md` |

## Decision procedure

When a flow, program or habit is not completing, work in this order:

1. **Distance** — how far is the reward from the user's current position? Move it nearer (GGE-05, GGE-06).
2. **Visibility** — can they see that they are moving? If not, add a persistent indicator (GGE-02).
3. **Zero check** — does anything render at 0% when work is already done? Credit it (GGE-01).
4. **Milestones** — is the journey one long stretch? Insert stages (GGE-03) and show pending credit (GGE-04).
5. **Reset** — what does the meter show right after a reward? Pre-load the next goal (GGE-08).
6. **Reachability** — can the user keep the current pace? Make difficulty adjustable (GGE-09).
7. **Freshness** — same goal all the way through? Vary the challenge and make the activity rewarding (GGE-10).
8. **Continuity** — does progress persist across sessions, in one scale, start to finish? (GGE-07, GGE-13).

## Anti-patterns

- A progress meter that starts at 0% on a flow already underway; a long activity with no progress display.
- A single distant prize with no nearer rung; 100% reached, then a fresh empty bar and silence.
- A rigid daily target the user keeps missing, with no way to rescale it.
- One static threshold across months of use; progress reset on every page load because state was never persisted.
- Sensory animation at constant intensity regardless of how close the goal is.

## Review checklist

- [ ] Nothing the user has already done is displayed at 0%
- [ ] Every multi-step activity shows persistent, visible progress
- [ ] Long journeys broken into marked milestones; pending credit shown
- [ ] Reward distance short enough to be felt from the current position
- [ ] Effort→reward delay as short as the business allows
- [ ] Progress, tiers and streaks persist across sessions
- [ ] Next goal visible the instant a reward is claimed
- [ ] Difficulty user-adjustable; challenge and reward texture varied across the journey
- [ ] One scale and denominator across all steps of a flow
- [ ] Activity tracked per session and social acknowledgement available
- [ ] Salience increases as the goal is approached

## Caveats

- **The source itself calls the human evidence understudied** — the hypothesis "has been investigated extensively with animals … but its implications for human behavior and decision making are understudied."
- **The foundational evidence is animal.** The originating experiments are rats in a straight alley and in mazes (Hull 1934), replicated in animal work (Anderson 1933; Brown 1948; review Heilizer 1977). Rat speed-up is not a human finding.
- **Unknown: effect sizes and sample sizes.** The 2006 Kivetz, Urminsky & Zheng field experiments — purchase acceleration in a café reward program, song-rating behaviour for gift certificates — are reported qualitatively only. **No sample sizes, effect sizes or confidence intervals appear in this source (`unknown: true`).** Never attach a magnitude to a rule here.
- **"Less total reward at higher velocity" is a claim without a number.** No supporting figure is given.
- **Most examples are illustrative, not evidence.** The sprinter's "mad dash", the *Aliens* motion tracker, Nucor's policy, the Starbucks / Domino's / Morrison's / Interaction Design Foundation / Strava cases, and the 52-books habit demonstrate the principle; only the 2006 paper is research.
- **The embedded Myers 1985 percent-done abstract is progress-indicator evidence, not goal-gradient evidence**, and its constant-vs-variable replication failed to reach significance.
- **Practical advice here is practitioner heuristics** derived from the two articles, not controlled experimental results. The rules are the takeaways; the magnitudes are not established.
- **Neighbours, not duplicates:** `response-time-progress-feedback.md` covers progress indicators from a latency / waiting-time angle; the mobile commerce patterns skill applies goal gradient to paywalls, carts and order tracking.
- Evidence limits are recorded above. Check them before defending a rule in review.