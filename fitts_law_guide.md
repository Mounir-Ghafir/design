# Fitts's Law & Touch Target Design — Structured Knowledge Base

> **Purpose:** Authoritative reference on Fitts's Law (the speed–accuracy relationship between target distance, target size, and movement time): its origin, mathematical formulations, limits, UI design implications for mouse and touch, and empirical findings on how people actually hold and touch mobile devices.
> **Audience:** Downstream AI agents and human designers, researchers, and product teams.
> **Companion documents:** `mobile_app_design_guide.md`, `cognitive_load_guide.md`, `chunking_and_progressive_disclosure_guide.md`, `response_time_and_progress_feedback_guide.md`, `choice_overload_guide.md`, `cognitive_bias_guide.md`, `aesthetic_usability_effect_guide.md`.
> **Conventions:**
> - `> **RULE:**` = non-negotiable guidance. `> **KEY TAKEAWAY:**` = high-value summary.
> - Research claims and statistics are **source-reported**.
> - **[Source note]** = ambiguity, inconsistency, or quality warning in the raw material.
> - Sections marked **(Derived)** are implications synthesized from the sources, not direct source claims.
> - Symbols: **D** = distance to target center; **W** = target width along the axis of motion; **MT** = movement time; **ID** = index of difficulty (bits); **IP/TP** = index of performance / throughput (bits/s).

---

## Table of Contents

1. [Definition & Core Concept](#1-definition--core-concept)
2. [Key Takeaways](#2-key-takeaways)
3. [Origins & History](#3-origins--history)
4. [Mathematical Formulations](#4-mathematical-formulations)
5. [Movement Model: The Two-Component Model](#5-movement-model-the-two-component-model)
6. [Extending the Model: 2D Targets, Steering & Temporal Targets](#6-extending-the-model-2d-targets-steering--temporal-targets)
7. [Scope, Limits & Criticisms of the Model](#7-scope-limits--criticisms-of-the-model)
8. [UI Design Implications: Target Size](#8-ui-design-implications-target-size)
9. [UI Design Implications: Distance & Position](#9-ui-design-implications-distance--position)
10. [Menu Design Under Fitts's Law](#10-menu-design-under-fittss-law)
11. [Fitts's Law in the Touch Era (Hoober)](#11-fittss-law-in-the-touch-era-hoober)
12. [Old Advice vs. Touch Reality (Comparison Table)](#12-old-advice-vs-touch-reality-comparison-table)
13. [Empirical Research on Touch Behavior](#13-empirical-research-on-touch-behavior)
14. [Touchscreen Technology & Obsolete Standards](#14-touchscreen-technology--obsolete-standards)
15. [Touch-Friendly Information Design Framework](#15-touch-friendly-information-design-framework)
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

| Context | Statement |
|---|---|
| **Design summary** | The time to acquire a target is a function of the distance to and size of the target |
| **IxDF (simplified)** | The time required to move a pointer (e.g., mouse cursor) to a target area is a function of the distance to the target **divided by** the size of the target; the longer the distance and the smaller the target, the longer it takes |
| **Wikipedia** | A predictive model of human movement used in HCI and ergonomics: the time to rapidly move to a target area is a function of the **ratio** between distance and target width; models pointing either physically (hand/finger) or virtually (pointing device) |
| **NN/g (Budiu)** | Gives the relationship between the time it takes a pointer (mouse cursor, finger, hand) to move to a target (physical or digital button, physical object) in order to interact (click, tap, grasp) |
| **Speed–accuracy trade-off** | Fast movements and small targets produce greater error rates; all variants of the law encompass this idea |

> **KEY TAKEAWAY:** Bigger targets and closer targets are faster to acquire and less error-prone. In UI design this means: make interactive elements large enough, space them adequately, and place them near where the user's attention/pointer already is.

---

## 2. Key Takeaways

1. **Touch targets should be large enough** to be selected accurately, **spaced adequately**, and **placed where they are easily acquired**.
2. Movement time grows with distance and shrinks with size — but **logarithmically**: twice as far is longer, not twice as long.
3. Movement has two phases: a fast, coarse **ballistic** move (driven by distance) and a slow, precise **final adjustment** (driven by target size).
4. **Icons + labels** create larger targets (if the whole area is clickable) and reduce ambiguity.
5. **Screen edges and corners are "infinite" targets for mouse pointers** (the pointer stops at the edge) — but this advantage **does not apply to touchscreens**, where edges can be *slower* (users may overshoot off-screen).
6. **Don't crowd targets** — small, close targets cause overshoot and wrong selections. **Invisible padding alone is not enough** if users don't know it exists.
7. Put **related, sequential controls near each other** (e.g., Submit next to the last form field); avoid placing primary actions far from the user's likely finger position.
8. **Pop-up/context menus** beat fixed drop-downs (no travel); **pie/radial menus** equalize distances; linear menus should put the most-used items nearest the handle.
9. The classic mouse-based interpretation **makes assumptions that fail on touch**: hand position is unknown, edges aren't "walls," workspace clears after taps, and people prefer the **center** of the screen.
10. Empirical touch data: **75%** of users touch with one thumb; **fewer than 50%** hold a phone with one hand; **36%** cradle it; targets in the center can be as small as **~7 mm**, corners need **~12 mm**.
11. **Standards can be wrong or obsolete** (e.g., pixel-based sizes, IR-grid-era 22 × 22 mm); understand the basis of any guideline before applying it.
12. Fitts's law applies to **rapid pointing, not continuous motion** (e.g., drawing), and is **one-dimensional in its original form**.

---

## 3. Origins & History

| Period | Event |
|---|---|
| **Late 19th century** | R. S. Woodworth presents the **two-component model** of upper-limb movement (initial coarse move + final controlled adjustment) |
| **WWII** | Paul Fitts studies airplane-cockpit design; argues many losses attributed to "human error" were actually **poor design** (he was a senior US Air Force officer; founded the Aviation Psychology Research Laboratory at Ohio State) |
| **1948–1953** | Information theory (Shannon) spreads into psychology; Miller and others apply channel capacity to memory and perception; related work on rate of information gain (~5 bits/s per perceptual-motor act, in a cited paper) |
| **1954** | Fitts, "The information capacity of the human motor system in controlling the amplitude of movement," *Journal of Experimental Psychology* 47, 381–391 (reprinted later) — introduces ID, IP and the law |
| **1956** | Crossman proposes the **effective target width** adjustment (used by Fitts & Peterson 1964) |
| **1964** | Fitts & Peterson, "Information capacity of discrete motor responses" |
| **1968** | Welford's **two-factor** model |
| **1978–early 1980s** | Card, English & Burr: first HCI application — mouse outperformed joystick and directional keys (mouse's commercial introduction at Xerox was influenced by this work) |
| **1991** | Boritz et al.: radial menu direction effects |
| **1992** | MacKenzie & Buxton: use the smaller target dimension for rectangular targets |
| **~1992–2000s** | MacKenzie's **Shannon formulation** becomes standard in HCI |
| **2002** | **ISO 9241** (later 9241-9 guidance) standardizes HCI pointing-device testing incl. the Shannon form |
| **2010** | Kopper et al.: angle-aware Welford variant |
| **2013–2017** | Hoober's research on how people hold/touch phones (1,300+ observations; 651 more; meta-analysis of 120M touch events) |
| **2016** | Temporal-pointing model introduced to HCI |
| **2017–2022** | Hoober, *Fitts' Law in the Touch Era* (Smashing); Budiu (NN/g, July 31, 2022) |

**Fitts's intent (per NN/g):** like George Miller, who used channel capacity to find the "bandwidth" of short-term memory (magical number 7), Fitts sought the **bandwidth of human movement** — how many repetitive movements can be performed in a given interval.

**Fitts 1954 abstract (summary):** extends information theory (amount of information, noise, channel capacity, rate of information transmission) to the human motor system; subjects made rapid, uniform, highly overlearned responses; the "motor system" includes visual and proprioceptive feedback loops; information capacity = ability to consistently produce one class of movement among alternatives; capacity limited by statistical variability ("noise") of repeated efforts. ~8,675 citations.

---

## 4. Mathematical Formulations

### 4.1 Core Forms

| Form | Equation | Notes |
|---|---|---|
| **Original (Fitts 1954) ID** | `ID = log₂(2D / W)` | Distance to target center is "signal"; tolerance/width is "noise"; ID in **bits** |
| **Index of performance (throughput)** | `IP = ID / MT` (bits/s) | "Average information per movement divided by time per movement"; today called **throughput (TP)**; usually adjusted for accuracy |
| **Regression form** | `MT = a + b · ID = a + b · log₂(2D/W)` | `a`, `b` are empirical constants per input device (pointer type) |
| **Shannon formulation** (MacKenzie) | `ID = log₂(D/W + 1)` | Most used in HCI; resembles Shannon–Hartley; in ISO 9241 |
| **Effective width (Crossman 1956)** | `W_e = 4.133 × SD_x`; `ID_e = log₂(D/W_e + 1)`; `IP = ID_e / MT` | Uses standard deviation of actual selection coordinates; reflects what users **did**, not what they were asked to do; recommended in ISO 9241-9 |
| **Welford (1968)** | `MT = a + b₁·log₂(D) + b₂·log₂(W)` | Separate effects of distance and width; better prediction |
| **Welford–Shannon variant** | `MT = a + b₁·log₂(D+W) + b₂·log₂(W) = a + b·log₂((D+W)/Wᵏ)` | `k` allows angle effects (Kopper 2010); reduces to Shannon form at `k = 1`; empirically best for virtual pointing; robust to control-display gain changes |

### 4.2 Parameter Interpretation

| Parameter | Meaning |
|---|---|
| **a** | Y-intercept; interpreted as a delay; typically positive and close to zero (sometimes ignored, as in Fitts' original) |
| **b** | Slope; relates to acceleration; **1/b ≈ IP**; used to compare pointing devices (lower b = better) |
| **D** | Distance from the start point to the **center** of the target |
| **W** | Width **along the axis of motion**; equivalent to allowed error tolerance (final point within ±W/2 of center) |

### 4.3 Effective Width and Error Rate

- If selection coordinates are normally distributed, `W_e` spans **96%** of the distribution.
- Observed error rate **4%** → `W_e = W`; error rate **> 4%** → `W_e > W`; error rate **< 4%** → `W_e < W`.
- Advantage: incorporates **spatial variability (accuracy)** → captures the true speed–accuracy trade-off.

### 4.4 Why the Logarithm Matters

- Time does **not** grow linearly with distance: movement accelerates then decelerates; on longer distances the pointer reaches higher speed for part of the trip.
- So "twice as far" ≠ "twice as long."

### 4.5 Rectangular Targets in UI Practice

- Strictly, use width along the direction of movement; for typical rectangular UI targets, use the **smaller of height and width** (MacKenzie & Buxton, 1992).

### 4.6 Model Weaknesses (as reported)

- Predictive power **deteriorates** when both D and W are varied over a significant range (many experiments vary only one).
- Because ID depends only on D/W ratio, the model implies distance–width combinations can be **rescaled arbitrarily** without changing movement time — which is impossible.
- Despite this, the model has "remarkable predictive power" across interface modalities and motor tasks.
- Keystroke information vs. Fitts-implied ID are not perfectly consistent (error deemed negligible except for comparing devices with known entropy or measuring human information processing).

---

## 5. Movement Model: The Two-Component Model

| Phase | Nature | Driven mainly by |
|---|---|---|
| **1. Initial (ballistic) movement** | Rapid, relatively coarse; moves the pointer toward the target | **Distance** |
| **2. Final movement (fine adjustment)** | Slower, controlled; secures accuracy and avoids overshoot | **Target size** — smaller targets spend more time here |

- Applies to **goal-directed** movement (not e.g. tapping to a rhythm).
- **Infinite/very large targets** reduce or eliminate the final phase (no overshoot concern), which is why edge targets are fast with a mouse.
- **[Source note]** Wikipedia infers "distance has a greater impact than target size on overall task time" from the fact that different tasks can share the same difficulty — a loose inference; use cautiously.

---

## 6. Extending the Model: 2D Targets, Steering & Temporal Targets

### 6.1 Dimensionality

- Original form is **one-dimensional**; original experiments used a reciprocal tapping task between two plates (the perpendicular width was wide to avoid influence).
- 2D pointing generally holds "as is" but needs adjustments for target geometry and error definition.

### 6.2 Methods for Defining Target Size in 2D

| Method | Definition |
|---|---|
| **Status quo** | Horizontal width |
| **Sum model** | W = height + width |
| **Area model** | W = height × width |
| **Smaller-of model** | W = min(height, width) |
| **W-model** | Effective width in the direction of movement (considered state-of-the-art; the fully correct treatment of non-circular targets requires angle-specific convolution and is substantially more complex) |

### 6.3 Steering Law

- For navigating hierarchical pull-down menus (trajectory constrained by menu geometry), the **Accot–Zhai steering law** applies.

### 6.4 Temporal Targets

- Targets defined **in time** (blinking, moving toward a selection area): temporal distance **Dt** (wait until it appears) and temporal width **Wt** (duration it is available).
- `ID_t = log₂(Dt / Wt)`; larger Dt or smaller Wt → harder. Temporal pointing model introduced to HCI in **2016**.

### 6.5 Range of Validity (Reported)

- Holds across many limbs (hands, feet, lower lip, head-mounted sights), input devices, environments (even underwater), and populations (young, old, special education needs, drugged participants).

---

## 7. Scope, Limits & Criticisms of the Model

| Limitation | Detail |
|---|---|
| **Rapid pointing only** | Applies to rapid, pointing movements — **not continuous motion** (e.g., drawing) |
| **One-dimensional math** | The equation concerns 1D movement; default mouse interpretation measures target size as the **horizontal** component even for wide, short buttons approached from below |
| **Limb-movement systems** | Applies well to systems moved with the limb (whole arm: mouse, trackpad, joystick, yoke, pen tablet); **isometric/force-sensing controls** are modeled poorly and need modified models |
| **Eye tracking** | Applicability is controversial: during fast saccades the user is blind, whereas in a Fitts task the user sees the target (Drewes) |
| **Parameter estimation** | Methods for identifying `a` and `b` are debated; method variation can produce differences larger than true performance differences |
| **Success-rate confound** | Aggressive users can shorten MT at the cost of missed targets; if misses aren't modeled, MT is artificially lowered |
| **Human vs. mouse movement** | The law is about **human movement**, not mouse movement; assumptions about hand position may not hold |
| **Assumed hand on pointer** | Mouse-based application assumes the hand is always on the mouse and the pixel under the cursor is instantly usable (zero time) |
| **Environment assumptions** | Viewport edges are often not display edges (browser chrome; taskbars) → "infinite" edges may not be infinite |
| **Touch has no persistent pointer** | No cursor position known to the system; no part of the screen is "closer" to the user's hand by default |
| **Not directly fit-able to touch** | Touch results are predictable and repeatable but don't neatly fit an existing model; too many variables for a single Index of Difficulty fit (Hoober) |
| **Over-large buttons** | Overly large buttons stop being perceived as buttons; users focus on the action object (icon/label), sapping some size benefit |
| **Standards' assumptions** | Human-factors standards often assumed fit, young, non-colorblind, mostly white European male users and controlled environments |

> **RULE:** Use Fitts's law as a **directional design principle** ("bigger, closer, less crowded"), not a precise predictor, especially on touch devices. Validate with real users in real contexts.

---

## 8. UI Design Implications: Target Size

### 8.1 Size Principles

| # | Principle | Detail |
|---|---|---|
| 1 | **Bigger is better** | People are faster to click, tap, or hover on bigger targets; **error rates go down** as target size increases |
| 2 | **Determine guideline sizes by error rate** | Guidelines usually derive from measuring error rates at various sizes and finding where the rate **levels off** |
| 3 | **Distinguish interactive elements by size** | Command buttons and interactive elements should be distinguished from non-interactive ones; larger buttons are easier to click; smaller ones require precision and raise selection time |
| 4 | **Make the whole target clickable** | Links (text, image, or button, e.g., ASOS) should respond across their whole region; forcing the cursor over a specific portion is a common web design failure |
| 5 | **Icons plus labels** | An icon + text label forms a larger target than the icon alone (assuming the entire area is active), improving movement time and reducing ambiguity |
| 6 | **Effective size matters** | Optimize the **effective** size in the direction of user movement |

### 8.2 Spacing & Padding

| Issue | Guidance |
|---|---|
| **Don't crowd targets** | Close, small targets → overshoot and accidental activation of the wrong target |
| **Padding is not enough** | Invisible padding enlarges the active area, but if users don't know it's there they still slow down cautiously near the visible edge |
| **Consequence-aware spacing** | Place dangerous/unrelated items **far** from other items to limit accidental-tap consequences |
| **Related targets in sequence** | Place them close, but not too close |

### 8.3 Bigger-Is-Better Caveats (Hoober)

- Overly large buttons can lose "button-ness" and not be perceived as buttons.
- Users aim at icon/label inside a button, not its full extent.
- Make elements only as big as needed for their **expected screen location**; keep labels clear and succinct.

---

## 9. UI Design Implications: Distance & Position

### 9.1 Distance Principles

| # | Principle | Detail |
|---|---|---|
| 1 | **Reduce distance between sequential controls** | Cluster functions that are commonly used together |
| 2 | **Place controls near the user's likely prior position** | Position targets close to the user's most probable previous location |
| 3 | **Pop-ups over drop-downs** (mouse UIs) | Pop-up/context menus appear at the pointer ("zero point," "prime pixel," "magic pixel"), so no travel |
| 4 | **Keep task controls near the task area** | Distance between the user's attention area and the task-related button should be as short as possible |
| 5 | **Avoid small, far-apart objects** | Small objects spread apart take the longest to select |

### 9.2 Screen Edges and Corners (Mouse/Trackball)

| Concept | Description |
|---|---|
| **Rule of the infinite edges** | Screen edges act as walls; targets there are effectively infinite along the axis of movement; users needn't slow down |
| **Magic corners** | Two edges collide → doubly infinite; the easiest non-cursor areas to hit |
| **Examples** | macOS menu bar at the top edge (options become infinite targets); macOS close button upper-left with menu bar filling the corner; Windows Start button in the lower-left corner (until Windows 8 per NN/g; "prior to Windows 11" per Wikipedia); Windows taskbar along the bottom; Office 2007 "Office" button upper-left |
| **Task bars** | IxDF notes multiple/inner task bars need more precision than edge placement (and add confusion) |

### 9.3 Edge Advantage Does Not Transfer to Touch

- **Touchscreens:** no advantage; a study (Avrahami) found it actually takes **longer** to hit targets around the edges, possibly because on touchscreens you can overshoot past the edge.
- Hoober: "Edges and corners are the hardest to tap areas" on touch devices; good places to **hide low-use menus and anchored actions** — but only a few, and make them big.
- Viewport edges often aren't display edges even on desktops (browser chrome, taskbars).

### 9.4 Placement Examples in Forms

| Good | Poor |
|---|---|
| Submit/CTA placed next to or just below the **last form field** (Taxa 4x35, a Danish taxi app) | Submit/Save placed at the **top of the page/header** far from the last field (Sephora iPhone; forces long finger travel against natural top-down workflow) |

---

## 10. Menu Design Under Fitts's Law

### 10.1 Menu Type Comparison

| Menu type | Distance profile | Notes |
|---|---|---|
| **Linear menu** (vertical drop-down or horizontal nav) | Distance grows with position; first item nearest, last farthest | Order by **frequency of use** (most-used on top); if items are used about equally, **align the handle with the middle** of the menu so the farthest items are the first and last |
| **Rectangular / mega menu** | Items spread in two dimensions → lower average distance than linear | |
| **Pie / radial menu** | All items **equidistant** from the handle; wedge targets are large (bigger margin for error) | Relatively unfamiliar to users; benefits shrink when far from the cursor; unexpected (learning curve) |
| **Pop-up / context menu** | Starts at the pointer ("prime pixel") | Faster than fixed drop-downs; e.g., right-click menus |

### 10.2 Radial Menu Direction Effects

- Boritz et al. (1991): the **direction** of movement matters even when distances are equal — for **right-handed users**, selecting the **left-most** item was significantly harder than the right-most; no difference between upper→lower and lower→upper transitions.

### 10.3 Long Menus

- Short drop-downs and right-click menus were "resoundingly successful" by minimizing travel.
- Long drop-downs and title menus **impede** users by raising movement-time demands.

### 10.4 Mobile Contextual Menus

| Better | Worse |
|---|---|
| **Mail for iOS:** delete-icon contextual menu appears immediately next to the icon (minimal movement) | **Gmail for iOS:** ellipsis-menu options appear in a **bottom sheet far from the handle** — long finger travel |

Guideline: options should appear **close to the label/handle**.

---

## 11. Fitts's Law in the Touch Era (Hoober)

### 11.1 Common "Mouse-Era" Corollaries

| Term | Claim |
|---|---|
| **Zero point** | The pixel under the pointer is instantly usable without movement |
| **Bigger is better** | A larger target is always easier to click |
| **Magic edges** | Screen edges are "infinitely deep" |
| **Magic corners** | Corners are doubly infinite |

Hoober: these are **not universally true**; other factors apply — overly large buttons, unclear edges, unknown hand position, or no mouse at all.

### 11.2 Why the Assumptions Break

| Assumption | Problem on touch |
|---|---|
| Hand always on the pointer | Users type, write, hang up the phone, put the phone down; **we never know where the hand is** |
| Constant grip | People hold phones in many ways and shift grips constantly (see Section 13) |
| Cursor location is known | No system-detectable pointer; no screen area is inherently closer to the pointer (the hand) |
| Target size = horizontal component | Default mouse interpretation ignores actual geometry |
| Workspace persists | After a tap or scroll, fingers usually **move away** from the screen; sometimes users disengage entirely (drink, pocket, set phone down to watch) and must cognitively re-engage |
| Edges are walls | Viewports ≠ display edges; on touch you can overshoot |
| Focused, undistracted use | Real life is distracted; usability tests may overstate attention and speed |

### 11.3 Fitts's Work Is Not Generally Applicable

- Applies well to whole-arm limb movement; poorly to isometric joysticks and force-sensing controls; touch findings are repeatable but do not fit neatly into existing models.
- Hoober chose to provide **guidelines rather than mathematical models**, and **deliberately did not publish time-to-tap** values because they vary widely with context.

### 11.4 Everyday-Life Speed: The Disappearing-Controls Example

- Video players hide controls after a short time. With a mouse and focused attention this works (skip credits instantly; controls nearby).
- On touch, users tap, move fingers away, settle in, later realize they want to skip — must shift back to interactive mode, orient, and reach — by then the **controls have vanished**.
- **Guideline:** don't rely on short timeouts for controls or notifications; people live in the world and are distracted.
- **Testing tip:** put the phone in your pocket or sit back and let the system run, then re-engage; observe real contexts (analytics, ethnography), since usability tests can produce unrealistic attention.

### 11.5 Ethics of "One Best Way"

- Historical lineage: F. W. Taylor's scientific management → Gilbreth time-and-motion → assumptions of a single "best way."
- Aviation moved beyond it with **Crew Resource Management (CRM)** (teamwork, checklists, error avoidance).
- In digital design, "happy path only" thinking treats non-conforming user behavior as user error, making error prevention seem unimportant; Hoober calls this "just about unethical" for UX (a user advocate).
- Standards can be wrong, outdated, narrowly applicable, over-applied, misinterpreted, or misapplied; ask what guidelines mean for **your** users.

---

## 12. Old Advice vs. Touch Reality (Comparison Table)

*(Hoober's checklist: "current advice — good and bad" → "best new advice.")*

| # | Old (mouse-era / commonly repeated) advice | Hoober's touch-era advice |
|---|---|---|
| 1 | Lay out content top-to-bottom, left-to-right; most important in the **top-left** | People read and interact best at the **center**; put key info in the big scrolling middle area |
| 2 | Watch the fold; distrust scrolling (scrollbars are far away) | **Everyone scrolls** (gesture is easy); signal that more content exists but expect users to discover it |
| 3 | Keep all control options close; **Cancel and Submit right next to each other** | Accidents happen: keep **disparate and especially destructive choices far** from positive actions |
| 4 | **Guard dialogs** ("Are you sure?") protect from accidental activation | **Avoid destructive actions**; when needed, provide **undo** (or fake undo), not guards before the action |
| 5 | People are focused and want speed above all | People live in the world and are distracted: **don't time out** notifications or limit time to act |
| 6 | Edges and corners are infinitely deep → place menus there | Edges/corners are the **hardest to tap**; good for **low-use menus and anchored actions** — just a few, and make them **big** |
| 7 | Pop-ups are best (appear under the mouse) | Pop-ups are terrible (disassociated from context); use **in-UI items, drawers, accordions, contextual items** |
| 8 | Provide tools to select quickly, incl. jumping the mouse to the primary action | Empower **informed decisions**; for consequential choices, some **delay in reaching the action** provides a moment to think |
| 9 | Bigger is better: pad buttons; use very long labels for important buttons | Make elements only **as big as needed for their screen location**; clear, succinct labels |
| 10 | Radial menus are fastest (equal distances) | They lose value away from the cursor and are unexpected; the **learning curve** undermines the theoretical benefit |

> **[Source note]** Row 3 conflicts with common "keep Cancel and Submit close" guidance; row 4 conflicts with the "confirm destructive actions" pattern. These are Hoober's contextual recommendations, tied to touch and error-consequence reasoning.

---

## 13. Empirical Research on Touch Behavior

### 13.1 Research Base (Hoober, UXmatters 2017)

| Item | Detail |
|---|---|
| Observations | **1,300+** people observed using phones (streets, bus stops, trains, airports, coffee shops; several countries) |
| Additional | **651** observations in schools, offices, homes (with the eLearning Guild) — tablets and more user types |
| Meta-research | Dozens of ACM Digital Library reports normalized; all agreed with his findings; one study recorded **120 million** touch events |
| Other methods | Intercepts and remote unmoderated testing |
| Motivation | Earlier columns (2013) contained assumptions from desktop observation, older standards, and anecdotes; later research corrected them |

### 13.2 How People Hold and Touch Phones

| Finding | Value |
|---|---|
| People hold phones in **multiple ways**, depending on device, needs, context | — |
| They **change grasps without realizing** it (so cannot self-report/predict) | — |
| Touch the screen with **one thumb only** | **75%** |
| Hold the phone with **one hand** | **< 50%** |
| **Cradle** the phone (second hand for reach and stability) | **36%** |
| Hold in one hand, tap with a **finger of the other hand** | **10%** |
| Common holding methods | Six most common methods shown in his figure; more exist (device on surfaces, tablets, context-adaptive) |

- The thumb is the strongest digit; tapping with it means gripping with weaker fingers; in real-world jostling users **cradle** the phone, securing it with the non-tapping thumb.

### 13.3 Thumb Anatomy

- Thumb movement sweeps (extension/flexion) from the **carpometacarpal (CMC) joint** near the wrist; other joints bend the thumb toward the screen but add no additional sweep.
- Fingers grasping the handset limit thumb range; **shifting finger grip changes reach**.
- The familiar **thumb-sweep chart** (assumes one-hand grip, taps at the bottom, unreachable upper-left) is described as **incorrect**.
- In field research the **Back button** is used constantly — usually the most-used button on screen — even in the upper-right corner.

### 13.4 Touch Accuracy by Screen Region

| Finding | Detail |
|---|---|
| **Users prefer to view and touch the center** | They do not scan upper-left → lower-right (desktop) nor lower-right → upper-left; they often **scroll content to the middle** of the screen |
| **Center accuracy is highest** | Targets at the center can be as small as **~7 mm**; **corner targets need ~12 mm** |
| **Taps are never exact** | No observed user tapped the exact center of an icon; some missed entirely |
| **Sizing method** | Record all taps; misses lie on a continuum — pick an acceptable miss rate; Hoober's sizes contain **95%** of observed taps |
| **Mitigation** | Accept imprecision; place dangerous or unrelated items far from others |

### 13.5 Related Finding (NN/g via Avrahami)

- On touch devices, targets around the **edges** take longer to hit.

---

## 14. Touchscreen Technology & Obsolete Standards

### 14.1 Technology History (Why Standards Look the Way They Do)

| Technology | Description | Design consequence |
|---|---|---|
| **Light pens / styli** | Preceded the mouse; first production use in SAGE (US Air Force); a reader coupled to display timing (like the Nintendo Duck Hunt gun) | Pointing, selecting, copying, gesturing since the late 1960s |
| **IR grids** | Infrared beams across the screen detect the finger (1980s ATMs, kiosks); coarse beams detect the whole finger | Screen as a grid of large selectable areas → **large buttons**; thick bezels |
| **Resistive** | Flexible top layer presses onto a conductive grid; responsive/precise but fragile (or rugged and harder to use) | Made touch feel natural; now mostly obsolete |
| **Capacitive** | Finger acts as a capacitor sensed on an X–Y grid; coarse grids; reports a **single centroid** point | Doesn't work with gloves/any pen/dry skin; **finger size is irrelevant to accuracy**; pressure/multi-touch not consistently supported — "pretend touchscreens don't detect pressure" unless building a drawing tool or game |

### 14.2 Obsolete or Weak Standards (Hoober's Critique)

| Standard / source | Problem |
|---|---|
| **ISO (IR-grid era)** | Specifies **22 × 22 mm** targets to accommodate larger fingers; little research on pointing accuracy |
| **Pixel-based standards** | "Useless": device-independent pixels vary between screens and don't relate to human dimensions |
| **Nokia** | Borrowed an early version of Hoober's old standards and never updated |
| **Microsoft** | Suggests spacing between targets, but target sizes still too small |
| **Google / Apple** | Sizes seem based more on **platform convenience** than human factors |
| **W3C WCAG** | Assumes desktop PCs with keyboard/mouse at arm's length; uses 72/96 ppi pixel definitions; no reference to viewing angles, glare, distance; Hoober cites WCAG for clarity but notes it doesn't fit mobile well |

> **RULE:** Understand the **basis** of any target-size standard (technology, population, physical vs. pixel units) before adopting it. Prefer **physical dimensions** and empirical tap data.

### 14.3 Data-Skepticism Advice

- Designers usually have one phone (likely an iPhone though most of the world uses Android), are poor self-reporters, and are prone to biases (see `cognitive_bias_guide.md`); trust **data over gut**.
- Touch is **not** a natural paradigm; interaction patterns for touch are still developing.

---

## 15. Touch-Friendly Information Design Framework

| Zone | Content | Rationale |
|---|---|---|
| **Center of screen** | **Primary content** (lists, grids, main content) — design with real content from the start | Users read and touch best at the center; explains popularity of list/grid views |
| **Top and bottom edges** | **Secondary actions** — tabs (switch views/sections), action buttons (compose, search) | Reachable and consistent |
| **Corners → menus** | **Tertiary functions** hidden behind menus launched from a corner | Corners are hardest to tap but fine for low-use items |

- **Hamburger menu:** "wrong and must be eliminated" advice goes too far; it works poorly only when navigation to subsections is essential. Better: put key content at the center or architect the app to avoid deep category drill-down; tabs are more effective than a menu but still secondary.
- **Validation:** products using this layout tested with several user types; **100%** of test participants found a menu option within a few seconds, even users with no mobile experience.
- Follow-up series (announced): Part 2 — ten common user behaviors and tactics; Part 3 — five more heuristics for real-world touch design.

---

## 16. Case Studies & Examples

| Example | Domain | Lesson |
|---|---|---|
| **macOS menu bar (top edge)** | Desktop OS | Edge placement makes menus infinite targets (mouse only) |
| **Windows Start/taskbar** | Desktop OS | Corner/edge placement of frequent items (mouse only) |
| **Right-click context menu** | Desktop | Pop-up at the pointer = zero travel ("prime pixel") |
| **Pie/radial menus** | Various | Equal distances but unfamiliar; direction and handedness matter |
| **Mail for iOS vs. Gmail for iOS** | Mobile menus | Options appear beside the trigger vs. in a far bottom sheet |
| **Sephora (iPhone) vs. Taxa 4x35** | Mobile forms | Save/Submit far from the last field vs. CTA at the bottom near the last field |
| **ASOS links** | E-commerce | Whole link region should be clickable |
| **Video player controls** | Media | Short-timeout disappearing controls fail on touch/distracted use |
| **Back button** | Mobile UI | Most-used button on screen even in the upper-right corner |
| **Card, English & Burr (mouse vs. joystick/keys)** | HCI history | Fitts-based device comparison influenced the mouse's commercialization |

---

## 17. Application to Mobile App Design (Derived)

> Links source principles to `mobile_app_design_guide.md` and companions. These are design inferences, not source claims.

| Source principle | Mobile application |
|---|---|
| **Bigger targets, lower error** | Follow platform minimums (iOS 44 × 44 pt, Android 48 × 48 dp, WCAG 2.2 AA 24 × 24 CSS px floor) as **minimums**; Hoober's data (≈7 mm center, ≈12 mm corners) suggests enlarging targets located near edges/corners; verify physical sizes on target devices |
| **Icons + labels** | Bottom tab bars with icon **and** text; make the full tab cell tappable |
| **Spacing** | Keep ample space (the mobile guide's 8–12 pt buffer); increase spacing further where an accidental tap is costly |
| **Destructive actions** | Separate destructive controls from primary ones; prefer **undo** (snackbars/toasts with undo) over "Are you sure?" dialogs |
| **Related controls near each other** | Place primary CTAs near the last input; avoid header-only Save/Submit on long forms; sticky bottom action bars where appropriate |
| **Contextual menus** | Show menu options adjacent to the trigger (popover/context menu near the tapped item) rather than distant bottom sheets, when the trigger is mid-screen |
| **Center-focused layouts** | Place primary content in the center scrolling area; secondary actions in top/bottom bars; tertiary functions in corner menus |
| **Edges/corners** | Don't assume corners are easy: use larger targets for corner-anchored actions (FABs, menu icons) and only a few |
| **Thumb zone caution** | Treat thumb-zone charts as a **heuristic**: Hoober found grips vary widely (75% one-thumb; <50% one-handed; 36% cradle) and the classic thumb-sweep chart is incorrect; support multiple grips and both hands |
| **Distraction contexts** | Avoid short-timeout disappearing controls and time-limited notifications; keep controls available long enough for distracted users |
| **Gesture alternatives** | Provide tap alternatives; gestures are shortcuts (see the mobile guide's gesture rule) |
| **Back navigation** | Keep Back visible/predictable — it is the most-used control even at the top |
| **Testing** | Record taps and misses (heatmaps), test in realistic contexts (one-handed, walking, distracted), and choose a target size that captures ~95% of taps |
| **Standards literacy** | Prefer physical units (mm) or platform dp/pt with device verification; avoid raw pixel rules |

> **Cross-document note:** The mobile guide's "primary actions in the thumb zone" and "bottom tab bar" recommendations remain valid design heuristics for reach and convention, but Hoober's data implies users adapt grip constantly and prefer the **center** of the screen; combine reach heuristics with real-user validation.

---

## 18. Decision Rules (IF → THEN)

| Condition | Action |
|---|---|
| Designing any interactive element | Make it as large as sensible for its location; ensure the full visual + padded area is active and obvious |
| Element is an icon | Add a text label and make the icon + label a single tap target |
| Targets are close together | Increase spacing; especially for small targets |
| Padding used to enlarge active area | Don't rely on it alone — make the visible affordance large too |
| Controls are used in sequence | Place them near each other (not touching) and near the user's likely prior touch point |
| Form CTA | Place next to/below the last field, not in a distant header |
| Mouse-driven desktop UI | Use edges/corners for frequent controls; use pop-up/context menus; consider pie menus for equidistant options |
| Touch-driven UI | Do **not** rely on edges/corners as "fast"; put primary content in the center; use bigger targets near edges/corners |
| Linear menu | Order by frequency (most-used nearest the handle); if equal use, center the handle |
| Mobile contextual menu | Show options adjacent to the trigger |
| Destructive or dangerous action | Keep it far from common actions; provide undo instead of pre-action confirmation |
| Controls that auto-hide | Provide long timeouts, easy re-summon, and don't time out important notifications |
| Uncertain grip/hand position | Design for multiple grips; don't assume one thumb or one hand |
| Need to compare input devices | Use throughput (effective width, Shannon form; ISO 9241-9) |
| Evaluating touch guidelines | Check origin (technology/population/units); prefer research-backed physical dimensions |
| Temporal (blinking/timed) targets | Consider temporal ID (Dt/Wt): lengthen availability windows |
| Precise timing predictions needed | Fit Fitts parameters empirically for the specific device/context; don't reuse mouse constants for touch |
| Continuous motion (drawing) | Fitts's law is not the right model |

---

## 19. Checklists

### 19.1 Target Design Checklist

- [ ] All touch targets meet platform minimums and, where possible, exceed them in corners/edges
- [ ] Whole tappable area is obvious and active (icon + label, full links)
- [ ] Spacing adequate; small targets not crowded
- [ ] Destructive actions separated from primary actions, with undo available
- [ ] Sequential controls placed near each other and near the last interaction point
- [ ] Primary CTA near the end of the flow (e.g., last field), not far away
- [ ] Contextual menus appear adjacent to their trigger
- [ ] Primary content centered; secondary actions in top/bottom bars; tertiary in corner menus
- [ ] No reliance on edge/corner "infinite target" assumptions on touch
- [ ] Auto-hiding controls persist long enough for distracted users
- [ ] Supports different grips/hands; no single-thumb assumption

### 19.2 Research & Testing Checklist

- [ ] Record all taps (including misses); size targets to a chosen capture rate (e.g., 95%)
- [ ] Test in realistic contexts (walking, one-handed, distracted, disengage/re-engage)
- [ ] Observe grips instead of relying on self-report
- [ ] Verify sizes in physical units on real devices
- [ ] Review guidelines/standards for technology and population assumptions
- [ ] Use analytics/heatmaps for mis-tap rates and rage taps

---

## 20. Key Facts Reference

| Fact | Value |
|---|---|
| Law origin | Paul Fitts, **1954**, *J. Experimental Psychology* 47, 381–391 |
| Original ID | `log₂(2D/W)` bits |
| Shannon form | `log₂(D/W + 1)` (MacKenzie) |
| MT regression | `MT = a + b·ID` |
| Throughput | `IP = ID/MT` (bits/s), adjusted with effective width |
| Effective width | `W_e = 4.133 × SD` (spans 96% of a normal distribution; equals W at 4% error) |
| Two-component model | Woodworth, late 19th century |
| Welford | 1968, two-factor model |
| Kopper et al. | 2010, angle-aware variant |
| ISO | ISO 9241 published 2002 (Shannon form); 9241-9 recommends effective-width throughput |
| Rectangular targets | Use smaller dimension (MacKenzie & Buxton, 1992) |
| Temporal ID | `log₂(Dt/Wt)` (2016) |
| Touch grips | 75% one thumb; <50% one-handed; 36% cradle; 10% other-hand finger |
| Touch target size (center / corner) | ~7 mm / ~12 mm (95% of taps) |
| Obsolete ISO target | 22 × 22 mm (IR-grid era) |
| Research sample | 1,300+ observed; 651 more; 120M touch events (meta) |
| Menu discovery test | 100% of participants found a menu option within a few seconds |
| Fitts 1954 citations | ~8,675 |
| NN/g article | Raluca Budiu, July 31, 2022 |

---

## 21. People & Sources Reference

| Person / Source | Contribution |
|---|---|
| **Paul M. Fitts** | Law of movement (1954); cockpit human factors; Aviation Psychology Research Laboratory (Ohio State) |
| **R. S. Woodworth** | Two-component movement model |
| **Claude Shannon** | Information theory foundation |
| **George A. Miller** | Parallel information-theoretic work on memory |
| **Crossman (1956); Fitts & Peterson (1964)** | Effective target width |
| **Welford (1968)** | Two-factor model |
| **Card, English & Burr** | First HCI application; mouse vs. joystick/keys |
| **Scott MacKenzie** | Shannon formulation; target-size methods; with Buxton (1992) smaller-dimension rule |
| **Kopper et al. (2010)** | Angle-aware model |
| **Accot & Zhai** | Steering law |
| **Boritz et al. (1991)** | Radial menu direction effects |
| **Daniel Avrahami** | Edge targets slower on touchscreens |
| **Drewes** | Fitts's law and eye tracking controversy |
| **Steven Hoober** | Touch research; *Touch Design for Mobile Interfaces*; *Fitts' Law in the Touch Era*; UXmatters columns |
| **Raluca Budiu (NN/g)** | *Fitts's Law and Its Applications in UX* |
| **Interaction Design Foundation (IxDF)** | Definitions and UI implications |
| **F. W. Taylor / Gilbreth** | Scientific management / time-and-motion (context for "one best way") |
| **Wikipedia** | Formal model overview |

---

## 22. Glossary

| Term | Definition |
|---|---|
| **Target acquisition** | Moving a pointer to and selecting a target |
| **Index of difficulty (ID)** | Task difficulty in bits, from the D/W ratio |
| **Index of performance / throughput** | Information rate of pointing performance (bits/s) |
| **Effective width (W_e)** | Target width computed from actual selection spread |
| **Speed–accuracy trade-off** | Faster movement → more errors (and vice versa) |
| **Ballistic movement** | Fast initial phase toward the target |
| **Infinite target** | Target that can't be overshot (e.g., screen edge for a mouse) |
| **Magic corners / edges** | Screen corners/edges exploited as infinite targets |
| **Prime / magic pixel / zero point** | The pixel under the pointer where pop-ups appear |
| **Pie / radial menu** | Circular menu with equidistant items |
| **Steering law** | Model for constrained trajectory movements (menus) |
| **Temporal pointing** | Selecting targets defined in time |
| **Control-display gain** | Ratio between hand movement and cursor movement |
| **Contact patch** | Area of finger in contact with a touchscreen |
| **Centroid** | Geometric center reported as the touch point |
| **CMC joint** | Carpometacarpal joint; pivot of thumb sweep |
| **Cradling** | Holding the phone with one hand and stabilizing with the other |
| **Thumb-sweep chart** | Diagram of assumed thumb reach zones (criticized as incorrect) |
| **Guard dialog** | "Are you sure?" confirmation before an action |
| **Fake undo** | Deferred execution presented as undoable |
| **CRM** | Crew Resource Management (aviation teamwork/checklists) |
| **Isometric control** | Force-sensing control (no limb movement) |

---

## 23. Source Notes & Caveats

1. **Sources merged:** Laws-of-UX/IxDF definition summaries; NN/g (Budiu, 2022); Smashing Magazine (Hoober, *Fitts' Law in the Touch Era*); IxDF article "Fitts's Law: The Importance of Size and Distance in UI Design"; Wikipedia (*Fitts's law*); UXmatters (Hoober, *Design for Fingers, Touch, and People, Part 1*, 2017); Fitts (1954) abstract page with citation listings. Overlaps are deduplicated.
2. **Simplified statements:** IxDF summaries say the time is a function of distance **divided by** size; the actual model is **logarithmic** in the ratio (Section 4).
3. **Windows Start button timing:** NN/g says it was bottom-left until Windows 8; Wikipedia says prior to Windows 11. Treat as approximate.
4. **Data age:** Hoober's touch research (2013–2017) and standards critique reflect capacitive-touch smartphones of that era; percentages and millimeter sizes should be re-validated for current devices (foldables, larger phones, tablets).
5. **Hoober's caution about generalization:** he intentionally gives guidelines instead of formulas and doesn't publish time-to-tap; the ~7 mm/~12 mm sizes contain **95%** of observed taps, not 100%.
6. **Conflicting guidance across sources:** mouse-era advice (edges/corners fast; Cancel/Submit adjacent; guard dialogs; pop-ups) is contradicted or qualified by touch-era advice; both are recorded in Section 12.
7. **Loose inference:** the Wikipedia claim that distance matters more than size is weakly justified in the text.
8. **Omitted material:** IxDF course promotions, quizzes and "earn a gift" prompts, newsletter sign-ups, FAQ headings without answers, Baymard cart-abandonment promo statistic, Smashing/UXmatters advertisements, and the Semantic Scholar "related papers"/reference-list boilerplate. Only the abstract and a few related-paper themes from the Fitts 1954 page were retained.
9. **Derived sections:** Section 17 and the Decision Rules synthesize across sources and companion documents; they are not direct claims of any one source.
