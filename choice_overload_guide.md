# Choice Overload (Paradox of Choice) — Structured Knowledge Base

> **Purpose:** Authoritative reference on choice overload / overchoice / the paradox of choice: definitions, psychology, evidence, controversies, and design countermeasures.
> **Audience:** Downstream AI agents and human designers, researchers, and product teams.
> **Companion documents:** `mobile_app_design_guide.md`, `aesthetic_usability_effect_guide.md`.
> **Conventions:**
> - `> **RULE:**` = non-negotiable guidance. `> **KEY TAKEAWAY:**` = high-value summary.
> - Study figures and claims are **source-reported**.
> - **[Source note]** = ambiguity, missing citation, or inconsistency in the raw material.
> - Sections marked **(Derived)** are design implications synthesized from the source, not direct quotations of research.

---

## Table of Contents

1. [Definition & Terminology](#1-definition--terminology)
2. [Key Takeaways](#2-key-takeaways)
3. [Origins & History](#3-origins--history)
4. [Psychological Mechanisms](#4-psychological-mechanisms)
5. [Preconditions (When the Effect Occurs)](#5-preconditions-when-the-effect-occurs)
6. [Moderators & Reversals](#6-moderators--reversals)
7. [Consequences](#7-consequences)
8. [Economic & Consumer Context](#8-economic--consumer-context)
9. [Landmark Studies & Data](#9-landmark-studies--data)
10. [Controversies & Counter-Evidence](#10-controversies--counter-evidence)
11. [Design Countermeasures](#11-design-countermeasures)
12. [Feature Creep & the Simplicity Tradeoff](#12-feature-creep--the-simplicity-tradeoff)
13. [Case Studies](#13-case-studies)
14. [Application to Mobile App Design (Derived)](#14-application-to-mobile-app-design-derived)
15. [Decision Rules (IF → THEN)](#15-decision-rules-if--then)
16. [Checklists](#16-checklists)
17. [Key Facts Reference](#17-key-facts-reference)
18. [People Reference](#18-people-reference)
19. [Glossary](#19-glossary)
20. [Source Notes & Caveats](#20-source-notes--caveats)

---

## 1. Definition & Terminology

| Term | Definition |
|---|---|
| **Choice overload** | Tendency for people to get overwhelmed when presented with a large number of options; often used interchangeably with *paradox of choice* |
| **Overchoice** | Paradoxical phenomenon in which choosing among a large variety of options is detrimental to decision-making (Alvin Toffler's term) |
| **Paradox of choice** | Concept popularized by Barry Schwartz: the more options we have, the less satisfied we feel with our decision; more choices require more cognitive effort → decision fatigue and increased regret |
| **Maximizer** | Person who seeks the optimal (maximum-utility) outcome |
| **Satisficer** | Person concerned with a decision that is "good enough" and meets desired criteria, rather than the best |
| **Choice architecture** | Techniques that organize the context in which people decide, to influence decisions (e.g., changing how choices are presented to reduce overwhelm without infringing on freedom) |
| **Second-order decisions** | Decisions made to simplify future decisions (e.g., a regular breakfast routine) |
| **Opportunity cost / missed opportunities** | Costs or benefits of options not chosen; mentally costly to compute across many options |
| **Decision fatigue** | Depletion of limited decision-making stamina → mental exhaustion and reduced self-control |
| **Featuritis / feature creep** | Adding marginally useful features that make a product overly complicated rather than desirable |
| **Decoy effect** | We feel more strongly about an option when three options exist than when only two |
| **Single-choice aversion** | Unwillingness to choose an attractive option when no alternatives exist to compare it against (Daniel Mochon) |
| **Variety** | Positive aspect of an assortment (valued when selecting an assortment) |
| **Complexity** | Negative aspect of an assortment (matters when choosing an item within it) |
| **Visual heuristic** | Shortcut of processing images as a whole (Townsend) |

> **KEY TAKEAWAY:** Too many options hurts decision-making ability and can significantly damage how users feel about the whole experience — including causing them to abandon the process.

---

## 2. Key Takeaways

1. Too many options impair decision-making and sour the overall experience.
2. When comparison is necessary, enable **side-by-side comparison** of related items or decision options (e.g., **pricing tiers**).
3. Optimize designs for the **decision-making process**: prioritize what is shown at any moment (e.g., a **featured product**) and provide up-front tools for narrowing choices (**search and filtering**).
4. Prefer **nudging / choice architecture** (organize, highlight, recommend) over **removing** options.
5. Choice overload is **conditional**, not universal (see Section 5).
6. Users take the path of least effort to protect themselves from information overload — simplicity usually wins.
7. The goal is the **sweet spot**, not the minimum: too few options also hurts (single-choice aversion; zero choice = very low satisfaction).
8. Each added feature adds decisions, explanations, error risk, and interaction complexity.

---

## 3. Origins & History

| Year | Event |
|---|---|
| **1956** | Miller: a consumer can process only about **seven items** at a time; beyond that, coping strategies are needed |
| **1970** | Alvin Toffler introduces **overchoice** in *Future Shock*; notes "freedom of more choices" becomes its opposite, "unfreedom" |
| **Mid-1970s** | Studies supporting real and perceived overchoice appear |
| **2001** | Iyengar & Lepper, "When Choice is Demotivating: Can One Desire Too Much of a Good Thing" — the study that sparked Schwartz's interest (did not itself coin "paradox of choice") |
| **2004** | Barry Schwartz publishes *The Paradox of Choice: Why More is Less*; with Andrew Ward publishes "Doing Better but Feeling Worse" ("unconstrained freedom leads to paralysis") |
| **2004** | Iyengar, Jiang & Huberman 401(k) study |
| **2015** | NN/g (Hoa Loranger) "Simplicity Wins over Abundance of Choice" |
| **2021** | The Decision Lab article on the paradox of choice (Pilat & Krastev) |

**Schwartz's motivation:** The range of choices available today far exceeds the past, yet consumer satisfaction has not risen as much as traditional economic theory predicts. Western (especially American) societies equate freedom with choice; businesses often assume more choice → greater customer utility. Schwartz found the opposite: more options made people less satisfied that they had chosen the best.

**Schwartz's position:** Well-being comes from "self-determination within significant constraints — within 'rules' of some sort." The role of psychology and behavioral economics is to find the limits on freedom that yield the greatest happiness.

---

## 4. Psychological Mechanisms

### 4.1 Core Mechanism

- Occurs when many **equivalent** choices are available.
- Deciding becomes overwhelming due to many potential outcomes and the risk of choosing wrong.
- Having many approximately equally good options is mentally draining: each must be weighed against alternatives.

### 4.2 Inverted-U Model of Satisfaction

| Number of options | Satisfaction |
|---|---|
| None | Very low |
| Initial increase | Rises |
| **Sweet spot (peak)** | Highest |
| Beyond the peak | Pressure, confusion, potential dissatisfaction increase; subjective state declines and can turn negative |

- Larger choice sets can be initially appealing, but **smaller choice sets → higher satisfaction and reduced regret**.

### 4.3 Time Perception

- Extensive choice sets feel harder under time constraints.
- Large sets + little time → **more regret**.
- More time → choosing is **more enjoyable** in large-array situations and results in **less regret**.

### 4.4 Responsibility, Regret & Cognitive Dissonance

- People in large-choice situations **enjoy the process more** but feel **more responsible**, and experience **more dissatisfaction and regret**.
- Responsibility produces **cognitive dissonance**: a mental gap between the choice made and the choice that "should have been" made; more options → higher chance of having chosen wrong.
- Opposing emotions (enjoyment vs. overwhelm) reduce motivation to decide and impair use of psychological processes that enhance the attractiveness of one's own choice.
- Post-choice: a nagging feeling of having missed something important (NN/g).

### 4.5 Maximizers vs. Satisficers

- Following Herbert Simon's **bounded rationality** and **satisficing**, Schwartz found the paradox affects **maximizers** most.
- Maximizers obsess over optimizing → harder with many options → **greater post-choice regret**.
- More options also increase **opportunity costs**, leaving more regret.

### 4.6 Effort Minimization

- Humans have limited information-processing capacity and often take the **path of least effort**, even when an alternative would yield better outcomes.
- Shortcuts protect against information overload and fatigue (users may appear "lazy" but are self-protecting).
- Every decision, large or small, costs time and effort; technological progress increases the work required to choose well.

---

## 5. Preconditions (When the Effect Occurs)

> **RULE:** Choice overload is **not** universal. Check these three preconditions before assuming it applies.

| # | Precondition | Implication |
|---|---|---|
| 1 | Chooser has **no clear prior preference** for an item type/category | If a preference exists, option count has little effect on decision and satisfaction |
| 2 | **No clearly dominant option**; all options perceived as equivalent quality | A superior option amid many lesser ones yields a more satisfied decision |
| 3 | Chooser is **less familiar** with the choice set | Negative correlation between assortment size and satisfaction appears only in less-familiar people; experts can sort through variety more easily |

Additional context: NN/g notes the correct level of choices depends on **context, user commitment and expertise, user goals, and mental capabilities**; human mental capacity is the constant.

---

## 6. Moderators & Reversals

### 6.1 Choosing for Others (Reverse Choice Overload)

- Choice overload **reverses** when people choose for another person (Polman): overload is **context-dependent**; choosing from many alternatives is not inherently demotivating.
- **Regulatory focus** differs for self vs. others ("selective focus on positive and negative information" — flagged in the source as `[citation needed]`).
- Personal decision-makers: a **prevention focus** is activated → more satisfied after choosing from few options.
- **Proxy decision-makers** experience the **reverse** effect.

### 6.2 Assortment Stages: Variety vs. Complexity

| Stage | What consumers want | Effect |
|---|---|---|
| **1. Select an assortment** (perception stage) | More **variety** | Variety is positive |
| **2. Choose an option within the assortment** | Lower **complexity** | Too much variety increases complexity → delay or opt-out |

### 6.3 Images vs. Verbal Descriptions

| Presentation | Processing | Effect |
|---|---|---|
| **Images** | Processed as a whole ("visual heuristic"); less mental effort; feels faster | Consumers prefer this shortcut regardless of choice-set size; images **increase perceived variety** (good for step 1) |
| **Verbal descriptions** | Words perceived individually and strung together | In large, varied sets, **perceived complexity decreases** with verbal descriptions |

### 6.4 Other Moderators

- **Time available** (4.3).
- **Expertise / familiarity** (Section 5).
- **Commitment:** restaurant customers tolerate inefficiency because they've already paid; web users are less committed and can easily leave.

---

## 7. Consequences

| Consequence | Detail |
|---|---|
| **Anxiety & decision fatigue** | Stamina for decisions is drained; mental exhaustion; reduced self-control |
| **Impulsive / default choices** | Fatigued people opt for easier, impulsive choices, e.g., splurging on prominently displayed or salesperson-recommended options; car buyers accept more **default features** at the end of the buying process |
| **Time cost** | Extensive deliberation (research, reviews) can consume so much time that people miss making a choice at all |
| **Default to routine** | Over-deliberation leads to regular defaults (same show, same takeout) and missed spontaneity/new experiences |
| **Choice avoidance** | Under time pressure, many prefer **no choice at all**, even if choosing would be better; consumers may be indecisive, unhappy, or refrain from purchasing |
| **Post-choice regret** | Especially for maximizers; increased by opportunity costs |
| **Abandonment** | Fatigue and dissatisfaction can cause users to abandon the process |
| **Slower decisions** | More choices increase time required to decide |
| **Errors** | Crowded screens/complex menus make it harder to notice the target option; more misunderstandings and accidental wrong selections |
| **Reduced ethical/self-regulatory capacity** | Polman & Vohs: decision fatigue reduces self-regulatory resources needed for ethical decisions |

**Decision-fatigue evidence (source-reported):**
- Doctors were more likely to prescribe unnecessary antibiotics after working several hours.
- Parole judges were more likely to grant parole in the morning than late in the workday.

**Real-life patterns cited:** grabbing takeout after a big grocery trip; staying home because choosing a Friday-night activity took too long.

---

## 8. Economic & Consumer Context

- Overchoice is most visible in economic settings: limitless products/services appear appealing but make decisions harder.
- Consumers often decide without sufficiently researching (which may require days).
- Brand counts (soaps to cars) have risen steadily for over 50 years.

| Example | Data |
|---|---|
| Soap and detergent brands offered by an average US supermarket | **65** (1950) → **200** (1963) → **360+** (2004) |
| Miller (1956) | ~**7 items** processable at once |
| Milk aisle illustration | Fat percentage (1%, 2%, skim…) × source (cow, almond, soy, oat…) creates overwhelm |

Two-step purchase process: (1) select an assortment; (2) choose an option within it (see 6.2).

**Sources of modern abundance:** social/scientific/technological advances; the internet and social media (options visible without visiting a store); new jobs and applications; dating apps.

---

## 9. Landmark Studies & Data

### 9.1 Iyengar & Lepper — Jam Study (2001)

| Item | Detail |
|---|---|
| Setting | Grocery store tasting display of gourmet jam |
| Incentive | Tasting ≥ 1 jam earned a **$1 coupon** for any jam |
| Conditions | **Extensive choice: 24 varieties** vs. **limited choice: 6 varieties** |
| Measures | Number who stopped to taste; number who purchased |
| Results | More shoppers **stopped** at the 24-jam table, but shoppers at the 6-jam table were **more likely to purchase** |
| Conclusion | Abundant options attract initially but may cause people not to decide at all |

> **[Source note]** The raw text gives no purchase-rate figures for this study.

### 9.2 Iyengar, Jiang & Huberman — 401(k) Participation (2004)

| Item | Detail |
|---|---|
| Data | ~**800,000** employee records |
| Finding | Participation **decreased** as plans offered more funds |
| Rate of decline | Every additional **10 funds** reduced participation by **up to 2%** |
| Extremes | Plans with **2 funds**: peak participation **75%**; plans with **59 funds**: as low as **60%** |
| Threshold | Plans with **fewer than 10 funds** had significantly higher participation than plans with more |
| Interpretation | Generous options may **intimidate** rather than entice; complex financial decisions need **guidance or recommendations** |

### 9.3 Choice Architecture — Cafeteria Study

- Two-year study: increasing **visibility and accessibility** of healthy foods increased healthy food sales and decreased unhealthy food sales.

### 9.4 Soda-Fountain Observation (NN/g, Loranger)

| Item | Detail |
|---|---|
| Device | Touchscreen soda machines mixing **100+ flavors** with multi-level menus |
| Normal task time | Usually **< 10 seconds** |
| With machine | Some users need **> 1 minute** (time on task bloated by **> 500%**) |
| Behaviors | New customers struggle with unfamiliar multi-level interface; some cycle "choose → dispense → sip → pour out → retry" |
| Outcomes | Long lines, grumpy customers; families with children and the elderly are especially affected; customers give up and leave |
| User quotes (paraphrased) | "Too much tech for a simple need"; "I just want a soda… not a job" |

> **KEY TAKEAWAY:** Subjecting the majority to unnecessary complexity to satisfy a few curious users is bad for business.

---

## 10. Controversies & Counter-Evidence

> **RULE:** Do not treat "fewer is always better" as a law. The evidence is mixed; the goal is calibration.

| Counterpoint | Detail |
|---|---|
| **People like having options** | Studies conflict; critics say the paradox lacks enough concrete scientific evidence |
| **Starbucks** | Hundreds of menu possibilities/customizations, yet hugely popular and profitable |
| **Decoy effect** | Feelings about an option are stronger with three options than two |
| **Single-choice aversion** (Mochon) | People avoid choosing an attractive option when no alternatives exist for comparison |
| **Enjoyment** | Decision-makers in large sets enjoy the process more, despite more regret |
| **Reversal** | Effect reverses for proxy decision-makers (6.1) |
| **Preconditions** | Effect absent with prior preference, dominant option, or expertise (Section 5) |

**Schwartz's response:** Compiled studies would likely average out — sometimes more options raise satisfaction, sometimes lower it. The answer is not to dismiss the effect but to find the **right balance / "magic number"** through more nuanced research.

---

## 11. Design Countermeasures

### 11.1 Strategy Matrix

| Strategy | Description | Examples from source |
|---|---|---|
| **Side-by-side comparison** | Let users compare related items/decision options directly when comparison is necessary | Pricing tiers |
| **Prioritize displayed content** | Decide what appears at a given moment; spotlight a default/recommended option | Featured product |
| **Narrowing tools up front** | Give users ways to reduce the set early | Search, filtering |
| **Categorization / grouping** | Organize options into categories | Netflix categories |
| **Highlighting** | Emphasize desirable/beneficial options | Prominently displayed healthy food |
| **Personalized recommendations** | Curate based on history to avoid endless scrolling | Netflix recommendations from watch history |
| **Visibility & accessibility** | Make beneficial options easier to see/reach | Cafeteria healthy-food study |
| **Guidance for complex decisions** | Provide recommendations/support | 401(k) fund selection |
| **Second-order decisions** | Help users set defaults/routines that simplify future choices | Regular routines |
| **Reasonable option counts** | Keep options at a level that allows easy decisions and faster task completion | NN/g conclusion |
| **Time relief** | Provide time/less pressure for large choice sets | Section 4.3 |

### 11.2 Nudging vs. Restriction

> **RULE:** Prefer **choice architecture (nudging)** over **restricting** choices. Manage overwhelm by presenting options more manageably rather than removing them, preserving autonomy and avoiding ethical issues.

- Example: Users would likely not want Netflix to delete content; they want it organized and curated.

### 11.3 Presentation Guidance (from variety/complexity research)

| Situation | Guidance |
|---|---|
| Helping users **select an assortment / browse** (variety wanted) | Use images to increase perceived variety and reduce effort |
| Helping users **choose within a large, varied set** (complexity is the risk) | Use concise verbal descriptions to lower perceived complexity |

---

## 12. Feature Creep & the Simplicity Tradeoff

### 12.1 The Paradox for Products

- Consumers are attracted to many capabilities and may find a feature-rich product **more appealing**, but when **deciding and using**, fewer options make selection easier.
- Business pressure exists to add features to differentiate or stay relevant.
- Key UI decision: **feature richness vs. simplicity**; the acceptable level of functionality is key to creating useful, long-lasting products.

### 12.2 Costs of Each Additional Feature

1. More things for users to consider (each takes time).
2. More explanations, help text, instructional overhead.
3. Greater risk of choosing wrong or making errors.
4. Feature interactions compound complexity and make mental-model formation harder.
5. More options make screens crowded and menus complex → harder to notice the target option → more selection errors.

### 12.3 Resistance to Added Work

> **RULE:** Do not add exploration work to an already satisfactory solution. Users resist it strongly — and web/app users, being less committed, can easily go elsewhere (or delete).

> **KEY TAKEAWAY:** Adding features of little or no value to most users undermines their ability to collect and process information efficiently. Keeping options at a reasonable level speeds decisions and task completion.

---

## 13. Case Studies

### 13.1 Tinder / Dating Apps

| Aspect | Detail |
|---|---|
| Then vs. now | Historically a limited pool of in-person options; dating apps provide access to many potential matches, essentially strangers |
| Paradox effects | "Is there someone better?" thinking; rash decisions due to insufficient time; careless mass right-swiping |
| Commitment | People less likely to commit or invest time since they can return to the app |
| Testimony | A *Stanford Daily* writer described how seemingly infinite options let them care less, distance themselves, and treat people like items in a shopping cart, leaving them deeply unhappy |

### 13.2 401(k) Plans

See 9.2. Extensive fund menus reduce participation; guidance helps.

### 13.3 Netflix

Curated recommendations based on watch history let users discover content without scrolling through everything; a model of choice architecture over restriction.

### 13.4 Starbucks

Counterexample: extensive customization and popularity (Section 10).

### 13.5 Soda Fountains

See 9.4. Over-featured interface for a simple need.

### 13.6 Related Reading Themes (from source)

- Tea-ordering joke: layered option after option (type, milk, sweetener) illustrating overload.
- Gift giving: many choices lead to suboptimal decisions.
- Terms of Service: information overload leads to clicking "agree" without reading (rash decision; anxiety/distress parallels).

---

## 14. Application to Mobile App Design (Derived)

> This section links source principles to the mobile guidance in `mobile_app_design_guide.md`. Items are design implications, not source claims.

| Source principle | Mobile design application |
|---|---|
| Limit options / prioritize what's shown | One primary action per screen; bottom tab bar limited to **3–5** destinations |
| Narrowing tools up front | Search, filters, sorting on lists and catalogs |
| Featured/default option | Highlight recommended plan, item, or next step |
| Side-by-side comparison | Compare pricing tiers/plans in a table or aligned cards (paywalls) |
| Progressive disclosure | Reveal detail on demand; show a "taste" of long lists with expand |
| Categorization | Group content (e.g., Netflix-style rows, tabs, chips) |
| Personalization | Recommendations from behavior; keep transparency and user control |
| Feature creep | MVP + MoSCoW prioritization; defer "won't-have" items |
| Onboarding | Keep to 3–5 skippable screens; avoid front-loading configuration choices |
| Time/mobile context | Users are on the go with limited time → fewer, clearer choices |
| Low commitment | On phones users delete quickly; simplicity lowers abandonment |
| Settings & customization | Offer sensible defaults; hide advanced options behind progressive disclosure |
| Testing | Observe time-on-task and errors, not just stated preferences |

---

## 15. Decision Rules (IF → THEN)

| Condition | Action |
|---|---|
| Many roughly equivalent options, users unfamiliar, no clear preference | High overload risk → reduce, group, recommend, or provide filters |
| One option is clearly best | Highlight it; overload risk is lower |
| Users are experts/have strong preferences | Larger sets are tolerable; offer power tools (search/filter/sort) |
| Users must compare | Provide side-by-side comparison of key attributes |
| Complex or high-stakes decision (e.g., finance) | Provide guidance, defaults, or recommendations; limit fund/option counts |
| Time-constrained context | Reduce options; surface defaults |
| Only one option available | Consider adding a comparison alternative (single-choice aversion) |
| Browsing/discovery stage | Use images and variety to attract |
| Choosing within a large set | Use concise verbal descriptions; reduce visual complexity |
| Someone is choosing on behalf of others (proxy) | Larger sets may be less problematic |
| Tempted to add a marginal feature | Test time-on-task; weigh added decisions, help text, and error risk; default to simplicity |
| Need to reduce choices without limiting autonomy | Use choice architecture (categories, highlights, visibility) rather than deletion |
| Users are maximizers | Anticipate regret; provide confidence cues and reassurance |
| Screen feels crowded | Remove or defer options; simplify menus |

---

## 16. Checklists

### 16.1 Design Review Checklist

- [ ] Number of options on each screen is justified
- [ ] A clear default/featured/recommended option exists where appropriate
- [ ] Search/filtering available for large sets
- [ ] Options grouped into meaningful categories
- [ ] Side-by-side comparison available when users must compare
- [ ] Marginal features deferred or hidden via progressive disclosure
- [ ] Advanced settings do not burden common tasks
- [ ] Time-on-task measured for core flows (watch for large inflation)
- [ ] Nudges preferred over removal of options
- [ ] Guidance provided for complex/high-stakes decisions
- [ ] Recommendation logic is transparent and controllable

### 16.2 Research Checklist

- [ ] Determine users' familiarity and prior preferences (preconditions)
- [ ] Test with different option counts to find the "sweet spot"
- [ ] Measure abandonment, time, errors, and regret/satisfaction after choice
- [ ] Include less-experienced users and edge groups (e.g., families with children, elderly)
- [ ] Compare stated appeal (attractive breadth) with actual usage behavior

---

## 17. Key Facts Reference

| Fact | Value |
|---|---|
| Term origin | Alvin Toffler, *Future Shock*, 1970 |
| Miller's limit | ~7 items (1956) |
| Schwartz book | *The Paradox of Choice: Why More is Less* (2004) |
| Schwartz & Ward paper | "Doing Better but Feeling Worse" (2004) |
| Jam study | 24 vs. 6 varieties; $1 coupon; Iyengar & Lepper 2001 |
| 401(k) study | Iyengar, Jiang & Huberman 2004; ~800,000 records; −up to 2% per +10 funds; 75% (2 funds) vs. as low as 60% (59 funds); <10 funds performs significantly better |
| Soap brand counts | 65 (1950) → 200 (1963) → 360+ (2004) |
| Soda machine | 100+ flavors; <10 s normal vs. >1 min; >500% time-on-task increase |
| Preconditions | 3 (no prior preference; no dominant option; low familiarity) |
| Decision-fatigue studies | Doctors (antibiotics), parole judges (morning vs. late day), car buyers (defaults) |
| NN/g article | Hoa Loranger, Nov 22, 2015 |
| TDL article | Dan Pilat & Dr. Sekoul Krastev, Feb 17, 2021 |

---

## 18. People Reference

| Person | Contribution |
|---|---|
| **Alvin Toffler** | Introduced "overchoice" (*Future Shock*, 1970); "unfreedom" |
| **Barry Schwartz** | Popularized the paradox of choice; Professor of Social Theory and Social Action, Swarthmore College; critiques the rational economic model assuming more choice = better outcomes |
| **Sheena Iyengar** | Choice researcher; author of *The Art of Choosing*; S.T. Lee Professor of Business, Columbia Business School; jam and 401(k) studies |
| **Mark Lepper** | Co-author of the jam study |
| **Andrew Ward** | Co-author with Schwartz of "Doing Better but Feeling Worse" |
| **Wei Jiang, Gur Huberman** | Co-authors of the 401(k) study |
| **George A. Miller (1956)** | Seven-item processing limit (cited as "Miller") |
| **Herbert Simon** | Bounded rationality and satisficing |
| **Daniel Mochon** | Single-choice aversion |
| **Polman (and Vohs)** | Reverse choice overload for others; decision fatigue and self-regulation |
| **Townsend** | "Visual heuristic" |
| **Hoa Loranger** | NN/g article on simplicity vs. abundance of choice |

---

## 19. Glossary

| Term | Definition |
|---|---|
| Assortment | The set of options offered |
| Bounded rationality | Simon's idea that decision-makers have limited information and cognitive capacity |
| Cognitive dissonance | Mental conflict between the choice made and the choice that should have been made |
| Default | Pre-selected or automatically accepted option |
| Featuritis | Feature creep making products exhausting for users |
| Inverted-U model | Satisfaction rises with options, peaks, then declines |
| Nudge | Subtle change in presentation steering people toward beneficial choices without removing options |
| Proxy decision-maker | Person choosing on behalf of someone else |
| Regulatory focus | Orientation (e.g., prevention focus) shaping how positive/negative information is weighed |
| Self-regulatory resources | Capacity for self-control and ethical decision-making, depleted by decision fatigue |
| Time on task | Duration to complete a task; used to measure complexity cost |
| Unfreedom | Toffler's term for the opposite of freedom when choice becomes overchoice |

---

## 20. Source Notes & Caveats

1. **Sources merged:** NN/g/Laws-of-UX-style summary of choice overload; Wikipedia entry on overchoice; The Decision Lab article "The Paradox of Choice"; NN/g article "Simplicity Wins over Abundance of Choice" (Hoa Loranger, 2015). Overlapping definitions and origin details are deduplicated.
2. **Missing citation:** The Polman regulatory-focus claim is marked `[citation needed]` in the source.
3. **Study date:** The source dates the Iyengar & Lepper jam study to 2001 as written; preserved as reported. No purchase-rate numbers were provided.
4. **Mixed evidence:** Critics argue the effect lacks concrete scientific support; Schwartz argues results average out and the task is to find the optimal number. Treat the effect as conditional.
5. **Anecdotal elements:** Soda-machine observations, quotes from commenters, and dating-app testimony are illustrative, not controlled experiments.
6. **Statistics:** All figures are source-reported and not independently verified.
