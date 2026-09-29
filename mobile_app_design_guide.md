# Mobile App Design Guide — Structured Knowledge Base

> **Purpose:** Authoritative, machine-readable and human-readable reference for designing mobile apps (iOS, Android, cross-platform).
> **Audience:** Downstream AI agents and human designers/developers.
> **Conventions used in this document:**
> - `> **RULE:**` blockquotes = non-negotiable rules.
> - `> **KEY TAKEAWAY:**` blockquotes = high-value summaries.
> - Numeric thresholds are stated exactly as sourced. Statistics are **source-reported** and should be treated as directional, not audited.
> - Units: `pt` = iOS points, `dp` = Android density-independent pixels, `px` = pixels, `CSS px` = WCAG reference pixels.

---

## Table of Contents

1. [Foundations & Definitions](#1-foundations--definitions)
2. [Core Design Principles](#2-core-design-principles)
3. [Design Process (End-to-End)](#3-design-process-end-to-end)
4. [UX Frameworks & Models](#4-ux-frameworks--models)
5. [Information Architecture & Navigation](#5-information-architecture--navigation)
6. [Touch, Gesture & Ergonomics](#6-touch-gesture--ergonomics)
7. [Visual Design System](#7-visual-design-system)
8. [Content Layout for Mobile](#8-content-layout-for-mobile)
9. [Platform Guidelines (iOS / Android / Cross-Platform)](#9-platform-guidelines-ios--android--cross-platform)
10. [Accessibility & Compliance](#10-accessibility--compliance)
11. [Dark Mode](#11-dark-mode)
12. [Performance & Offline](#12-performance--offline)
13. [Responsive Design](#13-responsive-design)
14. [Onboarding & First-Time User Experience](#14-onboarding--first-time-user-experience)
15. [Feedback, Notifications & Personalization](#15-feedback-notifications--personalization)
16. [Prototyping, Testing & Data-Driven Iteration](#16-prototyping-testing--data-driven-iteration)
17. [Development Considerations](#17-development-considerations)
18. [AI in Mobile Product Design](#18-ai-in-mobile-product-design)
19. [Reference App Case Studies](#19-reference-app-case-studies)
20. [Common Mistakes (Anti-Patterns)](#20-common-mistakes-anti-patterns)
21. [Master Checklist & Decision Rules](#21-master-checklist--decision-rules)
22. [Key Statistics Reference](#22-key-statistics-reference)
23. [Tools Reference](#23-tools-reference)
24. [Glossary: AI-for-UX Terms (100)](#24-glossary-ai-for-ux-terms-100)

---

## 1. Foundations & Definitions

### 1.1 What Mobile App Design Is

Mobile app design is the multidisciplinary process of creating the visual and interactive elements of a mobile application. It combines **UI design** and **UX design** with an understanding of user behavior and the technical constraints of mobile platforms (notably limited screen size).

| Term | Definition | Scope |
|---|---|---|
| **UI (User Interface)** | How the app *looks*: buttons, menus, icons, colors, fonts, graphics, layout | Everything the user sees and touches |
| **UX (User Experience)** | How the app *feels*: ease of task completion, flow, satisfaction; organizes content and anticipates needs | Structure, flow, feedback, emotion |

> **KEY TAKEAWAY:** Both matter and support each other. Beautiful apps fail with confusing workflows; visually simple apps delight when they feel smooth.

### 1.2 Mobile vs. Desktop Constraints

| Factor | Mobile implication |
|---|---|
| Screen size / aspect ratio | Limited real estate → prioritize essential elements; omit non-essential info; layouts must adapt to sizes and orientations |
| Input method | Touch (imprecise) and gestures (swipe, pinch, tap, long-press), not a mouse |
| User behavior | Users are often on the go with limited time → content must be digestible quickly |
| Connectivity | Networks are unreliable (subways, elevators, rural areas) and bandwidth may be limited |
| App context | Apps require a more restrictive layout; limit information per screen to minimize scrolling |

### 1.3 Design Mission (Every Screen Must Answer)

1. Where am I? (users always know their location)
2. What can I do here? (users quickly see available actions)
3. Where can I go next? (navigation is easy)
4. Can I trust this interface? (it feels reliable and steady)

### 1.4 Why Design Matters (Source-Reported Impact)

- First impression forms in roughly **50 ms**; about **94%** of it is design-driven.
- **72%** of users abandon apps within 30 days.
- Mobile accounts for over **60%** of web traffic.
- Adults in the US spend an average of **5.5 hours/day** on mobile devices; **72.6%** of global internet users were predicted to access the web *only* via smartphone by 2025.

---

## 2. Core Design Principles

### 2.1 Principle Matrix (Deduplicated Across All Sources)

| # | Principle | What it means | Implementation guidance |
|---|---|---|---|
| 1 | **Simplicity** | Less is more; every element has a purpose | Show only essential elements/functions; eliminate excess; question every element ("if it doesn't serve a purpose, it doesn't belong") |
| 2 | **Consistency** | Backbone of trust; users learn once | Same fonts, colors, button styles, interactions, gestures, feedback across all screens; establish a design system / style guide early |
| 3 | **Readability** | Apps communicate mostly through text | Legible typography, size, and contrast even at a glance; text must stand out from its background |
| 4 | **Feedback** | Every interaction gets a response | Subtle animation, color change, haptic feedback; microinteractions confirm actions and add personality |
| 5 | **Design for thumbs** | Handheld use is thumb-driven | Place primary actions in the "thumb zone"; support left- and right-handed users |
| 6 | **Strategic push notifications** | Value vs. annoyance | Respect preferences, time zones, interaction patterns; provide customization |
| 7 | **Personalization** | Users expect tailored experiences | Remember preferences, use past behavior, greet by name, AI-driven recommendations, adaptive features |
| 8 | **Platform fidelity** | Muscle memory | Follow Apple HIG / Material Design; use native, platform-standard components |
| 9 | **Accessibility first** | Foundational, not optional | See [Section 10](#10-accessibility--compliance) |
| 10 | **Clear visual hierarchy** | Users scan, not read | One primary action per screen; size, color, spacing, typography |
| 11 | **Speed** | Performance is a design decision | See [Section 12](#12-performance--offline) |
| 12 | **Test before building** | Cheapest place to catch mistakes | Prototype → user test → iterate |

> **RULE:** Keep it clear, keep it steady, focus on what matters. Clarity outranks decoration.

### 2.2 Design Mission Statements (Operational Heuristics)

- Users always know where they are.
- Users quickly see what they can do.
- Navigation is easy.
- The interface feels reliable and steady.
- Familiar, native components beat clever novelty ("don't try to be too clever").

---

## 3. Design Process (End-to-End)

### 3.1 Five-Step Process Overview

| Step | Name | Outputs |
|---|---|---|
| 1 | Define the app idea | Problem statement, market/competitive research, target audience, personas |
| 2 | Design the app | Feature list/PRD, wireframes, color palette, typography |
| 3 | Build prototypes | User flows, information architecture, prioritized features, interactive prototype |
| 4 | Begin development | App type decision, frontend/backend build, MVP, early feedback |
| 5 | Test, iterate, launch | Multi-type testing, store submission, continuous improvement |

### 3.2 Step 1 — Define the App Idea

**Identify the problem/need — answer these:**
1. What is the app's primary purpose?
2. Who is it for, and what are they trying to accomplish?
3. What is missing from existing solutions?
4. How will this app improve that experience?
5. How does this app align with the company's larger mission and values?

**Market research:**
- Analyze existing apps for trends and market gaps.
- Run a **competitive analysis** to understand the landscape.
- Run a **SWOT analysis** (strengths, weaknesses, opportunities, threats).
- Validate the idea and confirm strong **product-market fit**.

**Define target audience:**
- Understand what users are trying to do, what frustrates them, and what would feel better.
- Conduct user interviews early (informal is acceptable; goal is pattern-spotting).
- Consider age, background, location, device (smartphone vs. tablet), context (on-the-go vs. at a desk), needs, goals, and whether mobile is chosen out of need or preference.

**Create user personas:** Represent typical users with shared behaviors/needs/preferences; use them to check design decisions and prioritize features.

> **KEY TAKEAWAY:** "If you don't know who you're building for, then the time you invest in building and creating something will be wasted." — Ana Boyer, Figma

### 3.3 Step 2 — Design the App

**Outline core functions/features.** Every feature must connect to the app's primary goal. If it doesn't support a user task or improve the experience, defer it (at least from v1).

Common mobile features:

| Category | Features |
|---|---|
| Engagement | Push notifications, gamification, personalization based on behavior, ratings and reviews |
| Location/commerce | Location and GPS services, payment and checkout flow, order tracking |
| Discovery | Search and filtering |
| Social/support | Social media integrations, in-app support |
| Reach | Language options |

Consider a **Product Requirements Document (PRD)** to align everyone on purpose, core features, and functionality.

**Create wireframes:**
- Define structure before visuals: layout, content hierarchy, interaction points.
- Focus on each screen's main goal, content organization, and usability.
- Include simple outlines of interactive elements.
- Wireframes are flexible alignment tools; iterate as design evolves.

**Choose color palette and typography:**
- Typography must be readable across screen sizes.
- Color palettes should guide interactions and create clear hierarchy.
- Examples: Calm uses shades of blue (tranquility/relaxation); DoorDash uses red (appetite stimulation/urgency); Citymapper uses vibrant color coding with a green-and-white theme.

### 3.4 Step 3 — Build Prototypes

Prototype goal: map core flows, interactions, and screen transitions to validate the design before writing code.

**User flows:** Show how a user moves screen-by-screen and action-by-action (e.g., browse → add to cart → checkout). Outline key paths first, then map screens to flows (design interactions in order, not screens in isolation).

**Organize content (IA):**

| Area | Practice |
|---|---|
| Organization | Use **card sorting** to learn how users expect content to be grouped |
| Labeling | Clear, intuitive labels |
| Navigation | Intuitive menus and systems |
| Search | Search, filters, and related suggestions |

**Prioritize features — MoSCoW method:**

| Bucket | Meaning |
|---|---|
| **Must-have** | Required for the core user task |
| **Should-have** | Important but not critical for launch |
| **Could-have** | Nice to have if resources allow |
| **Won't-have** | Explicitly excluded (for now) |

**Design for interactivity:** Use hover effects (where applicable), color changes, animations, and micro-interactions (e.g., animated heart on like) to provide instant visual feedback.

### 3.5 Step 4 — Begin Development

See [Section 17](#17-development-considerations). Key tasks: choose app type → code frontend/backend → build an **MVP** (only the most essential features) → gather early feedback with real users.

**Friction logging** ("walking the store", used at Stripe): team members experience the product firsthand to reveal points of confusion.

### 3.6 Step 5 — Test, Iterate, Launch

| Test type | Purpose |
|---|---|
| **Usability testing** | Observe how users complete tasks; reveal challenges |
| **Accessibility testing** | Ensure usability for people with disabilities/impairments |
| **Performance testing** | Assess speed, loading time, battery usage under varied conditions |
| **Compatibility testing** | Verify function across devices and OS versions (iOS/Android) |
| **QA testing** | Identify bugs and errors |

After feedback: implement changes, then **re-run tests** to confirm improvements.

**Store submission:** Each store (Apple, Google Play) has its own publishing rules. Meet all requirements: **metadata, privacy policies, screenshots**.

**Continuous improvement:** Launch is the beginning. Track usage, collect feedback, monitor which features are used/ignored, where users drop off, and what reviews flag. Ship regular updates.

> **KEY TAKEAWAY:** "Our users prefer—and even expect—to have a product that's always getting better." — Yuhki Yamashita, Figma

### 3.7 Practical Structure-Building Workflow (Practitioner Method)

1. **Map out everything:** list all features (must-haves and maybes).
2. **Prioritize ruthlessly:** rank by user and business value; merge or remove vague/overlapping features.
3. **Step into users' shoes:** mentally act out scenarios; identify what feels extra or distracting.
4. **Clean up and repeat:** remove or streamline anything that doesn't serve the main goal.

**Worked examples:**
- *Vinyl collection app:* launched directly into the record crates (not a menu or logo screen); "Add New Record" button placed in context.
- *Homework planner:* home screen contained only "Add Assignment" and "View Calendar"; everything else went into a simple menu.

---

## 4. UX Frameworks & Models

### 4.1 The 5 Elements of UX (Jesse James Garrett)

Five stacked planes, from abstract (bottom) to concrete (top). Each builds on the previous one. In practice, planes overlap; finish the lower plane's decisions before completing the plane above so decisions stay aligned.

| Plane | Focus | Deliverables | EV-charger-finder example |
|---|---|---|---|
| **1. Strategy** | Product objectives + user needs (via user research) | Goals, user needs | Objective: inform EV owners of the nearest charger; user needs: directions, charger availability, price |
| **2. Scope** | Features and content | Functional specifications; content requirements | Save previously discovered stations; images, maps, voltage details |
| **3. Structure** | Interaction design + information architecture | Conceptual models/flow charts; site maps | Site map (home → station list → station page); flow for location-entry errors |
| **4. Skeleton** | Information design, navigation and interface layout | Wireframes, prototypes | Header with logo/back nav → image → map link → practical info |
| **5. Surface** | Sensory experience: color, texture, visual presentation | Final visual design | Consistent palette/layout; key info emphasized |

### 4.2 Universal Design

> "Universal Design is the design and composition of an environment so that it can be accessed, understood and used to the greatest extent possible by all people, regardless of their age, size or disability." — Centre for Excellence in Universal Design

- Design for the needs of **all** users, not only those with disabilities.
- Using the 5 Elements systematically helps account for all user needs and functionality requirements.

### 4.3 Design Thinking

> "A human-centered approach to innovation that draws from the designer's toolkit to integrate the needs of people, the possibilities of technology, and the requirements for business success." — Tim Brown, IDEO

- Starts with understanding the problem; ends with a final product.
- Keeps people at the center while balancing business requirements and technical constraints.
- The 5 Elements is one way to practice design thinking, provided the team stays open-minded and user-centric.

### 4.4 Laws/Effects Referenced

- Aesthetic-Usability Effect: attractive, compelling, clear things attract users ("When something is more attractive, compelling, and clear, people tend to gravitate towards it." — Katie Dill, Stripe).
- Choice Overload: too many options overwhelm users (see Section 20).
- Progressive disclosure (see Section 5.4).

---

## 5. Information Architecture & Navigation

### 5.1 Structure Principles

- A rock-solid structure is the foundation: how information and features are organized and prioritized.
- Organize by what belongs together, where things go, and how users find them.
- Content grouping should be consistent and meaningful (by time, progress, or type—whichever fits).
- Lists are flexible for lots of text or multiple actions per item.

### 5.2 Navigation Rules

> **RULE:** Users must always be able to answer: *Where am I? What can I do here? Where can I go next?*

> **RULE:** Primary actions must be no more than **two taps** from the home screen.

> **RULE:** Never hide a key function in a secondary menu; place main actions in context where users need them.

| Pattern | Use for | Constraints |
|---|---|---|
| **Bottom tab bar** | Top-level destinations | **3–5** tabs; universally recognizable icons **plus text labels**; too many tabs feels messy |
| **Stack navigation** | Linear flows / drilling into details (list → detail) | Creates a clear hierarchical path with an obvious way back |
| **Drawer menu** | Secondary destinations | Use sparingly; do not bury key functions |
| **Search + filters + suggestions** | Content-heavy apps | Help users find things quickly |
| **Accordion / expandable sections** | Non-essential detail | Reveal on demand |

**Navigation best practices:**
- Use clear, well-known icons and explicit labels — no "mysteries or hidden meanings."
- Keep the experience consistent on every screen (same feel and behavior).
- Prefer native, platform-standard components over custom navigation.
- Never switch navigation patterns between screens (makes screens feel like different apps).
- Map IA early using wireframes; test navigation flows early with high-fidelity wireframes.
- Example: Strava places "Home," "Maps," and "Record" in a persistent bottom tab bar.

### 5.3 Card Sorting & Labeling

- Use **card sorting** to learn users' mental models for grouping content.
- Labels must be clear and intuitive so users can identify information and navigate.

### 5.4 Progressive Disclosure

- Show essentials first; reveal more detail as users drill in (e.g., show a "taste" of a long list and let users expand).
- Gives users everything they'd get on desktop without information overload.
- Supplement text with visual aids (icons, infographics, images, video, audio) to communicate faster in less space.

---

## 6. Touch, Gesture & Ergonomics

### 6.1 Touch Target Sizes (Minimums)

| Standard / Platform | Minimum size | Notes |
|---|---|---|
| **Apple iOS (HIG)** | **44×44 pt** (≈ 59 px) | iOS baseline |
| **Google Material Design** | **48×48 dp** | Android baseline |
| **WCAG 2.2 Level AA** | **24×24 CSS px** | Legal/accessibility floor; lower than platform guidance |
| **Apple visionOS** | **60×60 pt** | Largest; spatial input is less precise |

> **RULE:** Use **44 pt (iOS) / 48 dp (Android)** as the working minimum, not the 24 px WCAG floor. Targets below ~44 px have reported error rates **3× higher** than properly sized ones.

### 6.2 Spacing & Feedback

- Provide a buffer of **at least 8–12 points** between interactive elements to prevent accidental taps.
- Provide **visual feedback** on press (background color change, slight scale) and **haptic feedback** for critical actions.
- React Native enforcement: `minWidth` / `minHeight` on `Pressable` / `TouchableOpacity`; margins/gap for spacing; `react-native-haptic-feedback` for haptics.
- Test **one-handed** use.

### 6.3 Thumb Zone

- Primary actions and essential elements belong within easy thumb reach.
- Optimize layouts for **both left- and right-handed** users.
- Consider swipe and pinch-to-zoom as alternatives to scrolling for content interaction.

### 6.4 Gestures

> **RULE:** Gestures are shortcuts, never requirements. Every gesture (swipe, pinch, long-press) must have a **visible, tap-based alternative** for users who cannot perform complex motions.

- Gesture navigation is replacing button-heavy interfaces: swipes, long-presses, pull-to-refresh feel natural.
- Platform expectations: iOS users expect **swipe-to-go-back**; Android users expect a **bottom navigation bar** and system back action.

---

## 7. Visual Design System

### 7.1 Visual Hierarchy

> **RULE:** Every screen has **one clear primary action**, and it is the most prominent element on screen.

| Lever | Guidance |
|---|---|
| **Size & weight** | Larger/bolder elements draw attention first; primary CTA most prominent |
| **Color & contrast** | Use the accent color **sparingly**, only on primary actions ("when everything is highlighted, nothing stands out"); bright colors for action items |
| **Spacing & grouping** | Related elements closer together; whitespace separates sections; cramped UIs feel chaotic |
| **Typography scale** | Limit to **2–3 font sizes per screen** |
| **White space** | Gives breathing room; reduces cognitive load; feels premium; isolate CTAs with extra surrounding space |

**Hierarchy validation techniques:** view the screen in black-and-white; squint at it. If it can't be read/understood fast, revise.

### 7.2 Typography

| Rule | Detail |
|---|---|
| Font count | Use **one or two fonts** (e.g., one for headlines, another for details) |
| Type roles (M3 Expressive) | display, headline, title, body, label |
| System text styles | Prefer system text styles/sizes → flexibility and accessibility (Dynamic Type) |
| Header vs. body | Headers should be **1.5–2×** the size of body text and bolder |
| Opacity levels for emphasis | **100%** primary text, **60%** secondary, **40%** tertiary (creates hierarchy without new colors) |
| Testing | Test with multiple font sizes; ensure text scales to **200%** without breaking UI or functionality |

### 7.3 Color

- Build a simple palette: a main **brand** color, one complementary color, and **neutral** shades.
- Use **high-contrast pairs** for readability.
- Images and colors should belong to the same "family" (cohesive imagery).
- Use built-in **system colors** for light/dark modes so the UI adapts automatically.
- Text over busy images: add a subtle background/scrim.
- Verify readability in tough lighting and across backgrounds.
- Color communicates meaning (blue = calm; red = appetite/urgency) — but never rely on color alone (see Section 10).

### 7.4 Spacing & Grid

> **RULE:** Use a consistent spacing scale based on an **8 px (8-point) grid**: 8, 16, 24, 32. No arbitrary margin/padding values.

- NativeWind examples: `p-4` = 16 px padding; `m-6` = 24 px margin.
- Alignment and a simple spacing system make layouts look stable and neat.

### 7.5 Design Tokens

- Tokens (colors, spacing, typography) are the building blocks of a design system; they ensure consistency across products/platforms.
- Establish a design system/style guide early to keep screens uniform.

### 7.6 Iconography & Imagery

- Use clear, well-known icons; pair with text labels where meaning could be ambiguous.
- Use optimized image formats (**WebP**), provide alt text, and provide alternate assets for dark backgrounds where needed.

---

## 8. Content Layout for Mobile

### 8.1 Five Best Practices

| # | Practice | Detail |
|---|---|---|
| 1 | **Understand your audience** | Research age, background, location, device, context (on-the-go vs. desk), needs, goals; build user flows per page |
| 2 | **Optimize for touch** | Large tap targets, adequate spacing, thumb-reach placement, left/right-hand support |
| 3 | **Signposting and structure** | Headings, subheadings, bullets, descriptive signposting; short paragraphs; think IA (what do users want to know first?) |
| 4 | **Hide and condense information** | Accordions, expandable sections, progressive disclosure, icons/infographics, images/video/audio |
| 5 | **Accessibility** | Descriptive text, headings, and links for screen readers; contrast, appropriate font sizes, clear headings |

### 8.2 Writing for Mobile

- Avoid long paragraphs and in-depth explanations; prefer short paragraphs and clear signposting.
- Content should be scannable at a glance (users scan, they don't read).
- Audio can replace text for hands-busy contexts (e.g., in transit).

---

## 9. Platform Guidelines (iOS / Android / Cross-Platform)

> **RULE:** Follow the guidelines of the platform you build on. iOS → Apple HIG. Android → Material Design 3. Cross-platform → choose **one** as the primary design language and adapt key patterns (navigation, gestures, typography) for the other.

### 9.1 Apple Human Interface Guidelines (HIG)

- Definitive resource for iOS, iPadOS, macOS, watchOS, visionOS.
- **Liquid Glass** (introduced mid-2025): translucent material with refraction and reflection effects; the most significant visual redesign since iOS 7 (2013); first time Apple unified its design language across all platforms simultaneously.
- HIG is free, continuously updated, and includes downloadable design templates for Figma and Sketch.

### 9.2 Google Material Design 3 Expressive (M3 Expressive)

- Major 2025 update; backed by **46 studies with 18,000+ participants**.
- Users identified key UI elements up to **4× faster** in expressive layouts vs. previous M3.
- Features: spring-based motion system, **35 new shapes** with morphing, larger typography with heavier weights, background blur for depth.
- Up to **87% preference** among 18–24-year-olds; reduced performance gaps between older and younger users.

### 9.3 iOS vs. Android Comparison

| Dimension | iOS | Android |
|---|---|---|
| **Design guideline** | Apple HIG (Liquid Glass) | Material Design 3 Expressive |
| **Min touch target** | 44×44 pt | 48×48 dp |
| **Back navigation** | Swipe-back gesture | System back action / hardware-software back button |
| **Primary nav expectation** | Tab bar | Bottom navigation bar |
| **Transitions (example)** | Subtle fade (Instagram) | Slide transitions aligned with Material (Instagram) |
| **Languages** | Swift (modern, safe, performant), Objective-C | Kotlin (increasingly preferred), Java |
| **IDE** | Xcode | Android Studio |
| **Device fragmentation** | Low (limited iPhone/iPad variants and screen sizes) | High (wide range of devices, screens, hardware) |
| **Market profile** | Younger, higher average income; North America and Western Europe | Global dominance; more diverse audience across demographics |
| **Complexity** | Simpler | More complex, broader reach |

### 9.4 Cross-Platform Implementation (React Native / Expo)

| Technique | Purpose |
|---|---|
| `Platform.select()` | Platform-specific font weights, shadows, margins within one style object |
| Platform-aware UI kits (e.g., gluestack-ui) | Modals/action sheets render native-style UI automatically |
| React Navigation | Swipe-back gestures on iOS; correct system back on Android |
| Reference HIG + M3 | Source of truth for button placement, alerts, patterns |

> **KEY TAKEAWAY:** Balance a consistent brand identity with a native feel. Respecting platform conventions builds trust and reduces cognitive load; ignoring them makes an app feel foreign.

---

## 10. Accessibility & Compliance

> **RULE:** Accessibility is a foundational requirement from day one, not a retrofit. It is both an ethical responsibility and a legal requirement.

### 10.1 Non-Negotiables

| Requirement | Specification |
|---|---|
| **Color contrast** | **4.5:1** for normal text; **3:1** for large text (WCAG 2.2) |
| **Dynamic type** | Support system font-size preferences; never hardcode font sizes; text scales to **200%** without breaking |
| **Screen readers** | All interactive elements need labels for **VoiceOver (iOS)** and **TalkBack (Android)**; e.g., `accessibilityLabel="Open settings"`; provide alt text for images |
| **Gesture alternatives** | Every swipe/pinch has a tap-based fallback |
| **Motion sensitivity** | Respect the **"Reduce Motion"** system setting |
| **Touch targets** | WCAG 2.2 AA floor 24×24 CSS px (use 44/48 in practice) |
| **Semantic info** | Descriptive labels for buttons/icons; headings and links with descriptive text |
| **Don't rely on color alone** | Add labels/shape/text cues |

### 10.2 Standards & Regulation (Source-Reported)

| Item | Detail |
|---|---|
| **WCAG 2.2 Level AA** | Current baseline (covers touch targets, contrast, screen reader compatibility). Note: some UI libraries cite WCAG 2.1 AA; target 2.2 AA |
| **European Accessibility Act (EAA)** | In force since **28 June 2025** across all 27 EU member states |
| **Enforcement signals** | France has filed court summons against major retailers; the Netherlands running spring 2026 audits |
| **Penalties** | **€75,000–€100,000 per violation**, depending on country |
| **EN 301 549 v4.1.0** | Technical standard referencing WCAG 2.2; **expected to be finalized by Q3 2026** — implement now |

### 10.3 Business Case

- Over **15%** of the global population lives with some form of disability.
- Inclusive apps see up to **35% higher engagement**.
- Only a small fraction of top sites meet full compliance (WebAIM analysis) → competitive edge.

### 10.4 Testing Accessibility

- Regularly test with **VoiceOver** (iOS) and **TalkBack** (Android) — manual testing reveals real-world experience.
- Check contrast (e.g., WebAIM contrast checker).
- Use accessibility-first component libraries (ARIA attributes and focus management built in).
- Consider automated scanners and AI tools as a *starting point only* (human review required).
- Adopt **universal design**: design for all abilities, ages, and tech-literacy levels.

### 10.5 Visual/Cognitive Considerations

- Smaller screens are harder for people with visual and cognitive impairments: use effective contrast, appropriate font sizes, and clear headings.
- High-contrast dark mode may be required for readability (e.g., finance app for low-vision users).
- Screen-reader compatibility must extend to core content (e.g., a meditation app's guided sessions).

---

## 11. Dark Mode

> **RULE:** Support system-wide dark mode. Default to the OS setting; allow in-app override.

### 11.1 Rationale (Source-Reported)

- **82%** of mobile users prefer dark mode when available.
- **92%** of top-tier apps support system-wide dark themes.
- On OLED screens it reduces power consumption by **14–58%**.
- Not offering it makes an app feel dated.

### 11.2 Implementation Rules

| Rule | Detail |
|---|---|
| **Don't just invert colors** | Pure white on pure black causes **halation** (affecting roughly 50% of people with uncorrected astigmatism). Use **off-white `#E0E0E0` on dark gray `#121212`** |
| **Test images** | Logos/illustrations designed for light backgrounds often look wrong; provide alternate assets |
| **Respect system preferences** | Default to OS setting; let users override in-app |
| **Rethink elevation** | Shadows are invisible on dark backgrounds → use **lighter surface colors** to indicate elevation |
| **Use system colors** | Built-in system colors adapt automatically between modes |
| **Contrast** | Maintain the same 4.5:1 / 3:1 contrast requirements in dark mode |

---

## 12. Performance & Offline

### 12.1 Speed Principles

> **RULE:** Speed is a design decision. **Never show a blank screen.**

| Metric / Target | Value |
|---|---|
| Users leaving if load takes > 3 s | **53%** |
| 1-second delay impact | Can erase **20%** of potential sales |
| Mobile pages taking > 5 s to render above-the-fold | **70%** |
| 1-second load improvement | Can boost conversions **12%+** |
| **LCP target** | **< 2.5 s** (Largest Contentful Paint; Google's primary loading metric and a confirmed ranking factor) |

### 12.2 Optimization Techniques

| Technique | Detail |
|---|---|
| **Lazy load** | Load only what's visible; defer below-the-fold content |
| **Code splitting** | `React.lazy()` + `<Suspense>` to shrink initial bundle and startup time |
| **Minimize network requests** | Bundle API calls; cache aggressively |
| **Optimized images** | Use **WebP** (20–30% smaller without noticeable loss); `expo-image` for caching/loading |
| **Loading states** | Skeleton screens and progress indicators make waits feel shorter |
| **Profile continuously** | React Native Debugger, Expo performance monitoring, **real devices** (not just simulators); watch main thread, memory, CPU |
| **Set performance budgets** | Use Lighthouse or platform profilers to find bottlenecks (startup, transitions, rendering, asset loading) |
| **Start with optimized foundations** | Pre-optimized templates avoid common pitfalls |

**Measurement tools:** Google PageSpeed Insights (Core Web Vitals), Lighthouse, platform profilers.

### 12.3 Offline Functionality & Graceful Degradation

> **RULE:** Never show an endless spinner or a freeze on network loss. Either work offline via caching or transparently limit features until connectivity returns.

| Strategy | Implementation |
|---|---|
| **Local storage (simple)** | `AsyncStorage` for key-value data (settings, tokens) |
| **Local database (complex)** | SQLite via `expo-sqlite` for structured data (messages, documents) |
| **Network detection** | `react-native-netinfo` → trigger sync, show "Offline Mode" banner, disable connection-dependent features |
| **Request queuing** | Queue offline actions (send message, update task) via Redux/Zustand; auto-send on reconnect; do not show an error |
| **Communicate status** | Clearly show the app's connectivity state |

Examples: Spotify offline playlists; Google Maps cached map data.

**Complexity note:** offline support requires caching, sync, and conflict resolution; high engineering effort and extensive testing.

---

## 13. Responsive Design

> **RULE:** Design **mobile-first**: get core functionality solid on the smallest screen, then progressively enhance for larger screens (more columns, extra information, larger elements).

### 13.1 Concept

Create a single UI that fluidly adapts to screen sizes, resolutions, and orientations (compact phone → tablet → web) while feeling native, without separate codebases. Without it, users on some devices see distorted layouts, unreadable text, and inaccessible controls.

Examples: a finance dashboard must read equally well on a 6.1-inch iPhone and a 12.9-inch iPad Pro; fitness workout displays must adapt from watch to tablet.

### 13.2 Implementation (React Native / Expo)

| Technique | Detail |
|---|---|
| **Breakpoint modifiers (NativeWind)** | Tailwind breakpoints `sm:`, `md:`, `lg:`; e.g., `flex-col` on small screens, `md:flex-row` on medium and up |
| **Responsive component props (gluestack-ui)** | Object props with breakpoints, e.g., `p={{ base: '$2', md: '$4' }}` |
| **Safe areas & orientation** | Account for safe areas and orientation changes |
| **Device testing matrix** | Test across a range of devices/sizes |
| **Layout flexibility** | Aspect ratios differ from desktop; design content to adapt |

---

## 14. Onboarding & First-Time User Experience

The first few minutes are the most critical; poor onboarding is a primary cause of uninstalls. Goal: guide users, showcase core value, reduce friction, drive activation and Day 1/Day 7 retention.

| Rule | Detail |
|---|---|
| **Concise and skippable** | Limit the primary tour to **3–5 screens**; always offer "skip" (consider making it less prominent for first-timers) |
| **Explain permissions in context** | Show a rationale screen *before* the OS prompt (e.g., "Allow location access to find nearby running trails and track your workouts") |
| **Interactive elements** | Have users perform a core action (create first to-do, like a post) instead of static screens |
| **Empty states** | Use empty dashboards as contextual onboarding with a clear call-to-action to create the first item |
| **Demonstrate value early** | Duolingo: immediate playful first lesson; Headspace: free intro session |
| **Progressive disclosure** | Reveal advanced features gradually |
| **A/B test** | Test onboarding flows, since small changes have large impact |
| **AI features** | If the app has AI features, onboarding must set expectations: what it can do, how to interact, its limitations (see Section 18) |

---

## 15. Feedback, Notifications & Personalization

### 15.1 Feedback & Microinteractions

> **RULE:** Every tap, swipe, or gesture must produce a visible/tactile response.

- Forms: subtle animation, color change, scale change, haptics.
- Examples: Instagram's animated heart on double-tap, emoji reactions to Stories.
- Purpose: reassure that the action registered, provide instant feedback, add personality.

### 15.2 Push Notifications

| Do | Don't |
|---|---|
| Provide real value (updates, reminders) | Overuse or mistime |
| Factor in user preferences, **time zones**, interaction patterns | Ignore context |
| Let users **customize** notification preferences | Force all-or-nothing |
| Use to keep users informed without opening the app (e.g., Uber, DoorDash delivery updates) | Annoy users into uninstalling |

### 15.3 Personalization

- Remember preferences; offer content based on past behavior; greet by name; adapt features.
- Examples: Spotify "Discover Weekly" and "Daily Mixes"; Instagram curated feeds.
- Balance personalization with **transparency** (users should understand why content appears and retain control).
- Related AI patterns: Section 18.

---

## 16. Prototyping, Testing & Data-Driven Iteration

### 16.1 Prototype Fidelity Ladder

| Stage | Tool/Method | Purpose |
|---|---|---|
| Paper prototypes | Sketches | Fast, free concept validation; catches navigation problems |
| Wireframes | Figma, FigJam, etc. | Structure/hierarchy before visuals |
| Interactive prototypes | Figma, Framer | Test realistic interactions; **5 users find ~85% of usability issues** (Nielsen Norman Group) |
| A/B tests in production | Firebase A/B Testing, third-party | Optimize specific flows; data beats opinions |
| AI-generated prototypes | Figma Make, v0, Claude Code | Working drafts from prompts in minutes; test on realistic behavior instead of static mockups |

> **KEY TAKEAWAY:** Every $1 invested in UX research yields an average return of **$100** (9,900% ROI). Prototyping and testing find issues when they are cheapest to fix.

### 16.2 Usability Testing Practice

- Build a prototype; have real users (or colleagues resembling users) attempt tasks; observe where they get stuck; use honest feedback to iterate.
- Tools: Figma, Maze.
- Ask friends/coworkers to try builds; if an idea isn't landing, drop it and retry.
- Use **friction logging** internally.

### 16.3 Data-Driven Design Workflow

| Step | Detail |
|---|---|
| **Integrate analytics early** | Firebase Analytics + Crashlytics from day one; track events such as `app_open`, `user_signup`, `feature_usage`, `purchase` |
| **A/B test high-impact areas** | Onboarding flows, CTA buttons, paywalls |
| **Review cadence** | Weekly or monthly reviews; analyze funnels, find drop-offs, form hypotheses |
| **Mix quantitative + qualitative** | Quantitative = *what* is happening; qualitative (interviews, surveys) = *why* |
| **Heatmaps** | Locate friction (e.g., checkout abandonment at the address field) |
| **Compliance** | Consider privacy/compliance when collecting analytics data |

Examples: a dating app found video profiles increased matches by 30%; a finance app used heatmaps to find checkout abandonment at the address field.

**UX audit action:** review an existing app against these principles and identify **3–5 key areas** for immediate improvement.

---

## 17. Development Considerations

### 17.1 App Type Comparison

| Type | Description | Pros | Cons |
|---|---|---|---|
| **Native** | Built for one OS (iOS or Android) | Best performance; full hardware/feature access | Most expensive; separate development per OS |
| **Cross-platform** | One codebase, multiple platforms | Saves time and money | — |
| **Hybrid** | Web technologies packaged as a native app | Easier to maintain | Fewer features than native |
| **PWA** | Website that behaves like an app, runs in a browser | Simple to deploy; accessible from any device | Doesn't always offer full native feature set |

### 17.2 Languages, Frameworks, Tools

| Layer | Options |
|---|---|
| Frontend / native | Swift, Objective-C (iOS); Kotlin, Java (Android) |
| Cross-platform frameworks | React Native, Expo, Flutter, React |
| Backend | Java, Python, SQL databases |
| Design-to-code | Figma Dev Mode (CSS, iOS, Android snippets; plugins for framework-specific output) |
| React Native styling / UI | NativeWind (Tailwind for mobile), gluestack-ui |
| Navigation | React Navigation |
| State / queuing | Redux, Zustand |
| Storage | AsyncStorage, expo-sqlite |

AI in coding: **68%** of developers use prompts to generate code; **82%** report satisfaction (source-reported).

### 17.3 MVP

- A simplified version with only the most essential features; the "test" version.
- Launch to real users to validate core functionality before the full release; use findings to refine.
- Fewer features at first launch reduces overwhelm.

### 17.4 Design System / UI Kit Acceleration

Using a design system or production-ready UI kit/template ensures consistency, bakes in accessibility standards, responsiveness, platform consistency, and performance, so effort can go into unique value.

---

## 18. AI in Mobile Product Design

### 18.1 Two Distinct Topics

1. **AI as a design/workflow tool** (faster research, prototyping, content, testing).
2. **Designing AI-powered product features** (chat, agents, recommendations; trust, control, transparency).

### 18.2 AI as a Designer's Tool

| Use case | Examples / Notes |
|---|---|
| **Data-driven analysis** | Behavior analytics (Hotjar, Mixpanel, Crazy Egg, FullStory); NLP sentiment analysis of reviews (MonkeyLearn, SmartOne); help defining KPIs/success metrics |
| **Efficiency** | Auto-generated responsive layouts/code (Framer, Sketch2React); AI-suggested UI elements, wireframes, prototypes; research recruitment/synthesis; survey/interview question design |
| **Accessibility & inclusion** | Automated WCAG scanners (Monsido, accessiBe, Recite Me); inclusive-language checkers (Acrolinx, Grammarly); AI-generated guidelines |
| **Creativity** | Project briefs, workshop ideas, word-association brand inspiration (color, typeface, imagery, competitors) |
| **Growth** | Trend tracking (Feedly, Scribbler.so); custom learning plans |

> **RULE:** Never rely solely on AI. Human review, validation, and judgment are required (AI can perpetuate stereotypes/bias; AI-generated personas, microcopy, and accessibility fixes need human validation).

### 18.3 Designing AI-Powered Experiences (Principles)

| Principle | Guidance |
|---|---|
| **Transparency & trust** | Show trust signals: explanations, confidence indicators, source citations, ability to verify/edit |
| **User control** | Provide human override controls and human-in-the-loop review; clearly communicate what an agent is doing and allow intervention |
| **Trust calibration** | Communicate capabilities and limitations so users trust the system at the *right* level |
| **Explainability** | Use progressive AI disclosure: short explanation first ("suggested based on your recent activity"), deeper detail on demand |
| **Hallucination handling** | Add verification mechanisms and transparency |
| **Bias mitigation** | Recognize bias sources (training data, design assumptions); add transparency and human oversight |
| **Guardrails** | Rules/constraints preventing harmful outputs |
| **AI onboarding** | Set expectations, teach interaction, disclose limitations |
| **Balance assistance and intrusion** | Copilot patterns must help without overwhelming or distracting (suggestion systems) |
| **Recovery** | Conversational workflows must let users recover from mistakes |

### 18.4 AI Skills (2026, Source-Reported)

| Skill | Meaning |
|---|---|
| Practical AI literacy | Understand what AI can/can't do and where it adds value |
| Prompt engineering | Provide context, specify output format, set constraints on tone/length/inclusions |
| Ethics and compliance | Data privacy, bias, transparency, accountability |
| AI data fundamentals | Question data source, completeness, currency, bias |
| Strategic adoption and integration | Coordinated, consistent adoption with human oversight where needed |

Statistics: **86%** of companies are adopting or planning AI tools; only **49%** of professionals feel confident using AI (Pluralsight).

---

## 19. Reference App Case Studies

| App | Domain | What they got right | Takeaway |
|---|---|---|---|
| **Spotify** | Music/podcasts | Intuitive navigation; data-driven personalization ("Discover Weekly", "Daily Mixes"); social sharing; offline listening; native swipe-back on iOS / back button on Android | Personalization based on individual preferences boosts engagement |
| **DoorDash** | Food delivery | Simple UI; clear icons for restaurants/food/grocery; location services; real-time tracking; push notifications; ratings/reviews; red color palette for urgency | Real-time feedback + color aligned to mission |
| **Instagram** | Social | Subtle micro-interactions (animated heart, emoji reactions); native camera/gallery/GPS integration; curated feeds; platform-specific transitions (fade on iOS, slide on Android) | Micro-interactions create delight |
| **Uber** | Ride-hailing | Minimal UI showing only necessary steps at each point (pickup, drop-off, driver info, payment); GPS tracking; real-time ETA; push notifications; ratings | Show only what the current step needs |
| **Citymapper** | Urban transit | Vibrant color coding for complex transit; real-time data; consolidates transport modes; green-and-white theme avoids confusion | Dynamic real-time content + purposeful color |
| **Notion** | Productivity | All-in-one but not overwhelming; modular design; drag-and-drop; minimalist | Complex, content-heavy apps can stay easy via intuitive principles |
| **Calm** | Meditation | Shades of blue for tranquility; generous whitespace | Color supports app purpose |
| **Netflix** | Streaming | Clear categories and intuitive navigation | Good IA makes discovery easy |
| **Strava** | Fitness | Persistent bottom tabs: Home, Maps, Record | Core actions in persistent tab bar |
| **Duolingo / Headspace** | Learning / meditation | Onboarding that delivers immediate value (interactive lesson / free session) | Show value before asking for commitment |
| **Stripe / Calm** | Payments / meditation | Minimalist flows and generous spacing focus attention on CTAs | White space directs attention |
| **Google Maps** | Navigation | Cached map data for offline use | Design for connectivity loss |

---

## 20. Common Mistakes (Anti-Patterns)

| Anti-pattern | Why it fails | Correct approach |
|---|---|---|
| Too many colors or fonts | Feels random | Small palette; 1–2 fonts |
| Small buttons / unreadable text | Frustrates users; higher error rates | 44 pt / 48 dp targets; readable, scalable type |
| Switching navigation patterns between screens | Screens feel like different apps | One consistent navigation model |
| Confusing labels or icons | Users can't predict outcomes | Clear, well-known icons + text labels |
| Over-customizing standard components | Breaks familiarity | Trust platform built-ins |
| Too many options/actions on one screen | Choice overload; cognitive load | One primary action; progressive disclosure |
| Highlighting everything | Nothing stands out | Accent color only on primary actions |
| Blank screens while loading | Feels broken | Skeleton screens / progress indicators |
| Endless spinner offline | Poor resilience | Cache, queue, offline banner |
| Inverting colors for dark mode / pure white on black | Halation | `#E0E0E0` on `#121212` |
| Gesture-only interactions | Excludes users | Visible tap alternative |
| Hardcoded font sizes | Breaks Dynamic Type | Use system text styles |
| Ignoring "Reduce Motion" | Motion sensitivity issues | Respect the system setting |
| Generic OS permission pop-ups | Lower grant rates / confusion | Contextual pre-permission explanation |
| Overusing or mistiming push notifications | Uninstalls | Value-based, customizable |
| Hiding key functions in secondary menus | Discoverability failure | Actions in context |
| Skipping user testing until after launch | Most expensive mistakes | Prototype and test early |
| Relying on simulators only | Misses real-device issues | Profile on real devices |
| Feature bloat at v1 | Overwhelms users | MVP + MoSCoW |

---

## 21. Master Checklist & Decision Rules

### 21.1 Pre-Launch Checklist

**Strategy & Structure**
- [ ] Primary purpose, audience, and personas documented
- [ ] Every feature ties to a user task/primary goal (MoSCoW applied)
- [ ] User flows defined; IA validated via card sorting
- [ ] Primary actions reachable within 2 taps from home
- [ ] Bottom tabs limited to 3–5 with icons + labels

**Touch & Interaction**
- [ ] All targets ≥ 44×44 pt (iOS) / 48×48 dp (Android)
- [ ] ≥ 8–12 pt spacing between interactive elements
- [ ] Primary actions in thumb zone; left/right-handed support
- [ ] Every gesture has a visible tap alternative
- [ ] Every interaction has visual (and where critical, haptic) feedback

**Visual System**
- [ ] One primary action per screen
- [ ] 8-pt spacing scale; 1–2 fonts; ≤ 2–3 font sizes per screen
- [ ] Accent color used sparingly; palette = brand + complement + neutrals
- [ ] Design system / tokens established

**Platform**
- [ ] Follows Apple HIG (iOS) and/or Material Design 3 (Android)
- [ ] Swipe-back on iOS; system back on Android
- [ ] Native components used; `Platform.select()` for differences

**Accessibility**
- [ ] Contrast 4.5:1 (normal) / 3:1 (large)
- [ ] Dynamic type supported; scales to 200% without breakage
- [ ] VoiceOver and TalkBack labels on all interactive elements; alt text on images
- [ ] Reduce Motion respected
- [ ] Tested manually with VoiceOver/TalkBack
- [ ] EAA / EN 301 549 obligations reviewed (if serving EU users)

**Dark Mode**
- [ ] Follows OS setting with in-app override
- [ ] Off-white on dark gray (not pure white on black)
- [ ] Alternate image/logo assets tested
- [ ] Elevation shown through lighter surfaces

**Performance & Offline**
- [ ] LCP < 2.5 s; no blank screens; skeleton/progress loaders
- [ ] Lazy loading, code splitting, WebP images, cached assets
- [ ] Profiled on real devices
- [ ] Offline behavior designed (cache, queue, banner)

**Onboarding**
- [ ] 3–5 screens, skippable, interactive; contextual permission requests
- [ ] Empty states guide first actions

**Testing & Iteration**
- [ ] Usability, accessibility, performance, compatibility, and QA testing complete
- [ ] Analytics + crash reporting live from day one
- [ ] A/B test plan for onboarding, CTAs, paywalls
- [ ] Store requirements met: metadata, privacy policy, screenshots

### 21.2 Decision Rules (IF → THEN)

| Condition | Action |
|---|---|
| Building for iOS only | Follow Apple HIG; 44×44 pt targets; swipe-back; Liquid Glass conventions |
| Building for Android only | Follow Material Design 3 Expressive; 48×48 dp targets; system back; bottom nav |
| Building cross-platform | Pick one primary design language; adapt navigation, gestures, typography per platform; use `Platform.select()` |
| More than 5 top-level destinations | Reduce/merge; move secondary items into a menu; keep tabs to 3–5 |
| A gesture triggers a function | Add a visible tap-based alternative |
| A screen has multiple competing CTAs | Pick one primary; demote others visually |
| User is offline | Serve cached data, queue mutations, show offline status; do not show error/spinner |
| Requesting a device permission | Show a contextual rationale screen first |
| App has an empty state | Turn it into guided onboarding with a CTA |
| Long list or dense content | Progressive disclosure / expandable sections |
| Text on an image | Add a subtle background/scrim; verify contrast |
| Dark theme design | Use system colors; off-white on dark gray; lighter surfaces for elevation |
| Feature doesn't support the primary goal | Defer/remove (MoSCoW "won't-have" for v1) |
| AI feature included | Add trust signals, override controls, progressive disclosure, onboarding for limitations |
| Choosing between tools/speed | Prototype first; test with ~5 users before build |
| Unsure whether a design element stands out | Check in black-and-white / squint test |

---

## 22. Key Statistics Reference

> All values are **source-reported**; use as directional evidence.

| Topic | Statistic |
|---|---|
| First impression | ~50 ms; ~94% design-driven |
| App abandonment | 72% within 30 days |
| Mobile share of web traffic | > 60% |
| Small touch targets | < 44 px → 3× higher error rate |
| Accessibility population | > 15% of global population has a disability |
| Inclusive apps | Up to 35% higher engagement |
| EAA penalties | €75,000–€100,000 per violation |
| Dark mode preference | 82% of users |
| Top apps with dark mode | 92% |
| OLED power savings (dark mode) | 14–58% |
| Halation / astigmatism | ~50% with uncorrected astigmatism |
| Load-time abandonment | 53% leave after > 3 s |
| 1-second delay | Can erase 20% of potential sales |
| Slow mobile pages | 70% take > 5 s for above-the-fold content |
| 1-second faster load | 12%+ conversion lift |
| LCP target | < 2.5 s |
| WebP savings | 20–30% smaller files |
| M3 Expressive research | 46 studies, 18,000+ participants; up to 4× faster element identification; up to 87% preference among 18–24 year-olds |
| Usability testing | 5 users → ~85% of issues (NN/g) |
| UX research ROI | $1 → $100 (9,900%) |
| Developer AI usage | 68% use prompts to generate code; 82% satisfied |
| AI adoption | 86% of companies adopting/planning; 49% of professionals confident |
| US mobile time | ~5.5 hours/day (adults) |
| Video profiles (dating-app example) | +30% matches |

---

## 23. Tools Reference

| Tool | Category | Notes |
|---|---|---|
| **Figma** | Design/prototyping | Browser-based; component libraries; FigJam whiteboard; Dev Mode for handoff; Figma Make (AI prompt → prototype) |
| **Framer** | Prototyping | Mobile-native interactions/animations; responsive layout/code generation |
| **InVision** | Prototyping | Interactive prototypes from static designs; device mirroring |
| **Adobe XD** | Design/prototyping | Repeat grid; auto-animate |
| **Sketch** | Design | Plugins; device artboard presets |
| **Maze** | Usability testing | Prototype testing with users |
| **Paper / FigJam** | Ideation | Sketching, collaboration |
| **v0, Claude Code** | AI prototyping | Prompt → interactive screens |
| **WebAIM Contrast Checker** | Accessibility | WCAG AA/AAA contrast checks |
| **VoiceOver / TalkBack** | Accessibility testing | iOS / Android screen readers |
| **Google PageSpeed Insights, Lighthouse** | Performance | Core Web Vitals, profiling |
| **Firebase Analytics, Crashlytics, A/B Testing** | Analytics | Event tracking, crash reports, experiments |
| **Hotjar, Mixpanel, Crazy Egg, FullStory** | Behavior analytics | Heatmaps, session analysis |
| **React Native Debugger, Expo monitoring** | Performance | Profiling on real devices |
| **NativeWind, gluestack-ui** | UI frameworks | Tailwind-style responsive mobile styling; accessible, platform-aware components |
| **React Navigation** | Navigation | Tabs, stacks, swipe-back |
| **Xcode, Android Studio** | IDEs | iOS / Android |
| **Laws of UX, Nielsen Norman Group** | Reference | Principles and research guidance |

---

## 24. Glossary: AI-for-UX Terms (100)

### 24.1 Interface Paradigms & Interaction Models

| Term | Definition |
|---|---|
| Adaptive interface | UI that auto-adjusts layout/content/functionality by behavior, preferences, or context (e.g., promoting most-used tools) |
| Adaptive personalisation | Dynamically tailors content/recommendations/UI to individuals from real-time data (e.g., Spotify home) |
| Agent interface | UI for interacting with an AI agent that completes tasks; requires design of task assignment, progress monitoring, intervention |
| AI assistant | AI tool that helps complete tasks/answer questions; often a copilot or chat interface |
| AI-first interface | AI is central; users interact via natural language prompts/commands rather than menus |
| Command-based interaction | Control by entering commands/prompts; requires structured commands and teaching what the system can do |
| Context-aware interface | Adapts to situation (location, device, past behavior) |
| Conversational UI (CUI) | Text/voice dialogue as the primary interaction (vs. GUI) |
| Conversational workflow | Task flow via dialogue; needs error-recovery design |
| Copilot interface | AI integrated alongside the user's work to suggest, generate, or perform tasks; balance help with control |
| Dynamic UI | Interface that changes in real time with behavior, context, or system data |
| Generative UI | Interfaces dynamically assembled/adapted by AI rather than fully predefined |
| Goal-based interaction | Users state outcomes; the system determines the steps |
| Intent-based interaction | Users convey what they want; the AI determines how |
| Interactive AI systems | Continuously respond to user input; feedback loop between user and AI |
| Natural language interface | Everyday language input instead of structured commands/menus |
| Predictive interface | Adapts based on predictions of next user action |
| Predictive UX | Anticipates needs and proactively surfaces actions/info |
| Multimodal AI | Processes/generates text, images, audio, video |
| Decision-support interface | Presents complex info to help users evaluate options; must feel trustworthy and easy to interpret |

### 24.2 AI Systems & Technical Concepts

| Term | Definition |
|---|---|
| Agentic AI | Autonomously plans and executes tasks toward a goal; raises control/trust/transparency challenges |
| Autonomous agents | Plan and carry out multi-step tasks independently |
| Generative AI | Creates new content (text, images, audio, code) |
| Generative design | Algorithms generate design variations from constraints/goals |
| Large Language Model (LLM) | Model trained on vast text to understand/generate language |
| Natural language processing (NLP) | AI for understanding/generating human language |
| Intent detection | Identifies what the user is trying to accomplish from input |
| Pattern recognition | Detects patterns in large datasets; powers recommendations, automation, prediction |
| Recommendation system | Suggests content/products/actions based on behavior and preferences |
| Personalisation algorithms | Tailor content/features to individuals; balance relevance with transparency |
| AI-powered recommendations | Predictions of what users find useful; consider presentation, transparency, user control |
| AI-powered search | Understands intent, handles natural language, gives summarized answers |
| AI suggestion systems | Proactively recommend actions/content/inputs; risk of overwhelming users |
| Sentiment analysis | Determines emotional tone of text |
| Style transfer | Applies visual/stylistic characteristics of one piece of content to another |
| Text-to-image generation | Generates images from written prompts |
| Training data | Dataset teaching a model; quality/diversity determines reliability |
| Data labelling | Tagging data so AI can learn; poor labels → biased/inaccurate output |
| Unstructured data | Text, images, video, audio without fixed format |
| User data modelling | Organizing/analyzing user data to predict behavior/preferences |
| System prompt | Behind-the-scenes instruction defining AI behavior, tone, boundaries |
| Prompt design | Crafting inputs/instructions to guide AI response (UX-oriented) |
| Prompt engineering | Systematic prompt structure/examples/constraints for reliable outputs |
| Few-shot prompting | Provide a few examples to guide AI output format/tone |

### 24.3 Trust, Ethics & Governance

| Term | Definition |
|---|---|
| AI trust signals | Explanations, confidence indicators, citations, verify/edit options |
| Algorithmic bias | Unfair/skewed outcomes from biased data or design |
| Bias | Systematic errors producing unbalanced results; design to mitigate harm |
| Ethical AI design | Fair, transparent, responsible AI products |
| Explainable AI (XAI) | Understandable explanations of how outputs were generated |
| Explainability UI patterns | Show supporting data, key factors, deeper explanation on demand |
| Guardrails | Rules/constraints preventing harmful or inappropriate output |
| Hallucination | Plausible-sounding but incorrect/fabricated output |
| Human-AI collaboration | People and AI partner on tasks |
| Human-in-the-loop AI | Human oversight built into AI process (review/correct/guide) |
| Human override controls | Users can intervene and override AI decisions |
| Progressive AI disclosure | Reveal AI information gradually: simple first, deeper on demand |
| Responsible AI | Ethical, transparent, accountable; addresses bias, privacy, fairness |
| Trust calibration | Users trust the system at the right level (not too much, not too little) |
| AI onboarding | Introduces AI features, sets expectations, shows limitations |

### 24.4 AI-Assisted Design & Prototyping

| Term | Definition |
|---|---|
| AI co-creation | Humans and AI collaboratively create content/designs |
| AI content design | AI-assisted UX writing/microcopy (human review essential) |
| AI design critique tools | Analyze designs for usability/accessibility issues |
| AI design suggestions | Recommendations for layouts/components/hierarchy |
| AI experience design (AIX) | Discipline for designing AI-powered products: transparency, trust, automation, uncertainty, collaboration |
| AI interaction patterns | Recurring patterns: prompt input, conversational workflows, copilots |
| AI layout generation | Generates layout variations from prompts/rules/components |
| AI microcopy generation | AI-drafted labels, tooltips, error messages (human edit needed) |
| AI product designer | Designer specializing in AI-powered products |
| AI prototyping tools | Generate interactive prototypes from prompts/sketches/wireframes |
| AI visual generation | Creates images/graphics from prompts |
| AI-assisted ideation | AI in brainstorming/concept development |
| Component generation | Auto-creates UI components (buttons, cards, nav) per design system |
| Design automation | Automates repetitive design tasks (resizing, variations, responsive versions) |
| Design system automation | Automation/AI maintains and scales design systems |
| Design token generation | Creates/manages color, spacing, typography tokens |
| Flow generation | Generates user flows from prompts |
| Interface generation | Creates UIs from prompts, sketches, specs |
| Prototype generation | Auto-creates interactive prototypes |
| Wireframe generation | Auto-creates low-fidelity layouts |
| Conversational AI | Natural-language conversation systems (chatbots, assistants, copilots); design tone, feedback, flow |
| Conversational design | Designing interactions via conversation: questions, response structure, guidance |
| LLM interface design | Designing prompt input, result presentation, refinement for LLM products |
| Contextual AI | AI using surrounding context for relevant output |

### 24.5 AI in Research, Analytics & Operations

| Term | Definition |
|---|---|
| AI feature discovery | Uses data to surface potential features/improvements |
| AI-generated personas | Draft personas from research/analytics (need human validation) |
| AI insight clustering | Auto-groups similar feedback/insights |
| AI journey mapping | Generates/enhances journey maps from behavior data |
| AI research assistant | Summarizes transcripts, extracts themes, clusters insights |
| AI research synthesis | Combines/summarizes insights across sources |
| AI-assisted research analysis | Speeds qualitative analysis (clustering, patterns, summaries) |
| AI transcription tools | Convert speech to text for research |
| Automated usability testing | AI detects hesitation, repeated clicks, navigation loops |
| Behavioural analytics | Analyzes how users actually interact with a product |
| Data-driven design | Decisions based on real user data rather than assumptions |
| Decision intelligence | Data/analytics/AI to support better decisions and next actions |
| Feature suggestion systems | AI recommends features/actions from usage patterns |
| Journey prediction | Anticipates likely user paths/friction points |
| Task automation | Software/AI performs manual tasks; keep users informed and in control |
| Workflow automation | Streamlines multi-step processes across actions |
| Goal-oriented AI systems | Plan actions and adapt to achieve specific objectives; users must understand and influence the goal |
