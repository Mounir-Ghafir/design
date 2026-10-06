---
name: millers-law
title: Miller's Law — Design Rules
description: Rules for using — and refusing to misuse — the "7 ± 2" working-memory figure. Load when chunking content, sizing a menu or option set, capping a list, or when someone proposes a five-to-seven item limit.
applies_when: [memory limits, chunking, option counts, menus and navigation, forms and drop-downs, simplification, ux review]
priority: supporting
rules: 9
---

# Miller's Law — Design Rules

## Core principle

7 ± 2 describes what a person can hold in mind at once. It is not a licence to remove anything from the product.

```
hold in mind  → 7 ± 2 items (an average; varies per person and per situation)
ship          → every option the user might need — group, don't delete
```

## Rules

### ML-01 · Seven is not a product limit
rule: 7 ± 2 is a fact about recall, not a licence to remove features or options.
do: Cite a real reason for any cap — space, thumb reach, clarity — and use Miller only to size what people must hold.
never: Cut an option, menu, or section because "Miller says seven".
because: A capacity figure describes holding information in mind, never what an interface may offer.

### ML-02 · Chunk content into smaller units
rule: Break content into smaller chunks so users can process, understand, and memorize it easily.
do: Group related items into meaningful units; the group then occupies one slot (see `chunking.md`).
never: Present an undifferentiated block of text or options and call it one chunk.
because: Chunking, not deletion, is how limited memory handles a large set.

### ML-03 · Capacity varies per person and per situation
rule: Treat 7 ± 2 as an average that moves with prior knowledge and situational context.
do: Test with high- and low-capacity users, in the distracting context the real task happens in.
never: Approve a layout because the count felt obviously fine to you.
because: Short-term memory capacity varies per individual, based on their prior knowledge and situational context.

### ML-04 · Diagnose load by its three causes
rule: Trace load to one of three causes: too many choices, too much thought required, or lack of clarity.
do: Fix the cause you found — fewer options, less inference to make, or a clearer signal.
never: Record "this screen feels busy" as a finding.

### ML-05 · Remove what doesn't serve the goal, but stop before clarity breaks
rule: Any element not helping the user achieve their goal is working against them.
do: Cut excessive colour, imagery, design flourishes, and layouts that add no value; keep the user's goal in view.
never: Overvalue simplicity at the cost of clarity.
because: Users must process and store every element, alongside the ones that actually help.

### ML-06 · Reuse patterns the user already knows
rule: Leverage common design patterns so the elements require no new learning.
do: Reuse established layouts and labels before inventing new ones.
never: Redesign a solved interaction to look original.

### ML-07 · Offload tasks onto the system
rule: Asking the user to read, remember, or decide costs load; shift it wherever possible.
do: Set defaults that can be edited, surface previously entered information, anticipate the next need.
never: Ask for information the system already holds or can reasonably derive.

### ML-08 · Minimise choices at each moment
rule: Too many choices raise load through decision paralysis; cut the count.
do: Reduce options where decisions happen most — navigation, forms, and drop-downs.
never: Present every variant at once "to be safe".

### ML-09 · Show a choice set as one group
rule: When choices are split and hidden, users read the visible ones as the complete set.
do: Display choices as a group; signal that other groups exist if you must split them.
never: Hide part of a set with no indication the rest is available.

## Hard numbers

| Constant | Value | Note |
|---|---|---|
| Working memory capacity | **7 ± 2 items** | Stated as "the average person"; no task definition, sample size, effect size, or venue given — `unknown: true` |
| Task behind the figure | Recall of "no more than about seven randomly ordered, meaningful items or chunks (letters, digits, or words)" | Described in the Cowan text appended to this scrape, which credits **Miller (1956)** |
| Competing figure, same text | **3–5 chunks in young adults**; ~3 units when verbal rehearsal is prevented; models "settle on a value of about 4" | Central capacity limit, not Miller's claim |
| Span is procedure- and person-dependent | Running span: last **3 to 5 digits**; silent rehearsal: about **2 seconds** of speech; ~**1.5** items (7-year-olds) vs ~**3.0** (older children, adults) | The same span moves with the test conditions and the user |

## Decision procedure

1. **Justify** — is a count cap in the design? Name its real reason. "Miller" is not a reason; browse-only content takes no cap.
2. **Diagnose** — is the load coming from too many choices, too much thought, or lack of clarity?
3. **Strip** — remove elements that don't serve the goal; back off the moment clarity suffers.
4. **Offload** — what still requires the user to read, remember, or decide? Move it into defaults, stored input, or anticipation.
5. **Group** — count visible options in navigation, forms, and drop-downs; is every set displayed whole?

## Anti-patterns

- "Miller says seven" used to justify removing a feature, option, or section.
- Chunking used as deletion, or simplification pushed until the interface stops being clear.
- Split or hidden choice sets with no signal that more exist.
- A new interaction where a familiar pattern would do.
- Blank required fields where defaults or saved input exist.

## Review checklist

- [ ] Every count cap justified by space, reach, or clarity — not by 7 ± 2
- [ ] Content that must be memorized or entered is chunked; browse-only content uncapped
- [ ] Non-goal elements removed; clarity intact; the user's goal still visible
- [ ] Familiar patterns and labels reused
- [ ] Editable defaults / previously entered information / anticipation used
- [ ] Options minimised at each decision point, in whole visible sets (nav, forms, drop-downs)

## Caveats

- **7 ± 2 is unsupported here**: asserted with no task definition, sample size, effect size, or venue — `unknown: true`. The only attribution in this scrape is Miller (1956), inside the appended Cowan text.
- **The figure is disputed**: competing estimates of working-memory capacity exist (7 ± 2 vs 4 ± 1 vs 3, per `chunking.md`). Treat any single number as a heuristic, not a constant.
- The scrape also appends a Cowan text arguing a **3–5 chunk** central limit under controlled conditions. That is a different claim from Miller's, not a correction of this article.
- Rules ML-04 to ML-09 are standard cognitive-load principles, **not derived from Miller's paper**. The full set lives in `cognitive-load.md`; chunk sizing in `chunking.md`.