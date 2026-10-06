---
name: responsive-web-design
title: Responsive Web Design — Design Rules
description: Rules for building layouts that adapt to any screen size and input mode — fluid grids, relative units, content-driven breakpoints, mobile-first, responsive media and typography, the viewport meta tag, and mobile navigation. Load when building or reviewing any web layout, choosing breakpoints, setting up a responsive grid, sizing media and type for multiple screens, or auditing a site on phone, tablet, and desktop.
applies_when: [responsive layout, fluid grids, breakpoints, media queries, mobile-first design, flexible images and video, responsive typography, viewport meta tag, mobile navigation, cross-device testing, web layout review]
priority: core
rules: 18
---

# Responsive Web Design — Design Rules

## Core principle

One fluid site that adapts to the device, never separate sites per device. HTML itself is fundamentally responsive — a page with no CSS reflows to fit the viewport — so responsiveness is not a separate technology; it is a set of best practices. You design small first, then add layout only when the content needs more width.

## Rules

### RWD-01 · One codebase, one URL
rule: Responsive design is the default way to build the web; maintain a single responsive site, not desktop and mobile versions.
do: Build one page whose layout, content, and media adapt to the viewport.
never: Maintain a separate m-dot mobile site with its own server, codebase, content, and base URL.
because: A second site duplicates content and links, requires redirect logic that can be wrong or unwanted, and adds server and maintenance cost; search engines have ranked mobile-friendly single sites higher since early 2015.

### RWD-02 · Always set the viewport meta tag
rule: Every document must declare `<meta name="viewport" content="width=device-width, initial-scale=1">` in its head.
do: Separate attributes with commas so older browsers parse them correctly; pair `width=device-width` with `initial-scale=1` so CSS pixels map 1:1 to device-independent pixels in any orientation.
never: Rely on breakpoints or media queries without the tag, or add `minimum-scale`, `maximum-scale`, or `user-scalable` attributes.
because: Mobile browsers default to a desktop-width viewport (usually about 980px), so without the tag a responsive layout's narrow-screen styles never kick in — and disabling user scaling breaks zooming and accessibility.

### RWD-03 · Design content-driven, not device-class
rule: Choose breakpoints where the content degrades, not where a device category ends.
do: Define breakpoints with relative units (rem/em) or content behaviour rather than the pixel width of an individual device; let content decide when to reflow.
never: Set breakpoints to match named devices, brands, operating systems, or product classes.
because: Screens span an unpredictable range; per-device breakpoints make code unmaintainable, while content-driven breakpoints naturally cover unknown future sizes.

### RWD-04 · Mobile-first, then enhance
rule: Build the single-column small-screen layout first, then add multi-column layout only when there is enough width.
do: Write the base styles for narrow screens, then query for wider screens and layer layout changes on top.
never: Design four columns first and try to break them down to one.
because: Starting small minimises the number of breakpoints and keeps the mobile experience — usually the majority of traffic — the deliberate one.

### RWD-05 · Move with relative units, not fixed pixels
rule: Size layout, widths, and gaps with relative units — percentages, `fr`, `em`/`rem`, `vw` — not fixed pixels.
do: Use percentage widths or flexible grid units so columns narrow as the screen narrows; reserve pixels for small fixed elements only.
never: Give containers or text blocks fixed pixel widths that overflow the viewport on small screens.
because: A fixed 640px block is not fully visible on a 320px phone without scrolling or zooming; a percentage stays full-width and the text keeps wrapping.

### RWD-06 · Rely on flexible grid techniques
rule: Use Flexbox, CSS Grid, or multicol for responsive structure; each is responsive by default.
do: Distribute space with `flex-grow`/`flex-shrink`/`flex-basis`, `1fr` grid tracks, or `column-width` (e.g. a grid of cards with `repeat(auto-fit, minmax(200px, 1fr))` adds tracks as width allows).
never: Assume you must hand-set every grid size with media queries — the techniques handle most scaling on their own.
because: Modern layout methods make columns narrow, wrap, or reflow automatically; media queries become reserved for big structural changes.

### RWD-07 · Keep media inside their containers
rule: Images, video, and picture elements must never overflow the viewport.
do: Give `img, picture, video { max-width: 100%; }`, add `height: auto` to preserve aspect ratio, and state explicit `width`/`height` attributes on images so the browser reserves space before load (preventing layout shift).
never: Let media inherit its intrinsic width; a fixed-size image larger than the viewport forces horizontal scrolling.
because: Overflow content requires horizontal scroll or pinch-zoom to see — either is a poor experience; reserving space prevents layout jumps while images load.

### RWD-08 · Serve media sized to the display
rule: Choose the smallest media suitable for the rendered size; do not download full-size assets to scale them down.
do: Optimise file size before upload (correct format such as PNG or JPG, graphics-editor optimisation); where appropriate use `<picture>`, `srcset`, and `sizes`, and responsive `<source>` media queries inside `<video>`/`<audio>`.
never: Serve one giant landscape image to a portrait phone just to shrink it with CSS; it wastes bandwidth and crops the subject.
because: Mobile devices face bandwidth and battery constraints, and a landscape image can be hard to see on a device that suits a portrait one; CSS effects like gradients and shadows can replace image-heavy decoration with no download cost.

### RWD-09 · Fluid typography, never vw alone
rule: Scale type with media queries or a fluid function — never with viewport units alone.
do: Set a small default and override upward at a breakpoint (e.g. 2rem default, 4rem at `width >= 1200px`), or use `calc(1.5rem + 4vw)` or `clamp(min, preferred, max)` so the fluid part sits on top of a fixed-sized, zoomable base.
never: Set `font-size` as pure `vw` (e.g. `6vw`) without a fixed base unit.
because: Text set only in viewport units is always tied to viewport size and users lose the ability to zoom it; adding `vw` to a value set in ems or rems stays zoomable while still scaling gradually.

### RWD-10 · Guard reading length at every range
rule: Keep text blocks readable at every size by constraining line length at larger viewports.
do: Watch for line lengths past about 10 words (an ideal column runs about 70–80 characters, roughly 8–10 words, per line) and add a breakpoint or cap the content width when it exceeds that.
never: Let a text block stretch across the full width of a wide monitor.
because: Long full-width lines are hard to read; constraining the column (e.g. content width 550px once the browser is past 575px) keeps reading comfortable.

### RWD-11 · Use major and minor breakpoints
rule: Add major breakpoints for structural changes and minor breakpoints for refinements between them.
do: Insert a major breakpoint when the layout must change significantly; between majors, adjust margins, padding, or font size to feel natural (e.g. boost body font past 360px, put two values on one line at 500px, cap panel width at 700px).
never: Keep one monolithic breakpoint set that only flips whole layouts.
because: Refining between major changes makes every intermediate width feel intentional rather than stretched.

### RWD-12 · Never hide content just to fit the screen
rule: Screen size must not decide what content a user may want.
do: Reflow, compress, or reorganise content for small screens; hide only what is genuinely secondary and reachable another way.
never: Drop or hide information because it does not fit — a removed piece of content is invisible to the user who needs it (e.g. deleting a pollen count from a weather forecast harms allergy sufferers who decide by it).
because: Display width does not predict task; hidden content creates a poor or broken experience for exactly the users who depend on it.

### RWD-13 · Mobile navigation must stay reachable and honest
rule: On small screens, compress navigation (hamburger, accordion, or tabbed) but keep the same information architecture.
do: Place primary mobile navigation where thumbs can reach it — typically middle or bottom of the screen, not the top — and keep the visible label faithful to what is inside.
never: Stuff a hamburger with content users would not expect there, or place primary nav at the top where thumbs cannot comfortably reach it.
because: Desktop users can use a pointer to reach a top bar; phone users hold the device, so nav must sit in the thumb zone — and a hamburger that bundles a product menu into general options confuses users expecting something else.

### RWD-14 · Query capability, not just width
rule: Use capability media queries (`hover`, `pointer`, `any-hover`, `any-pointer`) only when interaction mode matters to the design.
do: Customise for touchscreens and small screens when the task calls for it; use `any-hover`/`any-pointer` when you genuinely need to know whether any pointer can hover or interact (e.g. a laptop with a trackpad and touchscreen matches both coarse and fine pointers).
never: Treat big screen = desktop with a pointer, or small screen = touch, and never force an interaction that requires switching input modes.
because: Device size does not predict input; assuming a pointer on large devices or touch on small ones mis-serves real hardware combinations.

### RWD-15 · Size content to the viewport, always
rule: Every element must fit inside the viewport width at every breakpoint.
do: Audit for overflowing content — an image wider than the viewport, a fixed-width column, an oversized fixed element — and fix the cause rather than masking it.
never: Ship a page where horizontal scrolling is needed to read the main content.
because: Users scroll vertically comfortably, but horizontal scrolling or zooming out to see a page reads as broken; automated Lighthouse audits ("`<meta name="viewport">`", "content not sized to viewport") catch both classes.

### RWD-16 · Performance is a responsive concern
rule: Keep mobile load light — mobile remains constrained by battery and bandwidth even when capable.
do: Optimise images, cache aggressively, and keep the critical rendering path short; remember downloaded media that is then scaled down in CSS is wasted bytes.
never: Treat desktop fast-enough as mobile fast-enough or ship unoptimised media because CSS will shrink it.
because: Faster pages lower bounce; delivering less data is the responsive version of performance, and lighter layouts also pass Lighthouse and ranking signals more easily.

### RWD-17 · Think in responsive components, not pages
rule: Build responsiveness at the component level — marquees, cards, carousels, CTAs — so every unit already adapts at every viewport.
do: Design and develop components together, deciding how each reflows, shrinks, or is reorganised across widths; then page assembly is composition of ready components.
never: Design a full page at one width and retrofit responsiveness afterward.
because: Page-by-page retrofits duplicate effort and miss states; component-level responsiveness means each element already shines at every viewport width.

### RWD-18 · Test across viewports, devices, and input modes
rule: Verify the design at every breakpoint on real and emulated devices before launch.
do: Use browser device mode and "show media queries" to jump between breakpoints; test on real devices when possible; cover the device–browser combinations your analytics show; test fonts on multiple devices; and test speed, navigation, and touch interactions at each size.
never: Assume a layout that works in one emulated viewport works everywhere, or release a font before checking it renders on target devices.
because: Breakpoint shifts, unsupported fonts (rendering as random characters), navigation changes, and tap/thumb interactions only show up when exercised at real widths; smooth adjustments, readable content, and working navigation at all breakpoints are the bar.

## Hard numbers

| Value | Meaning |
|---|---|
| `width=device-width, initial-scale=1` | viewport meta tag; `initial-scale=1` maps CSS pixels to device-independent pixels (DIP) 1:1 |
| ~980px | the width mobile browsers default to when rendering a page without the viewport tag (varies across devices) |
| 70–80 characters (≈ 8–10 words) per line | classic ideal reading-column length; add a breakpoint when a text block passes ~10 words |
| 550px | content width used in the web.dev reading-length example once the browser is ≥ 575px |
| 360px / 500px / 700px | web.dev minor/main breakpoint examples (body font boost / single-line temps with 64px icons / capped panel width) |
| 600px | the running web.dev and MDN example breakpoints for a two-column switch (max-width 600px plus min-width 601px pair) |
| 1200px | MDN example threshold where an h1 jumps 2rem → 4rem |
| 2–3 | typical number of major breakpoints per page (Adobe/Figma guidance) |
| 500px / 1200px / 1400px | common device-grid breakpoint edges with 4-, 8-, and 12-column grids (Figma guidance: extra-small ≤ 500px 4-col, small 500–1200px 8-col, medium 1200–1400px 12-col, large ≥ 1400px 12-col) |
| 200px | example minimum width for grid cards (auto-fit) and for adding a multicol column |
| 1vw | one percent of viewport width (the reason pure-vw type is non-zoomable) |

Source-reported numbers, not measured findings: **> 60%** of web traffic from mobile devices; **74%** of online users likely to revisit a site with a mobile-friendly design; Google surfacing mobile-friendly rankings **since early 2015**; NYT responsive redesign **2018**. All other effect sizes, sample sizes, and conversion measurements: `unknown: true`.

## Decision procedure

1. Open the layout in the narrowest viewport that matters — the base is mobile-first, single column.
2. Confirm the viewport meta tag (`RWD-02`) is set in every page head.
3. Assign each element a relative unit (`RWD-05`) and a flexible grid technique (`RWD-06`); audit media rules (`RWD-07`) before breakpoints.
4. Widen the viewport; the first moment content looks bad is a breakpoint — record it in the content's units, not a device (RWD-03).
5. Between major breakpoints, add minor refinements (type size, spacing) rather than new layouts (RWD-11).
6. Check reading length at the widest setting you allow; cap the column or add a breakpoint (RWD-10).
7. Trim what you really cannot fit — but reflow or reorder content rather than hiding it (RWD-12). Reorder mobile navigation for thumb reach (RWD-13).
8. Confirm no element can force horizontal scrolling (RWD-15) and that media is served at the rendered size (RWD-08).
9. Run the breakpoint-plus-real-device pass (RWD-18), then review performance at mobile network conditions (RWD-16).

## Anti-patterns

- **A second m-dot site** — duplicated codebases, URLs, content, and redirect logic for "mobile users".
- **Fixed pixel widths everywhere** — columns or text that overflow narrow screens and scroll horizontally.
- **Breakpoints named after iPhones or brands** — unmaintainable and wrong for the next device.
- **Downscaling one giant image with CSS** — wasted bandwidth and a subject that crops badly on phones.
- **Pure `vw` typography** — users can no longer zoom the text.
- **`maximum-scale`, `minimum-scale`, or `user-scalable`** — blocks the user from zooming; an accessibility failure.
- **Hiding a needed datum to make the small screen tidy** — e.g. removing the pollen count from a forecast.
- **Top-of-screen primary navigation on phones** — out of thumb reach.
- **Layouts tuned in empty emulations only** — untested on the device–browser pairs real analytics show, with unsupported fonts or broken tap targets.

## Review checklist

- [ ] Viewport meta tag present and correct in every page head.
- [ ] Layout, widths, and type use relative units; no fixed-width container overflows a narrow viewport.
- [ ] Base styles are mobile-first; multi-column only appears under a width query.
- [ ] Every breakpoint is justified by content degradation, not a device class.
- [ ] `img`, `picture`, `video` capped with `max-width: 100%` (+ `height: auto`), with explicit image dimensions.
- [ ] Media is optimised and dimensioned for the rendered size, not merely rescaled by CSS.
- [ ] Type is zoomable (rem/em base; `vw` never alone).
- [ ] Reading lines are capped near 70–80 characters on wide screens.
- [ ] No content is hidden purely to fit the screen; nav is faithful and thumb-reachable.
- [ ] No horizontal scrolling at any breakpoint.
- [ ] Capability queries (`hover`/`pointer`/`any-*`) used only where input mode truly matters.
- [ ] Tested at every breakpoint on emulated and real devices, including touch, speed, and fonts.

## Caveats

- The raw source is a concatenation of **five unrelated documents**: MDN's "Responsive design" guide (the bulk; rules RWD-02–RWD-11 and the 980px/reading-length content), Google web.dev's "Responsive web design basics" by Pete LePage and Rachel Andrew (readability, capability queries, content-constraint examples), a Figma blog article (component/grid breakpoint conventions and the framework comparisons, which were dropped as product material), an Adobe article on responsive best practices (thumb-reachable navigation, frequency of testing, the published traffic/ranking numbers), and Jarrod Nix's "Back to Basics" intro (m-dot critique, pixel vs relative units) — the concatenation means the same claim sometimes appears in several sources without a shared study.
- There is a genuine tension inside the set: MDN and web.dev say define breakpoints by content (relative units), while the Figma guidance publishes fixed pixel device-grid breakpoints (500/1200/1400) and says teams "typically" use 2–3 breakpoints per page. Both are recorded; neither reconciles the other. There is also no single agreed breakpoint value — the examples use 360, 480, 500, 575, 600, 640, 700, 720, 768, 1200, and 1280px across the sources.
- The numeric claims above the Hard-numbers table — the >60% mobile-traffic share, the 74% revisit statistic, and the mobile-friendly ranking effect — are source-reported marketing/industry figures with no study or sample size attached: `unknown: true`. The verified mechanics (viewport default width, relative-unit behaviour, zoomability of fluid type) are browser specification behaviour, not usability measurements.
- Sibling coverage: `website-design.md` (core, the visual/UX counterpart — this file is the layout-and-technique layer), the mobile hub skill (platform numbers there), `fitts-law-touch-targets.md` (tap-target and thumb-zone sizing), `pagination.md` (list navigation at scale), `cognitive-load.md` (why cluttered small screens fail), and `progressive-disclosure.md` (hiding vs revealing content — see RWD-12).