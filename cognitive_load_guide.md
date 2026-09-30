# Cognitive Load — Structured Knowledge Base

> **Purpose:** Authoritative reference on cognitive load and cognitive overload: theory, types, measurement, effects, population differences, and a practical catalog of UX/UI causes and countermeasures.
> **Audience:** Downstream AI agents and human designers, researchers, and product teams.
> **Companion documents:** `mobile_app_design_guide.md`, `chunking_and_progressive_disclosure_guide.md`, `choice_overload_guide.md`, `cognitive_bias_guide.md`, `aesthetic_usability_effect_guide.md`.
> **Conventions:**
> - `> **RULE:**` = non-negotiable guidance. `> **KEY TAKEAWAY:**` = high-value summary.
> - Research claims are **source-reported**; many Wikipedia-derived claims carry `[citation needed]` flags in the raw material (preserved where relevant).
> - **[Source note]** = ambiguity, inconsistency, or quality warning in the raw material.
> - Sections marked **(Derived)** are implications synthesized from the source, not direct source claims.

---

## Table of Contents

1. [Definition & Core Concept](#1-definition--core-concept)
2. [Key Takeaways](#2-key-takeaways)
3. [Origins & History](#3-origins--history)
4. [Working Memory Fundamentals](#4-working-memory-fundamentals)
5. [The Three Types of Cognitive Load](#5-the-three-types-of-cognitive-load)
6. [Learning Effects from Cognitive Load Theory](#6-learning-effects-from-cognitive-load-theory)
7. [Measurement](#7-measurement)
8. [Effects of Heavy Cognitive Load](#8-effects-of-heavy-cognitive-load)
9. [Digital Environments: Internet & AI Effects](#9-digital-environments-internet--ai-effects)
10. [Sub-Populations & Individual Differences](#10-sub-populations--individual-differences)
11. [Embodiment, Interactivity & Other Domains](#11-embodiment-interactivity--other-domains)
12. [Causes of Cognitive Overload in UX](#12-causes-of-cognitive-overload-in-ux)
13. [Design Strategy Catalog for Reducing Cognitive Load](#13-design-strategy-catalog-for-reducing-cognitive-load)
14. [The Seven Common Causes: Problems, Solutions & Examples](#14-the-seven-common-causes-problems-solutions--examples)
15. [Krug's "Don't Make Me Think" Lessons](#15-krugs-dont-make-me-think-lessons)
16. [Case Studies & Examples](#16-case-studies--examples)
17. [Application to Mobile App Design (Derived)](#17-application-to-mobile-app-design-derived)
18. [Decision Rules (IF → THEN)](#18-decision-rules-if--then)
19. [Checklists](#19-checklists)
20. [Key Facts Reference](#20-key-facts-reference)
21. [People & Sources Reference](#21-people--sources-reference)
22. [Glossary](#22-glossary)
23. [Source Notes & Caveats](#23-source-notes--caveats)

---

## 1. Definition & Core Concept

| Context | Definition |
|---|---|
| **UX definition (NN/g)** | The amount of mental resources required to operate a system; informally "brain power," formally **slots in working memory** |
| **Design summary (Laws-of-UX style)** | The amount of mental resources needed to understand and interact with an interface |
| **Cognitive psychology (Wikipedia)** | The effort being used in working memory |
| **Cognitive load theory (CLT)** | Examines how cognitive processing resources work during problem solving and learning, centered on **working memory**: a limited system for temporarily storing and managing information |
| **Cognitive overload** | Occurs when working memory receives more information than it can handle comfortably → frustration, compromised decision-making, missed details, abandonment |
| **Relationship to Miller's Law** | Closely related psychology concept; CLT expands Miller's information-processing work |

> **KEY TAKEAWAY:** When incoming information exceeds available mental capacity, tasks get harder, details are missed, and users feel overwhelmed or abandon the task. Human "processing power" cannot be upgraded — designers must accommodate its limits.

**Analogy (NN/g):** Like a computer running too many programs at once, the brain slows or "crashes" when overloaded; but unlike a computer, you cannot upgrade it.

---

## 2. Key Takeaways

1. Cognitive load cannot be eliminated (and shouldn't be — users come to learn something), but **extraneous load should be minimized**.
2. **Intrinsic load** = effort of absorbing new information and tracking goals; **extraneous load** = processing that consumes resources without helping understanding (e.g., distracting or unnecessary design elements).
3. Users bring their own load: worries, noise, fatigue, low tech experience — **beyond the designer's control**.
4. Load differs by person: **novices, children, older adults** typically experience higher load than experts.
5. Main UX causes: **unnecessary actions, overstimulation, too many options, too much content, ambiguous interfaces, hard-to-find pages/features, internal inconsistency**.
6. Core countermeasures: **remove clutter, use familiar patterns, offload tasks (defaults/autofill), minimize and group choices, chunk content, use step forms with progress, keep proximity of related elements (avoid split attention), give immediate feedback, keep consistency, support with onboarding/worked examples**.
7. Simplicity must not come at the cost of **clarity**.
8. Every extra step is a potential drop-off point.
9. Speed and pacing matter: lag adds load.
10. The three-load additivity model is **contested**; the types likely influence each other.

---

## 3. Origins & History

| Period | Event |
|---|---|
| **1950s** | Cognitive science begins; **G. A. Miller** (1956), "The Magical Number Seven, Plus or Minus Two": working memory has inherent limits (~7 ± 2 units) |
| **1950s** | William Hick & Ray Hyman first test the relationship between number of options and decision time (Hick's Law) |
| **1973** | Simon & Chase first use the term **chunk** to describe how people organize information in short-term memory (chunking also described as **schema construction**) |
| **1984** | Established individual differences in processing capacity between **novices and experts** |
| **Late 1980s** | **John Sweller** (Australian educational psychologist) develops CLT from a study of problem solving |
| **1988** | Sweller: "Cognitive Load Theory, Learning Difficulty, and Instructional Design" (reworked/republished 1994) |
| **Early 1990s** | Chandler & Sweller introduce the terms **intrinsic** and **extraneous** cognitive load (six experiments, many on the split-attention effect) |
| **1990s** | Learning effects demonstrated (see Section 6) |
| **1993** | Paas & Van Merriënboer develop **relative condition efficiency** to measure perceived mental effort |
| **2004** | Baddeley & Hitch: working-memory components in place by age six |
| **2013** | NN/g (Whitenton): Minimize Cognitive Load to Maximize Usability; poverty-and-cognitive-load theory |
| **2015** | Yablonski and Smashing Magazine (Halarewich) articles applying CLT to UX; a 2015 MRI study documented brain effects related to Hick's Law |
| **Later** | Additivity of the three load types investigated and questioned; embodied CLT proposed; internet/AI effects studied |

**Purpose of Sweller's theory:** provide guidelines for presenting information so it encourages learner activities that optimize intellectual performance; instructional design can reduce cognitive load. Sweller's theory uses the **schema** as the primary unit of analysis.

**Miller's legacy in UX:** ingrained chunking in digital design; also prompted designers to limit menus to 5–9 items, a practice since **demoted** in digital design (see `chunking_and_progressive_disclosure_guide.md`).

---

## 4. Working Memory Fundamentals

| Concept | Description |
|---|---|
| **Working memory** | Brain activity used to complete a task in the moment; sorts external stimuli and short-term memory items and draws from long-term memory as needed; **extremely limited in capacity and duration** |
| **Short-term memory** | A "scratch pad" for important-but-not-permanent information; working memory *processes*, short-term memory *holds* |
| **Long-term memory** | Stores knowledge (e.g., that blue text means a link) |
| **Computer analogy (Smashing)** | Working memory ≈ RAM; long-term memory ≈ hard drive |
| **Gateway model** | Atkinson–Shiffrin: declarative knowledge stored in long-term memory only after being attended to and processed by working memory. **Modern research:** some long-term memory can be encoded bypassing or in parallel with working memory |
| **Impact of limits** | Under some conditions, working-memory limits impede learning `[citation needed]` |

**Worked reading example (Smashing):** unfamiliar blue-text concept → working memory needs its meaning; long-term memory says "blue = link"; short-term memory remembers your place in the article (forgotten by next morning).

---

## 5. The Three Types of Cognitive Load

### 5.1 Classical Definitions (Instructional Design)

| Type | Definition (CLT / Wikipedia) | Controlled by |
|---|---|---|
| **Intrinsic** | Inherent difficulty associated with a specific topic/task (2 + 2 vs. differential equation). Cannot be altered by the instructor, but a schema may be split into **subschemas** taught in isolation, later recombined | Task/topic |
| **Extraneous** | Load generated by **how information is presented**; attributable to the design of materials; under designer control | Designer |
| **Germane** | Working-memory resources dedicated to managing intrinsic load and creating a permanent store of knowledge (**schema**); arises from the learner's characteristics, not the presented information | Learner |

**Germane–extraneous relationship:** If intrinsic load is high and extraneous load low → germane load high (learner can devote resources to the essential material). If extraneous load rises → germane load drops and learning suffers. Assumes constant motivation.

**Primary aim of CLT:** structure learning to **reduce extraneous** load and **optimize intrinsic** load, directing attention to schema construction (thereby increasing germane load).

### 5.2 UX-Specific Definitions (Comparison)

| Type | NN/g | IxDF (Interaction Design Foundation) | Example (UX) |
|---|---|---|---|
| **Intrinsic** | Effort of absorbing new information and keeping track of goals; carrying goal-relevant information (e.g., vacation constraints like price and timeframe) | Inherent difficulty of what you're trying to do; **UI appearance doesn't change it** | Booking a one-way flight (low) vs. configuring advanced router network settings (high) |
| **Extraneous** | Processing that consumes mental resources but doesn't help users understand content | Unnecessary distractions that take attention from the main task; unrelated to task difficulty | Cluttered, confusing checkout page (high) vs. well-organized mobile menu (low); font styles that convey no unique meaning |
| **Germane** | (Not emphasized) | Effort people **willingly invest** in understanding/completing a task: learning the interface, problem-solving, building mental schemas/shortcuts | Users mastering a new app's features |

> **[Source note — definitional variance]** Sources define the types slightly differently. Wikipedia: intrinsic = topic difficulty; NN/g: intrinsic includes goal-tracking and absorbing new information; Wikipedia's germane load = schema-building effort *from learner characteristics*; IxDF's germane = willing effort. Use the UX-oriented definitions for design decisions and treat theoretical nuances as contested.

### 5.3 Additivity Debate

- Original theory treated the three loads as **additive**.
- Over the years this has been questioned; now believed the types **circularly influence each other**.
- The "Additivity hypothesis" suggests types may overlap, requiring clearer distinctions.

### 5.4 Extraneous Load Components

- May include **clarity of texts** and **interactive demands of educational software**.
- A 2020 study: multiple demand components together form extraneous load, possibly needing different questionnaires to measure.

### 5.5 Extraneous Load Example (Square)

Describing a square verbally takes more effort than just showing one; the **figural medium** is more efficient because it doesn't add unnecessary processing. Unnecessary processing = extraneous load.

---

## 6. Learning Effects from Cognitive Load Theory

The 1990s empirical work demonstrated these effects:

| Effect | Notes from source |
|---|---|
| **Completion-problem effect** | Named; completion problems ranked second-most efficient after worked examples (Paas & Van Merriënboer) |
| **Modality effect** | Named |
| **Split-attention effect** | Information split across space/format forces the learner to mentally integrate it; Chandler & Sweller's experiments used materials demonstrating it. **UX implication:** place related items together |
| **Worked-example effect** | Learners studying worked examples were **most efficient** (vs. completion problems and discovery practice) |
| **Expertise reversal effect** | Named (experts and novices respond differently) |

**Means–ends analysis:** A problem-solving strategy that uses large processing capacity that might otherwise go to schema construction. Sweller recommended materials that avoid problem solving: **worked examples** and **goal-free problems**.

---

## 7. Measurement

| Method | Description |
|---|---|
| **Perceived mental effort ratings** | Index of cognitive load (developed later than the theory) |
| **Relative condition efficiency** (Paas & Van Merriënboer, 1993) | Standardized performance minus standardized mental effort, divided by √2; compares instructional conditions |
| **Task-invoked pupillary response** | Reliable, sensitive measure directly related to working memory; **pupil dilation occurs with high load** |
| **Ergonomic approach** | Quantitative neurophysiological measures, e.g., **heart rate–blood pressure product (RPP)** for cognitive and physical workload |
| **Physiological signals** | Pupil diameter, eye gaze, respiratory rate, heart rate; correlations found but **not held outside controlled laboratory environments** |
| **Comparison of measures** | Deleeuw & Mayer (2008): three common measures responded differently to extraneous, intrinsic, and germane load |
| **Driving/piloting** | Heart rate, facial expression, ocular parameters, cardiac and EEG signals |

---

## 8. Effects of Heavy Cognitive Load

| Effect | Detail |
|---|---|
| **Errors & interference** | Heavy load typically creates errors or interference in the task |
| **Slower comprehension / missed details / abandonment** | (NN/g) |
| **Stress, frustration, feeling overwhelmed, reduced focus** | Impacts productivity, problem-solving, task performance (IxDF) |
| **Stereotyping** | Heavy load pushes excess information into subconscious processing using schemas → activates stereotypical associations (implicit stereotype effect) |
| **Fundamental attribution error** | Increases with heavier load (see `cognitive_bias_guide.md`) |
| **Social facilitation (overload hypothesis)** | With an audience, people perform **worse on subjectively complex tasks** and better on subjectively easy ones |
| **Decision problems** | Overload → decision paralysis and compromised decision-making |
| **Task abandonment** | Even momentary pauses "rip users back" from immersion |

---

## 9. Digital Environments: Internet & AI Effects

> **[Source note]** The Wikipedia section "Effects of the internet" carries a **warning that it may contain LLM-generated text** with possible hallucinations and unverified claims (flagged February 2026). Treat this section as **lower-confidence, hypothesis-level** material.

### 9.1 Internet — Benefits and Burdens

| Direction | Detail |
|---|---|
| **Cognitive offloading** | External systems hold memory demands; frees working memory for complex problems |
| **Google effect / digital amnesia** | People forget information readily available online; aligns with **transactive memory theory** (knowing *who/where* knows rather than retaining everything) |
| **Efficiency tools** | Auto-complete, calculators, grammar checkers; well-designed learning platforms (interactive elements, real-time feedback, adaptive tech) reduce extraneous load |
| **Information overload** | Filtering for credibility/relevance adds extraneous burden; decision fatigue; reduced retention |
| **Attention fragmentation** | Hyperlinks, ads, continuous updates |
| **Media multitasking** | Associated with reduced working-memory efficiency, diminished attentional control, more distractibility; neuroimaging: decreased activation in sustained-attention/impulse-control regions among frequent multitaskers |
| **Illusion of knowledge** | Instant lookup creates overestimated understanding |
| **Spatial navigation** | London taxi drivers' memorization enlarges the **hippocampus** (possibly protective against dementia); over-reliance on GPS may suppress spatial-navigation plasticity |

### 9.2 Emerging AI Effects (Source-Reported)

- A growing body of evidence suggests AI may have a uniquely harmful effect on cognition by outsourcing sensing (face recognition), movement (robotics), choices (recommendation systems), and problem solving (chatbots).
- **Desirable difficulty:** productive struggle engaging working and long-term memory improves cognitive performance.
- **Deskilling:** a study found AI tool use led to physician deskilling and poorer surgical outcomes, **reversed by discontinuing** the tool.

> **(Derived)** Design tension: reducing load helps task completion, but in **learning** contexts some effortful processing is beneficial. Distinguish *extraneous* load (remove) from *desirable difficulty* (retain).

---

## 10. Sub-Populations & Individual Differences

| Group | Findings |
|---|---|
| **Novices vs. experts** | Experts have more knowledge → lower load on the task; novices bear heavier load (established by 1984) |
| **Elderly** | Aging reduces working-memory efficiency → higher load; heavy load disturbs **balance** (center-of-mass sway increases with load; balance demands can raise load `[citation needed]`); prefer **larger text, simpler designs**, trouble with small fonts and fast animations (IxDF) |
| **College students** | Laptop multitasking (social media) jeopardizes performance; a 2013 study found heavy Facebook users and those seated near them had lower GPA; task-switching under abundant resources is not optimal (2014) |
| **Children** | Working-memory components in place by 6 (Baddeley & Hitch 2004); higher load from **lack of general knowledge**; superior processes, **metacognition**, and content knowledge develop with age and reduce load; **gesturing/pointing** reduces load by offloading representation; benefit from **bright, engaging visuals and easy navigation** |
| **Children in impoverished families** | Often higher load in learning environments (less exposure to school-related numbers, words, concepts) |
| **Poverty (2013 theory)** | Impoverished environments contribute to higher cognitive load regardless of task; multiple contributing factors not present in middle/upper-class people |
| **People with disabilities** | Struggle with messy menus, flashing animations, low color contrast; follow **WCAG** (helps ADA compliance) |
| **Personality/stress** | Easygoing users may focus better than those who stress; users who rarely go online must think more than experienced users (Smashing) |

> **RULE:** Design for the users most susceptible to overload (children, seniors, novices, users under stress); offer **personalization** (theme, font size, layout options).

---

## 11. Embodiment, Interactivity & Other Domains

| Topic | Detail |
|---|---|
| **Embodied CLT** | Bodily activity can help or hinder learning; proposed to predict the usefulness of interactive features: **benefits (easier cognitive processing) must exceed costs (e.g., motor coordination)** |
| **Driving & piloting** | More secondary cockpit tasks make load estimation important; drowsiness detection; physiological parameters (heart rate, facial expression, eye metrics; EEG for fast-jet pilots) |
| **Instructional design** | Fundamental tenet: instructional quality rises when working-memory limits are considered |
| **Digital distraction in education** | Smartphones/digital technology increase distraction → higher load → reduced academic success |

---

## 12. Causes of Cognitive Overload in UX

### 12.1 Consolidated Cause List

| Source | Causes |
|---|---|
| **Yablonski (3 root factors)** | Too many choices; too much thought required; lack of clarity |
| **IxDF (design choices)** | Complex interfaces; lack of intuitiveness; inconsistent design patterns; too much information; too many simultaneous tasks |
| **Smashing Magazine (7 categories)** | 1) Unnecessary actions; 2) Overstimulation; 3) Too many options (Hick's Law); 4) Too much content; 5) Ambiguous interface; 6) Hard-to-find pages and features; 7) Internal inconsistency |

### 12.2 Uncontrollable Factors

- Users may be worried about tomorrow's presentation, or exposed to loud construction outside; these drain working memory regardless of design.
- Each user has different working-memory capacity.

---

## 13. Design Strategy Catalog for Reducing Cognitive Load

| # | Strategy | Guidance |
|---|---|---|
| 1 | **Avoid unnecessary elements / visual clutter** | Remove redundant links, irrelevant images, meaningless typography flourishes, excessive colors/imagery. Meaningful links/images/typography are valuable — only overuse backfires. **Don't overvalue simplicity at the cost of clarity** |
| 2 | **Build on existing mental models & common patterns** | Use labels/layouts users have met elsewhere; don't reinvent the wheel; put a brand spin on familiar patterns |
| 3 | **Offload / eliminate unnecessary tasks** | Find anywhere users must read, remember, or decide; use pictures, **re-display previously entered info**, **smart defaults** (editable), autofill; anticipatory design |
| 4 | **Minimize choices** | Especially in navigation, forms, drop-downs (see Hick's Law) |
| 5 | **Display choices as a group** | Hidden/split groups lead users to assume the visible options are complete |
| 6 | **Strive for readability** | Typography that is aesthetically pleasing, appropriate, easy to read; design should remain "relatively invisible" |
| 7 | **Use iconography with caution** | Icons can be hard to memorize and can *increase* load; only universal icons (print, close, play/pause, reply, share) work alone; **accompany with text labels** |
| 8 | **Consistency** | Same colors, typography, icons, layouts; design guidelines/style guide; test across popular devices; audit with user feedback |
| 9 | **Tailor to audience needs** | Larger text for seniors; engaging visuals for children; WCAG for disabilities; personalization controls |
| 10 | **Prioritize task hierarchies** | Identify primary tasks via surveys/interviews; rank; emphasize; avoid detours; add menus/breadcrumbs |
| 11 | **Avoid too much information** | Keep only what's necessary; ample white space; ask: What's the screen's primary purpose? What can be left out? What's redundant? (Example: scheduling app shows calendar/appointments; reminders/notes in a secondary menu) |
| 12 | **Simplify tasks** | Map flows/journeys; remove steps; minimize clicks/taps; defaults and autofill; **progress bars** for multi-step processes |
| 13 | **Avoid split attention** | Keep related elements close; group by function; use grid alignment; separate groups with subtle lines/borders (e.g., news categories in a nav bar; music playback controls grouped at the bottom) |
| 14 | **Immediate feedback** | Hover/click state changes, confirmation messages, loading spinners for processing |
| 15 | **Worked examples & onboarding** | Step-by-step guides, video demos, interactive tutorials, annotated screenshots; choose format by audience (interactive for tech-savvy; annotated screenshots for beginners) |
| 16 | **Chunking & step forms** | Group data; multi-step forms with a progress marker |
| 17 | **Content-type balance** | Mix text, images, video, infographics for harmony |
| 18 | **Symmetry / constructive asymmetry** | Balance visual weight and direction so layouts are quicker to understand |
| 19 | **Speed & pacing** | Remove lag; users want brisk, purposeful pacing |
| 20 | **Cursor/focus defaults** | Start the cursor in the primary field (e.g., Google's search box) — micro-interactions add up |

> **RULE:** "Don't make users think any more than they have to." (Krug) Every pause — "Is this clickable?", "Where's home?", "How do I save?" — burdens working memory.

---

## 14. The Seven Common Causes: Problems, Solutions & Examples

### 14.1 Unnecessary Actions

| Item | Detail |
|---|---|
| Problem | Every step adds load; unnecessary steps derail thought and irritate; lag hurts pacing |
| Diagnostic exercise | List every step to complete a task (e.g., sending email); scan for redundancy (e.g., auto-focus the "Send to" field to remove a step) |
| Negative example | **Touch of Modern** demands registration before showing anything (first mandatory unnecessary action scares away users) |
| Positive example | **Google** home page: cursor starts in the search field |

### 14.2 Overstimulation

| Item | Detail |
|---|---|
| Problem | Too many images, animations, icons, ads, text types, bright colors compete; even two simultaneous animations can overwhelm |
| Solutions | Remove all non-essential elements (also speeds loading); a study on aesthetics and first impressions found users **prefer simple over visually complex** sites; balance content types; symmetric/constructive-asymmetric layout |
| Negative example | **LINGsCARS** (extreme clutter and motion) |
| Positive examples | **IMDb** (balanced visual and text); **Groupon** (hourglass shape via photos/color blocks pinched by text); **OTHR** (asymmetry that still feels organized) |

### 14.3 Too Many Options (Hick's Law)

| Item | Detail |
|---|---|
| Principle | More options → more decision time (Hick & Hyman, 1950s); confirmed by behavioral studies and a 2015 MRI study |
| Mental model | Each option is a "bright flashing light" |
| Solutions | Remove redundant options; group into umbrella categories; use mega-menus/drawers/pull-outs (many options in digestible doses); manage via IA |
| Trade-off | Hidden menus limit **discoverability** — complement with out-of-the-way links (Amazon's "Related purchases") or generalize header categories to fit one visible menu (Apple, CNN) |
| Negative example | **Rakuten** |
| Note | It's not necessarily too many options, but too many **at one time** |

### 14.4 Too Much Content

| Item | Detail |
|---|---|
| Problem | Content pulls working memory in many directions |
| Solutions | **Chunking** (group data; phone number broken into country code/area code/3 digits/4 digits); group product images by type or seller; text chunking = short paragraphs, headings/subheadings, white space; **multi-step forms with progress markers** for long forms |
| Negative example | **Arngren** (too many products at the same time) |
| Positive examples | **Etsy** (chunks by seller), **Virgin Atlantic** (flight → passenger info → payment on separate steps/pages) |

### 14.5 Ambiguous Interface

| Item | Detail |
|---|---|
| Problem | Biggest culprit in overload; users waste effort deciphering icons or figuring out actions |
| Solutions | Reuse familiar visual cues, affordances, signifiers; brand-tint common icons (Home Depot's orange); use **standard microcopy** ("Contact," "Submit" > "Address," "Go"); for brand-new features use **real-life metaphors (skeuomorphism)**, e.g., envelope for email; avoid vague symbols; test with fresh eyes; watch icon mistakes (too similar, too complex); provide **onboarding** for non-obvious UIs (Slack's narrated video tour) |
| Negative examples | **SpeedCrunch** (vague icons), **Issuu** (some unfamiliar icons) |

### 14.6 Hard-to-Find Pages and Features

| Item | Detail |
|---|---|
| Problem | A feature users can't find is as good as broken; navigation should feel intuitive and build confidence |
| Solutions | Build **IA around users' mental models** using **card sorting** (how users categorize) and **tree tests** (how well structure is understood); combine redundant pages (e.g., Waaark merges intro/team/contact on one page); use size, animation, contrasting color to emphasize key functions |
| IA principles (Dan Brown) | **Multiple classification** (several categorization methods); **disclosure** (show only enough so users know what to expect) — 8 principles total |
| Negative example | **Mojo Yogurt** (nav revealed only by hovering the logo) |
| Positive example | **PayPal** (log-in button set apart on a white block for returning users) |

### 14.7 Internal Inconsistency

| Item | Detail |
|---|---|
| Problem | Inconsistent link styling (blue + underline vs. blue only), typos, and grammar errors cause a "split second" of distraction; inconsistency with the site, with other sites' standard patterns, or with language norms all use working memory |
| Solutions | Consistent format; **style guide** (colors, image dimensions, heading typography); proofread beyond spell-check (e.g., Grammarly) |
| Negative example | **SIPhawaii** (inconsistent capitalization, font sizes, price display, non-standard hamburger behavior) |
| Positive examples | **Pinterest** (identical card format; enables staggered rows without confusion); **Lonely Planet** (style-guide case study) |

---

## 15. Krug's "Don't Make Me Think" Lessons

(Steve Krug popularized cognitive load in web design.)

| Lesson | Implication |
|---|---|
| Every page should be **self-explanatory** | Users enter mid-site as often as at the homepage |
| Users **satisfice** | Take the first/easiest solution, not the best, and repeat it habitually |
| Adequate usability | An average-ability user can accomplish goals |
| Time-saving motivation | Users adopt a "keep moving or die" mentality |
| **Back button** is the most-used browser feature | Support predictable back behavior |
| A visible **home button** reassures | Even if never clicked |

---

## 16. Case Studies & Examples

| Example | Domain | Lesson |
|---|---|---|
| **Resume-now.com** (see `cognitive_bias_guide.md`) | Onboarding | Reduce upfront friction (no account until value invested) |
| **Google search** | Micro-interaction | Auto-focus removes a step |
| **Touch of Modern** | Registration gate | Forced unnecessary actions scare users |
| **Etsy / Virgin Atlantic** | Chunking, multi-step | Group and stage content/forms |
| **Amazon / Apple / CNN** | Navigation | Mega-menus vs. generalized headers trade off discoverability and option count |
| **Slack** | Onboarding | Video tour for a novel interface |
| **Pinterest** | Consistency | Uniform cards enable visual variety |
| **PayPal** | Prioritization | Emphasize the returning-user action |
| **Home Depot** | Familiar patterns + brand | Brand color on standard icons |
| **Sphinx riddle / fridge analogy** | Illustration | Needless riddles = frustration akin to poor UX |

---

## 17. Application to Mobile App Design (Derived)

> Links source principles to `mobile_app_design_guide.md` and other companion docs. These are design inferences, not source claims.

| Source principle | Mobile application |
|---|---|
| Reduce extraneous load | One primary action per screen; only essential elements; generous white space |
| Familiar patterns / mental models | Follow Apple HIG / Material Design; native components; standard back gestures |
| Icons need labels | Bottom tab bar with **icons + text labels** (3–5 tabs) |
| Offload tasks | Autofill, smart defaults, remember prior inputs, OS-level sign-in/biometrics, contextual permission prompts |
| Minimize/group choices | Chunked settings; progressive disclosure; search + filters (see `choice_overload_guide.md`) |
| Chunking & step forms | Multi-step checkout/sign-up with progress indicators; chunked OTPs/card numbers (see `chunking_and_progressive_disclosure_guide.md`) |
| Split attention | Keep labels, inputs, errors, and related controls adjacent; group controls (e.g., playback controls at bottom) |
| Immediate feedback | Tap states, haptics, loading indicators/skeleton screens, confirmations |
| Consistency | Design tokens, style guide, 8-pt spacing scale, consistent components |
| Tailor to audience | Dynamic Type, high contrast, Reduce Motion, larger touch targets for seniors; WCAG |
| Speed & pacing | Fast loads, no blank screens; lag is extraneous load |
| Onboarding | 3–5 skippable screens; interactive first tasks; worked examples/annotated tips for complex features |
| Hidden navigation trade-off | Drawers/hamburger menus reduce discoverability; prefer visible primary nav |
| Mobile context | On-the-go users under external load (noise, stress, distraction) → simplify more than on desktop |
| Notifications & multitasking | Avoid interrupting flows; media multitasking degrades attention |
| Learning apps | Distinguish extraneous load (remove) from desirable difficulty (retain) |
| Testing | Card sorting, tree testing, usability sessions; measure time on task, errors, abandonment |

---

## 18. Decision Rules (IF → THEN)

| Condition | Action |
|---|---|
| Users must recall or re-enter information | Re-display, autofill, or set an editable default |
| A step adds no value | Remove it; minimize taps/clicks |
| Multiple competing animations/images/ads | Cut to essentials; avoid simultaneous animations |
| Many options present simultaneously | Group into categories; use hidden/collapsible menus **and** provide discoverability cues |
| Options are split into hidden groups | Ensure users know other groups exist; display choices as a group where feasible |
| Long form | Multi-step with a progress marker |
| Large content set | Chunk by type/source; short paragraphs, headings, white space |
| Icon meaning not universal | Add text label |
| Feature is novel | Use a real-life metaphor; add onboarding/tutorial |
| Non-standard label idea (e.g., "Go") | Use conventional labels ("Submit," "Contact") |
| Navigation seems unclear | Card-sort and tree-test the IA; merge redundant pages |
| Key function is important | Increase prominence (size, contrast, motion — sparingly) |
| Users repeat a task (returning users) | Emphasize their primary action (e.g., PayPal log-in) |
| Related elements far apart | Move them together; group with proximity/borders |
| Inconsistent styling discovered | Fix via style guide; proofread |
| Task has inherently high intrinsic load | Break into subtasks/steps; provide worked examples; minimize extraneous load even more |
| Audience includes seniors/children/novices/disabled users | Larger text, simpler layouts, engaging visuals, WCAG; offer personalization |
| Learning goal (education) | Provide worked examples; retain desirable difficulty |
| Simplification harms clarity | Prefer clarity; don't over-simplify |

---

## 19. Checklists

### 19.1 Design Review Checklist

- [ ] Every element helps the user's goal; nothing decorative competes for attention
- [ ] Primary purpose of each screen is clear
- [ ] Familiar patterns and standard labels used
- [ ] Icons paired with text labels unless universal
- [ ] Choices minimized and grouped; hidden menus paired with discoverability cues
- [ ] Long content chunked; long forms broken into steps with progress
- [ ] Related elements grouped and adjacent (no split attention)
- [ ] Defaults, autofill, and re-display of prior input used
- [ ] Immediate feedback for every interaction; loading states shown
- [ ] Consistent colors, typography, spacing, link styles; no typos
- [ ] Onboarding/tutorial for non-obvious features
- [ ] Accessible for seniors, children, and disabled users; personalization available
- [ ] Task flows audited for unnecessary steps

### 19.2 Research Checklist

- [ ] Card sorting and tree testing on IA
- [ ] Usability tests observing pauses, hesitation, backtracking, abandonment
- [ ] Testing with novices, seniors, and stressed/distracted users
- [ ] Time-on-task and steps-to-complete measured
- [ ] Consistency audits across devices/screens

---

## 20. Key Facts Reference

| Fact | Value |
|---|---|
| CLT developed | Late 1980s (John Sweller); key paper 1988 |
| Miller's paper | 1956, 7 ± 2 |
| "Chunk" term | Simon & Chase, 1973 |
| Intrinsic/extraneous terms | Chandler & Sweller, early 1990s |
| Relative condition efficiency | (Standardized performance − standardized mental effort) / √2; Paas & Van Merriënboer 1993 |
| Novice/expert differences | Established 1984 |
| Children's working memory | Components in place by age 6 (Baddeley & Hitch 2004) |
| Hick's Law | 1950s; MRI study 2015 |
| Load types | Intrinsic, extraneous, germane (additivity contested) |
| Seven common UX causes | Unnecessary actions, overstimulation, too many options, too much content, ambiguous interface, hard-to-find features, inconsistency |
| IA principles (Dan Brown) | 8 |
| Article dates | NN/g Whitenton Dec 22, 2013; Yablonski Nov 30, 2015; Smashing (Halarewich) ~22 min read |

---

## 21. People & Sources Reference

| Person / Source | Contribution |
|---|---|
| **John Sweller** | Developed cognitive load theory; 1988 paper |
| **George A. Miller** | Working-memory limits; chunking origin |
| **Simon & Chase** | Term "chunk" (1973) |
| **Chandler & Sweller** | Intrinsic/extraneous load; split-attention experiments |
| **Paas & Van Merriënboer** | Relative condition efficiency (1993) |
| **Deleeuw & Mayer (2008)** | Compared load measures |
| **Baddeley & Hitch (2004)** | Working memory in children |
| **William Hick & Ray Hyman** | Hick's Law |
| **Steve Krug** | *Don't Make Me Think* |
| **Kathryn Whitenton (NN/g)** | *Minimize Cognitive Load to Maximize Usability* (2013) |
| **Jon Yablonski** | *Design Principles for Reducing Cognitive Load* (2015) |
| **Danny Halarewich (Smashing Magazine)** | *Reducing Cognitive Overload For A Better User Experience* |
| **Interaction Design Foundation (IxDF)** | *Ease Cognitive Overload in UX Design* |
| **Dan Brown** | *Eight Principles of Information Architecture* |
| **Luke Wroblewski** | Quote on going to where users are (freight-train analogy) |
| **Denis Kortunov** | 10 common icon mistakes |
| **Wikipedia** | Cognitive load overview |

---

## 22. Glossary

| Term | Definition |
|---|---|
| **Schema** | Organized pattern of knowledge stored in long-term memory; primary unit of analysis in CLT |
| **Subschema** | A component of a schema that can be taught in isolation |
| **Means–ends analysis** | Problem-solving strategy that consumes large processing capacity |
| **Worked example** | Demonstrated solution used as a learning model |
| **Goal-free problem** | Problem without a specific goal, reducing means–ends demands |
| **Split-attention effect** | Load caused by mentally integrating separated information sources |
| **Satisficing** | Choosing the first acceptable option instead of the best |
| **Hick's Law** | Decision time increases with number of options |
| **Decision paralysis** | Inability or slowness to choose when options overwhelm |
| **Chunking** | Grouping information into meaningful units |
| **Mental model** | User's expectation of how systems work, formed from experience |
| **Affordance / signifier** | Cues that indicate how an element can be used |
| **Skeuomorphism** | Digital elements mimicking real-world objects |
| **Anticipatory design** | Predicting needs to reduce user decisions |
| **Cognitive offloading** | Shifting memory/processing to external tools |
| **Google effect (digital amnesia)** | Forgetting information that's readily searchable |
| **Transactive memory** | Knowing who/where information is instead of storing it |
| **Desirable difficulty** | Productive struggle that improves learning |
| **Task-invoked pupillary response** | Pupil dilation as a physiological load indicator |
| **Card sort / tree test** | IA research methods for grouping and findability |
| **Breadcrumbs** | Navigation trail showing location |
| **Information architecture (IA)** | Organization and labeling of content |

---

## 23. Source Notes & Caveats

1. **Sources merged:** Laws-of-UX-style summary; Wikipedia (*Cognitive load*); IxDF article *Ease Cognitive Overload in UX Design*; NN/g (Whitenton 2013); Yablonski (2015); Smashing Magazine (Halarewich). Overlaps deduplicated.
2. **Wikipedia quality flags:** Numerous `[citation needed]` tags remain in the source (e.g., elderly/students/children load differences, balance/load relationships, germane load definition). The "Effects of the internet" section is flagged as possibly **LLM-generated**; treat as low-confidence.
3. **Definition variance:** Intrinsic/germane definitions differ between educational-psychology and UX sources (Section 5.2). Additivity of load types is contested.
4. **Hick's Law vs. choice overload:** The Smashing article equates Hick's Law with "decision paralysis"; the related but distinct *choice overload* research is in `choice_overload_guide.md`.
5. **Miller's number:** The 5–9 menu-item practice is described as "demoted"; consistent with cautions in `chunking_and_progressive_disclosure_guide.md`.
6. **Evidence strength:** Physiological measures work in the lab but not necessarily outside it. Many UX recommendations are practitioner heuristics, not controlled experiments.
7. **Cross-document consistency:** Recommendations to reduce choices and chunk content here align with the choice-overload and chunking guides; the "desirable difficulty" caveat (Section 9.2) qualifies "always reduce effort" in learning contexts.
8. **Omitted:** Site navigation chrome, ads (e.g., Smashing workshop promotions), newsletter prompts, image credits.
