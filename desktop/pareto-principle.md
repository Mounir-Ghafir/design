---
name: pareto-principle
title: Pareto Principle (80/20) — Prioritisation Rules
description: Rules for deciding where to spend scarce design effort when inputs and outcomes are lopsided. Load when prioritising features, ranking bugs or usability problems, choosing what to redesign first, cutting scope, or defending a roadmap with data.
applies_when: [feature prioritisation, roadmap, scope cutting, bug triage, usability problem ranking, research planning, ux prioritisation]
priority: supporting
rules: 15
---

# Pareto Principle (80/20) — Prioritisation Rules

## Core principle

For many events, roughly 80% of the effects come from 20% of the causes.

```
inputs and outputs are often not evenly distributed
a large group may contain only a few meaningful contributors to the desired outcome
→ focus the majority of effort on the areas that bring the largest benefits to the most users
```

**80/20 is a rule of thumb, not a law.** The principle does not predict when the imbalance appears or why. Use the *magnitude* of the imbalance, never the exact figures.

## Rules

### PPE-01 · Read the ratio as a direction, not a number
rule: Treat 80/20 as an illustration of lopsidedness; the real ratio is whatever your data shows.
do: Act on "a small slice causes most of the effect"; compute the actual split before committing effort.
never: Assume the split is 80/20, or design a plan that fails if it comes out 27/70.
because: Distributions vary widely and often exceed 80/20; the pattern, not the constant, is the claim.

### PPE-02 · Find your own 20% from data, not intuition
rule: Locate the imbalance empirically before you prioritise anything.
do: Group your data by category — pages, features, user segments, tasks, bugs, support contacts — and measure a metric per category.
never: Rank features by how much the team argues about them or how loud the loudest customer is.

### PPE-03 · Start with a goal and a hypothesis
rule: No Pareto analysis without a stated goal, a hypothesis, and a chosen metric.
do: Write down the outcome you are trying to move, then the one metric that represents it.
never: Chart everything your analytics tool exports.
because: Analytics scope alone causes information overload and analysis paralysis.

### PPE-04 · Build the table before the chart
rule: Four columns: category, metric value, percent of total, cumulative percent of total.
do: List categories, sum the metric, sort descending by metric, then compute percent-of-total and cumulative percent.
never: Produce a Pareto chart without confirming the data is exportable, redundant-free, and error-free.

### PPE-05 · Keep the vital few visible at full quality
rule: The high-contribution slice gets the best design effort.
do: Put the most-used tasks and features on the shortest, clearest path; protect them when revising.
never: Degrade the core experience to shorten the scope list.

### PPE-06 · Follow the imbalance, not the ease of the fix
rule: Prioritise by disproportionate impact, even when other options are cheaper to implement.
do: Persuade stakeholders with the return on investment of the vital few.
never: Choose the fix that is easiest because it is easiest.

### PPE-07 · Weight segments, not raw totals
rule: A minority of users can still dominate if they are the ones you serve.
do: Give high-value segments more weight; 400 of 500 support calls on Feature A loses to B and C if those calls are all from high-revenue clients.
never: Apply an aggregate ranking to a decision whose stakes differ by segment.
because: Data should always be used in the largest context available.

### PPE-08 · Check the sample size before you trust the split
rule: Imbalance claims need a sufficient base to be meaningful.
do: Confirm the analysis covers enough observations to be statistically relevant.
never: Build a Pareto-driven roadmap on 5 helpdesk calls.

### PPE-09 · Rare use is not the same as low value
rule: Usage frequency alone does not rank a feature; some low-frequency features carry high value.
do: Judge on the outcome a feature delivers, and keep it reachable for the users who need it.
never: Cut a rarely used feature purely because usage data looks small.

### PPE-10 · Good UX is not just about minimising clicks
rule: Click depth is not a proxy for UX quality. A feature the user cannot find fails no matter how shallow it would be.
do: Treat feature *availability and findability* as first-class design concerns — how many places must be searched, how deep the context level, whether overflow menus are stacked.
never: Optimise only the number of clicks, or count a hard-to-find feature as cheap.

### PPE-11 · Apply it to problems, not just revenue
rule: The same analysis works on usability problems, task lists, support contacts, and feature requests.
do: Graph the frequency of issues encountered and of tasks performed; fix the head of the distribution.
never: Restrict Pareto to business metrics.

### PPE-12 · "The vital few and the useful many"
rule: Juran revised his own phrasing; the tail is useful, not trivial.
do: Reserve design and research bandwidth for the long tail deliberately.
never: Let the tail go unowned.
because: Investing exclusively in the 20% for too long leads to stagnation and overoptimisation of a few metrics to the detriment of others.

### PPE-13 · Don't let a few metrics own the roadmap
rule: A Pareto read is an input to prioritisation, not a definition of product vision.
do: Combine quantitative rankings with qualitative research; present the imbalance as an ROI case with a named metric and segment.
never: Reinforce the belief that a handful of metrics should drive all design work.
because: It is tempting to misuse the principle by ignoring 80% of the user experience.

### PPE-14 · Prioritise the vital few; shrink scope, don't discard the rest
rule: Use the analysis to cut research and implementation scope — but keep the tail's 20% of value.
do: Filter the analytics volume, reduce scope, de-emphasise or relocate the tail — see `progressive-disclosure.md`.
never: Delete the tail outright, or produce the analysis and then ship the full original backlog anyway.

### PPE-15 · Requests are not value; re-measure after shipping
rule: Many users asking for something does not mean they will value it, and the distribution moves once you fix it.
do: Focus attention with the analysis, verify with research, then re-measure after the vital few ship.
never: Use Pareto to eliminate ongoing user research, or to assume the old vital few are still vital.

## Hard numbers

Figures stated by the source. Most are single case observations, not general constants.

| Constant | Value | Note |
|---|---|---|
| Stated principle | **~80% of effects from ~20% of causes** | A rule of thumb; exact split varies |
| Top-task study | **222 users, 94 tasks → top 15 (16%) = 41% of votes** | One informational website; participants picked 5 tasks each |
| Usability-problem study | **33 issues, 181 encounters, 50 users → 9 issues (27%) = 72% of poor interactions** | Enterprise car-rental site |
| "What would you fix?" | **2 issues = 50% of comments; 5 = 75%** | Open-ended usability-test comments |
| Product-feedback example | **3 features = 86% of feedback submissions** | Worked example, not measured data |
| Pricing-page example | **77% of trial-signup segment visited the features/pricing page** | Worked example |
| Page-view example | **5% of pages = 67% of pageviews**; social media **1% of users = 90% of postings** | Illustrative counter-examples to exactly 80/20 |
| Bug fixing (Microsoft) | **Top 20% of most-reported bugs = 80% of errors and crashes** | Vendor claim, no method given |
| Bandwidth | **Top 10% of cell phone users consume 90% of wireless bandwidth** | Source gives no date or citation |
| Feature requests | **20% of customers demand 80% of new feature requests** | Source gives no measurement |
| Illustrative target | **Top 15% of tasks used by 90% of users, 80% of the time**; **10–40% of inputs** drive most results | Offered as a starting example, not a recommendation |
| Origin | **Pareto 1848–1923 (land, peas); Juran popularised it in the 1940s** | Economic and agricultural history — metaphor only, no design evidence |
| Effect size for the principle, in general | **unknown: true** | No controlled comparison reported |

## Decision procedure

When deciding what to design next:

1. **Goal** — name the outcome and the one metric that measures it (PPE-03).
2. **Data** — group by category; confirm the base is large enough to be meaningful (PPE-02, PPE-08).
3. **Table** — category, metric, percent of total, cumulative percent; sort descending (PPE-04).
4. **Read the curve** — where does it flatten? That is your vital few (PPE-01, PPE-05).
5. **Weight** — do high-value segments change the ranking? (PPE-07).
6. **Value check** — for each candidate, is it high value, or merely high frequency? (PPE-09).
7. **Findability** — can a user actually reach the vital few? (PPE-10).
8. **Scope** — cut the tail's effort, don't delete the tail (PPE-14).
9. **Balance** — name what you are deliberately leaving under-served this round (PPE-12, PPE-13).
10. **Re-measure** — the distribution shifts once the head is fixed (PPE-15).

## Anti-patterns

- Prioritising by clicks, usage frequency, or loudness alone.
- Analysing everything the analytics tool exports instead of one goal.
- Treating 80/20 as a target ratio to hit rather than a pattern to look for.
- Cutting the long tail to "stay focused".
- Letting a handful of metrics become the product vision.
- Dropping user research because the data already ranked the options.
- Fixing whatever is easiest while the expensive head of the curve stays broken.
- Degrading the core experience to shorten the scope list.

## Review checklist

- [ ] Goal, hypothesis, and metric stated before any ranking
- [ ] Metric values pulled from real usage or research data, sorted descending
- [ ] Percent-of-total and cumulative percent computed
- [ ] Sample size large enough to support the claim
- [ ] High-value segments weighted, not just raw totals
- [ ] Vital few get the best design effort
- [ ] Frequent ≠ valuable checked for every de-prioritised feature
- [ ] Vital few are easy to find, not just cheap to reach
- [ ] Tail de-emphasised rather than deleted; bandwidth reserved for it
- [ ] Qualitative research still in the loop; re-measurement scheduled

## Caveats

- **The source contains no measured distribution for the 80/20 claim in a general UX context.** It gives case studies with real numbers (222 users / 94 tasks; 33 issues over 50 users) but no effect sizes, no samples, and no controlled comparison for the principle itself — `unknown: true`. The ratio is an illustration, not a measurement.
- Several headline figures are unsourced in the text (Microsoft bug fix rate, 10% of cell phone users / 90% of bandwidth). Treat them as folklore, not evidence.
- The illustrative cases each describe one product at one moment; distributions shift after you act on them.
- The origin material — Italian land ownership, garden peapods, income and tax shares — is economic and agricultural history. It explains the metaphor and supplies nothing for design decisions.
- A Pareto read can be politically convenient. It is a good way to win an argument about ROI and a bad way to end one.
- `progressive-disclosure.md` is the technique for handling the low-priority 80% without removing it; the mobile hub skill covers feature prioritisation and scope.