# Chunking & Progressive Disclosure — Structured Knowledge Base

> **Purpose:** Authoritative reference on two complementary information-design techniques: **chunking** (grouping information into meaningful units) and **progressive disclosure** (sequencing information and actions to reduce overwhelm). Covers definitions, origins, when to use and *not* use each, implementation rules, evidence limits, and examples.
> **Audience:** Downstream AI agents and human designers, researchers, and product teams.
> **Companion documents:** `mobile_app_design_guide.md`, `choice_overload_guide.md`, `aesthetic_usability_effect_guide.md`.
> **Conventions:**
> - `> **RULE:**` = non-negotiable guidance. `> **KEY TAKEAWAY:**` = high-value summary.
> - Research claims are **source-reported**.
> - **[Source note]** = ambiguity or inconsistency in the raw material.
> - Sections marked **(Derived)** are implications synthesized from the source, not direct source claims.

---

## Table of Contents

1. [Overview & Relationship Between the Two Techniques](#1-overview--relationship-between-the-two-techniques)
2. [Key Takeaways](#2-key-takeaways)
3. [Part A — Chunking: Definitions & Origins](#3-part-a--chunking-definitions--origins)
4. [Chunk Size & Working Memory](#4-chunk-size--working-memory)
5. [When to Use Chunking — and When Not To](#5-when-to-use-chunking--and-when-not-to)
6. [Chunking Text & Data Strings](#6-chunking-text--data-strings)
7. [Chunking Multimedia & Layout](#7-chunking-multimedia--layout)
8. [Chunking Case Studies](#8-chunking-case-studies)
9. [The "Magical Number Seven" Myth](#9-the-magical-number-seven-myth)
10. [Part B — Progressive Disclosure: Definitions & Origins](#10-part-b--progressive-disclosure-definitions--origins)
11. [Evidence Limits & Evolving Definitions](#11-evidence-limits--evolving-definitions)
12. [Progressive Disclosure Techniques & Examples](#12-progressive-disclosure-techniques--examples)
13. [Nielsen's Guidelines for Progressive Disclosure](#13-nielsens-guidelines-for-progressive-disclosure)
14. [Research Method: Basing Disclosure on Observed Behavior](#14-research-method-basing-disclosure-on-observed-behavior)
15. [Pros, Cons & Misuse](#15-pros-cons--misuse)
16. [Application to Mobile App Design (Derived)](#16-application-to-mobile-app-design-derived)
17. [Decision Rules (IF → THEN)](#17-decision-rules-if--then)
18. [Checklists](#18-checklists)
19. [Key Facts Reference](#19-key-facts-reference)
20. [People & Sources Reference](#20-people--sources-reference)
21. [Glossary](#21-glossary)
22. [Source Notes & Caveats](#22-source-notes--caveats)

---

## 1. Overview & Relationship Between the Two Techniques

| Dimension | **Chunking** | **Progressive Disclosure** |
|---|---|---|
| **Core idea** | Break information into small, distinct, meaningful groups | Defer advanced/rarely used information and actions to later or secondary screens |
| **Primary goal** | Enhance scanning, comprehension, and **working-memory** retention | Reduce overwhelm; make apps easier to learn and less error-prone |
| **Operates on** | Content structure (how information is grouped and presented) | Interaction sequencing (what is shown when; simple → complex) |
| **Origin** | George A. Miller, 1956 (cognitive psychology) | Software usability; Carroll & Rosson (IBM), early 1980s |
| **Key risk** | Misapplied as a blanket "simplicity" rule (e.g., "max 5–7 menu items") | Over-constraining, hiding what users need, assuming importance without evidence |
| **Shared benefit** | Manages cognitive load; helps users "chunk the task" into steps that match expectations | |

> **KEY TAKEAWAY:** Chunking structures *what* users see together; progressive disclosure sequences *when* they see it. Both exist to align information with how people process content, and both work best when grounded in observed user behavior.

---

## 2. Key Takeaways

1. Chunking lets users **scan** content, identify what aligns with their goals, and process it faster.
2. Structuring content into **visually distinct groups with a clear hierarchy** aligns with how people evaluate digital content.
3. Chunking communicates **underlying relationships**: group content into distinctive modules, apply rules/separators, provide hierarchy.
4. The **primary purpose of chunking is enhancing working memory** — it suits information that must be remembered or entered, not information that must be searched, scanned, or analyzed.
5. Do **not** cite Miller's "seven" to justify menu-size limits; menus rely on **recognition, not recall**.
6. Chunk size for memory-oriented tasks: roughly **3–6 items (4 ± 1)** is ideal for interaction design.
7. Progressive disclosure **defers advanced or rarely used features** so apps are easier to learn and less error-prone.
8. Progressive disclosure is about **ramping users from simple to complex actions**, not merely from abstract to specific information.
9. Empirical support for progressive disclosure is **limited**; base it on **observed user behavior**.
10. Poorly applied disclosure (forced waiting, hidden essentials, over-simplification) backfires.

---

## 3. Part A — Chunking: Definitions & Origins

### 3.1 Definitions

| Term | Definition |
|---|---|
| **Chunk (cognitive psychology)** | A piece or part of something larger; an **organizational unit in memory**. Chunks vary in activation level (easier or harder to recall) |
| **Chunking (psychology)** | Recoding information so related concepts are grouped into one chunk; commonly a memorization technique |
| **Chunk (UX)** | A small, distinct unit of information, as opposed to an undifferentiated mass of atomic items |
| **Chunking (UX)** | Creating meaningful, visually distinct content units that make sense within the larger whole; breaking long strings/content into units easier to commit to working memory and scan |
| **General definition** | A process by which individual pieces of an information set are broken down and then grouped together into a meaningful whole |

- Chunking works across mediums: **text, sounds, pictures, and video**.

### 3.2 Origin

- Introduced in George A. Miller's 1956 paper, *"The Magical Number Seven, Plus or Minus Two: Some Limits on Our Capacity for Processing Information."*
- Context: information theory was beginning to be applied in psychology. Miller observed that some cognitive tasks fit a "channel capacity" model (roughly constant capacity in bits), but **short-term memory did not**.
- Miller's key insight (per NN/g): **chunk size does not seem to matter** — people could remember ~7 individual letters, or **28 letters if grouped into 7 four-letter words** (each unrelated letter is a chunk in the first case; each word is a chunk in the second).

### 3.3 Canonical Example: Phone Numbers

| Form | Example | Effect |
|---|---|---|
| Unchunked | `16047559385` | Hard to remember |
| Chunked | `1 604 755 9385` | Easier; more logical chunks |
| Chunked + delimiters | `1 (604) 755-9385` | Even more effective |

---

## 4. Chunk Size & Working Memory

### 4.1 Research Positions on Capacity

| Source / Researcher | Estimated capacity | Note |
|---|---|---|
| **Miller (1956)** | **7 ± 2** items (5–9) | Original; chunking enhances working memory most effectively for strings broken into 5–9 items |
| **Broadbent (1975)** | **4–6** items | Miller's contemporary |
| **LeCompte (1999)** | As few as **3** items | |
| **Practical guidance for interaction design** | **3–6** items (**4 ± 1**) | Judged ideal in practice |
| **Other researchers (NN/g)** | Anywhere from **3 to 6** | |

> **RULE:** For memory- or data-entry-oriented strings, target chunks of **about 3–6 items (4 ± 1)**.

### 4.2 Individual & Contextual Variation

- Capacity varies across individuals ("plus-one/plus-two" vs. "minus-one/minus-two" people), a cause of variability in user performance.
- Developers may be disproportionately high-capacity (people with high capacity are drawn to careers requiring many items in memory) → **they may misjudge ease of use** for typical users, who may struggle with what developers find easy.
- Short-term memory limits are further affected by **context**: where users are and what else is happening around them.
- **Therefore you cannot judge ease of use by whether you personally find a design easy.**

### 4.3 Worked Example: License Key (Figure 2)

Random example key: `B17JQX84MEHP3JCXQV74QLVBE` (25 characters)

| Format | Example | Chunk description (as labeled in source) |
|---|---|---|
| Unchunked | `B17JQX84MEHP3JCXQV74QLVBE` | Chunking that is > 7 ± 1 |
| Two chunks | `B17JQX84MEHP3JC  XQV74QLVBE` | Chunking that is = 7 ± 1 |
| Five chunks of five | `B17JQ  X84ME  HP3JC  XQV74  QLVBE` | Chunking that is = 4 ± 1 |

- Best for most people: the **five-character chunks** — quick glance at one chunk, hold it in working memory, enter it into the field, repeat for the remaining four chunks.
- **[Source note]** The labels in the original Figure 2 are terse and somewhat inconsistent with the text (they refer to chunk *size*, not chunk count). Interpret by the accompanying explanation: shorter chunks (~5 characters) support quick glance → memorize → enter cycles.

---

## 5. When to Use Chunking — and When Not To

### 5.1 Core Principle

> **RULE:** The primary purpose of chunking is **enhancing working memory**. Do **not** chunk information that must be **searched, scanned, or analyzed**.

### 5.2 Decision Table

| Use chunking when… | Do NOT use chunking when… |
|---|---|
| Specific information must be **memorized** for later use | Information must be **searched, scanned, or analyzed** (e.g., search results) |
| Users must **transcribe/enter** information (license keys, IDs, card numbers) | Users can rely on **recognition** with all options visible (menus) |
| The interface must **compete with other stimuli** for attention/working memory | Your only justification is "simplicity," "legibility," or "uncluttered page design" |
| E-learning applications (aid memorization) | You are applying arbitrary limits like "rule of six" |
| High-distraction contexts: car navigation, cell phones, public kiosks, emergency rooms | |
| Users need to scan long text easily (short paragraphs, hierarchy) | |

### 5.3 The Search-Results Example

- Constraining search results to **five per page (4 ± 1)** would make users spend *more* time moving back and forth between pages (searching), comparing definitions (scanning), and deciding on the best one (analyzing).
- Search results need not be memorized → **do not chunk them this way**.

### 5.4 Misapplications of Chunking (Invalid Uses)

Novice practitioners often (Bailey 2000):
- Limit menu bars to 5–6 items.
- Place only 5–6 items in a pull-down menu.
- Apply "the rule of six" to PowerPoint slides or bulleted lists.
- Never place more than 5–6 radio buttons or checkboxes together.

**Why invalid:** Miller-type "limits on our capacity for processing information" are not a proper justification for these constraints. Misapplication led some to dismiss chunking as a "superstition" (Bailey 2000) or "urban legend" (Jones 2002).

> **KEY TAKEAWAY:** Such constraints may still be valid **for other design reasons** — just not on the basis of Miller's memory research.

### 5.5 Emergency-Room Scenario (Figure 3)

Health practitioners in emergency rooms often:
- Are barraged by visual and auditory stimuli (ringing phones, conversation, rapid movement).
- Have only moments to look at an interface and extract/memorize key information.
- Must enter information into **disparate systems** without referring back to the source.
- Use **legacy systems** that can't carry data from one screen to the next.
- Are **not allowed to write information down** due to privacy legislation.

| Column A — Without chunking | Column B — With chunking |
|---|---|
| `Patient ID:678290234` | `Patient ID   6782  9023  4` |
| `Name: Joe Smith` | `Name: Joe Smith` |
| `DOB:02111973` | `DOB 02 / 11 / 1973` |

Result: Column B makes it much easier and faster to focus on and memorize the Patient ID under sensory overload.

**Summary (Harrod):** Applied in the proper context, chunking is a subtle but powerful principle; its primary goal is helping when information must be committed to working memory, especially against competing stimuli.

---

## 6. Chunking Text & Data Strings

### 6.1 Text Chunking Methods

| Method | Guidance |
|---|---|
| **Short paragraphs** | Separate with white space; avoid intimidating "walls of text" |
| **Short line length** | About **50–75 characters** per line |
| **Clear visual hierarchy** | Group related items together |
| **Distinct groupings in strings** | Passwords, license keys, credit-card/account numbers, phone numbers, dates |

- Users appreciate chunked text; chunking enables **skimming**, users' preferred way to read online.

### 6.2 Data-String Formatting Rules

> **RULE:** Use the **most conventional format for each data type** to minimize user slips. Formats vary by country.

| Data type | Chunked format example | Note |
|---|---|---|
| Credit card | `4111 1111 1111 1111` (4 × 4) vs. `4111111111111111` | Standard is 4 chunks of 4 digits |
| Phone (generic example) | `14487324534` vs. `1 (448) 732 4534` | |
| Phone — Singapore | `+65-5555-5555` | |
| Phone — Mexico | `(01) 55 1234 5678` | |
| Phone — United States | `(919)-555-5555` | |
| Phone (NN/g definition example) | `+1-919-555-2743` vs. `19195552743` | |

### 6.3 Input Handling

> **RULE:** Formatting aids scanning but makes typing harder → **users should not have to type formatting characters**. Use **autoformatting**: input fields automatically chunk digits as the user types.

- Example: Apartments.com contact form chunks the phone number automatically as digits are typed. (NN/g still recommends **against displaying field labels inside input boxes**.)

### 6.4 Supporting Scanning (Beyond Splitting Text)

Chunking alone is insufficient — make the **main point of each chunk** easy to find:

- **Headings and subheadings** that clearly contrast with body text (bolder, larger).
- **Highlighted keywords** (bold, italic).
- **Bulleted or numbered lists.**
- A **short summary paragraph** for longer text such as articles.

---

## 7. Chunking Multimedia & Layout

### 7.1 Core Rule

> **RULE:** Keep **related things close together and aligned** (Gestalt **Law of Proximity**). Use background colors, horizontal rules, and white space to distinguish what is related from what isn't.

Applies to text, images, graphics, videos, buttons, and other elements.

### 7.2 Techniques

| Technique | Use |
|---|---|
| **Proximity** | Relate elements by closeness |
| **Alignment / shared width** | Creates invisible grouping (e.g., subheading and paragraph in the same width container) |
| **White space / negative space** | Separates chunks |
| **Background color** | Delineates chunks (e.g., product cards) |
| **Horizontal rules** | Divide sections |
| **Related imagery** | Reinforces section boundaries |
| **Video chapters** | Chunk video into individually accessible chapters/topics |
| **Toolbar grouping** | Group related tools in crowded application toolbars to aid recall of location |
| **Transcript segmentation** | Chunk a long video into navigable segments |

### 7.3 Content-Type Notes

- Any content can be chunked; the principle is dividing information into **clearly distinct groups of related content**.

---

## 8. Chunking Case Studies

| Site | Observation | Lesson |
|---|---|---|
| **ApartmentGuide.com** (negative) | Homepage wall of text: long lines, no highlighting, no subheadings. A user said it was messy and not worth reading ("Busy," "wordy," "unwelcoming") | Unchunked text repels users |
| **BBC** (positive) | Short paragraphs, generous white space, subheadings, short summary; each topic subheading has a subtle horizontal rule and related photo. A user judged it "nicely split up" and easy to read, then read the whole article | Effective chunking increases willingness to read |
| **MailChimp** (subtle) | Minimalist; chunks indicated by proximity and shared width (subheading and paragraph within a 500px-wide container). Harder to tell which chunk describes the central screenshot (it sits closer to the top paragraph) | Subtle chunking cues can leave ambiguity; be deliberate about image association |
| **TED.com** (mixed) | Interactive transcript chunks a long video into navigable segments; lacks subheadings/highlights to call out main ideas | Add headings and emphasis to chunked segments |
| **hp.com** (positive) | Subtle background color and negative space distinguish each laptop chunk; **21 options on one page** work fine because users browse/search rather than memorize | Number of chunks can exceed 7 when recognition/scanning is the task |
| **Apartments.com** (positive) | Auto-chunks phone input; phone number chunked in header | Autoformat inputs |

---

## 9. The "Magical Number Seven" Myth

| Common misconception | Correct interpretation |
|---|---|
| Humans can only process seven chunks at any time | Miller found ~7 chunks in **short-term memory**; the interesting point was that **chunk size didn't matter** |
| Global navigation must not exceed seven items | Menus rely on **recognition**, not recall; all options stay visible, so there is **no usability gain** in limiting to seven |
| "Seven" is a hard design law | Miller titled his paper "Seven, **Plus or Minus Two**"; other researchers suggest **3–6** |

> **RULE:** Do **not** limit menu items solely because of Miller's number. Menus may exceed seven items if the options are structured in a **meaningful** way.

> **KEY TAKEAWAY (for UX):** Human short-term memory is limited, so if you want users to retain more, **pack information into meaningful chunks**; don't ask users to hold more than a few pieces of information in short-term memory at once; don't get hung up on seven.

---

## 10. Part B — Progressive Disclosure: Definitions & Origins

### 10.1 Definitions

| Source | Definition |
|---|---|
| **Spillers (2004)** | Interaction design technique that **sequences information and actions across several screens** to reduce feelings of overwhelm |
| **Nielsen (2006)** | Technique that "**defers advanced or rarely used features to a secondary screen**, making applications easier to learn and less error-prone" |
| **Formal definition** | Move complex and less frequently used options **out of the main UI and into secondary screens** |
| **Spillers' maxim** | "Make more information available within reach, but don't overwhelm the user with all the features and possibilities" |
| **Nielsen (2002)** | Show a small number of features to less experienced users to lower the hurdle of getting started, while keeping a larger set available for experts to call up |
| **Nielsen (2000)** | "Best tool so far": show basics first; allow access to expert features after users understand; don't show everything at once |
| **Forrester (2003)** | Reduces interaction complexity by providing interface **layers that incrementally introduce content and function** based on the customer's progress through the application |

### 10.2 Nature of the Technique

- Reveals only the essentials; helps users manage the complexity of feature-rich sites/apps.
- Follows the notion of "abstract to specific," but is **not only about level of detail** — it is about **sequencing behaviors/interactions**, "ramping up" users from **simple to complex actions or tasks**.

### 10.3 History

- Around since at least the **early 1980s**.
- Attracted UI specialists via **John M. Carroll and Mary Rosson's** lab work at IBM (Carroll 1983): hiding advanced functionality early led to **increased success in using it later**.
- The approach dubbed **"training wheels"** (Carroll 1984) is one of the only references validating the technique.
- Historically from **software usability**; easier to apply to software than the Web.

---

## 11. Evidence Limits & Evolving Definitions

### 11.1 Empirical Research Is Lacking

| Point | Detail |
|---|---|
| Carroll & Rosson (1997) | No empirical evidence exists on the effectiveness of progressive disclosure; "training wheels" studied only a **single application (word processor)** and a **single interface style (menu-based control)** |
| Independent usability studies | Show appropriate usage is valuable, but **more empirical research is required** |
| Weakness of foundational studies | Based on **static desktop word-processor** metaphors and a user base unlike today's users, who are exposed to dozens of interfaces and sites |
| Practitioner thinking | Framed in early-1990s terms |

### 11.2 Software vs. Web Contexts

| Factor | Software | Web |
|---|---|---|
| Interaction model | Dialogues and "fixed state" interactions | Chaotic, randomized, dynamic; hypertext is **non-linear** |
| Audience | Predictable and targeted; predictable learning styles | Anyone (particle physicist, teen, grandmother); varied learning styles, comfort, expectations |
| Guidelines | More available | Few web-based progressive-disclosure guidelines exist |

### 11.3 Staged Disclosure

- Nielsen (2006) introduced **"staged disclosure"**, a hybrid characterized by the **wizard (back–next)** technique.
- As with other applications, **context of use can paralyze effectiveness**.

### 11.4 New Definitions Needed

Evolving interfaces demand new thinking about accessible, elegant formats of progressive disclosure across all displays and devices. Examples cited: Microsoft Office 2007 **task ribbons**, Apple Leopard **"stacks" and "spaces"**, **AJAX** "instant add/edit/delete" interfaces, and iPhone **pinch-and-zoom** interactions.

### 11.5 Emerging Implementation Advances (JavaScript/AJAX)

Promise for: extending **discoverability**; providing dynamic "smart" help; **shallower navigation** (less drill-down); showing related details or content (Spillers 2007).

---

## 12. Progressive Disclosure Techniques & Examples

### 12.1 The "Teaser" (Purest Form)

A good teaser can include:
- A **sample** of what is next.
- An **introductory task** that is most common.
- A **high-level view** of what is expected.
- A **wizard** that walks the user through the task (staged disclosure).
- A **button** leading to more advanced functions (e.g., editing).

### 12.2 Web Patterns

| Pattern | Notes |
|---|---|
| "Learn more" link | |
| "Related topics" link | |
| Overview of account information on the first screen | |
| "View more details" link | |
| "Advanced search" link | |
| Internet configurator tools | Provide the right level of detail at the right time; minimize jarring transitions (Forrester 2003) |

> **Web rule of thumb:** "Only show information that is relevant to the task the user wants to focus on, on any given page."

### 12.3 Anti-Examples (Misuse)

| Example | Problem |
|---|---|
| News article split across **four screens** with a "Next Page" link | Serves **advertising objectives** (banners per page), not the user's task |
| Site forcing users through **4–5 overview/benefit pages before revealing price** | Doesn't accommodate **free-form exploration**, typical web behavior; assumes reading builds acceptance of price |
| **Microsoft Word 2003** auto-hiding extra menus (down arrows at bottom of menus) | Users must repeatedly activate hidden items even if used often; Word 2007 moved to the **task ribbon** instead |

---

## 13. Nielsen's Guidelines for Progressive Disclosure

(Nielsen 2006, expanding on earlier 2000/2002 statements)

| # | Guideline | Detail |
|---|---|---|
| 1 | **Get the right split** between initial and secondary features | The core challenge; requires knowing real usage |
| 2 | **Make progression obvious** from primary to secondary levels | Increase **information scent**; make the **target area visible** |
| 3 | **Avoid multiple ways** to reach secondary options | Reduces confusion |
| 4 | **Consider multiple secondary displays**, each revealed by a different control on the initial display | Rather than one catch-all secondary screen |

---

## 14. Research Method: Basing Disclosure on Observed Behavior

> **RULE:** Base what is disclosed, and when, on **actual observed user behavior**. **Ad-hoc use of progressive disclosure yields inaccurate results.**

| Element | Detail |
|---|---|
| Origin of insight | **Field studies or task analysis** (user observation of tasks); observe workflow outside your technology |
| What you learn | How users prioritize and sequence tasks and problem-solving aids |
| Analogy | Observing eating habits: whether someone views dessert/drinks menus at start, middle, or end; whether they eat salad or main first; whether they drink before or after |
| Best use | As a **contextual research tool**: ethnographic insights → design decisions based on deep familiarity with what aids users' **sense-making** |
| Fallacy prevention | Tie disclosed tasks/information to observed behavior |

---

## 15. Pros, Cons & Misuse

### 15.1 Design Principles Embraced

- Advocate for users with different needs (experienced and inexperienced).
- Limit what is shown on a screen.
- Give access to the "low-hanging fruit"; de-emphasize infrequent tasks.
- Show users only what they need, when they need it.
- Focus the interface on making users **successful at the start**.

### 15.2 Benefits

| Benefit | Detail |
|---|---|
| Removes exploration burden | Users needn't explore/examine the whole interface first |
| Task chunking | Lets users chunk the task in a sequence matching their expectations |
| Lower cognitive load | Reduces cognitive overload |
| Efficiency | Increases efficiency and ease of use |
| Orientation | Users orient to a screen, work out what to do, and do it in steps revealing complexity gradually |

### 15.3 Dangers

| Danger | Detail |
|---|---|
| **Forced waiting** | Users must wait until the designer is ready to show content |
| **Repeat-use friction** | Repeat users may not need progressive disclosure (depends on task) |
| **Over-constraining** | "Dumbing down" or hiding too much |
| **Unverified assumptions** | Assuming you know the most popular/common/important task |
| **Inappropriate usage** | Hidden items users repeatedly re-activate (Word 2003) |

---

## 16. Application to Mobile App Design (Derived)

> Links source principles to guidance in `mobile_app_design_guide.md` and `choice_overload_guide.md`. These are design implications, not source claims.

| Source principle | Mobile application |
|---|---|
| Chunk long strings | Auto-format card numbers, phone numbers, OTP/verification codes, license/serial keys; **no typing of separators** |
| Locale-conventional formats | Adapt phone/date/card formats per country/locale |
| Short paragraphs, 50–75 char lines | Keep mobile text blocks short (mobile lines are naturally short; keep paragraphs brief with clear signposting) |
| Headings, bold keywords, lists, summaries | Signpost mobile content; scannable layout |
| Proximity, alignment, white space | Use spacing systems (e.g., 8-pt grid) and grouping to separate cards/sections; related items closer |
| Chunk multimedia | Video chapters; grouped toolbar/action sets |
| Progressive disclosure | Accordions, expandable sections, "View more," secondary screens/sheets; onboarding that teaches in steps |
| Staged disclosure / wizard | Multi-step forms (checkout, sign-up) with back/next, showing progress |
| Defer advanced features | Advanced settings/filters behind a clear entry point; sensible defaults |
| Information scent | Make the path to secondary content **visible and obvious** (labels, affordances) |
| Avoid multiple routes to the same secondary option | Keep a single, consistent path |
| Don't overuse | Avoid hiding frequently used actions (see "Never hide a key function in a secondary menu") |
| Recognition over recall | Keep primary navigation visible; menu size limits (e.g., 3–5 bottom tabs) are justified by **space, thumb reach, and clarity — not Miller's limit** |
| Distraction contexts | Mobile often competes with other stimuli (on-the-go) → chunk critical data entry |
| Empty states / onboarding | Use as staged teasers with a clear next action |
| Observation-driven | Use field studies/analytics to decide what is "primary" vs. "secondary" |

> **Cross-document note:** `choice_overload_guide.md` cites Miller (1956) for a ~7-item processing limit in the consumer-choice context. This document's sources caution against using Miller to justify **UI menu limits**. Treat option-count limits as context-dependent design heuristics, validate with testing, and avoid presenting "7" as a universal rule.

---

## 17. Decision Rules (IF → THEN)

| Condition | Action |
|---|---|
| Users must **remember or transcribe** a string (ID, key, code) | Chunk it into ~3–6-character groups with conventional delimiters |
| User types a chunked value | Autoformat; don't require separators |
| Data format differs by country | Use the locale's standard chunking |
| Content is meant to be **searched/scanned/analyzed** (lists of results, catalogs) | Do **not** impose small chunk limits; support scanning and comparison |
| Navigation/menu has many items | Keep visible if recognition-based; structure meaningfully; don't cap at 7 because of Miller |
| Long text block | Short paragraphs, subheadings, bold keywords, bullets, summary |
| Image/text/UI groups | Use proximity, alignment, spacing, background, rules |
| Long video | Add chapters/segmented transcript with subheadings |
| Interface competes with distractions (kiosk, car, ER, mobile on the go) | Apply chunking to critical information |
| Feature-rich product with novice and expert users | Progressive disclosure: basics first, advanced on demand |
| Advanced feature used frequently by most users | **Don't hide it**; reconsider the primary/secondary split |
| Unsure what's "primary" | Observe users (field studies/task analysis) before deciding |
| Multi-step task | Staged disclosure/wizard, with clear progress and back/next |
| Tempted to paginate for ad impressions | Avoid; user's task should drive sequencing |
| Tempted to withhold key info (e.g., price) to persuade | Avoid; allow free-form exploration |
| Secondary options exist | Provide **one obvious** path with strong information scent |
| Repeat users are the majority | Offer shortcuts/remembered state; don't force the full staged flow |

---

## 18. Checklists

### 18.1 Chunking Checklist

- [ ] Purpose identified: memorization/entry vs. search/scan/analyze
- [ ] Memory-oriented strings chunked to ~3–6 characters/items
- [ ] Conventional, locale-appropriate delimiters and formats
- [ ] Inputs autoformat; users don't type separators
- [ ] Text: short paragraphs, 50–75 character lines, white space
- [ ] Headings/subheadings contrast clearly; keywords highlighted; lists and summaries used
- [ ] Related elements close and aligned; unrelated elements separated
- [ ] No menu/list caps justified only by "seven plus or minus two"
- [ ] Tested with users of varied memory capacity/context (not just the team)

### 18.2 Progressive Disclosure Checklist

- [ ] Primary vs. secondary split is based on observed behavior
- [ ] Path from primary to secondary is obvious (information scent, visible target)
- [ ] Only one main route to each secondary option
- [ ] Multiple secondary displays considered where useful
- [ ] Frequently used features not hidden
- [ ] Users are not forced to wait or click through pages for the designer's benefit
- [ ] Free-form exploration still possible
- [ ] Repeat/expert users have efficient access
- [ ] Progression works for the full audience range (novice → expert)
- [ ] Verified with usability testing

---

## 19. Key Facts Reference

| Fact | Value |
|---|---|
| Miller paper | 1956, *The Magical Number Seven, Plus or Minus Two* |
| Miller's range | 7 ± 2 (5–9) |
| Broadbent (1975) | 4–6 items |
| LeCompte (1999) | As few as 3 items |
| Practical chunk size | 3–6 items (4 ± 1) |
| Line length for text | ~50–75 characters |
| Credit-card chunking | 4 × 4 digits |
| Miller letters example | 7 letters vs. 28 letters in 7 four-letter words |
| Progressive disclosure origin | Early 1980s; Carroll (1983), "training wheels" (Carroll 1984) |
| Carroll & Rosson (1997) | No empirical evidence; single word-processor, menu-based study |
| Nielsen guidelines | 2006; 4 guidelines (Section 13) |
| Nielsen "staged disclosure" | 2006; wizard/back-next hybrid |
| hp.com example | 21 laptops per page, acceptable due to browse/search task |
| Chunking article authors | Martin Harrod (Chunking, #43); Kate Moran (NN/g, March 20, 2016) |
| Progressive disclosure author | Frank Spillers (#44) |

---

## 20. People & Sources Reference

| Person | Contribution |
|---|---|
| **George A. Miller** | Introduced chunking / "magical number seven" (1956) |
| **Broadbent (1975)** | Proposed 4–6 item working memory capacity |
| **LeCompte (1999)** | Argued for as few as 3 items |
| **Bailey (2000)** | Criticized misapplied chunking (called it a "superstition") |
| **Jones (2002)** | Called misapplied chunking an "urban legend" |
| **Martin Harrod** | Author, Chunking (#43) |
| **Kate Moran (NN/g)** | "How Chunking Helps Content Processing" (2016) |
| **Frank Spillers** | Author, Progressive Disclosure (#44); definition (2004), 2007 comments |
| **Jakob Nielsen** | Interviews (2000, 2002); 2006 guidelines; staged disclosure |
| **John M. Carroll & Mary Rosson** | IBM lab work (1983); "training wheels" (1984); 1997 note on lacking empirical evidence |
| **Forrester Research (2003)** | Definition in configurator tools context |
| **Gestalt psychology** | Law of Proximity |

---

## 21. Glossary

| Term | Definition |
|---|---|
| **Working memory / short-term memory** | Limited-capacity memory holding information for immediate use |
| **Channel capacity** | Information-theory model of constant capacity in bits; Miller found short-term memory doesn't fit it |
| **Recognition vs. recall** | Recognizing visible options vs. retrieving from memory; menus rely on recognition |
| **Delimiter / deliminator** | Separator character (parentheses, hyphen, space) used to mark chunks |
| **Autoformatting** | Input field automatically inserts chunk separators as the user types |
| **Law of Proximity** | Gestalt principle: elements near each other are perceived as related |
| **Progressive disclosure** | Deferring advanced/rare options to later/secondary screens; ramping from simple to complex |
| **Staged disclosure** | Wizard-style (back–next) sequential disclosure |
| **Training wheels** | Carroll's approach of hiding advanced functionality early to improve later success |
| **Information scent** | Cues that signal what lies down a path; strengthens navigation to secondary levels |
| **Teaser** | Preview that introduces what is next in progressive disclosure |
| **Field study / task analysis** | Observation of users in real contexts to understand workflows |
| **Sense-making** | How users interpret and organize information to accomplish tasks |
| **Drill-down** | Deep, hierarchical navigation (less desirable than shallow navigation) |

---

## 22. Source Notes & Caveats

1. **Sources merged:** Laws-of-UX-style summary of chunking; Martin Harrod's *Chunking* (#43); Frank Spillers' *Progressive Disclosure* (#44); NN/g article by Kate Moran, "How Chunking Helps Content Processing" (2016). Overlapping definitions and Miller origin details are deduplicated.
2. **Chunk-size disagreement:** Harrod contrasts Miller's 7 ± 2 with a practical 3–6 (4 ± 1) range; NN/g emphasizes not fixating on any number. Use 3–6 as a guideline for memory tasks only.
3. **Figure labels:** The Figure 2 labels in the source are ambiguous; interpretation given in 4.3.
4. **Evidence base for progressive disclosure is thin** (acknowledged by Carroll & Rosson, 1997, and Spillers). Treat it as a widely endorsed practitioner technique, not a proven law.
5. **Dated examples:** Microsoft Word 2003/2007, Apple Leopard, early AJAX, and early iPhone gestures reflect the era of the source (mid-2000s). Principles remain relevant; specific products are historical.
6. **Anecdotal user quotes** (ApartmentGuide.com, BBC) are illustrative, not controlled experiments.
7. **Typos in source:** "deliminators" (delimiters), "desert" (dessert), "deign" (design) normalized or noted here.
