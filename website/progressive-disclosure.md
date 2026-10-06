---
name: progressive-disclosure
title: Progressive Disclosure — Design Rules
description: Rules for sequencing what a user sees and when — basics first, advanced options deferred to secondary screens. Progressive disclosure has NO empirical validation (Carroll & Rosson 1997) and is practitioner convention, not a proven law. Load when a screen is overloaded, when splitting a feature set into primary and secondary levels, when building a wizard or multi-step flow, when deciding what to hide, or when reviewing UX.
applies_when: [feature-rich interfaces, settings and advanced options, wizards and multi-step flows, onboarding, information architecture, mobile accordions, ux review]
evidence_class: practitioner-convention-unvalidated
priority: core
rules: 15
---

# Progressive Disclosure — Design Rules

> ### ⚠ Read first — no empirical validation
>
> **No empirical evidence exists on the effectiveness of progressive disclosure** (Carroll & Rosson, 1997). Its foundation is a single static desktop word processor with a single menu-based interface style. Every rule below is **widely endorsed practitioner convention, not a proven law** — never cite it as validated, never let it be the sole reason to hide something. Justify the split from **observed user behavior** (PD-06) and confirm it by usability testing.

## Core principle

Defer advanced or rarely used information and actions to later or secondary screens, ramping users from **simple to complex actions**. It sequences *behaviour*, not merely levels of detail.

```
primary screen   = the low-hanging fruit; enough to be successful at the start
secondary levels = advanced / infrequent options, reached on demand
the hard part    = where the line falls — it requires knowing real usage (PD-02)
```

Source formulations: Spillers (2004) sequence information and actions across several screens to reduce overwhelm; Nielsen (2006) defer advanced or rarely used features to a secondary screen; Nielsen (2002) show fewer features to novices while experts call up more; Forrester (2003) incremental layers keyed to progress through a configurator. **Sibling:** `chunking.md` structures *what* users see together; this file sequences *when* they see it — complementary, not alternatives, and **either can be used alone.**

## Rules

### PD-01 · Treat this as convention, not law
rule: Progressive disclosure has no empirical validation; it is a heuristic.
do: Justify every primary/secondary split from observed behavior plus usability testing.
never: Cite it as a validated law, or let it be the only argument for hiding an option.
because: Carroll & Rosson (1997) found no empirical evidence of effectiveness.

### PD-02 · Get the right split (Nielsen 1)
rule: Choosing the split between initial and secondary features is the core challenge.
do: Derive the primary screen from real usage — observation, task analysis, or analytics.
never: Guess which features are primary from your own preference or the org chart.
because: Everything downstream depends on this one line, and it needs real usage data.

### PD-03 · Make progression obvious (Nielsen 2)
rule: The path from primary to secondary must be visible and obvious.
do: Raise information scent — explicit labels, affordances, a visible target area; prefer shallow in-place reveals to deep drill-down.
never: Bury the route behind an unlabelled icon or give no signal that more exists.
because: A hidden next level is a next level nobody reaches.

### PD-04 · One option, one route (Nielsen 3)
rule: Avoid multiple ways to reach the same secondary option.
do: Keep a single consistent entry point per secondary screen.
never: Offer a link, a menu item, a search result and a shortcut all leading to the same place.
because: Competing routes to one destination produce confusion.

### PD-05 · Several secondary displays, not one catch-all (Nielsen 4)
rule: Consider multiple secondary displays, each revealed by its own control.
do: Group advanced options by task so each group has a purposeful entry point.
never: Build a single "Advanced" dumping ground for unrelated settings.
because: A catch-all screen replaces one overwhelming list with a smaller one.

### PD-06 · Base it on observed behavior
rule: Decide *what* is disclosed and *when* from actual observed user behavior.
do: Run field studies or task analysis; watch the workflow outside your own technology.
never: Apply progressive disclosure ad-hoc — ad-hoc use yields inaccurate results.
because: Task priority and sequencing are only knowable by watching users.

### PD-07 · Don't hide what people actually use
rule: Never hide a frequently used feature.
do: Promote back to primary anything most users need — Word 2003's auto-collapsed menus became Word 2007's task ribbon for exactly this reason.
never: Make users repeatedly re-activate a hidden item they want often.
because: Repeat-use friction is a direct cost paid by the majority.

### PD-08 · Never sequence for the designer's benefit
rule: Order screens and steps by the user's task.
do: Ask what the user came to do, then sequence to serve that.
never: Split one article across four "Next page" screens for banner ads, or force 4–5 benefit pages before revealing the price.
because: Both serve advertising or persuasion goals, not the user.

### PD-09 · Preserve free-form exploration
rule: Let users jump ahead and inspect out of order.
do: Offer previews and overviews, "view more details", "related topics".
never: Assume users will read sequentially to build acceptance of your offer.
because: Non-sequential exploration is normal web behavior, not a deviation.

### PD-10 · Shortcut the repeat and expert path
rule: Return users and experts must not pay the novice tax.
do: Give advanced entry points, remembered state, and direct links from the first visit.
never: Force a repeat user through the full staged flow every time.

### PD-11 · Sequence actions, not just detail
rule: "Progressive" means ramping from simple to complex *actions*, not just terser words.
do: Order steps by what the task requires, revealing complexity as it becomes relevant.
never: Reduce the description while leaving the underlying work just as complex.

### PD-12 · Use the known teaser components
rule: Introduce the next level with one of the established teaser forms.
do: A sample of what is next; an introductory task (the most common one); a high-level view of what is expected; a wizard; a button to advanced functions.
never: Drop users into an empty secondary screen with no preview of its purpose.

### PD-13 · Web rule of thumb: task relevance per page
rule: Only show information relevant to the task the user wants to focus on, on that page.
do: Use the established web patterns — "learn more", "related topics", "view more details", account overview on the first screen, "advanced search", internet configurators at the right level of detail at the right time without jarring transitions.
never: Pad a page with content belonging to a different task.

### PD-14 · Staged disclosure is a wizard
rule: Nielsen's staged disclosure is the wizard (back–next) hybrid.
do: Use it for multi-step tasks (checkout, sign-up) with visible progress; use onboarding and empty states as staged teasers with a clear next action.
never: Assume it will work — context of use can paralyze its effectiveness.
because: Nielsen (2006) defines it this way; the limitation is unresolved.

### PD-15 · Match the pattern to the medium
rule: Software and web contexts differ; the technique applies more readily to software.
do: In software lean on dialogs and fixed-state interactions; on the web compensate for non-linear hypertext with strong information scent and a targeted audience.
never: Port menu-based assumptions onto chaotic, randomized, dynamic web pages.
because: Web audiences are unpredictable and few web-specific guidelines exist.

## Hard numbers

**There are none.** No validated threshold, cap, effect size, or metric exists for this technique.

| Quantity | Value | Note |
|---|---|---|
| Validated effect size | None reported | Carroll & Rosson (1997): no empirical evidence of effectiveness |
| Study sample sizes | None reported | Foundation = one word processor, one menu-based interface |
| Metric for a "correct" split | None | Nielsen's 4 guidelines have no reported empirical validation |
| Items on a primary screen | No rule of thumb | This is a chunk-size question — see `chunking.md` |

## Decision procedure

1. **Evidence** — assume nothing; you need observation, not doctrine (PD-01).
2. **Observe** — field study, task analysis, or usage data. Find what users actually do first (PD-06).
3. **Split** — put the low-hanging fruit and the most common task on the primary screen (PD-02).
4. **Audit frequency** — promote back anything most users need (PD-07).
5. **Route** — one obvious path per secondary option, with visible information scent, and group secondary options into several purposeful displays rather than one (PD-03, PD-04, PD-05).
6. **Sequence check** — walk the flow; cut any step that exists for ads, persuasion, or forced reading (PD-08, PD-09).
7. **Repeat path** — verify a repeat user reaches advanced options in one action (PD-10).
8. **Verify** — usability-test with novices *and* experts; with PD-01, testing is the only validation you have.

## Anti-patterns

- **Forced waiting** — content withheld until the designer is ready to show it.
- **Repeat-use friction** — repeat users forced through the staged flow, or hidden items they repeatedly re-activate (Word 2003).
- **Over-constraining** — "dumbing down" or hiding so much that users cannot reach what they need.
- **Unverified assumptions** — assuming you know the most popular, common, or important task; or applying disclosure ad-hoc.
- **Designer-benefit sequencing** — an article split over four screens for banner ads; 4–5 benefit pages before the price.
- **Structural mistakes** — one catch-all advanced screen, several routes to the same secondary option, or a next level nothing signals.

## Review checklist

- [ ] Primary/secondary split derived from observed behavior
- [ ] Frequently used features promoted back to the primary screen
- [ ] Path from primary to secondary obvious (information scent, visible target)
- [ ] Exactly one route to each secondary option; no catch-all advanced screen
- [ ] Every secondary screen has a teaser or preview
- [ ] Free-form exploration still possible
- [ ] No forced waiting or click-throughs serving the designer's benefit
- [ ] Repeat and expert users have a one-action path
- [ ] Works across the audience range, novice → expert
- [ ] Checked with assistive technology and verified by usability testing

## Caveats

- **No empirical validation.** Carroll & Rosson (1997): no empirical evidence exists on the effectiveness of progressive disclosure. Treat this whole skill as practitioner convention, not a proven law.
- **The effectiveness conflict is unresolved in the source.** Carroll (1983/1984, "training wheels") reported increased later success from hiding advanced functionality early, and Nielsen (2000) called it "best tool so far"; Carroll & Rosson (1997) report no empirical evidence. Record the conflict; do not resolve it in a spec — validate locally.
- **Foundation overgeneralized, and there are no numbers.** The basis is one static desktop word processor with menu-based control, and a user base unlike today's users, who meet dozens of interfaces. No effect sizes, sample sizes, or validated metrics exist; Nielsen's 4 guidelines have no reported empirical validation. Findings may not transfer.
- **Dated examples.** Word 2003/2007 task ribbons, Apple Leopard stacks and spaces, early AJAX, early iPhone pinch-and-zoom = mid-2000s. The principles hold; the products are historical.
- **Medium bias.** The technique originated in software usability; the web context (§3.2 of the reference) is harder, with unpredictable audiences and few disclosure-specific guidelines.
- **Mobile disclosures are derived, not sourced.** Accordions, bottom sheets, "view more", staged onboarding, and deferred advanced settings are design inferences — validate each by observation, never by appeal to the technique's reputation.
- No effect sizes, sample sizes, or validated metrics exist for any rule in this skill. Check the caveats above before defending one.