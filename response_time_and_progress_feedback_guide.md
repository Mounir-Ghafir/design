# Response Time, the Doherty Threshold & Progress Feedback — Structured Knowledge Base

> **Purpose:** Authoritative reference on how system response time shapes user productivity, attention, and satisfaction, and how feedback (including progress indicators) mitigates waiting. Consolidates three sources: (A) the **Doherty Threshold** (Laws of UX summary + Doherty & Thadhani's 1982 IBM brief), (B) **Robert B. Miller (1968)**, *Response Time in Man-Computer Conversational Transactions*, and (C) **Brad A. Myers (1985)**, *The Importance of Percent-Done Progress Indicators for Computer-Human Interfaces*.
> **Audience:** Downstream AI agents and human designers, developers, researchers, and product teams.
> **Companion documents:** `mobile_app_design_guide.md`, `cognitive_load_guide.md`, `chunking_and_progressive_disclosure_guide.md`, `choice_overload_guide.md`, `cognitive_bias_guide.md`, `aesthetic_usability_effect_guide.md`.
> **Conventions:**
> - `> **RULE:**` = non-negotiable guidance. `> **KEY TAKEAWAY:**` = high-value summary.
> - Figures and claims are **source-reported**.
> - **[Source note]** = ambiguity, inconsistency, or quality warning in the raw material.
> - Sections marked **(Derived)** are implications synthesized from the sources, not direct source claims.
> - **Disambiguation:** three different "Miller"s appear across this knowledge base — **George A. Miller** (1956, "Miller's Law," 7 ± 2 memory), **Robert B. Miller** (1968, response time; this document), and **Lawrence H. Miller** (1977, constant vs. variable response time; cited by Myers).

---

## Table of Contents

1. [Overview & Scope of Sources](#1-overview--scope-of-sources)
2. [Key Takeaways](#2-key-takeaways)
3. [Foundational Concepts & Definitions](#3-foundational-concepts--definitions)
4. [Timeline & Origins](#4-timeline--origins)
5. [Part A — The Doherty Threshold](#5-part-a--the-doherty-threshold)
6. [Part B — Miller (1968): Response Time Principles](#6-part-b--miller-1968-response-time-principles)
7. [Part B (cont.) — The 17 Response Topics](#7-part-b-cont--the-17-response-topics)
8. [Part C — Percent-Done Progress Indicators (Myers, 1985)](#8-part-c--percent-done-progress-indicators-myers-1985)
9. [Part C (cont.) — The Experiment](#9-part-c-cont--the-experiment)
10. [Synthesis: Response-Time Tiers](#10-synthesis-response-time-tiers)
11. [Perceived Performance Techniques](#11-perceived-performance-techniques)
12. [Later Research Signals (Low-Confidence)](#12-later-research-signals-low-confidence)
13. [Application to Mobile App Design (Derived)](#13-application-to-mobile-app-design-derived)
14. [Decision Rules (IF → THEN)](#14-decision-rules-if--then)
15. [Checklists](#15-checklists)
16. [Key Facts Reference](#16-key-facts-reference)
17. [People & Sources Reference](#17-people--sources-reference)
18. [Glossary](#18-glossary)
19. [Source Notes & Caveats](#19-source-notes--caveats)

---

## 1. Overview & Scope of Sources

| Source | Type | Core contribution |
|---|---|---|
| **Laws of UX–style summary: "Doherty Threshold"** | Design principle summary | Feedback within **400 ms** keeps attention and raises productivity; perceived performance tactics |
| **Doherty & Thadhani (Nov 1982), "The Economic Value of Rapid Response Time"** (IBM; reproduced on Jim Elliott's Mainframe Blog) | Industry research brief | Productivity rises more than proportionally as response time drops; sub-second response yields large cost, schedule, and quality gains |
| **Blog commentary (June 15, 2015, #webperf)** | Popularization | Frames the finding for web performance; cites "under 400 ms" |
| **Robert B. Miller (1968)**, AFIPS Fall Joint Computer Conference | Foundational conceptual paper | Response-time requirements depend on *what* the response is to; catalog of **17 response types** with estimated time limits; psychological rationale |
| **Brad A. Myers (1985)**, CHI '85 | Empirical paper | Percent-done progress indicators: implementation and a 48-subject experiment showing users prefer them |
| **ResearchGate citation snippets** | Secondary, low-confidence | Later work citing Myers (2025–2026 papers on agentic assistants, VR agents, progress-bar thickness) |

> **KEY TAKEAWAY:** Response time is not one number. Acceptable delay depends on the *type* of response, the user's *task continuity* (closure), and whether *feedback* tells them the system is working. Fast responses raise productivity nonlinearly; where speed is impossible, well-designed progress feedback reduces anxiety and improves preference.

---

## 2. Key Takeaways

1. Provide system feedback within **~400 ms** to keep users' attention and increase productivity (Doherty Threshold).
2. Productivity increases **more than in direct proportion** to decreases in response time; gains accelerate below one second.
3. The older "**2-second**" rule (from Miller 1968) assumed users were thinking during the wait; Doherty's research showed users hold a sequence of actions in short-term memory that delays **disrupt**.
4. Miller himself stated that "two-second response" is **not a universal requirement**: acceptable delay depends on the response type and on **closure** (a perceived sense of task completion).
5. **Direct manipulation feedback** (key/click/tap) should be effectively immediate: **≤ 0.1 s**.
6. Delays > **~2 s** are acceptable mainly **after task closure**; delays > **~15 s** break conversational continuity and should free the user to do other things.
7. **Progress indicators** are preferred by users (86.1% liked them; p = 0.0006 in Myers' study) and show that the system has not crashed.
8. Users' feelings about constant vs. variable response time were **not** significantly different in Myers' replication; earlier "constant is better" findings may not generalize.
9. **Perceived performance** techniques (animation, progress bars, skeleton/loading feedback) make waits more tolerable, even if not perfectly accurate.
10. Speed improvements have **downstream infrastructure implications**: faster users generate more transactions and more computing load.
11. After failures, **recovery time** and **state preservation** matter psychologically (Miller Postscript 2).

---

## 3. Foundational Concepts & Definitions

### 3.1 Elements of an Online Transaction (Doherty & Thadhani)

A **transaction** = a user command from a terminal + the system's reply; the fundamental unit of work for online users.

| Component | Definition |
|---|---|
| **User response time (think time)** | Span between receiving a complete reply to one command and entering the next |
| **System response time (SRT)** | Span between entering a command and the display of a complete response |
| ↳ **Computer response time** | Time the computer spends processing/servicing the command |
| ↳ **Communication time** | Transit time of the command to the computer and the reply back |

### 3.2 Miller's Semantic Questions

| Question | Implication |
|---|---|
| **"Response time to what?"** | Different human purposes and actions have different acceptable response times; "response time" needs a definition per response type |
| **"What is a need or requirement?"** | Miller's working definition: "some demonstrably better alternative in a set of competing known alternatives that enable a human purpose or action to be implemented" (intentionally ignores value vs. cost). Alternative view: need = what is demanded and can be made available (a cultural/technical outcome) |

### 3.3 Operating vs. Psychological Needs

| Type | Example | Notes |
|---|---|---|
| **Operating need** | An airplane must exceed stall speed to stay aloft; hypothetical: airline reservation delays > 5 minutes reduce future reservations by 20% (Miller says "let's assume we know the numbers"); longer processing → more clerks/terminals needed | Miller does not explore these except to note when they outweigh a psychological need |
| **Psychological need** | (a) response to expectancies; (b) activity clumping and closure; (c) short-term-memory limits | Focus of Miller's paper |

### 3.4 Psychological Constructs Used by Miller

| Construct | Description |
|---|---|
| **Response to expectancies** | In human conversation, you expect some communicative response within ~**2–4 seconds** (even a grunt); silences > **4 seconds** become embarrassing, implying a break in the thread of communication (like a dead phone line) |
| **Conditioning evidence** | Experiments (to be used cautiously for cognitive activities) suggest an almost "magical" **2-second boundary** for effectiveness of feedback ("knowledge of results"), with peak effectiveness for very simple responses at about **0.5 s** |
| **Activity clumping & closure** | Humans organize activity into clumps terminated by completion of a subjective purpose/subpurpose ("closure"); delays are tolerated more readily **after** closure than **during** the process toward it |
| **Hierarchy of closures** | Closure comes in degrees (find the name → dial the number → reach the person); **greater closure → longer acceptable delay** |
| **Short-term memory** | Tasks require holding information in mind; interruption/delay causes frustration; the longer content is held, the greater the risk of forgetting or error; awareness of waiting arrives within a few seconds; closure partially purges short-term memory |
| **Step-down discontinuities** | Efficiency does not fall in a straight line with delay; **sudden drops** occur at certain delay points — so a 10-second system may be no better (for some tasks) than a 1-minute or 5-minute one |
| **"Mental heat"** | Sustained, concentrated attention in creative work can "cool off" in interruptions < 1 minute; systems should preserve it |
| **Psychological present** | Interval subjectively felt as "now": **2.3–3.5 s** (up to ~12 s in special conditions) (cited via Stevens) |

---

## 4. Timeline & Origins

| Year | Event |
|---|---|
| **1956** | George A. Miller: memory limits (see `chunking_and_progressive_disclosure_guide.md`) |
| **1968** | Robert B. Miller: response-time principles; conversational-mode requirements; 2-second rule for "meaningful replies" after closure |
| **1968** | Carbonell, Elkind & Nickerson: psychological importance of time in time-sharing (cited by Myers) |
| **1974** | Foley: novices likely to panic without feedback (cited by Myers) |
| **1976** | Spence: graphical count-down clock in a CAD-CAM application (early progress display) |
| **1977** | Lawrence H. Miller: study finding preference for constant response time (cited by Myers) |
| **1979** | Doherty & Kelisky: each second of SRT degradation adds a similar degradation to the user's next-command time; NIH system studies |
| **1979–1982** | Thadhani's article; IBM confirmatory studies (SPD, Portsmouth, Poughkeepsie) |
| **1982 (Nov)** | Doherty & Thadhani publish the IBM brief; in the Laws of UX framing, it "set" 400 ms (not 2,000 ms) as the requirement |
| **1984** | Progress indicators in Apple Macintosh MacTerminal file transfer; Sapphire/PERQ systems integrate them |
| **1985** | Myers, CHI '85: formal experiment on progress indicators |
| **2015** | Blog revival of the Doherty paper (#webperf) |

---

## 5. Part A — The Doherty Threshold

### 5.1 Statement

> **RULE (Doherty Threshold):** Productivity soars when a computer and its users interact at a pace (**< 400 ms**) such that neither has to wait on the other. Provide system feedback within 400 ms to keep users' attention.

| Claim | Detail |
|---|---|
| **Laws of UX–style origin claim** | Doherty & Thadani (1982, *IBM Systems Journal*) set computer response time at **400 ms, not 2,000 ms** (the previous standard); responses under 400 ms exceed the "Doherty threshold," and applications were deemed "addicting" |
| **Original brief's framing** | When system and user interact at a balanced pace: productivity soars, cost per task falls, employee satisfaction and quality improve; productivity rises **more than proportionally** with reduced response time |
| **Blog popularization** | Under 400 ms an activity is "addicting"; over 400 ms it's "painful" and attention strays (dramatized by the TV series *Halt and Catch Fire*) |

> **[Source note]** The excerpted 1982 text emphasizes **sub-second** response and reports data points at 0.25, 0.3, 0.5, 0.6, and 1.0 s; the specific "400 ms" figure and the "addicting" language come from the summary/popularizing sources (and a chart described in the blog). Treat 400 ms as a widely cited design target rather than a single experimentally isolated cutoff in the excerpted brief.

### 5.2 Why Earlier Thinking Was Wrong

- Early belief: up to 2 seconds was fine because users were **thinking about the next step** during the wait; users were assumed to think at their own pace, uninfluenced by system speed.
- Doherty & Kelisky (1979): each second of SRT degradation leads to a similar degradation added to the user's time for the next command; related to **attention span**. People hold a **sequence of actions in short-term memory**; longer SRT disrupts the thought process and may force them to **rethink the sequence**.

### 5.3 Evidence Catalog

| Study | Setting | Findings |
|---|---|---|
| **Thadhani** (IBM San Jose) | Programmers | 3.0 s SRT → ~**180 transactions/hour**; 0.3 s → **371/hour** (**+106%**); a 2.7 s reduction saves **10.3 s** of user time per transaction; gains rise dramatically below 1 s |
| **NIH computer utility (1979)** | Designed for **300** simultaneous users (80% of transactions ≤ 0.5 s); ~95,000 tasks/month | Grew to almost 400 users (projected 500 in 18 months); at **390 users**, computer response degraded to **~4 s** avg; average task time rose **32 → 48 min (+50%)**; users spent **22,500 extra hours/month** at terminals for the same number of tasks; cost **~$900,000/month** — **15×** the incremental cost of a processor supporting sub-second response for 500 users |
| **IBM System Products Division (SPD)** | 75 work sessions, 15 engineers, high-function graphics | Confirmed Thadhani's curve; **all users** benefited from sub-second response; an average experienced engineer with sub-second response was as productive as an expert with slower response; novice performance matched experienced professionals; expert productivity dramatically enhanced |
| **SPD card-wiring experiments** (4 labs) | Task time vs. SRT | Significant task-time reductions in all labs. **Lab A:** 82 → 66 min (**20%**) as SRT fell 6 s → 0.25 s. **Lab D:** 36 → 23.5 min (**35%**) as SRT fell 0.6 → 0.25 s (3.6 min saved per 0.1 s) |
| **IBM Portsmouth (England)** | Programming project with individual terminals and high-speed lines | SRT reduced **2.3 s → 0.84 s**. Estimated **30.8** programmer-months over 19 weeks; actual **18.7** programmer-months (**39% less**), finished **4 weeks early**. Productivity **14.4 function points/month vs. 9.1** on the earlier project (**+58%**) |
| **Quality (Portsmouth)** | QA trouble reports | **3.0 vs. 6.9** trouble reports per 100 function points; programmers explored a wider range of solutions |
| **Poughkeepsie component forecasters** | 5 administrative professionals; half-day test | Baseline SRT ≥ 5 s, **99 transactions/hour**; with sub-second response **336/hour** (the brief reports a "339%" increase) |

> **[Source notes]**
> - **Forecasters:** 99 → 336 transactions/hour is ~**3.4×** baseline (≈ +239% *increase*); the brief's "339%" is best read as 339% *of* baseline. Thadhani's 180 → 371 is correctly stated as +106%.
> - **Card wiring (Lab A):** the stated "4.5 minutes per 0.1 s" does not reconcile with 82 → 66 min over a 5.75 s reduction; treat per-0.1-s slopes as applying only within the sub-second range or as unverified.
> - **Spelling:** the source alternates *Thadani / Thadhani*.

### 5.3.1 Broader Applicability

- Benefits held for scientists, engineers, programmers **and** administrative professionals in database applications — inherent in the computing situation, independent of work type.

### 5.4 Benefit Categories

| Benefit | Description |
|---|---|
| **Substantial cost savings** | Saved seconds accumulate; can justify larger processors |
| **Improved individual productivity** | Perhaps the most significant benefit |
| **Shortened project schedules** | Portsmouth early completion |
| **Better quality** | Fewer trouble reports; wider exploration |
| **Satisfaction** | Employees get more satisfaction from their work |

### 5.5 Effect on Other Computing (Infrastructure Implication)

- Faster response **does not reduce** demand; it **compresses** computing into a shorter time span and increases total output.
- Worked example: online entry, batch compilation, and debugging needing 100 million instructions: ~1 day with several-second response and 2-hour batch turnaround → ~4 hours with sub-second response and 1-hour batch turnaround.
- NIH: ~90 transactions and 2 batch submissions per session regardless of session length; Portsmouth: processor time per function point roughly constant → daily processor time **rose** because output rose.
- **Implication:** to realize the gain, expand capacity or distribute online workloads to smaller local systems.

### 5.6 Cost/Benefit Illustration (Source Table)

Assumptions: a task = 180 transactions (1 hour at 3 s SRT); 8 tasks/day; burdened user time = $35/hour; 21 workdays/month.

| System response time (s) | Transactions/hour | Task time (min) | Saved per task (min) | Saved per day (min) |
|---|---|---|---|---|
| 3.0 | 180 | 60.0 | — | — |
| 2.0 | 208 | 51.9 | 8.1 | 64.8 |
| 1.0 | 252 | 42.9 | 17.1 | 136.8 |
| 0.6 | 279 | 37.7 | 22.3 | 178.4 |
| 0.3 | 371 | 29.1 | 30.9 | 247.2 |

- Max time saved: **247.2 min/day (4.1 h)** → about **$3,028/user/month**.
- Organizational value of moving from 3 s to sub-second: **~$150,000/month** (50 simultaneous users) to **~$908,000/month** (300 simultaneous users).

### 5.7 Perceived-Performance Guidance (Laws of UX–Style Takeaways)

| Tactic | Guidance |
|---|---|
| **Feedback within 400 ms** | Keep attention; increase productivity |
| **Perceived performance** | Improve *perceived* response time and reduce the perception of waiting |
| **Animation** | Visually engage people while loading/processing happens in the background |
| **Progress bars** | Make wait times tolerable, **regardless of their accuracy** |
| **Purposeful delay** | Deliberately adding a delay can **increase perceived value** and instill trust even when the process is actually faster |

> **[Source note]** The "purposeful delay" and "progress bars regardless of accuracy" claims are stated as takeaways without supporting studies in the raw material. They also sit in tension with Myers (1985), where the progress indicator's value includes signaling that the program **has not crashed** and giving an **approximate completion estimate** (Section 8). Apply artificial delay sparingly and ethically.

---

## 6. Part B — Miller (1968): Response Time Principles

### 6.1 Core Thesis

- Controversy about "the" acceptable system response time arises because different human purposes need different response times. Miller lists **classes of human action and purpose** at terminals and shows "two-second response" is **not a universal requirement**.

### 6.2 General Rules of Guidance

> **RULE (Miller):** For good communication with humans, response delays of **more than two seconds** should follow only a condition of **task closure** as perceived by the human, or as structured for the human.

> **RULE:** If the user's attention is diverted from the thought matrix (e.g., waiting for a system response to some other train of thought), the significance of response delay changes dramatically.

> **RULE (Postscript 1):** Delays of approximately **15 seconds**, and certainly any longer, **rule out conversational interaction**. If longer delays will occur, design the system to **free the user** (physically and mentally) to do other things and retrieve the answer at their convenience.

Additional principles:

- A response signal can convey **several messages at once**; if combined, the response time must satisfy the component demanding the **fastest** response.
- Response to a request also serves as **feedback to a continuity of thought**.
- Tasks *can* be done in non-conversational modes (batch; 30 s or an hour beats 24 h "for some purposes"), but **many inquiries will not be made** and many promising alternatives not examined if conversational speed is unavailable; some tasks will be completed more poorly (a "testable hypothesis").
- Improved *operating* efficiency (e.g., 2 days → 15 minutes) does not necessarily change the *psychological* behavior of the person receiving the information.
- Tasks change character when delays exceed ~2–3 s; a standard **10-second** system won't support the thinking continuity needed for sustained problem solving, especially with high ambiguity (still useful, but for different tasks).

### 6.3 Response-Signal Messages (Four Messages)

A reply like "I've started doing your work" tells the user: (a) the request has been **listened to**, (b) it has been **accepted**, (c) an **interpretation** has been made, and (d) the system is now **busy** providing an answer. (Cited again by Myers as the value of progress indicators.)

### 6.4 Time-Perception Tolerance Data (Laboratory, Indirect)

| Interval | Finding |
|---|---|
| **2.0–4.0 s** | 75% correct "same/different" judgments at ±8% of the stimulus (e.g., 1.84 s judged shorter than 2.0; 2.16 s longer) → ~**16% tolerance** |
| **0.6–0.8 s** | Most accurate; tolerance somewhat less than **10%** |
| **6–30 s** | Tolerance ~**20–30%** |
| **Conditions** | Careful stimuli and full attention; real-world variation in task environments may **exceed** these tolerances substantially (empirical data needed) |
| **Psychological present** | **2.3–3.5 s** (up to ~12 s in special conditions) |

**Specification principle:** any implementation spec should include a **nominal value and acceptable tolerance**; the acceptable variation is the range within which the user cannot detect differences under actual use.

### 6.5 Miller's Qualifications (Provisos)

1. The 17 response categories are **not exhaustive** (though they cover much interactive behavior).
2. A response signal can communicate several messages simultaneously.
3. Topic titles (e.g., "Here I am, what work should I do next?") are **not literal inputs**; the query/response may be implicit (e.g., lifting a phone receiver implicitly asks "are you listening?"; dial tone answers).
4. Tasks can be done in **non-conversational** modes.
5. **Permissible ranges of variation** are not cited for most values.

### 6.6 Basis of Estimates

> **RULE:** Treat Miller's time values as **indicative, not conclusive.** They are the author's "best calculated guesses" (a behavioral scientist specializing in task behavior and problem solving), based on psychological rationales, and **should be verified** in extended studies with real-life tasks and subjects with dozens of hours of relevant skill practice (novices' short-term memory is heavily filled with learning, so they are not guides to skilled-user needs).

- Demonstration for skeptics: absorbed, motivated, emotionally aroused users find four seconds feels very long.

---

## 7. Part B (cont.) — The 17 Response Topics

| # | Topic (implicit user question) | Time limit / guidance | Notes |
|---|---|---|---|
| **1** | **Response to control activation** (key, switch, click) | **≤ 0.1 s**, immediate and perceived as part of the mechanical action; visual echo of typed characters **≤ 0.1–0.2 s**; light-pen character confirmation **≤ 0.2 s** | Skilled typists notice out-of-sync eye–hand feedback; hearing is more time-dependent than vision |
| **2** | **"System, are you listening?"** | **Up to 3 s** (variable onset at some cost to confidence; highest confidence if within **1 s**) | Applies when initializing a session. During an active conversation, input acknowledgment must be immediate; waiting 4 s, or even 0.5 s, to enter information is "violently disrupting" |
| **3** | **"System, can you do work for me?"** | Routine request ack **≤ 2 s**; impromptu/complex request **up to 5 s**; loading programs/data **≤ 15 s** (up to **1 min** tolerable); "set up my job from where I left off yesterday" **≤ 15 s** favorable, up to **1 min** acceptable | User is "psychologically locked into a conversation" as they key in the request; annoyance capacity rises |
| **4** | **"System, do you understand me?"** (error detection) | Inform of an error **after 2 s and before 4 s** after the user completes keying their "thought" | Don't interrupt mid-thought; the 2-s pause lets the user gain closure so an error is more acceptable |
| **5** | **Response to identification** (badge/ID reader) | Positioning feedback (click/detent) **< 0.4–0.5 s** (unnecessary if failures rare); "OK, I've read you" **≤ 2 s and a fixed length**; inquiry-terminal identification may take **5–7 s** | Standardized brief feedback so it can be reflexive; clocking out: 2 s feels like 4× a 1-s delay; time-clock example: ~3 s cycle/employee, clock response ~1 s → 0.5 s cuts cycle time **16%**; cutting 4 s → 1 s doubles throughput |
| **6** | **"Here I am, what work should I do next?"** | Factory worker terminal **10–15 s**; computer-assisted-instruction student **< 5 s** | |
| **7** | **Simple inquiry of listed information** | **≤ 2 s** for frequently used terminals (> once/hour) | User holds a specific issue in mind and may scan several responses |
| **8** | **Simple inquiry of status** | **~2 s**; may relax to **7–10 s** if the user recognizes searching is required | Single idea held in mind ("Can I take an order for 2000 items?") |
| **9** | **Complex inquiry in tabular form** | **≤ 4 s** (complete response); for multiple items, **4 s per item** (2 s preferable in all cases) | Users need time to assimilate complex patterns |
| **10** | **Request for next page** | **≤ 1 s** until first lines appear; while *searching* pages, **0.5 s is relatively long**; custom-built index frames: warn users of **2 s** delays; delays > 2 s make users unlikely to use the medium for scanning; users should skip **10 pages** as fast as one | Test: get absorbed in text and have someone hold you off from turning the page to a slow count of four |
| **11** | **"Now run my problem."** | Result within **15 s** keeps the user "in the problem-solving frame of mind" | Patience depends on effort invested, number of expected runs, anxiety to get back to other work; longer delays lead to secondary activities and less experimentation |
| **12** | **Keyboard entry vs. light-pen category entry** | Light pen ~**2 s**, keyboard ~**3 s**; **1–1.5 s** attention-shift adaptation from keyboard to display; page-turning/scan max **1 s** | Easier input → faster expected response |
| **13** | **Graphic response from light pen** | Deliberate line drawing: **≤ 0.1 s** with **no perceived variability**; positioning a symbol from a menu: **≤ 1 s** | Delay in image following the pen can be longer when placing rather than tracing |
| **14** | **Complex inquiry in graphic form** | Begin within **2 s**, complete within **10 s** to maintain thought continuity | Same principles as Topic 9 |
| **15** | **Manipulation of dynamic models** | No estimates offered ("not even guesses"); users will want to enlarge segments, suppress detail, and highlight paths while dimming the rest; scenarios should be compressible into ~**50-minute** periods | Calls for developmental studies (like RAND's SAGE operator work) |
| **16** | **Structural design manipulation** (bridges, buildings) | **~2 s** to be told a sketched element violates a rule; idle time beyond a couple of seconds inhibits creativity; after a completed idea ("chunk"), waiting **1–2 min** for the system to catch up is tolerable; relevant graphic motion can hold attention up to **10 s** | Preserve "mental heat" (interruptions < 1 min) |
| **17** | **"Execute this command into the operational system"** | System confirms understanding within **4 s**; final execution/confirmation may take **minutes** | User has reached closure upon entering the command; psychological incompleteness only to the degree they expect a failure/interference notice |

### 7.1 Postscript 1 — Discontinuity of Waiting Time at 15 Seconds

- A user is "captive" to the terminal until a response arrives. Captivity > 15 s, even for essential information, can become a **demoralizer** (reduces work pace and motivation).
- If delays > 15 s will occur, free the user (physically and mentally) to do other work and get the answer when convenient.
- Possible but doubtful exception: user in series with a process that needs the answer immediately.

### 7.2 Postscript 2 — Time Recovery from Errors and Failures

| Principle | Detail |
|---|---|
| **Recovery speed matters** | "How quickly can I get going again after something goes wrong?" — machine failure, program failure, operator error, or user error mid-task |
| **Design for simple, fast recovery** | Simplify effort and shorten time to recover as perceived by the user |
| **Restore state by mode** | **Simple inquiry:** user probably has a record of the last inquiry and can re-enter. **Complex inquiry:** retain the last **index of categories** in use. **Conversational problem-solving:** retain a copy of all **parameters and starting structure** of the constructed model (reconstruction is "arduous and unreliable") |
| **Psychology** | Lost creative work is demoralizing; users feel an irrational sense of personal failure; defenses (e.g., avoiding the cause in future) follow |
| **Timing** | Restore "as quickly as possible" = while the user is still in the dialogue: within **15 s**, or failing that, **< 5 minutes**; tell users **immediately** how long they may need to be patient |

---

## 8. Part C — Percent-Done Progress Indicators (Myers, 1985)

### 8.1 Definition & Purpose

| Term | Definition |
|---|---|
| **Percent-done progress indicator** | A graphical technique for monitoring the progress of a long task, "filling up" from empty to full like a charity-drive thermometer; lets users estimate at a glance how much is done and when it will finish |
| **Static busy indicators** (hourglass, clock, Buddha "for patience") | Show that computation is in progress but not **how swiftly**, or **whether the program has crashed** |

**Why long tasks exist:** compilers, text formatters, slow-device file loading, remote file transfers/printing, database processing; even "easy-to-use" interactive systems face waits.

**Multi-processing:** with multitasking + window managers (BLIT, PERQ), users run several tasks (e.g., edit while compiling); progress indicators show the progress of **each** process and keep the user informed of the whole environment.

### 8.2 Advantages of Graphical (vs. Numeric) Display

1. Users **assimilate** graphics faster than text when an exact value isn't required (Myers 1983).
2. The graphic **implies approximation**, appropriate since exact times are rarely determinable.
3. It fits in **small space** without interfering with other displays (e.g., icon-embedded indicators).

**Crash detection:** implementations require applications to update indicators explicitly, so a stalled indicator signals a crash/hang — progress indicators also tell users the program **is still running**.

### 8.3 Implementation Guidance

| Topic | Guidance |
|---|---|
| **Display formats** | Character terminal: row of asterisks reaching the right margin; bitmap display: growing bar, filling hourglass, clock with a moving hand (title-line bars in Sapphire windows) |
| **Centralization** | Use a **centralized routine** to draw progress pictures so all programs are **uniform**; add auxiliary routines (e.g., progress from a file variable's percent read) |
| **Calculating percentages** | Easiest for algorithms that process input **linearly** (file transfers, program loading, compilation, text processing) |
| **Non-linear parts** | Compiles referencing imported/included files; UNIX piping (unknown input length) — approach: have all programs in a pipeline process at about the same rate and base progress on the **original data producer** |
| **Multi-pass programs** | Divide the indicator into **sections** per pass |
| **Estimation** | Since progress is approximate, estimate using **heuristics or past experience** |
| **Hierarchies of programs** | Show **multiple indicators** for one process — e.g., Sapphire icons show one for the **current program** and one for the **entire task** |
| **Cost** | Some cost in algorithm design and execution time — justified if users perceive value |

### 8.4 Random (Indeterminate) Progress

- When a program cannot calculate its duration, show **random progress**: printing dots, a moving "busy bee," a flickering/constantly changing pattern.
- Signals the system is processing and hasn't crashed, without percentage information.
- Open question raised: is mixing programs with percent-done indicators and others with only random progress **more annoying** than having none? PERQ POS experience suggests **no**.

### 8.5 Interpretation: Why Progress Indicators Help

| Reason | Detail |
|---|---|
| **Miller's four messages** | Progress indicators (appearing after the command is parsed/understood) convey that the request was heard, accepted, interpreted, and is being worked on |
| **Novice support** | Novices expect computers to be fast and may **panic** and assume a crash without feedback (Foley 1974) |
| **Expert support** | Experts may know typical durations but benefit from estimates to **plan and monitor parallel tasks** (their time is valuable; multitasking is hard to track) |
| **Idle-time aversion** | People rarely like to sit idle; unknown wait durations make it impossible to schedule appropriate tasks or even relax effectively (e.g., "on hold" on the phone) → **tension**; indication of progress or advance knowledge of duration lets time be used productively → **reduced anxiety** |
| **Alternative** | An **actual number or analog display of time remaining**, if estimable, could substitute for a percent-done indicator |

### 8.5.1 Historical Notes

- Earlier examples: Spence (1976) count-down clock in a CAD-CAM app; MacTerminal file transfer (Apple Macintosh, Williams 1984); PERQ POS and Sapphire integrated progress indicators throughout their interfaces.
- Myers notes progress indicators "have only rarely been used" despite their value.

---

## 9. Part C (cont.) — The Experiment

### 9.1 Hypotheses

| # | Hypothesis | Outcome |
|---|---|---|
| **H1** | People prefer systems **with** progress indicators | **Strongly supported** (p = 0.0006) |
| **H2** | Progress indicators are **more useful** when response time is **variable** than constant | Not supported |
| **H3** | The prior finding (users prefer constant to variable response time, even if the variable average is shorter) is **reversed** with progress indicators | Direction observed but **not statistically significant** |

Background: earlier work (L. H. Miller 1977; Carbonell 1968; Weisberg 1984) favored predictable constant response times.

### 9.2 Method

| Item | Detail |
|---|---|
| **System** | Simplified forms-based transportation management query system on a **PERQ** workstation; ~**100** travel entries; simple pattern matching |
| **Task** | Answer **8 questions** (~**14 queries**) using the system; questions on paper, answers on a separate sheet |
| **Query flow** | Fill in an on-screen form, press a key; delay before results |
| **Delay** | **Constant 10 s**, or **randomly varied 1–17 s** (uniform; empirical mean **8.601 s**); a progress indicator **may or may not** be shown |
| **Measure** | Semantic-differential questionnaire: **10 items**, 1 (negative) – 9 (positive) (e.g., Sad–Happy, Anxious–Relaxed, Impatient–Patient, Annoyed–Calm, Tired–Energetic, Uncomfortable–Comfortable, Helpless–Powerful, Bored–Excited, Tense–At Ease, Confused–Confident); dimensions chosen intuitively; plus a direct-comparison questionnaire and background info |
| **Design** | Each subject used **two versions** in one session; 4 groups (Constant: Progress→No Progress; Variable: Progress→No Progress; No Progress: Constant→Variable; Progress: Constant→Variable), each subdivided for counterbalanced order; random assignment with equal group sizes (16 version-combinations; each group of 6 subjects) |
| **Duration** | ~5 min instructions + ~10 min per version + ~5 min per questionnaire ≈ **40 min** per subject |
| **Population** | **48 subjects**, mostly computer-science graduate students, ~**one-fifth computer novices**, unpaid volunteers |

### 9.3 Results

| Finding | Value |
|---|---|
| **Learnability** | No trouble learning/using; all versions rated easy (favorable comments, few errors) |
| **Progress vs. no progress** | Highly significant, **pr = 0.0006** ("6 chances in 10,000" of random occurrence) |
| **Preference for progress indicators** | **86.1%** liked them; mean rating **2.94** (1 = Very Useful, 9 = Useless/Annoying) |
| **Constant vs. variable time** | **Not significant** (pr = **0.2046**); even among no-progress versions only, pr = **0.1497** |
| **Mean scores (semantic differential)** | No progress: constant **5.73** vs. variable **5.41**; with progress: variable **5.98** vs. constant **5.90** (direction reversed as hypothesized, but not significant) |
| **Order effect** | The **first** version used was rated higher than the second (pr = **0.0025**) — boredom/annoyance at repeated long waits; controlled for by design |
| **Subject differences** | Substantial |
| **Perceived variability** | Without progress indicators, subjects rated constant and variable versions **the same**; with them, ratings differed significantly (interaction pr = **0.0011**) — progress indicators help users perceive timing correctly |
| **Behavioral observation** | With an indicator, subjects **watched the screen**; without it, they got bored, looked around the room or at the question sheet, and noticed answers only via peripheral vision |

### 9.4 Discussion & Limits

- The experiment **failed to replicate** earlier findings that constant time is preferred; this "calls into question" their general applicability.
- In L. H. Miller's (1977) study, variability seemingly concerned the **rate at which characters were displayed** — a different situation.
- If variability is very low, the system seems constant; if very high (e.g., 1 s to 1 hour), it is unacceptable regardless of mean — an experiment on the acceptable **range of variability** (with/without indicators, under different wait conditions) is suggested.
- Suggested improvements: timed tests; a faint signal when answers are ready; displaying questions on-screen; testing **multi-processing** environments.
- Conclusion: percent-done indicators help novices (command accepted, task progressing) and experts (completion estimates, planning), especially in multi-processing windowed systems; benefits probably justify the extra computation/implementation cost.

> **[Source notes]** (1) OCR of Table 1 and Table 3 is imperfect in the raw text; means quoted in Section 9.3 are from the paper's prose. (2) "pr = 0.0006" is described as "6 chances out of 10,000"; interpret as a p-value. (3) The sample is small, skewed toward CS graduate students, and the waits (avg ~8.6–10 s) are long by modern standards.

---

## 10. Synthesis: Response-Time Tiers

*(Consolidated from all three sources; thresholds are guidance, not laws.)*

| Tier | Approx. time | What it feels like | Source guidance | Design implication |
|---|---|---|---|---|
| **Instant / direct manipulation** | ≤ **0.1 s** | Part of the physical action | Miller Topic 1, 13 (0.1 s; 0.1–0.2 s for typed echo) | Immediate visual/haptic feedback on tap/press/keystroke; drawing/dragging with no perceived variability |
| **Sub-second flow** | ≤ **0.4 s** (Doherty), ≤ **~1 s** | Neither waits on the other; attention retained | Doherty; Miller Topics 10, 13 (1 s) | Target for common interactions; page-turn/scroll-like navigation ≤ 1 s |
| **Conversational** | ≤ **~2 s** (up to ~3–4 s for complex) | Continuity of thought maintained | Miller: 2 s for routine, simple inquiry; 4 s complex; 2–4 s error notice | Most responses; beyond 2 s only after closure |
| **Tolerable with feedback** | **~5–10 s** | Attention stretches; needs signals | Miller Topics 3, 8 (5 s, 7–10 s); Topic 14 (10 s) | Show progress/busy feedback; keep user oriented |
| **Attention limit** | **~15 s** | User captive, may demoralize | Miller Postscript 1, Topics 3, 6, 11 (10–15 s) | Free the user to do other things; allow background completion |
| **Extended / batch-like** | > 15 s to minutes | Not conversational | Miller Topics 3, 17, Postscript 2 (1 min; minutes; < 5 min recovery) | Progress indicator with estimate/remaining time; notify on completion; preserve state |

> **KEY TAKEAWAY:** Use both **absolute targets** (Doherty ~400 ms; Miller 0.1/1/2/4/15 s) and **relative closure**: longer delays are more acceptable at natural task boundaries than mid-thought.

---

## 11. Perceived Performance Techniques

| Technique | Purpose | Notes / cautions |
|---|---|---|
| **Immediate acknowledgment** | Tell the user the input registered (Miller's four messages) | Should precede any long processing |
| **Percent-done progress indicator** | Show how much is complete and when it will end; signal that the system hasn't crashed | Needs computable progress; approximate is fine; use graphical form; consider multiple indicators (current step + whole task) |
| **Indeterminate/random progress** | Show liveness when duration is unknown | Dots, moving mascot, changing pattern; mixing determinate/indeterminate indicators is not necessarily annoying (PERQ experience) |
| **Time-remaining display** | Alternative when duration is estimable | Actual number or analog display |
| **Animation** | Engage attention while loading/processing | (Laws of UX summary) |
| **Free the user** | For delays > ~15 s, allow other activity and asynchronous retrieval | Miller Postscript 1 |
| **State preservation & recovery** | Reduce psychological cost of failure | Restore last inquiry/index/model parameters; tell users expected recovery time immediately |
| **Sequenced/staged results** | For multi-part complex results, deliver items progressively (4 s per item) | Miller Topic 9 |
| **Purposeful delay** | Claimed to raise perceived value and trust | Unsupported in the raw material; use sparingly and transparently |

---

## 12. Later Research Signals (Low-Confidence)

> **[Source note]** The raw text includes *citation snippets and recommended-publication lists* from a ResearchGate page. They summarize other authors' statements about prior work and are **not verified here**; treat as pointers.

| Snippet theme | Summary |
|---|---|
| **Unexpected delays & progress indicators** | Prior work shows unexpected delays degrade user experience and progress indicators improve perceived responsiveness (agentic in-car LLM assistant paper, 2026) |
| **Nielsen's 10-second bound** | A cited claim that ~**10 seconds** is the upper bound for keeping users' attention during waits; mitigation strategies include progress indicators, conversation fillers, and explanations of ongoing processing |
| **Agentic/LLM latency** | In agentic systems, latency is *inherent* (multi-step reasoning), raising the question of whether delay-mitigation findings transfer when waiting becomes **expected**; anxiety reduction and trust are goals |
| **VR conversational agents** | Progress bars (linear/circular) are well established and affect satisfaction and perceived waiting time; integrating them near embodied agents may affect perceived naturalness |
| **Progress-bar rate** | A cited result: progress bars with a **declining** (rather than constant) fill rate increase satisfaction without changing perceived waiting time (Gronier & Baudet) |
| **Progress-bar appearance** | A 2026 paper examines effects of progress-bar **thickness** on perceived waiting time |
| **Motivation** | Progress bars used to keep users motivated and engaged in learning/practice contexts; gamification with progress bars improved performance/retention in a VR simulation trial |
| **Continuous feedback guidance** | When immediate feedback isn't feasible, provide continuous feedback (progress indicator) to inform status and estimated completion (citing Myers 1985) |

---

## 13. Application to Mobile App Design (Derived)

> Links source principles to `mobile_app_design_guide.md` and companions. These are design inferences, not source claims.

| Source principle | Mobile application |
|---|---|
| **Direct-manipulation feedback ≤ 0.1 s** | Instant tap states, ripple/press highlights, haptic feedback; scrolling/dragging with no perceived jank |
| **Doherty ~400 ms** | Aim for common in-app interactions (navigation transitions, list updates, form validation) to respond visibly within ~400 ms; optimistic UI where safe |
| **Acknowledge, then process** | Acknowledge input immediately (button state, spinner), then fetch; never leave the UI unresponsive |
| **Skeleton screens & progress indicators** | Use skeletons/placeholders for content loads; determinate progress bars for uploads/downloads/installs/exports; indeterminate spinners only when duration is unknowable |
| **Distinguish page-load metrics from interaction latency** | The mobile guide's LCP < 2.5 s is a *loading* target; Doherty/Miller thresholds apply to *interaction responses* |
| **Free the user after ~15 s** | Move long tasks (uploads, syncs, processing, AI generation) to the **background**; send a **notification** on completion; allow leaving the screen |
| **Progress with estimate** | For long operations show percent done and (when estimable) time remaining; break multi-step tasks into sections (multi-pass) and show both step and overall progress (Sapphire's two indicators) |
| **Crash/hang detection** | Stalled progress should trigger timeouts, retry options, and clear errors — don't fake progress bars that continue after failure |
| **Error notice timing** | Validate at natural pauses (after the user finishes a field — Miller's 2–4 s rule) rather than interrupting mid-entry |
| **State preservation** | Autosave drafts, restore forms/carts/sessions after crashes/backgrounding; tell users how long recovery/sync will take (ties to offline-first guidance) |
| **Mobile network variability** | Variable delays are normal; Myers found progress feedback helped users perceive timing correctly and prefer the experience — pair variable network latency with visible progress |
| **Paging/scrolling** | Keep page-turn/next-content load ≤ ~1 s perceived; prefetch next pages when users scan/search |
| **Complex queries** | Return partial results progressively (e.g., first 4 s per item principle) and label loading regions |
| **Novices vs. experts** | Novices need reassurance (a command was accepted); experts want estimates to multitask (background operations) |
| **Purposeful delay** | Avoid artificial delays that block users; if used for trust/perceived value, keep short and honest |
| **Cognitive load link** | Waiting adds extraneous load and short-term-memory risk (see `cognitive_load_guide.md`); keep users' context visible while waiting |
| **AI/agentic features** | For multi-step AI processing, show intermediate steps/status (per later research snippets) — hypothesis-level guidance |

---

## 14. Decision Rules (IF → THEN)

| Condition | Action |
|---|---|
| User taps/clicks/types | Provide visible feedback within ~0.1 s (0.1–0.2 s for typed echo) |
| Interaction is part of an ongoing train of thought | Respond within ~400 ms–1 s where feasible; ≤ 2 s at most |
| Response will exceed ~2 s | Ensure it follows a natural task closure, or show acknowledgment + feedback |
| Response will take ~5–10 s | Show progress/busy feedback; keep context visible |
| Response will exceed ~15 s | Free the user to do other things; process in the background; notify on completion |
| Duration is computable | Show **percent-done** (graphical), optionally with time remaining |
| Duration is unknowable | Show **indeterminate** activity feedback (liveness); avoid fake percentages |
| Task has multiple stages/passes | Divide indicator into sections; show both current step and overall progress |
| Long operation may fail | Ensure progress indicator stops updating on failure; provide timeouts, retry, and clear error messaging |
| Users are novices | Make acknowledgment and progress especially clear (they may assume a crash) |
| Users are experts/multitaskers | Provide estimates and background execution |
| Error detected in user input | Wait for the user to finish their thought; notify ~2–4 s later (or on field blur), not mid-entry |
| Failure/crash occurs | Restore state (last inquiry/index/model parameters/draft); tell users expected recovery time immediately; recover within ~15 s or < 5 min |
| Response time varies | Use progress feedback so variability is perceived accurately; don't assume constant is always better |
| Speeding up the front end | Check backend capacity: faster users create more transactions/load |
| Considering an artificial delay | Justify with evidence; avoid where it blocks tasks; keep it short and transparent |
| Specifying a response-time requirement | Give a nominal value **and** tolerance; specify per response type |
| Using Miller's/Doherty's numbers | Treat as indicative; verify with your own user testing on real tasks |

---

## 15. Checklists

### 15.1 Performance & Feedback Design Checklist

- [ ] Every input yields feedback within ~0.1 s
- [ ] Common interactions target ~400 ms or less; none exceed ~2 s without closure or feedback
- [ ] Long operations show progress (determinate if computable, indeterminate otherwise)
- [ ] Multi-step operations show step-level and overall progress
- [ ] Progress indicators reflect real state (stalls/failures are detectable)
- [ ] Operations > ~15 s run in the background; users can leave and are notified
- [ ] Time remaining shown when estimable
- [ ] Autosave and state restoration implemented; recovery time communicated
- [ ] Error notices timed to natural pauses
- [ ] Novice users get explicit acknowledgment of accepted commands
- [ ] Backend capacity planned for increased usage after speedups
- [ ] Response-time specs include tolerances and response-type categories

### 15.2 Research/Testing Checklist

- [ ] Test perceived vs. actual waiting time
- [ ] Test with and without progress indicators, and with constant vs. variable latency
- [ ] Observe where users look/what they do while waiting (attention drift)
- [ ] Include novices and experts; test multitasking scenarios
- [ ] Measure transactions per hour/task time and satisfaction (e.g., semantic differential)
- [ ] Control for order effects (first-version bias)
- [ ] Validate Miller/Doherty thresholds against your own tasks

---

## 16. Key Facts Reference

| Fact | Value |
|---|---|
| Doherty Threshold | **400 ms** feedback; brief published **Nov 1982** (IBM) |
| Older standard | 2 seconds (Miller 1968) |
| Thadhani | 3 s → 180 tph; 0.3 s → 371 tph (+106%); saves 10.3 s per 2.7 s reduction |
| Time-savings example | Up to 247.2 min/day; ~$3,028 per user per month ($35/h; 21 days) |
| Organizational value | ~$150,000–$908,000 per month (50–300 simultaneous users) |
| NIH | 300 → ~400 users; response ~4 s; task time 32 → 48 min (+50%); +22,500 hours/month; ~$900,000/month; 15× processor cost |
| SPD | 15 engineers, 75 sessions; card wiring 20% (Lab A) and 35% (Lab D) faster |
| Portsmouth | SRT 2.3 → 0.84 s; 39% less programmer time; +58% function points/month; trouble reports 3.0 vs. 6.9 per 100 FP |
| Forecasters | 99 → 336 tph (≈ 3.4×; source states "339%") |
| Miller 1968 | 17 topics; 2-s rule after closure; 15-s discontinuity; 0.1 s control feedback; psychological present 2.3–3.5 s |
| Tolerance data | ±8% (≈16% range) at 2–4 s; < 10% at 0.6–0.8 s; 20–30% at 6–30 s |
| Myers 1985 | 48 subjects; delays 10 s constant or 1–17 s variable (mean 8.601 s); 10-item 1–9 semantic differential |
| Myers results | Progress vs. none: pr = 0.0006; 86.1% liked; mean 2.94; constant vs. variable: pr = 0.2046 (n.s.); first-version bias pr = 0.0025; perceived variability interaction pr = 0.0011 |
| Miller's four messages | Heard, accepted, interpreted, busy working |
| Recovery target | Within 15 s, or < 5 min; tell users how long immediately |

---

## 17. People & Sources Reference

| Person / Source | Contribution |
|---|---|
| **Walter J. Doherty** (IBM Watson Research Center) | Doherty Threshold; SRT and productivity research |
| **Ahrvind J. Thadhani / Thadani** (IBM San Jose) | Transactions-per-hour vs. SRT curve |
| **Richard P. Kelisky** | Co-author with Doherty (1979) on SRT and short-term memory disruption |
| **Joseph D. Naughton** (NIH Computer Center) | Proposed processor upgrade justified by user-time savings |
| **Robert B. Miller** (IBM Poughkeepsie) | 1968 response-time classification; closure; 2-second rule |
| **Lawrence H. Miller** | 1977 study on constant vs. variable response time (cited by Myers) |
| **Carbonell, Elkind & Nickerson (1968)** | Psychological importance of time in time-sharing |
| **Foley (1974)** | Novice panic without feedback |
| **Weisberg (1984)** | Network system architecture and CAD/CAM productivity |
| **Robert Spence (1976)** | Count-down clock display in CAD-CAM |
| **Gregg Williams (1984)** | MacTerminal progress example (Byte) |
| **Brad A. Myers** (Univ. of Toronto) | Progress indicator paper; Sapphire window manager |
| **S. S. Stevens / H. Woodrow** | Time perception (cited by Miller) |
| **Jim Elliott** | Mainframe blog reproducing the Doherty & Thadhani brief |
| **William Buxton** | Helped prepare Myers' experiment |
| **Gronier & Baudet** | Declining-rate progress bar satisfaction (via citation snippet) |
| **Nielsen** | 10-second attention bound (via citation snippet) |

---

## 18. Glossary

| Term | Definition |
|---|---|
| **Doherty Threshold** | Response-time target (~400 ms) at which user and system don't wait on each other and productivity rises sharply |
| **System response time (SRT)** | Time from entering a command to a complete displayed reply |
| **User response time / think time** | Time from receiving a reply to entering the next command |
| **Transaction** | One command + reply; the unit of online work |
| **Closure** | Subjective sense of completion of a task or subtask |
| **Activity clumping** | Organizing activity into chunks ending in closure |
| **Step-down discontinuity** | Sudden drop in efficiency at particular delay points |
| **Psychological present** | ~2.3–3.5 s window perceived as "now" |
| **Mental heat** | Concentrated attention state in creative work |
| **Perceived performance** | How fast a system *feels*, independent of actual speed |
| **Percent-done progress indicator** | Graphical display of the proportion of a task completed |
| **Indeterminate / random progress** | Activity indication without completion percentage |
| **Semantic differential** | Bipolar rating scale (e.g., Anxious–Relaxed) used to measure attitude |
| **Multi-processing** | Running more than one task at once |
| **Function point** | Measure of program size/complexity used in productivity comparison |
| **Light pen** | Early pointing/drawing input device |
| **Batch turnaround** | Time to receive results from non-interactive processing |
| **Labor illusion (informal)** | Perceived value increased by visible work or delay (implied by the "purposeful delay" takeaway) |

---

## 19. Source Notes & Caveats

1. **Sources merged:** Laws-of-UX-style Doherty summary; Doherty & Thadhani IBM brief (blog reproduction); 2015 #webperf blog commentary; Miller (1968); Myers (1985); ResearchGate boilerplate (citations, recommended publications). The Myers paper appeared twice in the raw text (PDF and pasted ResearchGate copy) and was deduplicated.
2. **Age of evidence:** Data comes from **1960s–1980s** mainframe/terminal systems; the *directional* findings (faster = more productive; feedback reduces anxiety) are widely applied, but exact thresholds should be validated for modern mobile/web contexts.
3. **Miller's numbers are estimates:** Robert Miller explicitly states his values are the author's best calculated guesses, meant to be verified; he also cautions that laboratory time-perception tolerances may be exceeded in real task environments.
4. **Doherty figures:** "400 ms" and "addicting" originate from summary/popularizing sources; the brief's own data emphasizes sub-second response. Arithmetic irregularities are flagged in Section 5.3 (forecasters' "339%", Lab A slope).
5. **Naming:** *Thadani/Thadhani* spelling varies in the source; three "Miller" authors are distinct (see header).
6. **Myers' scope:** Small, specialized sample (48; mostly CS graduate students); long waits (~8.6–10 s); constant-vs-variable non-significance means "no evidence of preference," not proof of equivalence.
7. **OCR artifacts:** PDF text contains OCR errors (e.g., "lOS" for POS, "Rtlanta" in figures, garbled tables). Values here were cross-checked against surrounding prose. The trailing blank page in the Miller PDF was ignored.
8. **Low-confidence material:** ResearchGate citation snippets (Section 12) are secondary and unverified.
9. **Promotional/boilerplate content omitted:** Site navigation, "join for free" prompts, and unrelated recommended publications (e.g., CrimeStat, intranet performance measurement) were excluded.
10. **Derived sections:** Sections 10, 13, and the Decision Rules synthesize across sources and are not direct claims of any single paper.
