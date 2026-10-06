---
name: postels-law
title: Postel's Law (Robustness Principle) — Design Rules
description: Rules for being liberal in what you accept from users and conservative in what the system sends back, plus the related rule of least power. Load when building forms, input fields, validation, parsing, dates and numbers, addresses, error feedback, or choosing front-end technologies.
applies_when: [form design, input fields, validation, parsing and normalisation, dates and numbers, addresses, error feedback, technology choice]
priority: supporting
rules: 15
---

# Postel's Law (Robustness Principle) — Design Rules

## Core principle

Be liberal in what you accept, and conservative in what you send.

```
human face   = liberal        → accept any input the user gives; be empathetic, flexible, tolerant
machine face = conservative   → treat input as untrusted, validate it, normalise it, emit clean canonical formats
```

The application owns the translation: accept human input in a variety of natural forms and convert it to what the computer needs. Boundaries still exist — define what is reasonable in each context and respond with clear feedback when input exceeds them. A related principle with the same engineering roots: choose the least powerful technology for the purpose.

## Rules

### POL-01 · Two faces, one application
rule: Give the interface a liberal human face and a conservative machine face.
do: Accept whatever users plausibly provide, then validate and normalise at the machine boundary.
never: Show system internals in UI language, or let unvalidated user data reach downstream systems.

### POL-02 · Be conservative in what you send
rule: Send the user only what the task demands — no extra fields.
do: Cut every inessential form field; shorter is better.
never: Add fields "just in case".
because: The more effort a form needs, the less likely users are to complete it.

### POL-03 · Be liberal in what you accept
rule: Accept common variations of the same answer.
do: Treat CA and California as the same state and store one consistent format.
never: Reject a legitimate variation because a single exact format was expected.

### POL-04 · The application owns the translation
rule: The system, not the user, converts human input into machine requirements.
do: Design input around human needs and preferences first, then translate internally to meet the system's needs.
never: Ask users to feed the machine — internal codes, exact syntax, or format specifications.

### POL-05 · Define boundaries, then give feedback
rule: Define what input is reasonable in each context; everything beyond that boundary gets clear feedback.
do: Sanity-check translations and report clearly when input is incomprehensible or out of the expected range.
never: Accept anything-and-everything with no boundary, or silently coerce out-of-range values.

### POL-06 · The machine face is conservative
rule: Validate the format of everything the system sends to downstream systems, treating user input as untrusted by default.
do: Emit clean, canonical, conventional formats.
never: Forward user input verbatim to another system without checking it.

### POL-07 · Numbers: normalise instead of dictating
rule: Accept how people naturally write amounts and normalise to a single canonical value.
do: Parse "one", "1", "1.00", "$10.00" or "10" into one decimal value the system can use.
never: Prompt "use digits only, no spaces or dashes" before the user has even typed.

### POL-08 · Dates: accept, then confirm
rule: Accept anything that resembles a date and confirm the interpretation rather than rejecting the format.
do: Parse natural date language with a library; flag a problem only when interpretation fails or falls out of bounds.
never: Impose rigid formatting with required leading zeroes where an ordinary date is easily understood.
because: Dates are a special case of numbers, and for a person context carries meaning that rigid formats strip away.

### POL-09 · Accept-and-normalise beats keystroke policing
rule: Prefer accepting raw input and normalising it over input masks that block characters as the user types.
do: Take whatever was entered, process it into the required type server-side, then sanity-check the result.
never: Filter keystrokes on keyup/blur in a way that places the computer's rules in the user's way.

### POL-10 · Confirm high-stakes interpretations
rule: When the normalised value drives a consequential action, confirm the interpretation before acting.
do: Read the result back and ask for confirmation even when the value looks normal — e.g. a donation amount.
never: Reduce text to a number and act on it silently when the result could be unexpected and problematic.
because: Overly aggressive reduction of text input to a number leads to unexpected results precisely when the value matters.

### POL-11 · Addresses: human structure over database columns
rule: Capture addresses the way people write them, and only as much structure as the data truly requires.
do: Consider a single textarea when the address is only ever used in full; use a standardisation service when discrete fields are a real business need.
never: Model address fields on a database schema with no thought for international, non-US, or complex addresses.

### POL-12 · Least power and nothing unexplained
rule: Choose the least powerful technology suitable, and keep no code you cannot justify.
do: Solve at the lowest workable point in the stack — CSS animation before JavaScript, HTML input types and `required` before JS validation, a real element before an ARIA role on a div — and cut boilerplate additions.
never: Pick a powerful technology out of familiarity, or add premature optimisation for problems you don't yet have (YAGNI).
because: Power comes with a price — complexity, trickier to use, harder to swap out; the simpler solution is less fragile, more foolproof, and just works.

### POL-13 · Stress-test with difficult data
rule: Design against the worst data you will actually receive, not ideal placeholder data.
do: Dig through real data for the worst cases — longest and shortest text, wild length variations, missing or unusual input; if you can handle the worst, the common cases are a breeze.
never: Evaluate a screen only with your own name and the most flattering viewport and copy.

### POL-14 · Common case first, long tail handled
rule: Make the typical flow flawless and handle the remaining edge cases with an extra feedback loop.
do: Spend the effort to build graceful, respectful edge-case handling while keeping the common case fast.
never: Let the long tail "wag the dog" — slow down or clutter the common case for rare exceptions.

### POL-15 · Feedback like a courteous clerk
rule: When input is not understood or out of bounds, clarify and read back rather than punish.
do: Ask for clarification the way an attentive human order-taker would; confirm the end result before proceeding.
never: Greet users with a rigid list of instructions and berate them when validation fails.

## Hard numbers

| Constant | Value | Note |
|---|---|---|
| Principle origin | 1980 | Early TCP specification by Jon Postel, per source; the source credits it with running the internet for more than three decades |
| Empirical evidence | `unknown: true` | Source gives no measured error-acceptance effects, sample sizes, or controlled results |
| Common-case / long-tail split | ~95% / remaining 5% | Stated judgment: make the common case flawless and build a feedback loop for the rest — not a measurement |
| Stated title-length case | shortest 8 chars; longest > 320; handful over 80 | From one list-page design case in the source — not a general limit |
| Localization length rule | test text at 2× source length; up to 80 languages | Stated practice for long languages like German, and a stated Mozilla context (W3C ratios referenced) |
| Unix time basis | seconds since Jan 1, 1970 | Dates are a special case of numbers, per source |
| Verbatim accepted forms | one, 1, 1.00, $10.00, 10; 1/1/1970, Thu, Thursday, tomorrow, next Friday, 11 April; MM/DD/YYYY vs CA vs California | Human-equivalent values that are different data types to a computer; accept, normalise, confirm, and still show the most reliable patterns |

## Decision procedure

Apply Postel's Law per data type and layer, in this order:

1. **What you send** — list the fields and options the screen sends the user. Delete every inessential one (POL-02).
2. **What you accept** — for each remaining input, list the natural human variations (formats, spellings, abbreviated forms) and design to accept all of them (POL-03).
3. **Who translates** — ensure the system, not the user, converts input to a canonical format (POL-04, POL-07, POL-08).
4. **Boundaries** — define what input is reasonable in this context; whatever is outside gets feedback, not silent repair (POL-05).
5. **Machine face** — validate and normalise everything before it leaves the system; nothing downstream trusts your input (POL-06).
6. **Protect the user's intent** — on high-stakes values such as donation amounts, confirm the interpretation before acting (POL-10).
7. **Errors and edge cases** — build one extra feedback loop for the long tail, delivered like a courteous clerk (POL-14, POL-15).
8. **Technology** — pick the least powerful technology that suffices, with no code without an explainable reason (POL-12).
9. **Stress-test** — re-run the screen against difficult data, not ideal placeholders (POL-13).

## Anti-patterns

- A credit card field demanding "digits only, no spaces or dashes" — the clerk knows a number when she hears one.
- Rejecting natural variation: "CA" when the system wanted "California", or "1/1/1970" when leading zeroes are missing.
- Keystroke-policing input masks that block characters before the user finishes typing.
- Silently reducing "$10.00"-style text to a number on a consequential action with no confirmation.
- Address forms shaped purely by CRM or database columns, ignoring international and complex addresses.
- JavaScript doing what HTML or CSS already does; ARIA roles on a div when a real element exists; boilerplate code kept only because "it's in the standard toolkit".
- Instructions-then-berating validation: strict rules up front, blame on failure.

## Review checklist

- [ ] Every field sent to the user is necessary; no "just in case" fields
- [ ] Each input accepts reasonable human variations and is normalised centrally
- [ ] Boundaries defined; clear, courteous feedback when input is out of range
- [ ] High-stakes values confirmed with the user after interpretation (donations, purchases)
- [ ] Everything sent downstream is validated; user input treated as untrusted
- [ ] Numbers, dates, and currency normalised instead of forcing entry formats
- [ ] Address capture serves the human and only the needed level of detail
- [ ] Least-power choice made lower in the stack; no unexplainable code or premature optimisation
- [ ] Screens stress-tested with difficult data (long/short text, wild variation)
- [ ] Edge cases have a graceful, respectful fallback rather than a wall of instructions

## Caveats

- This is a classic principle of internet design with engineering provenance (RFC-era guidance — 1980 TCP spec, per source), extended to UX by practitioner articles; the source gives **no empirical evidence** (no measured error-acceptance effects, sample sizes, or controlled studies) → `unknown: true`.
- **Recorded tension, unresolved**: liberal acceptance can hide bugs, and aggressive normalisation can produce unexpected results. The source resolves this by confirming important interpretations rather than narrowing input — do the same, and surface genuinely ambiguous input instead of guessing.
- Parsing human language into structured data won't always work and libraries have limits; provide examples of the most reliable accepted patterns and an alternate path for cases that won't parse (e.g. complex addresses).
- The 95%/5% split, the 8/320/80-character case, the 2× length rule, and the 80-languages context are **cases and judgments stated in the source**, not general findings.
- The source does not cover search typo tolerance, URL parameters, or copy-paste tolerance — do not import specifics for those here.
- Least power is related but distinct: KISS applies within a technology; least power chooses between technologies.
- Siblings: `cognitive-load.md` covers defaults and offloading; `clean-code.md` and `code-structure.md` cover engineering hygiene; the mobile commerce patterns skill covers input methods such as sliders vs text fields.