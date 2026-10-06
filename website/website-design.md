---
name: website-design
title: Website Design — Design Rules
description: Rules for designing websites — page layout, visual hierarchy, navigation, typography, colour, CTAs, mobile responsiveness, load speed, and accessibility. Load when designing a landing page or marketing site, reviewing a web page, choosing type and colour, building responsive layouts, or auditing performance and accessibility.
applies_when: [landing pages, marketing sites, page layout, visual hierarchy, navigation, typography and colour, ctas, responsive design, mobile web, site speed, web accessibility, usability review]
priority: core
rules: 15
---

# Website Design — Design Rules

## Core principle

A website exists to get a scanning visitor to the right information and the right action, fast. Clarity, consistency and speed outrank novelty; every element must earn its place.

```
hierarchy  = rank objectives → mirror that rank in size / weight / colour / position / spacing
convention = Jakob's Law → navigation and layout stay predictable
discipline = cap colour, type, text, options → white space and speed are the payoff
```

## Rules

### WEB-01 · Maintain visual consistency across every page
rule: One visual system — palette, fonts, imagery, button styles, tone — applies to every page.
do: Limit the palette to a cohesive 3–5 colours; use 1–2 legible fonts site-wide; keep imagery to consistent filters and themes; reuse one template per page type; keep backgrounds, text sizes, spacing and voice identical.
never: Let a single page switch palette, typeface, or button style.
because: Consistency defines brand identity and fosters familiarity and trust; a mid-site style switch makes visitors wonder whether they clicked the wrong thing.

### WEB-02 · Build hierarchy from ranked objectives
rule: Rank the page's objectives by importance, then make the dominant visual elements serve the top one.
do: Put the most important content in the above-the-fold area; use headers to structure and label, colour and element size to create focal points, and contrast plus white space to steer attention — larger, higher-contrast, top/centre elements win.
never: Let a decorative element out-shout the primary message, or bury the key message below the fold.
because: Visitors scan rather than read every word; top-of-page content has a much better chance of being noticed than content that requires scrolling.

### WEB-03 · Give every fold ample white space
rule: White space (the empty area between elements) groups content and reduces visual noise — it is not wasted space.
do: Place related items close so they read as related and separate unrelated ones; lay elements out on a grid; set generous, consistent margins and padding so key content can breathe.
never: Ship a congested layout with no rhythm, or fill every gap with something.
because: A cluttered page feels stressful and overwhelming, and whitespace raises reading comprehension while lowering cognitive burden.

### WEB-04 · Keep navigation conventional and predictable
rule: Navigation is not the place to get creative — match the mental models users arrive with.
do: Meet the three-click rule (each visitor goal reachable in fewer than 3 clicks; use a mega menu when sections overflow); keep primary nav simple and near the top, identical in label and position on every page; breadcrumbs on every page except the homepage; mobile header reduced to logo + hamburger (three stacked horizontal lines); keyword search near the top; nav repeated in the footer; site map no more than three levels deep; plain labels like "About", "Services", "Contact".
never: Rename standard items for novelty, move the menu between pages, or hide the way back.
because: Jakob's Law — users build mental models from past experience, and deviating from them confuses visitors and hinders their ability to find what they need.

### WEB-05 · Write for scanners
rule: People scan rather than read in depth; optimise every text block for skim-readers while limiting copy to the necessities.
do: Chunk text into paragraphs of 100–200 words at 50–75 characters per line; use clear, descriptive subheadings — one per distinct section; pair text with relevant visuals so meaning lands without reading.
never: Present long continuous blocks of text, or blow up and bold so much text that headings stop signalling anything.

### WEB-06 · Make CTAs prominent and actionable
rule: The primary call to action must be prominently displayed and clearly distinguishable from the surrounding content.
do: Give the button a colour that contrasts with background and neighbours; use verb labels — "Buy", "Subscribe", "Sign Up", "View Plans"; place CTAs where users are most likely to act and repeat them top and bottom of the page so a convinced visitor can act immediately; add subtle hover or animation.
never: Let the CTA blend into the page, or label it vaguely ("More", "Click Here").
because: Vague labels and buried buttons cost conversions; the source reports a 12% conversion lift from top-and-bottom placement plus actionable wording (anecdotal, unverified).

### WEB-07 · Design mobile-first for thumbs
rule: Design for the small screen first and assume no cursor, no hover, and imprecise input.
do: Size buttons and interactive elements around 44 × 44 px so a thumb can tap them; scale body copy to 14px minimum and confirm it reads comfortably on a small screen; collapse the header to logo + hamburger; replace hover menus with tap/focus states; stack blocks vertically with generous spacing; use accordions or collapsible sections instead of endless swiping; open external links in new tabs; keep text readable without zooming.
never: Use hover-dependent dropdowns, or fancy animated effects, on mobile.
because: In 2022 over 60% of the global internet population used a mobile device to go online, and Google prioritises sites with quality mobile versions.

### WEB-08 · Treat speed as a design objective
rule: Fast load times are a design requirement, not an afterthought.
do: Serve images as WebP/AVIF or compress them (TinyPNG); lazy-load images and non-essential elements until the user scrolls to them; put static files on a CDN served from servers near the user; cut heavy JS and animation libraries and unnecessary typefaces; measure load time, page size and image compression with performance tools.
never: Ship unoptimised full-size images, or load an animation library for effects that do not earn their weight.
because: About half of users expect a site to load in two seconds or less and will leave if it takes longer; the source also reports Google finding bounce rate up 32% when load time went from one second to three.

### WEB-09 · Build to a WCAG accessibility standard
rule: Accessibility is an ethical and practical necessity — apply it to structure, page format, visuals, and written and visual content.
do: Hold contrast ratios of at least 4.5:1 for normal text and 3:1 for large text (check with WebAIM Contrast Checker); alt text for every non-decorative image; captions and transcripts/close captioning for video; every interactive element reachable and operable with the Tab key; focus states enabled; descriptive link text and form field labels; never carry meaning in colour alone — add text labels, patterns, bold/underline, shapes; aim at perceivable, operable, understandable, robust.
never: Rely on hover states to convey information, or ship images and icons with no alt text.
because: The source cites CDC figures that about 27% of Americans have a disability — failing accessibility can shut out roughly a quarter of consumers.

### WEB-10 · Be memorable where conventions are safe
rule: Inject distinctiveness into content and flourish, never into navigation or core interaction.
do: Try asymmetrical layouts for visual interest; add microinteractions — hover effects, animated buttons, playful loading animations — that delight without distracting; use custom illustrations in a distinctive brand style.
never: Sacrifice consistency, clarity, or predictable navigation to look original, or make users learn your interface to finish a task.

### WEB-11 · Cap colour and type
rule: Limit colour to a small harmonious palette and type to a small, legible set.
do: Start from one dominant colour and layer outward (darker colours grab attention first and carry more visual weight); keep 3–5 colours, at most 3–4 prominent ones, applied the same way everywhere; use no more than three typefaces, clean and legible, with high text-to-background contrast; limit font sizes so hierarchy stays readable.
never: Carry an 11-colour palette that no channel can reproduce consistently, or add a typeface per section.

### WEB-12 · Give every image a job
rule: Each visual must illustrate a point or provide a visual break at a natural pause — never inserted at random.
do: Pair copy with screenshots, diagrams, product shots and short video so a complex offer lands instantly; keep imagery on brand and on palette; compress for load time; write descriptive alt text.
never: Fill space with decorative visuals, or let media weight slow the page — especially on mobile.

### WEB-13 · Ship the standard page skeleton with clear labels
rule: Every page carries a header and a footer, and every control says what it does.
do: Header = visible logo (top-left or centre), primary navigation, optional CTA or search bar. Footer = contact info, sign-up form, common-page links, legal and privacy policies, social links. Search where users expect it, visible on key pages, with a magnifying-glass cue and a clean results page. Label buttons, links, menu items and form fields by function — "View Pricing", "Download Guide".
never: Use ambiguous labels like "Learn More" or "Click Here" without context, or hide essentials from the footer.

### WEB-14 · Test with first-time users, not yourself
rule: The first published version is never final; validate with people who have never seen the site.
do: After launch run heatmaps, click maps, scroll-depth tracking, and page speed / Core Web Vitals measurement; A/B test CTA colour, headline and wording; refine and retest against the data.
never: Approve a design because it looks obvious to you — your investment in it biases your judgement.

### WEB-15 · Functionality over aesthetics
rule: If a site does not work and does not read clearly, how it looks does not count.
do: Concentrate on solutions that are easy to use, dependable and practical; let design support content and functionality, with user needs front and centre.
never: Trade usability, legibility, or accessibility for a visual flourish.

## Hard numbers

| Target | Value | Note |
|---|---|---|
| Colour palette | **3–5 colours**; at most **3–4 prominent** | second figure from the appended guideline article |
| Typefaces | **1–2** fonts site-wide; **no more than 3** | same |
| Paragraph / line length | **100–200 words** per paragraph, **50–75 characters** per line | Wix article |
| Clicks to goal | fewer than **3** (three-click rule); site map **≤ 3 levels deep** | mega menu if it won't fit |
| Mobile tap target | **~44 × 44 px** | thumb-sized |
| Mobile body text | **14px** minimum, checked on a small screen | source's minimum recommended size |
| Mobile share | **over 60%** of global internet population (2022); **58.67%** of global traffic (2023) | source-reported, unverified |
| Load-time expectation | **two seconds or less** for ~half of users | Kissmetrics via source, unverified |
| Load time → bounce | bounce **+32%** when load goes **1s → 3s** | Google via appended article, unverified |
| Text contrast | **≥ 4.5:1** normal, **≥ 3:1** large (Wix quoting WCAG) vs **4.5:1 / 4:1** (appended article) | source-internal conflict — verify against live WCAG |
| Disability prevalence | **~27%** of Americans | CDC via source, unverified |
| Sites considered accessible | **< 5%** | appended article, unverified |
| Image cadence | one image every **200–300 words**, **60/40** text-to-image, **40%** more shares | one team's claim, anecdotal |
| A/B variant impact | micro **≤ 2%**; macro **40–300%** conversion | appended article, unverified |
| CTA rewrite + placement | **+12%** conversion | vendor anecdote, unverified |
| First-impression window | **five seconds** to capture attention | appended article, unverified |

`unknown: true` — breakpoint values, grid column/gutter specifications, font-size scales, Core Web Vitals thresholds, and any numeric attention-span or response-time limit: the source asks for responsive layout, grids, readable type and Core Web Vitals but states no numbers for any of them.

## Decision procedure

1. **Skeleton** — header (logo top-left, primary nav near top, optional search) and footer (contact, legal, common links) on every page; nav label and position identical everywhere.
2. **Objectives** — rank the page's goals; place the top one above the fold.
3. **Hierarchy** — make the primary element win on size, weight, colour, position and spacing; nothing secondary may out-shout it.
4. **Density** — check paragraphs 100–200 words, lines 50–75 characters, one subheading per section, grid alignment, white space on every fold.
5. **CTA** — contrast colour, verb label, placed and repeated top and bottom.
6. **Mobile pass** — ~44 × 44 px targets, 14px body, no hover dependencies, hamburger header, accordions instead of endless scroll.
7. **Speed pass** — WebP/AVIF, lazy loading, CDN, no gratuitous libraries, measured.
8. **Accessibility pass** — 4.5:1 / 3:1 contrast, alt text, captions, keyboard tab order, focus states, no colour-only meaning.
9. **Test** — first-time users, heatmaps, scroll depth, A/B on the CTA; refine and retest.

## Anti-patterns

- Hover-only navigation or hover-only information on mobile.
- Wall of text with no subheadings or line-length control.
- Nav labels and position that change page to page; clever renames "to be different".
- A CTA that blends into its background, labelled "Learn More".
- Text below 4.5:1 on its background; meaning carried by colour alone.
- Full-size unoptimised images and animation libraries on the critical path.
- Palette drift per page; a new typeface per section.
- Approving your own design as usability evidence.

## Review checklist

- [ ] One palette (3–5), 1–2 fonts, consistent imagery, button styles and tone across pages
- [ ] Top objective above the fold; primary element dominates on size, weight, colour, position, spacing
- [ ] White space on every fold; grid alignment; paragraphs 100–200 words at 50–75 characters
- [ ] One descriptive subheading per section; text paired with purposeful visuals
- [ ] Nav conventional, near the top, identical everywhere; three-click rule; breadcrumbs; footer nav; search
- [ ] Labels say what they do — no "Learn More" or "Click Here"
- [ ] CTA contrasts with surroundings, verb label, repeated top and bottom
- [ ] Mobile: no hover dependencies, ~44 × 44 px targets, 14px body readable without zooming
- [ ] Images WebP/AVIF, lazy-loaded, CDN-served; no gratuitous libraries
- [ ] Contrast ≥ 4.5:1 / ≥ 3:1, alt text, captions and transcripts, keyboard operable, focus states
- [ ] Tested by first-time users; post-launch heatmap and scroll-depth data reviewed

## Caveats

- Provenance: this is practitioner listicle content, not research — the scraped file concatenates three articles (the Wix blog's "10 game-changing web design best practices", plus appended Tiller and HubSpot listicles); WEB-01–WEB-10 follow the Wix list and WEB-11–WEB-15 mine the appended sections.
- Evidence: no measured evidence anywhere — no before/after metrics of its own, no study results, no sample sizes, no citations; the Wix article gestures at "several studies" and "countless studies" (picture superiority effect) without naming them. `unknown: true`. All figures above are source-reported and unverified except the quoted WCAG ratios, and third-party figures (Kissmetrics, CDC, Google) arrive second-hand; the source contradicts itself on large-text contrast (3:1 vs 4:1).
- Sibling scope: this file is the web counterpart to the mobile hub skill, which owns platform/target/accessibility numbers for apps; `fitts-law-touch-targets.md` owns touch-target sizing; `cognitive-load.md` owns effort reduction; `jakobs-law.md` owns conventions.
