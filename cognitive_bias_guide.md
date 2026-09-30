# Cognitive Bias — Structured Knowledge Base

> **Purpose:** Authoritative reference on cognitive biases: definitions, origins, mechanisms, a catalog of common biases, the "rationality debate," debiasing methods, and how biases affect both **users** and **designers/researchers** (with a deep dive on framing).
> **Audience:** Downstream AI agents and human designers, researchers, and product teams.
> **Companion documents:** `mobile_app_design_guide.md`, `aesthetic_usability_effect_guide.md`, `choice_overload_guide.md`, `chunking_and_progressive_disclosure_guide.md`.
> **Conventions:**
> - `> **RULE:**` = non-negotiable guidance. `> **KEY TAKEAWAY:**` = high-value summary.
> - Research claims and statistics are **source-reported**.
> - **[Source note]** = ambiguity, missing citation, or inconsistency in the raw material.
> - Sections marked **(Derived)** are design/research implications synthesized from the source, not direct source claims.

---

## Table of Contents

1. [Definition & Core Concept](#1-definition--core-concept)
2. [Key Takeaways](#2-key-takeaways)
3. [Origins & History](#3-origins--history)
4. [Heuristics: The Engine Behind Many Biases](#4-heuristics-the-engine-behind-many-biases)
5. [The Rationality Debate](#5-the-rationality-debate)
6. [Taxonomy: Ways to Classify Biases](#6-taxonomy-ways-to-classify-biases)
7. [Catalog of Common Cognitive Biases](#7-catalog-of-common-cognitive-biases)
8. [Causes of Cognitive Bias](#8-causes-of-cognitive-bias)
9. [Practical Significance Across Domains](#9-practical-significance-across-domains)
10. [Individual Differences](#10-individual-differences)
11. [Recognizing Bias in Yourself](#11-recognizing-bias-in-yourself)
12. [Reducing Bias: Debiasing, Mitigation & Modification](#12-reducing-bias-debiasing-mitigation--modification)
13. [Cognitive Bias vs. Logical Fallacy](#13-cognitive-bias-vs-logical-fallacy)
14. [Biases in UX: Users vs. Practitioners](#14-biases-in-ux-users-vs-practitioners)
15. [Deep Dive: Decision Frames & Framing Bias in UX Practice](#15-deep-dive-decision-frames--framing-bias-in-ux-practice)
16. [Application to Mobile App Design (Derived)](#16-application-to-mobile-app-design-derived)
17. [Decision Rules (IF → THEN)](#17-decision-rules-if--then)
18. [Checklists](#18-checklists)
19. [Key Facts Reference](#19-key-facts-reference)
20. [People & Sources Reference](#20-people--sources-reference)
21. [Glossary](#21-glossary)
22. [Source Notes & Caveats](#22-source-notes--caveats)

---

## 1. Definition & Core Concept

| Attribute | Description |
|---|---|
| **Cognitive bias** | A systematic error of thinking or rationality in judgment that influences our perception of the world and our decision-making ability |
| **Umbrella meaning (IxDF)** | The systematic ways in which the **context and framing of information** influence individuals' judgment and decision-making; common characteristic: judgment and decision-making that **deviates from rational objectivity** |
| **Formal pattern definition** | A systematic pattern of deviation from the norm or rationality in judgment |
| **Mechanism** | Rather than thinking through every situation, people conserve mental energy with **rules of thumb** based on past experience; these shortcuts increase efficiency by enabling quick decisions without thorough analysis, but can influence judgment **without awareness** |
| **Subjective reality** | Individuals build their own "subjective reality" from perceived input; this construction (not the objective input) may dictate behavior, so biases can cause perceptual distortion, inaccurate judgment, illogical interpretation, and irrationality |
| **Not always bad** | Some biases are **adaptive** and lead to more effective actions in a context; faster decisions are desirable when **timeliness is more valuable than accuracy** |

**Formal definitions (from source):**

| Definition | Source |
|---|---|
| Bias "that occurs when humans are processing and interpreting information" | ISO/IEC TR 24027:2021, 3.2.4; ISO/IEC TR 24368:2022, 3.8 |
| Systematic errors in cognition that occur when, having an epistemic goal, we **non-consciously deviate** from it by relying on irrelevant or partially relevant information and ignoring relevant information | Nadurak (2025), *Memory & Cognition* |

> **KEY TAKEAWAY:** Understanding our own intrinsic biases may not eliminate them, but it increases the chance we can identify them in ourselves and others, and serves as a safeguard against fallacious reasoning, unintentional discrimination, and costly mistakes.

---

## 2. Key Takeaways

1. Biases are the predictable by-product of mental shortcuts (heuristics); they are **systematic and directional**, not random.
2. Everyone has biases; they are easier to spot in others than in yourself.
3. Biases can be **useful** (fast, adaptive) or **harmful** (errors, discrimination, poor decisions).
4. **Framing** — the way identical information is presented — can produce opposite conclusions.
5. **Designers and researchers are as vulnerable as users**; their design choices and interpretations of data are biased by how problems are framed.
6. Biases **cannot be averaged away** with wisdom-of-the-crowd techniques because they cause systematic errors.
7. Debiasing works through **awareness, training, incentives, accountability, nudges, structured processes** (checklists), and considering alternatives.
8. Even **one-shot training** (videos, games) can measurably reduce biases, with effects lasting up to three months in one study.
9. The **rationality debate** (Gigerenzer vs. Kahneman/Tversky) is unresolved: some "biases" may be adaptive rules of thumb.
10. Ethical dimension: biases can be exploited to manipulate people, and can also be harnessed for good.

---

## 3. Origins & History

| Year / Period | Event |
|---|---|
| **1972** | Amos Tversky and Daniel Kahneman introduce the notion of cognitive biases after observing people's **innumeracy** — inability to reason intuitively with greater orders of magnitude |
| **1967** | Jones & Harris: classic fundamental attribution error study (Castro speech experiment) |
| **1974** | Tversky & Kahneman, *Judgment under Uncertainty: Heuristics and Biases* — people rely on mental shortcuts under uncertainty |
| **1970s onward** | Replicable experiments show human judgment differs from **rational choice theory**; heuristics-and-biases research spreads to medicine, political science, law, finance, management |
| **2001** | Jermias — link between confirmation bias and cognitive dissonance |
| **2005** | Shane Frederick develops the **Cognitive Reflection Test (CRT)** |
| **2009** | Koster, Fox & MacLeod introduce **cognitive bias modification** |
| **2012** | *Psychological Bulletin*: noisy information processing can generate ≥ 8 seemingly unrelated biases |
| **2017 (rev. 2024)** | Kathryn Whitenton (NN/g), *Decision Frames: How Cognitive Biases Affect UX Practitioners* |
| **2025** | Nadurak's conceptual analysis of heuristics and biases |
| **Ongoing** | Continually evolving list of biases across six decades of research in cognitive science, social psychology, behavioral economics |

**Fields with practical study of biases:** clinical judgment, entrepreneurship, finance, management, medicine, law, political science.

---

## 4. Heuristics: The Engine Behind Many Biases

Heuristics are mental shortcuts that provide **swift estimates about the likelihood of uncertain events**. They are efficient and simple for the brain to compute, but can introduce **predictable, systematic cognitive errors** (biases).

| Heuristic | Definition | Example / Risk |
|---|---|---|
| **Representativeness** | Judge frequency/likelihood by how closely an event resembles the typical case | Can activate stereotypes and inaccurate judgments of others; the **Linda problem** |
| **Availability** | Estimate likelihood by how easy examples are to recall (biased toward vivid, unusual, or emotionally charged examples) | Overestimating rare but memorable events (e.g., plane crashes) |
| **Anchoring** | Prefer initial reference points that are recalled | Insufficient adjustment from a starting value |
| **Affect** | Base a decision on an emotional reaction instead of a calculation of risks and benefits | |
| **Attribute substitution** | Unconsciously replace a complex judgment with an easier one | |

### 4.1 The Linda Problem (Conjunction Fallacy)

| Item | Detail |
|---|---|
| Setup | "Linda" is described as concerned about discrimination and social justice (suggesting feminist) |
| Question | Is Linda more likely (a) a bank teller, or (b) a bank teller **and** active in the feminist movement? |
| Common answer | Majority choose **(b)** |
| Correct logic | (b) is a **subset** of (a), so it can never be more probable — a **conjunction fallacy** |
| Why it happens | (b) seems more **representative** of the description |
| Caveat | If respondents assumed (a) implied Linda is *not* active in the feminist movement, that would be a **pragmatic implicature** |

---

## 5. The Rationality Debate

| Position | Claim |
|---|---|
| **Kahneman & Tversky school** | Biases are systematic deviations from rationality and defects of human cognition |
| **Gerd Gigerenzer** | Heuristics should not make us see human thinking as "riddled with irrational biases"; rationality is an **adaptive tool**, not identical to formal logic or probability calculus; "biases" are rules of thumb or **"gut feelings"** that can help make accurate decisions; no clear evidence behaviors are genuinely, severely biased once real-world problems are understood; many behaviors labeled biases may be **optimal decision strategies** ("ecologically rational") |
| **"Rationality war"** | Pivots on whether biases are primarily **defects** or **adaptive/ecologically rational**; recently reignited with critiques of *overemphasis on biases* |
| **Middle ground — Haselton & Buss** | Both defect and adaptivity: **evolution favors a bias toward the least costly error** (adaptive bias / error management) |
| **Berthet critique** | Many studies lack **ecological validity** (often vignette-based); more exploration of individual differences needed |

> **RULE:** Treat "cognitive bias" as a useful **predictive model of judgment error**, not proof that human reasoning is fundamentally broken. Validate impact in the real context before assuming harm.

**Example of a helpful bias:** Walking in a dark alley and interpreting a shadow as a mugger — may be a false alarm (a waving flag), but the shortcut helps avoid danger in time-critical situations.

---

## 6. Taxonomy: Ways to Classify Biases

### 6.1 Dimensions

| Dimension | Examples |
|---|---|
| **Group vs. individual** | Group: risky shift; Individual: most others |
| **Decision-making** (desirability of options) | Sunk-cost fallacy |
| **Judgment of likelihood / causation** | Illusory correlation |
| **Memory** | Consistency bias (remembering past attitudes/behavior as more similar to present ones) |
| **Motivation** | Desire for positive self-image → egocentric bias; avoidance of unpleasant cognitive dissonance |
| **Attention** | Attentional bias (e.g., people addicted to alcohol/drugs pay more attention to drug-related stimuli) |
| **In-group / out-group** | Ingroup bias, outgroup homogeneity bias (in-groups seen as more diverse and "better," even when arbitrarily defined) |
| **Self-directed** | Illusion of asymmetric insight, self-serving bias |

### 6.2 "Hot" vs. "Cold" Cognition

| Type | Nature |
|---|---|
| **Hot cognition** | Motivated reasoning; can involve a state of arousal |
| **Cold cognition** | Due to how the brain perceives, forms memories, and judges |

**Cold biases include:**
- **Ignoring relevant information** (e.g., neglect of probability).
- **Being affected by irrelevant information** — e.g., the **framing effect** (same problem, different responses by description); the **distinction bias** (choices presented together vs. separately yield different outcomes).
- **Excess weight on an unimportant but salient feature** (e.g., anchoring).

### 6.3 Measurement Instruments

| Instrument | Purpose |
|---|---|
| **Stroop task**, **dot-probe task** | Measure attentional biases |
| **Cognitive Reflection Test (CRT)** (Shane Frederick, 2005) | Measures susceptibility to some biases / links bias to cognitive ability |

---

## 7. Catalog of Common Cognitive Biases

*(Deduplicated across Wikipedia, IxDF, and Verywell Mind entries.)*

| Bias | Definition | Notes / Examples |
|---|---|---|
| **Fundamental attribution error (FAE, correspondence bias)** | Overemphasize personality-based explanations for others' behavior; underemphasize situational influences | Jones & Harris (1967): participants attributed pro-Castro attitudes to the writer despite knowing the speech direction was assigned. Reduced by **monetary incentives** and **accountability** for attributions |
| **Actor–observer bias** | Attribute own actions to external causes, others' behavior to internal causes | Own high cholesterol = genetics; others' = poor diet/exercise |
| **Implicit bias (unconscious bias)** | Attribute positive/negative qualities to a group; can be non-factual or an abusive generalization from a frequent trait to all individuals | |
| **Priming bias** | Influenced by the first presentation of an issue, forming a preconceived idea later adjusted with new information | |
| **Confirmation bias** | Search for/interpret information that confirms preconceptions; discredit contrary information | Related to cognitive dissonance (Jermias 2001); makes discussion of hot-button issues hard; plane-crash stories vs. millions of safe flights |
| **Belief bias** | Judge an argument's logical strength by the plausibility of its conclusion | |
| **Affinity bias** | Favor people most like ourselves | |
| **Self-serving bias** | Claim more responsibility for successes than failures; evaluate ambiguous information to one's benefit | Poker: win = skill, loss = bad cards |
| **Framing** | Narrow the description of a situation to guide toward a conclusion; same information framed differently → different conclusions | "Discounted" price attracts more buyers than the same price without the label (see Section 15) |
| **Hindsight bias** | View past events as predictable ("I-knew-it-all-along") | |
| **Embodied cognition** | Selectivity in perception, attention, decision, motivation based on the body's biological state | |
| **Anchoring bias** | Inability to adjust adequately from a starting point; relies on first information | Affects negotiations, medical diagnoses, judicial sentencing; average car price sets "good deal" expectations. Also usable to set others' expectations |
| **Status quo bias** | Hold to the current situation to avoid risk/loss (loss aversion); increased propensity to choose the default | Affects choices like car insurance or electrical service |
| **Overconfidence effect** | Over-trust in one's own decision-making capability | Most recurrent bias across management, finance, medicine, law; see Dunning–Kruger |
| **Dunning–Kruger effect** | Believing one is smarter/more capable than one is; failing to recognize one's incompetence | |
| **Physical attractiveness stereotype** | Assume attractive people have other desirable traits | |
| **Halo effect** | Positive impressions contaminate other evaluations | Brand halo in marketing; attractive = popular/successful/happy |
| **Attentional bias** | Attend to some things while ignoring others | Car buyer focuses on looks, ignores safety/gas mileage |
| **Availability heuristic (as bias)** | Overvalue information that comes to mind quickly | Overestimates probability of similar events |
| **False consensus effect** | Overestimate how much others agree with you | Mirror image of *collective illusions* |
| **Functional fixedness** | See objects (or people) as working only in a particular way | Not using a wrench as a hammer; not seeing a personal assistant's leadership potential |
| **Misinformation effect** | Post-event information interferes with memory of the original event | Basis for mistrust of eyewitness accounts |
| **Optimism bias** | Believe you're less likely to suffer misfortune and more likely to succeed than peers | |
| **Superiority bias** | (see 9.2) | Can be beneficial in team problem-solving by preventing premature consensus |
| **Sunk-cost fallacy** | Decision-making bias regarding desirability of options | |
| **Illusory correlation** | Misjudge how likely something is / whether one thing causes another | |
| **Consistency bias** | Memory bias: recall past attitudes/behavior as more similar to present | |
| **Egocentric bias** | Motivated by desire for positive self-image | |
| **Neglect of probability** | Ignoring relevant probability information | |
| **Distinction bias** | Choices presented together yield different outcomes than when presented separately | |
| **Illusion of asymmetric insight** | Self-directed motivational bias | |
| **Bias blind spot** | Not recognizing one's own biases | Also an individual-difference variable |
| **Projection bias, representativeness (trainable)** | See 12.3 | |
| **Approach bias** | Linked to reduced inhibitory control in people who ate more unhealthy snack food | |
| **Risky shift** | Group-level bias | |
| **Collective illusions** | Group mistakenly believes its views aren't shared by the majority when they are | |

---

## 8. Causes of Cognitive Bias

| Cause | Description |
|---|---|
| **Heuristics (mental shortcuts)** | Major contributor; often surprisingly accurate but can produce errors |
| **Bounded rationality** | Limits on optimization and rationality |
| **Limited information-processing capacity** | Brain's finite capacity |
| **Embodied cognition** | Biological state of the body shapes perception and decisions |
| **Prospect theory** | Loss-aversion-based decision framing |
| **Evolutionary psychology** | Remnants of adaptive mental functions |
| **Mental accounting** | |
| **Adaptive bias** | Decisions on limited information, biased by the cost of being wrong |
| **Attribute substitution** | Complex judgment replaced by an easier one |
| **Attribution theory** | |
| **Salience** | |
| **Naïve realism** | |
| **Cognitive dissonance** (and related: impression management, self-perception theory) | |
| **Emotional and moral motivations** | Two-factor theory of emotion; somatic markers hypothesis; introspection illusion |
| **Emotions, individual motivations, social pressures/influence** | |
| **Misinterpretation of statistics; innumeracy** | |
| **Noisy information processing** | Distortions in memory storage/retrieval; a 2012 *Psychological Bulletin* article shows ≥ 8 seemingly unrelated biases (regressive conservatism, Bayesian conservatism, illusory correlations, illusory superiority / worse-than-average effect, subadditivity effect, exaggerated expectation, overconfidence, hard–easy effect) can come from one information-theoretic mechanism |
| **Aging / decreased cognitive flexibility** | Bias may increase with age |
| **Complexity of the environment** | Too much information makes shortcuts necessary |

---

## 9. Practical Significance Across Domains

### 9.1 Institutional Impact

| Domain | Impact |
|---|---|
| **Management, finance, medicine, law** | **Overconfidence** is the most recurrent bias; anchoring and framing also play substantial roles |
| **Finance / securities regulation** | Regulation largely assumes perfectly rational investors; real investors face cognitive limits (biases, heuristics, framing) |
| **Entrepreneurship** | Bias is widespread; most entrepreneurial decisions are computationally intractable |
| **Law enforcement / legal decisions** | Confirmation bias and related errors affect investigative decisions and evidence evaluation; **accountability measures and checklists** show promise. A fair jury requires ignoring irrelevant features, weighing relevant ones, open-mindedness, and resisting appeals to emotion — biases make this systematically difficult (though predictably so) |
| **Health / eating** | Participants who ate more unhealthy snack food had less inhibitory control and more approach bias; biases linked to eating disorders and body image |
| **Property valuation** | Showing an **unrelated** property first shifted valuations of a second property (anchoring) |

### 9.2 Constructive Uses

- **Superiority bias** can benefit **team science and collective problem-solving** by producing a **diversity of solutions** and preventing premature consensus on suboptimal options.

### 9.3 Destructive Uses

- Authorities/marketers may **exploit** biases to manipulate; some medications and health-care treatments rely on biases to persuade; some argue governments should **regulate misleading ads**.

### 9.4 Collective Illusions & Misinformation

| Phenomenon | Detail |
|---|---|
| **Collective illusions** | People wrongly believe their views aren't shared by the majority |
| **False consensus effect** | Mirror image: wrongly believing one's views are the majority's |
| **Misinformation spread** | Lazer, Baum & Grinberg (2018) analysis of >16,000 false news stories shared by millions of Twitter users during the 2016 US election found false information spread significantly faster than accurate news; partly because misinformation aligns with existing beliefs and triggers emotional reactions (linked to confirmation and availability biases) |

> **[Source note]** The Lazer/Baum/Grinberg citation carries a `[citation needed]` flag in the raw text. Treat as unverified.

### 9.5 Pseudoscience Susceptibility

- Biases can make individuals more inclined to endorse pseudoscientific beliefs by requiring less evidence for claims that confirm their preconceptions. Conspiracy beliefs are often influenced by multiple biases.

---

## 10. Individual Differences

| Factor | Finding |
|---|---|
| **Stable susceptibility** | People have stable individual differences in susceptibility to biases such as **overconfidence, temporal discounting, and bias blind spot** |
| **Changeable** | Stable levels can be changed: training videos + debiasing games produced **medium to large reductions**, immediately and up to **three months later**, in six biases: **anchoring, bias blind spot, confirmation bias, fundamental attribution error, projection bias, representativeness** |
| **Cognitive ability (CRT)** | Higher CRT scores correlate with higher cognitive ability / rational-thinking skill and better performance on heuristics-and-bias tasks (results described as **inconclusive** but with a correlation) |
| **Age** | Older adults tend to be more susceptible and have less cognitive flexibility, but **can decrease susceptibility over ongoing trials**; younger adults show more cognitive flexibility, which helps overcome pre-existing biases (framing-task experiments) |
| **Habit & convention** | Relation among bias, habit, and social convention is an open issue |

---

## 11. Recognizing Bias in Yourself

> **RULE:** Assume you are biased. Everyone exhibits cognitive bias; it is easier to see in others.

**Signs you may be influenced by a bias (Verywell Mind):**
- Only paying attention to news that confirms your opinions.
- Blaming outside factors when things go badly.
- Attributing others' success to luck but taking personal credit for your own.
- Assuming everyone shares your opinions or beliefs.
- Learning a little about a topic and assuming you know all there is to know.

**Recognition is hard:** David Susman, PhD: it's often hard to recognize our own biases or those of people around us; and even harder to help others spot and change theirs.

**Multiple biases can stack:** e.g., misremembering an event (misinformation effect) and assuming everyone shares that memory (false consensus effect).

---

## 12. Reducing Bias: Debiasing, Mitigation & Modification

### 12.1 Terminology

| Term | Definition |
|---|---|
| **Debiasing** | Reducing biases in judgment/decision-making through **incentives, nudges, and training** |
| **Cognitive bias mitigation** | Debiasing specifically applicable to cognitive biases and their effects |
| **Cognitive bias modification (CBM)** | Modifying cognitive biases in healthy people; also a growing area of **non-pharmaceutical therapies** for anxiety, depression, addiction (CBMT) |
| **CBMT** | Technology-assisted (computer-based, with or without clinician support) therapy modifying cognitive processes; grounded in the cognitive model of anxiety, cognitive neuroscience, attentional models; also used for **obsessive-compulsive beliefs/OCD**; a sub-group of applied cognitive processing therapies (ACPT) |
| **Reference class forecasting** | Systematic debiasing of estimates using Kahneman's **outside view** |

### 12.2 Strategy Matrix

| Strategy | Detail |
|---|---|
| **Awareness & feedback training** | Feedback and information helping people understand biases reduced bias effects by **29%** (Verywell-cited study) |
| **Controlled vs. automatic processing** | Encourage controlled (deliberate) processing over automatic |
| **Consider factors influencing your decision** | Overconfidence? Self-interest? |
| **Challenge your own biases** | What factors did you miss? Overweighting some? Ignoring inconvenient information? |
| **Challenge others' biases respectfully** | Present facts in a **nondirective** way; ask them to consider another view or compromise rather than confronting them as irrational |
| **Incentives + accountability** | Monetary incentives and telling people they'll be held accountable increase accurate attributions (FAE) |
| **Structured tools** | Accountability measures, **checklists** (e.g., legal case evaluations) |
| **One-shot interventions** | Educational videos and debiasing games significantly reduced several biases |
| **Outside view** | Reference class forecasting |
| **UX-specific** | Slow down, gather context, test alternative frames (Section 15) |

> **RULE:** Do **not** rely on aggregating many people's judgments (wisdom of the crowd) to cancel bias: because biases cause **systematic** errors, averaging does not remove them.

### 12.3 Limits

- Understanding biases does not eliminate them; it only improves the odds of catching them.
- Individual training effects are measurable but partial (e.g., 29% reduction; "medium to large" in the video/game study).

---

## 13. Cognitive Bias vs. Logical Fallacy

| Aspect | Cognitive bias | Logical fallacy |
|---|---|---|
| **Root** | Errors in **thought processing** (memory, attention, attribution, etc.) | Errors in the **structure of a logical argument** |
| **Nature** | Psychological, often non-conscious | Argumentative/logical |

---

## 14. Biases in UX: Users vs. Practitioners

| Group | How bias enters | Design implication |
|---|---|---|
| **Users** | Presentation of information on pages/UIs affects likelihood of actions such as purchasing; framing identical information differently can lead to opposite decisions | Information design is decision design; choose framing responsibly |
| **Designers, researchers, stakeholders** | Same psychological principles guide **their** choices: interpretation of research findings, choosing among design alternatives, team dynamics | Build bias-checks into research reporting and design decisions |

**Bias-informed design tactic cited (loss aversion / prospect theory):** Allow users to **try a service before signing up** → more registrations. Example: **Resume-now.com** lets visitors pick a template and start customizing without an account; after investing time they feel **ownership**, and at the end, prompting account creation to download/save motivates signup to avoid "losing" their work.

**Book reference (Design for Cognitive Bias, David Dylan Thomas):** covers why brains take shortcuts; how bias influences user behavior, stakeholder decision-making, and team dynamics; techniques for noticing your own biases and using them for good; making products more humane and conscientious.

---

## 15. Deep Dive: Decision Frames & Framing Bias in UX Practice

### 15.1 Definitions

| Term | Definition |
|---|---|
| **Frame** | The context used to describe an idea, question, or decision; frames heavily influence interpretations by emphasizing (or ignoring) certain aspects of a situation |
| **Framing effect** | The same information leads to opposite conclusions depending on the frame; e.g., a "discounted" price attracts more buyers than the same price without the label (Kahneman & Tversky) |

**Why UX is especially vulnerable:** most UX design choices have **no single right answer**; trade-offs depend on context → highly susceptible to framing.

### 15.2 NN/g Experiment (Whitenton)

| Item | Detail |
|---|---|
| Scenario | Usability test with **20 users**; task: use the site's search function |
| Frames | **Negative:** "4 out of 20 users could not find the search function." **Positive:** "16 out of 20 users found the search function." (logically identical) |
| Participants | Just over **1,000 UX practitioners**, randomly assigned to one of the two frames |
| Question | "Should the search function be redesigned?" |

| Frame | Support a redesign |
|---|---|
| Negative (failure rate) | **51%** |
| Positive (success rate) | **39%** |

- Negative framing → practitioners **~31% more likely** (30.7% relative increase) to support a redesign; statistically significant at **p < 0.0001**.
- "I'm not sure" was technically the best answer (no information on site type, search importance, or implementation cost) — yet only a **minority** admitted not knowing.

**[Source note]** The article states both "31% more likely" and "30.7%"; these are the same relative difference (51 vs. 39) rounded differently.

### 15.3 Statistical Caution

> **RULE:** Do not report small-sample results as percentages for the whole audience. With **20 participants**, 16/20 ≠ "80% success rate" for the population; the true rate may lie anywhere between **58% and 93%** (95% confidence). Percentages require larger samples and significance testing.

### 15.4 Subtler Framing Effects in Design Decisions

| Type | Example | Risk |
|---|---|---|
| **Incomplete frame** | Considers only existing users, not potential future users | Overlooks opportunities to expand the audience |
| **Overly specific frame** | "Should we implement a responsive version of our site to better support some tasks?" | Overlooks other considerations, e.g., search-ranking benefit of mobile-optimized design |

### 15.5 How to Counteract Framing Bias

> **RULE:** Framing can't be eliminated (without context you couldn't compare options); the goal is to become **aware of your frame** so you don't unconsciously overlook information.

| # | Strategy | Detail |
|---|---|---|
| 1 | **Resist snap judgments** | Take time to think through context. A 20-user study likely took **40+ hours**; a little more time on how findings are presented vastly increases ROI |
| 2 | **Gather more context** | Admit (at least to yourself) when you lack data; identify what additional data is needed |
| 3 | **Experiment with different frames** | Restate the question in reverse or from another viewpoint; flip success ↔ failure rate; consider the **actual number of people affected**, not just the percentage |

---

## 16. Application to Mobile App Design (Derived)

> Implications linking this document to the other guides. These are design inferences, not source claims.

| Bias / concept | Mobile / UX application |
|---|---|
| **Framing** | Present research findings in both success and failure terms; test copy frames (e.g., "discounted" price labeling) ethically |
| **Loss aversion / endowment** | Let users try before sign-up (guest mode, templates); ask for account creation **after** investment, at a save/export moment; avoid deceptive pressure |
| **Status quo bias** | **Defaults matter:** choose sensible, user-serving defaults for settings, notifications, permissions; supports the `choice_overload_guide.md` "default/featured option" tactic |
| **Anchoring** | Order pricing tiers and first-shown values deliberately; first information sets reference points |
| **Halo effect / attractiveness stereotype** | Links directly to `aesthetic_usability_effect_guide.md`: attractive UI raises perceived usability, and can mask problems in testing |
| **Confirmation bias** | In research and stakeholder debates, seek disconfirming evidence; avoid cherry-picking supportive user quotes |
| **Availability heuristic** | Vivid anecdotes (one angry review) can outweigh data; triangulate with analytics |
| **Overconfidence / Dunning–Kruger** | Validate design assumptions through prototyping and user testing before building |
| **False consensus effect** | "Designers are not the users" — the designer's preferences aren't the population's |
| **Anchoring & attentional bias in stakeholders** | Structure reviews with explicit criteria and checklists |
| **Attentional bias in users** | Users focus on salient elements; use visual hierarchy and one primary action per screen |
| **Misinformation / collective illusions** | Design sharing/feeds with awareness that emotionally charged content spreads faster; consider friction, labeling, or source cues |
| **Ethics of persuasion** | Use bias knowledge to make products more humane, not manipulative (dark patterns) |
| **Small-sample research** | Report counts and confidence intervals; avoid over-precise percentages from small usability tests |
| **Debiasing team process** | Checklists, devil's-advocate roles, accountability for decisions, reference-class ("outside view") comparisons |

---

## 17. Decision Rules (IF → THEN)

| Condition | Action |
|---|---|
| Reporting usability results | State both the success and failure framing and the **absolute number of people affected** |
| Sample size is small (e.g., ~20) | Don't present percentages as population rates; give ranges/confidence intervals |
| Stakeholder wants a snap redesign decision from one data point | Pause; gather context (site type, importance of feature, implementation cost) |
| You lack the data to decide | Say "I'm not sure" and define what data is needed |
| A decision could look different if restated | Reframe it (reverse, other viewpoint) and check for changed conclusions |
| Decision frame considers only current users | Widen the frame to include potential future users |
| Decision question is overly narrow | Broaden to surface other considerations |
| Evidence disagrees with your view | Actively look for what you're missing; ask if you're overweighting some factors |
| Someone is entrenched in a biased view | Present facts non-directively; invite alternatives or compromise |
| Aggregating group estimates to fix bias | Don't; averaging won't remove systematic bias — use outside-view or structured methods |
| High-stakes judgments (legal, medical, financial, hiring) | Use checklists, accountability, and incentives for accuracy |
| Users must register | Consider try-before-sign-up; ask for sign-up at the point of value |
| Setting defaults | Choose defaults that serve users (status quo bias makes defaults powerful) |
| Designing for speed-critical decisions | Recognize that some heuristics are adaptive; don't over-correct |
| Judging a "bias" claim | Check ecological validity; consider that it may be an adaptive heuristic |

---

## 18. Checklists

### 18.1 UX Research Reporting Checklist

- [ ] Findings stated in multiple frames (success/failure)
- [ ] Absolute counts reported alongside percentages
- [ ] Small-sample caveats and confidence intervals included
- [ ] Context provided (site type, feature importance, cost)
- [ ] Alternative interpretations listed
- [ ] Disconfirming evidence actively sought

### 18.2 Design Decision Checklist

- [ ] Decision frame written down explicitly
- [ ] Frame includes current **and** potential users
- [ ] Question not overly specific
- [ ] Question restated in reverse/from another viewpoint
- [ ] Time taken to avoid snap judgment
- [ ] Missing data identified
- [ ] Overconfidence and self-interest considered
- [ ] Defaults and anchors chosen deliberately
- [ ] Persuasive patterns reviewed for ethics

### 18.3 Team Debiasing Checklist

- [ ] Structured evaluation criteria (checklist) used
- [ ] Accountability for decisions established
- [ ] Outside-view / reference-class comparison considered
- [ ] Diversity of solutions preserved before converging
- [ ] Bias-awareness training or debiasing game used

---

## 19. Key Facts Reference

| Fact | Value |
|---|---|
| Concept introduced | 1972 (Tversky & Kahneman) |
| Foundational paper | 1974, *Judgment under Uncertainty: Heuristics and Biases* |
| CRT developed | 2005 (Shane Frederick) |
| Cognitive bias modification introduced | 2009 (Koster, Fox & MacLeod) |
| Most recurrent bias in management/finance/medicine/law | Overconfidence |
| Framing experiment | ~1,000+ UX practitioners; 51% (negative frame) vs. 39% (positive frame) support redesign; p < 0.0001 |
| Small-sample CI example | 16/20 → true rate ~58%–93% (95% confidence) |
| Awareness training effect (Verywell) | 29% reduction in bias effects |
| Debiasing video/game effect | Medium–large reductions; sustained up to 3 months; 6 biases |
| Biases from one noisy-processing mechanism | ≥ 8 (2012 *Psychological Bulletin*) |
| False-news study | >16,000 false stories (2016 US election); `[citation needed]` |
| Estimated user-study time (20 users) | > 40 hours |

---

## 20. People & Sources Reference

| Person / Source | Contribution |
|---|---|
| **Amos Tversky & Daniel Kahneman** | Introduced cognitive bias; heuristics and biases; framing; "outside view" (Kahneman) |
| **Gerd Gigerenzer** | Opponent of the bias framing; ecological rationality; "gut feelings" |
| **Martie Haselton & David Buss** | Middle ground: bias toward the least costly error |
| **Koster, Fox & MacLeod** | Cognitive bias modification |
| **Shane Frederick** | Cognitive Reflection Test |
| **Jones & Harris (1967)** | Fundamental attribution error (Castro speech study) |
| **Jermias (2001)** | Confirmation bias and cognitive dissonance |
| **Berthet** | Ecological validity critique |
| **Nadurak (2025)** | Conceptual analysis of heuristics and biases |
| **Lazer, Baum & Grinberg (2018)** | False news spread `[citation needed]` |
| **David Dylan Thomas** | *Design for Cognitive Bias* |
| **Kathryn Whitenton (NN/g)** | *Decision Frames: How Cognitive Biases Affect UX Practitioners* (2017; rev. 2024) |
| **Kendra Cherry, MSEd** (reviewed by Amy Morin, LCSW) | Verywell Mind: *How Cognitive Biases Influence the Way You Think and Act* (updated June 4, 2026) |
| **David Susman, PhD** | Quote on difficulty of recognizing biases |
| **Interaction Design Foundation (IxDF)** | "What are Cognitive Biases?" definition |
| **Wikipedia** | Cognitive bias overview, history, taxonomy, list |

---

## 21. Glossary

| Term | Definition |
|---|---|
| **Bounded rationality** | Rationality limited by information, time, and cognitive capacity |
| **Conjunction fallacy** | Judging a conjunction as more probable than one of its components (Linda problem) |
| **Pragmatic implicature** | Conversational inference that can alter how a question is interpreted |
| **Innumeracy** | Inability to reason intuitively about large magnitudes/numbers |
| **Ecological rationality** | Decision strategies that are effective given the structure of the real environment |
| **Ecological validity** | Degree to which study conditions reflect real-world situations |
| **Hot vs. cold cognition** | Motivated/arousal-driven vs. information-processing-driven biases |
| **Outside view** | Judging from statistics of similar past cases (reference class), not the details of the current one |
| **Reference class forecasting** | Estimating by comparison to a class of similar prior situations |
| **Debiasing** | Reducing bias through incentives, nudges, training |
| **Cognitive bias modification (CBM/CBMT)** | Training/therapy to modify biased cognitive processes |
| **Collective illusion** | Group-wide mistaken belief that one's view is a minority view |
| **Loss aversion** | Losses loom larger than equivalent gains (prospect theory) |
| **Decision frame** | Context in which a question or decision is described |
| **Negative / positive framing** | Presenting the same outcome as loss/failure vs. gain/success |
| **Stroop task / dot-probe task** | Experimental measures of attentional bias |
| **CRT** | Cognitive Reflection Test |
| **Dark pattern** | (Derived term) manipulative UI exploiting biases |

---

## 22. Source Notes & Caveats

1. **Sources merged:** Wikipedia (*Cognitive bias*), Laws-of-UX-style summary, NN/g (Whitenton, *Decision Frames*), IxDF definition, Verywell Mind (Kendra Cherry), and a *Design for Cognitive Bias* book blurb. Overlapping definitions, history, and bias entries are deduplicated.
2. **Excluded promotional content:** Course marketing (IxDF Design Thinking course, newsletter subscription prompts, Forrester ROI claims, "10 Signs You and Your Partner Are Compatible") was omitted as not relevant to the knowledge base.
3. **Unverified citation:** The Lazer/Baum/Grinberg fake-news finding is flagged `[citation needed]` in the raw text.
4. **Numbers are source-reported:** e.g., the 29% training effect, "medium to large" reductions, and the framing-experiment figures were not independently verified.
5. **Bias catalog is a subset:** The list reflects commonly studied biases named in the source, not an exhaustive catalog (the source references a separate "List of cognitive biases").
6. **Debate remains open:** Whether "biases" are defects or adaptive heuristics is contested; the KB records both positions.
7. **Derived sections:** Section 16 and the Decision Rules for mobile/UX are synthesis, not direct claims of the sources.
