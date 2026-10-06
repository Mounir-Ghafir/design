---
name: mental-model
title: Mental Model — Design Rules
description: Rules for aligning a product with what users already believe about how it works, and for deciding whether to conform to that belief or teach a new one. Load when redesigning, migrating, structuring information architecture, adding a novel pattern, shipping help or docs, or reviewing a flow users keep getting wrong.
applies_when: [information architecture, navigation, redesigns, novel patterns, instructions and docs, cart and checkout, back navigation, ux review]
priority: supporting
rules: 15
---

# Mental Model — Design Rules

## Core principle

A mental model is a compressed representation of what a user *believes* about how a system works. Design against the belief, not the truth.

```
designer's model ──(system image)──▶ user's model ──▶ predictions ──▶ actions
      detailed, accurate              sparse, borrowed from elsewhere, possibly wrong
on mismatch:  conform to the user's model   |   teach them a better one
```

## Rules

### MM-01 · A model is belief, and a reduction — never a fact, never a copy
rule: Design against what the user believes the system is, not against what is objectively true.
do: Make the interface clearly communicate the nature of the system so users form accurate, and therefore useful, models; design so a simplified model still suffices to finish the task.
never: Assume a user's understanding is correct without evidence, or that a user who reached the destination shares your picture of the route.
because: "The map is not the territory" — a model can be flatly wrong and still govern behaviour, and a model that were a perfect copy would be of no use.

### MM-02 · Your model is not the user's model
rule: Assume a gap between the designer's model and the user's model of the same system.
do: Validate your model through research before shipping.
never: Treat your own detailed understanding of a feature as evidence that it is easy to use.
because: Designers hold wonderfully detailed models of their own creations; most users' models are far less developed, so they make more mistakes.

### MM-03 · Users arrive pre-loaded from elsewhere
rule: Users build their model of your product largely from what other products taught them, and expect sites to act alike.
do: Import the conventions of the category the user is already in.
never: Assume your product is being evaluated on its own terms.

### MM-04 · One false belief poisons the whole session
rule: A single wrong assumption can make users systematically misinterpret everything that happens after it.
do: Find the one belief your UI contradicts and fix that first.
never: Polish secondary screens while a known false belief stays in place.
because: Users fail repeatedly without ever questioning their basic assumptions.

### MM-05 · Discover the model before you redesign
rule: Never redesign from assumption. Run research that surfaces the user's model.
do: User interviews, personas, journey maps, empathy maps; think-aloud sessions where users verbalise what they think, believe, and predict.
never: Declare the model settled after a handful of sessions without noting what advanced knowledge-elicitation methods could still surface.
because: Closing the designer–user gap is one of the biggest challenges in the field; simple user testing is the first step when a wrong model is costing you business.

### MM-06 · Conform or reteach — decide explicitly
rule: On a mismatch you have exactly two options: make the system conform to users' models, or improve users' models.
do: Conform when most users' models are similar; reteach when the underlying system must stay unchanged.
never: Break a model without also providing the new one.

### MM-07 · Move content to where users look
rule: If people look for something in the wrong place, move it to the place they look.
do: Use card sorting to discover users' model of an information space, then build navigation to match the groups they produced.
never: Leave an intuitively named location empty because it contradicts your sitemap.
because: This is the recommended fix for information-architecture problems.

### MM-08 · Each user holds a different model
rule: Different users construct different models of the same system from their own background and past experience.
do: Test whether divergence is a segment split, then serve each segment's model.
never: Average incompatible models into one design and call it consensus.
because: Mental models are highly individually subjective — we live in one world and construct different models of how it works.

### MM-09 · Teach early, or stop distinguishing
rule: You can fix a bad model by teaching it earlier in the experience, or by removing distinctions users will never learn.
do: Keep instructions, docs, tutorials, and demos short while teaching the key concepts needed to make sense of the system; collapse the UI when a distinction is not learnable.
never: Depend on catching the mistake at the point of failure.

### MM-10 · The system image is your only channel
rule: The designer's mental model reaches the user solely through the system image.
do: Treat appearance, past experience, sales literature, advertisements, articles, and instruction manuals as the entire transmission channel.
never: Assume the implementation communicates your intent; the system image is open to infinite interpretations.

### MM-11 · Inertia is the default
rule: Assume a well-known model sticks, even when it is no longer helpful.
do: Be conservative; innovate only where the new approach is clearly superior to the old well-known way.
never: Replace a working pattern for novelty's sake.

### MM-12 · One search box, one meaning
rule: Users model search bars as universal; multiple search features on a page break that model.
do: Ship a single well-placed search bar as the default entry point.
never: Offer two search boxes distinguished only by help and placeholder text.
because: Users enter their query in the wrong box and conclude the site simply has no answer.

### MM-13 · Back means undo
rule: Back is a long-standing essential that users model as undo — a return to the previous screen.
do: Make Back exit an overlay and return to the previous screen, especially when the overlay feels like a new page.
never: Repurpose Back to climb a hierarchy or to leave the app.

### MM-14 · Never add to the cart silently
rule: In the physical store the shopper controls what goes in the cart; that expectation carries over to ecommerce.
do: Make every add-on visible and opt-out.
never: Pre-select an add-on at checkout.
because: Adding unexpected items to a cart is a deceptive pattern known as sneaking or preselection — Nomad Lane pre-selected an $8.25 shipping-protection add-on that users had to notice and actively opt out of.

### MM-15 · Borrow the physical world for new patterns
rule: Use familiar real-world metaphors to make an unfamiliar interaction style learnable.
do: Reach for maps, doors, and other physical-space metaphors when the audience has no digital model to anchor on.
never: Force a novel interaction on users with no existing model to attach it to.
because: Young users may not yet have well-established mental models for digital navigation — Duo ABC uses a door to mark the journey's start and a map to walk through lessons.

## Hard numbers

| Item | Value | Note |
|---|---|---|
| Effect size of a mental-model mismatch | **unknown: true** | No quantitative outcome data in the source |
| Sample sizes, test statistics | **unknown: true** | None reported |
| Pre-selected shipping-protection add-on | **$8.25** | Nomad Lane cart example; on by default, opt-out required |
| Concept origin | 1943 — Craik, *The Nature of Explanation* | "small-scale model" of external reality, used to try out alternatives before acting |
| Deductive-reasoning process | 3 steps: build a model → derive a conclusion true to it → search for a refuting alternative model | Johnson-Laird, *Mental Models*, 1983 |

## Decision procedure

When a flow keeps producing mistakes, work in this order:

1. **Name the model** — write the one sentence a user would use to describe what this screen does. If they can't, the UI isn't communicating the system's nature (MM-01).
2. **Collect the models** — interviews, personas, journey maps, empathy maps, card sorting, think-aloud (MM-05, MM-07).
3. **Diff them** — split into designer model, shared model, and per-segment outliers (MM-02, MM-08).
4. **Decide** — conform or reteach, for which segment; if they look in the wrong place, move the content there (MM-06, MM-07).
5. **Check the channel, then re-audit** — does the system image (appearance, copy, docs, ads) carry the intended model (MM-10)? Models shift with experience; re-check after each major release.

## Anti-patterns

- Assuming the user reads help text first, or redesigning a working pattern because the team finds it dated.
- Expecting one model to serve every segment.
- Making Back "up a level" or out of the app.
- Pre-selected add-ons, hidden costs, or opt-out confirmation steps.
- Two search boxes on one page, separated only by placeholder text.

## Review checklist

- [ ] Can a user state the system's behaviour in one sentence after using it?
- [ ] Designer–user model gap researched, not assumed; conform-or-reteach decided per segment, not averaged
- [ ] Content placed where users actually look (card sort / think-aloud evidence)
- [ ] Labels, copy, docs, and demos match the model the design intends to teach
- [ ] Back exits overlays; one search entry point per page
- [ ] Cart and checkout: nothing added without an explicit, visible opt-out
- [ ] Novel patterns carry a familiar metaphor or a stated explanation

## Caveats

- **The source provides no quantitative data.** No effect sizes, sample sizes, error rates, or usability metrics are reported for any rule here; `unknown: true` where a figure would normally be cited.
- **Belief, not facts, is the core claim** — so a user model can be objectively wrong and still fully govern behaviour. Never treat a user's unverified belief as harmless.
- The three-way split of designer model, user model, and system image (Norman, 1988) is a framing model, not a measured construct.
- Whether humans reason by constructing and revising models or by applying built-in inference rules is an unresolved debate dating from the 1990s; Byrne & Johnson-Laird's position is more popular but not settled. Johnson-Laird's three-step process and the Craik / Shepard / Kosslyn / Metzler / Senge lineage are background, not evidence for any rule.
- The COVID-19 case studies in the source are qualitative and concern public-health risk communication, not interface design. They support no numeric claims here.
- Related psychology effects mentioned in passing have their own skills where applicable — use those rather than stretching this file.
- `jakobs-law.md` covers the industry-convention side of this idea (what users expect from other sites); `cognitive-load.md` covers building on familiar patterns to reduce effort.
