---
name: jakobs-law
title: Jakob's Law — Design Rules
description: Rules for making an interface behave the way users already expect from every other site they use, and for deciding whether a deviation is worth the learning it costs. Load when building a new screen or product, when redesigning or migrating, when picking an interaction pattern, when sizing a mobile layout, or reviewing conventions.
applies_when: [new screens, new products, redesigns, migrations, navigation, interaction patterns, mobile layout, ux review]
priority: supporting
rules: 15
---

# Jakob's Law — Design Rules

## Core principle

Users spend most of their time on other sites. They prefer your site to work the same way as all the other sites they already know.

```
novel pattern   /‾‾╲__________  starts high, plateaus late
old pattern     ‾‾‾‾‾‾‾‾‾‾‾‾‾‾  already flat — every user arrives pre-practised
```

## Rules

### JL-01 · Expectation transfer is automatic
rule: Users transfer expectations built around one familiar product to another that appears similar.
do: Follow the conventions of the category the user has already been using — most e-commerce sites work the same way for exactly this reason.
never: Treat looking like the category as a branding problem to be solved.

### JL-02 · Spend attention on the task, not on the model
rule: Leverage existing mental models so users can focus on their tasks rather than on learning new models.
do: Reuse labels, layouts, and gestures met elsewhere; let a familiar interface recede into the background.
never: Make a first session an orientation to your interface.
because: Removing the friction of an unfamiliar interface raises the likelihood users complete their intended tasks.

### JL-03 · Ship the old version alongside the new one, then retire it
rule: When making changes, minimise discord by empowering users to continue using a familiar version for a limited time.
do: Offer a preview, a way back, a feedback channel, and a stated end date.
never: Hard-cut a live interface on a date.
because: YouTube, 2017: after years of the same design, desktop users could preview the new Material Design UI, gain some familiarity, submit feedback, and revert — discordance was avoided by letting users switch when ready.

### JL-04 · Hold the baseline, on web and on mobile
rule: A new screen inherits the conventions of its platform and its category; reduce distinctiveness in visual design, terminology and labelling, interaction design and workflow, and information architecture.
do: Web — search box top right, logo on the left, navigation in a bar, vertical scrolling on desktop, blue text links, "shopping cart" and its icon, visited links that change colour. Mobile — spend scarce screen space on content and keep only the most necessary navigation features. When things always behave the same, users know what will happen and feel in control.
never: Logo on the right, horizontal scrolling on desktop, a hamburger in place of a desktop nav bar, the same gesture behaving differently two screens apart, or standardising the content itself.
because: Task analysis, content design, and per-site IA structure stay free to differ — what transfers is the convention. Small screens leave less room for navigation, which makes conventions matter more, not less.

### JL-05 · Controls keep the shape of their tactile ancestor
rule: Form toggles, radio inputs, and buttons originated in the design of their tactile counterparts.
do: Keep the affordance and the state model of the physical control: pressed, selected, filled.
never: Re-skin a solved control into a shape the user has no physical reference for.

### JL-06 · Treat every session as a novice session
rule: People very rarely use any individual website long enough to become expert users, so design for novices every time.
do: Make the screen obvious within a few seconds of arrival.
never: Assume last week's fluency survived the session.

### JL-07 · Give expert capability to the client
rule: Move expert features into the browser or other client software, where they work identically everywhere.
do: Hand navigation and history to the Back button and to bookmarks instead of rebuilding them in your chrome.
never: Re-implement Back, or gate a power feature behind site-specific UI.
because: A feature that is standardised or client-supported stays available to experts without being visually apparent, so it costs a novice nothing to learn.

### JL-08 · One service, same semantics across devices
rule: When a service is delivered over multiple devices, users should recognise it as the same service.
do: Deliver many of the same features on each platform; elide or push to background the ones that make less sense there; emphasise semantics over representation.
never: Let the rules change every time the user picks up a different device.
because: Content that flows in or out of your site survives only on a few portable mechanisms — headlines, bulleted lists, highlighted keywords. Anything too special creates a conflict.

### JL-09 · Gate 1 — beat the incumbent after the curve, or don't start
rule: Deviate only if the new design performs much better once users have "descended" the learning curve.
do: Compare against the incumbent at the plateau, not at first contact.
never: Ship a deviation whose only advantage appears in the first few repetitions.
because: On the first trial the designs take roughly the same time; divergence only shows up from the second repetition onward.

### JL-10 · Gate 2 — will they come back often enough to get there?
rule: Deviate only if it is credible users will try the new design again and again until they have learned it well enough to realise the benefit.
do: Count sessions per user per week against the incumbent's saturation point; assume non-captive users leave for the familiar option.
never: Introduce a design that is only worth anything after saturation when users visit once and leave.
because: Unless users are captive and you can force practice, they will give up and go elsewhere — users hate change. If the saturation point is far enough out they may never arrive: Windows 8 changed the design instead of waiting.

### JL-11 · Gate 3 — can you accelerate the learning?
rule: Deviate only if you can expose users to the new design more often, or make it easier to learn.
do: Raise frequency until saturation is reachable; ship contextual tips and progressive disclosure as scaffolds; ride an en-masse adoption that will supply the repetitions for you.
never: Expect a tutorial to carry the learning — swipe-to-delete and the mobile hamburger became standard because enough sites adopted them, not because anyone taught them.

### JL-12 · Repetition teaches; tutorials do not
rule: Doing something often is the way to strong learning, and showing a tutorial or help screen is not enough.
do: Count repetitions, not explanations; spend design effort making a pattern recur.
never: Add onboarding in place of a pattern the user will meet once.

### JL-13 · Price the innovation on both sides of the ledger
rule: Any innovation incurs a cost, for users and for designers. Decide which bill you are paying.
do: Charge the user a new pattern on an untrodden, slow path; charge yourself contextual tips, progressive disclosure, and their implementation cost.
never: Adopt a novel pattern just to be different — ask whether a traditional design serves you as well.
because: Innovation is easier to push with a captive audience, or when the perceived value of the brand far exceeds the cost of the new pattern. Large platforms with a big user base can afford it; enterprise users may simply have no choice but to accept it.

### JL-14 · Let frequency, not taste, pick the design
rule: Between a fast-to-learn design and a best-once-learned design, the user's session frequency decides.
do: For daily flows take the lower learned task time even though it saturates later; for rare flows take the early plateau.
never: Choose on aesthetics when the two designs differ on saturation point.
because: In the source's A/B/C example, A saturates at the 4th repetition with a learned task time of 2s; B saturates around repetition 11 but once learned is 1s. During the first week A is better; halfway through the second work week B is better and then stays better. An employee directory used once a day → B; VAT reclaimed from foreign travel, at most one business trip abroad each year → A.

### JL-15 · Spend novelty deliberately, never at the cost of usability
rule: Design for novelty only when differentiation from competition is the goal, when the technology is meant to disrupt an incumbent, or when exploration and surprise are the desired outcome.
do: Ground every deviation in user research and testing of the target audience; reconsider any unfamiliar pattern that has been shown to harm usability.
never: Ship novelty as a default aesthetic, or keep a novel pattern that testing shows costs usability.

## Hard numbers

| Constant | Value | Note |
|---|---|---|
| The law, verbatim | "users spend most of their time on other websites" | The only sentence the source gives as the law |
| Coined by | Jakob Nielsen, principal of the Nielsen Norman Group | Co-founded with Donald A. Norman, former VP of research at Apple; consistency is one of the original 10 usability heuristics |
| Learning curve shape | power law — a straight line in log–log scale | Newell, Carnegie Mellon, 1980s |
| First trial | roughly the same time on all designs | Divergence appears by the 2nd repetition |
| Saturation points | A at the 4th repetition; B around repetition 11; C at the 10th or 11th | A learns fastest of the three |
| Speed-up | approximately 20s for A (22 at repetition 1, 2 at repetition 15); approximately 19s for C | Highest-to-lowest difference on each curve |
| Learned task time | 1s for B vs 2s for A | B wins only after learning |
| Head start, old pattern | repetition 1 for the new interface = repetition 5 for the old | Illustrative pairing |
| Menu study | 8 practice blocks, the same 6 items selected per block | Ahlstrom et al.; participant count not stated |
| Memory saturation | approximately around day 12 | Pirolli & Anderson, 1985 |
| Slope reading | steep is good — "steep learning curve" is a misnomer | Slope is improvement relative to the saturation point |

Not established by this source: participant counts, effect sizes, any percentage or measured rate of user transfer, any measured abandonment rate — `unknown: true`.

## Decision procedure

1. **New screen or revision?** If it touches a live interface, clear gates 1–3 before drawing anything.
2. **Baseline** — check the screen against category and platform conventions, web and mobile (JL-04, JL-05).
3. **Novice test** — is it obvious in a few seconds to someone who has never seen it (JL-06)?
4. **Expert paths** — delegated to the browser or OS, not rebuilt (JL-07).
5. **Gate 1** — better at the plateau than the incumbent? If no, keep the convention (JL-09).
6. **Gate 2** — enough sessions per user to reach that plateau, or a captive audience? If no, keep the convention (JL-10).
7. **Gate 3** — can you add frequency or scaffolds, or ride an en-masse standard? If no, not viable (JL-11, JL-12).
8. **Ship the migration** — parallel old version, preview, revert, feedback, end date (JL-03).

## Anti-patterns

- Hard-cutting a redesign with no revert path.
- Logo on the right, horizontal scroll on desktop, hamburger in place of a desktop nav bar.
- A tutorial standing in for a pattern the user meets once.
- Re-implementing Back inside your own chrome.
- A deviation justified only by "it's fresher".
- Spending a small screen on navigation furniture.
- Third-party content that only survives inside your styles.

## Review checklist

- [ ] Screen checked against category and platform conventions; mobile space spent on content, not navigation
- [ ] Four distinctiveness checks run: visual design, terminology and labelling, interaction design and workflow, information architecture
- [ ] Controls keep their tactile affordance and state model
- [ ] Same gesture, same result, on every screen; obvious within a few seconds
- [ ] Expert features delegated to the browser or OS
- [ ] Same service recognisable across devices; semantics over representation
- [ ] Any deviation passed gates 1, 2 and 3, with cost booked against user and team
- [ ] Redesign ships with preview, revert, feedback, and an end date
- [ ] Novelty grounded in user research; onboarding not used as a substitute for repetition

## Caveats

- Jakob's Law is an **industry heuristic and a design convention, not a validated law**. The source states no effect sizes, no sample sizes, and no measured rate at which users transfer expectations — `unknown: true`.
- The source **does** contain quantitative data, but it measures *learning*, not the law: the saturation points, task times, and speed-ups above come from illustrative A/B/C designs and from named lab studies.
- The A/B/C figures are constructed illustrations, not measurements of a named product — do not quote them as benchmark task times. "Websites do more business the more standardized their design is" is asserted in the source with no data attached.
- The named conventions date from the source's era (web-design list first compiled 1996, updated 2011; learning-curve article 2016). Scope is desktop and mobile web; native, embedded, and voice interfaces are not covered.
- `mental-model.md` covers the underlying psychology of transferred expectations; `cognitive-load.md` covers building on patterns users already know.
- The source's own conclusion is that consistency is "the curse of innovation in design". Treat these rules as a default to argue against deliberately, not a prohibition.
