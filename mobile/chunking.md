---
name: chunking
title: Chunking — Design Rules
description: Rules for breaking content into small, distinct, meaningful units so people can hold and enter them. Load when formatting data strings, structuring long text or video, grouping related UI, choosing a chunk size, or reviewing content layout.
applies_when: [data entry, content structuring, long text, forms and input, video and transcripts, navigation and menus, layout grouping, ux review]
priority: core
rules: 14
---

# Chunking — Design Rules

## Core principle

A chunk is a small, distinct, meaningful unit. Chunking exists to help information reach **working memory** — so chunk what must be memorized or entered, and support scanning for everything else.

```
memorized / entered  →  CHUNK   (3–6 items, conventional delimiters, autoformatted)
searched / scanned / analysed  →  SUPPORT SCANNING (headings, bold, lists, summary) — no chunk caps
```

Pair it with `progressive-disclosure.md`: chunking structures **what** sits on a screen; progressive disclosure sequences **when** it appears. Complementary, either works alone.

## Rules

### CH-01 · Chunk for memory and entry — never for search, scan, or analysis
rule: Chunk information that must be memorized or typed; do not chunk what gets searched, scanned, or analyzed.
do: Chunk IDs, license keys, card numbers, OTPs, phone numbers, and critical values read under sensory overload.
never: Paginate search results to "4 ± 1 per page" — it forces more paging, comparing, and deciding.
because: The primary purpose of chunking is enhancing working memory; searched and analysed content needs comparison, not recall.

### CH-02 · Size memory strings at 3–6 items (4 ± 1)
rule: For memory- or data-entry-oriented strings, target chunks of about 3–6 items.
do: `B17JQX84MEHP3JCXQV74QLVBE` → `B17JQ  X84ME  HP3JC  XQV74  QLVBE` — glance, hold, type, repeat.
never: Apply the count to every list on the screen.
because: Miller found ~7 loose letters, or 28 letters grouped as 7 four-letter words — chunking, not counting, is the lever.

### CH-03 · Group by meaning, not by count
rule: Chunks must be meaningful units inside the larger whole.
do: Split where a category, step, or field boundary exists.
never: Slice content every five items just to hit a number ("the rule of six").

### CH-04 · Never cap menus by citing Miller
rule: Do not limit menu or navigation items on the basis of "seven plus or minus two".
do: Keep every option visible — menus rely on recognition, not recall; structure long menus meaningfully instead.
never: Ship "max 5–7 menu items", or cap radio buttons and bullets at five or six.
because: hp.com ran 21 products per page with no problem, because users browse and search there.

### CH-05 · If you cap, justify it by something other than Miller
rule: Option-count caps can still be valid — for space, thumb reach, clarity, or layout.
do: State the real reason (e.g. mobile bottom tabs bounded by reach and width).
never: Present "seven" as a universal design law.

### CH-06 · Use the conventional, locale-correct format
rule: Chunk each data type with the most conventional format for that locale to minimise slips.
do: Credit card 4 × 4 (`4111 1111 1111 1111`); Singapore `+65-5555-5555`; Mexico `(01) 55 1234 5678`; US `(919)-555-5555`.
never: Invent a bespoke delimiter scheme for a type the user already has a format for.

### CH-07 · Autoformat — users never type separators
rule: Formatting aids scanning but makes typing harder, so the field supplies the separators.
do: Chunk digits as the user types (Apartments.com contact form), and support paste without reformatting errors.
never: Ask the user to type spaces, hyphens, or parentheses into a card or phone field.

### CH-08 · Chunk hardest where stimuli compete
rule: Apply chunking where the user must extract a value against noise and has no second chance.
do: Car navigation, phones in motion, public kiosks, emergency rooms: `Patient ID 678290234` → `6782  9023  4`, `DOB 02111973` → `02 / 11 / 1973`.
never: Assume extra visible structure helps someone who cannot slow down; ER staff enter into systems that carry no data forward and may not write anything down.

### CH-09 · Keep related things close — Law of Proximity
rule: Related elements sit together and align; unrelated elements are separated.
do: Use proximity, shared width, white space, background colour, horizontal rules, and related imagery across text, images, and controls.
never: Scatter the members of one group across a wide layout.
because: Gestalt grouping does the work before the user reads a single label.

### CH-10 · Text needs short lines and a findable main point
rule: Chunk long text into short paragraphs and give every chunk a cue to its main point.
do: ~50–75 characters per line; subheadings that contrast with body text; bold keywords; bulleted or numbered lists; a short summary paragraph.
never: Ship long lines, no subheadings, and no emphasis — that wall of text repels readers.

### CH-11 · Chunk video, transcripts, and toolbars
rule: Any content type can be chunked into clearly distinct related groups.
do: Video chapters; a transcript segmented into navigable sections, each with headings and highlights; grouped toolbars so tool location is recalled.
never: Ship a long video or a full transcript as one unbroken unit.

### CH-12 · Make chunk cues unambiguous
rule: Subtle chunking still has to say which chunk an element belongs to.
do: Place each image inside the section it illustrates.
never: Let a screenshot sit nearer the top paragraph and be read as describing it.

### CH-13 · Never judge ease of use by your own memory
rule: Capacity varies by person and by context; you cannot tell whether a design is easy.
do: Test with high- and low-capacity users, in the distracting context the real task happens in.
never: Approve a layout because the count seemed obviously fine to you.
because: "Plus-one/plus-two" and "minus-one/minus-two" people both exist, developers skew high-capacity, and context shifts the limit further.

### CH-14 · Chunk the structure, sequence with disclosure
rule: Use chunking for one screen's content structure and progressive disclosure for what appears later.
do: Chunk a screen's fields and sections; move rarely used options to later or secondary screens (see `progressive-disclosure.md`).
never: Hide a chunked item on a later screen purely to keep the current one tidy.

## Hard numbers

| Constant | Value | Note |
|---|---|---|
| Practical chunk target | **3–6 items (4 ± 1)** | Memory and data-entry strings only; practitioner judgment |
| Miller (1956) | 7 ± 2 items (5–9) | Short-term memory — not a menu or page limit |
| Broadbent (1975) | 4–6 items | Miller's contemporary |
| LeCompte (1999) | as few as 3 items | |
| NN/g | 3–6, "don't fixate" on any number | |
| Text line length | 50–75 characters | |
| Credit card | 4 × 4 digits | `4111 1111 1111 1111` |
| Phone formats | `+65-5555-5555` (SG), `(01) 55 1234 5678` (MX), `(919)-555-5555` (US), `+1-919-555-2743` (NN/g) | Locale convention |
| Menu item caps | **No limit from Miller** | Recognition-based; hp.com ran 21 per page |

## Decision procedure

1. **Gate** — will this content be memorized or typed, or searched, scanned, or analyzed? Memorize/enter → chunk it. Search/scan/analyze → support scanning and comparison instead, and impose no chunk caps.
2. **Purpose** — name the task per chunk: what must the user hold in memory or transcribe?
3. **Size** — for memory strings only, aim at ~3–6 items per chunk.
4. **Format** — use the locale's conventional delimiters (card 4 × 4, phone by country, dates).
5. **Entry** — verify autoformatting, paste, and error handling; no typed separators.
6. **Structure** — proximity, alignment, white space, background, rules; text at 50–75 characters with headings, bold, lists, summary.
7. **Ambiguity** — check every image and cue attaches to one chunk only.
8. **People** — retest with varied memory capacity and in the real distracting context.

## Anti-patterns

- Capping menus, nav, radio buttons, or bullets at five to seven "because Miller".
- Paginating search results to four or five per page.
- Making users type separators into phone or card fields.
- Counting to a number instead of grouping by meaning.
- Wall-of-text pages: long lines, no subheadings, no highlighted keywords.
- Chapters or transcript segments with no headings or emphasis to call out main ideas.
- A screenshot floating between chunks and read as belonging to the wrong one.
- Signing off a design because the item count felt obviously fine to you.

## Review checklist

- [ ] Purpose classified: memorize/enter vs search/scan/analyze (CH-01)
- [ ] Memory and entry strings chunked to ~3–6 items
- [ ] Chunks grouped by meaning, not by count
- [ ] Locale-conventional delimiters (card 4 × 4, phone by country, dates)
- [ ] Inputs autoformat; users type no separators
- [ ] Text: short paragraphs, 50–75 character lines, white space
- [ ] Headings contrast; keywords highlighted; lists and summaries present
- [ ] Related elements close and aligned; unrelated separated
- [ ] Video and transcripts segmented with headings and emphasis
- [ ] No menu, list, or control-group cap justified by "seven plus or minus two"
- [ ] Any real cap justified by space, reach, or clarity
- [ ] Critical data chunked for the real distracting context (ER, car, on the go)
- [ ] Tested with varied memory capacity, not only the team

## Caveats

- **Capacity is disputed and unresolved**: 7 ± 2 vs. 4–6 vs. 3 vs. 3–6 "don't fixate". The practical 4 ± 1 figure is **practitioner judgment, not a study result**.
- **No empirical data reported**: no task definitions, sample sizes, or effect sizes were given for any capacity estimate, and no independent basis for 4 ± 1 is stated.
- Case-study observations (ApartmentGuide.com, BBC, MailChimp, hp.com) are **anecdotal single-user impressions**, not controlled experiments.
- The license-key figure's chunk-size labels are self-inconsistent with its prose; follow the prose (five-character chunks).
- Misapplied chunking caps have been called a "superstition" (Bailey 2000) and an "urban legend" (Jones 2002) — the criticism targets the caps, not the technique.
- NN/g recommends **against** displaying field labels inside input boxes, even with autoformatting.
- Some examples date to mid-2000s products. The principles hold; the specific products are historical.
- Sibling skill `progressive-disclosure.md` covers *when* things appear. The two are complementary; either can be used alone.