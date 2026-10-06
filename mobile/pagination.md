---
name: pagination
title: Pagination — Design Rules
description: Rules for paginating large content sets — choosing between pagination, infinite scroll and Load more, and designing controls, page size, placement, state and bulk-selection behaviour. Load when designing search results, product listings, data tables, dashboards, forums, comment threads or content libraries.
applies_when: [pagination, infinite scroll, load more, search results, product listings, data tables, dashboards, forums, comment threads, content libraries, navigation]
priority: supporting
rules: 15
---

# Pagination — Design Rules

## Core principle

Pagination is a navigation mechanism that separates content into discrete pages instead of forcing one endless scroll. It buys structure, progress and orientation: the user knows where they are and can move through a large set deliberately. Good pagination is simple, predictable and easy to navigate — users only notice it when it is bad.

## Rules

### PAG-01 · Match the pattern to the task
rule: Choose between pagination, infinite scroll and Load more from the task, before drawing any controls.
do: Use pagination when users need structure, orientation, comparison and control; use infinite scroll or Load more for discovery-focused experiences.
never: Put infinite scroll under a task where users must find, compare, manage or action specific items.
because: Without page breaks users struggle to return to something they saw earlier, and scanning tables, comparing entries and exporting data get far harder. Pagination is the most familiar pattern and keeps the interface predictable.

### PAG-02 · Previous and Next are the minimum
rule: Every pager ships with working Previous and Next controls.
do: Provide forward/back affordances even when numbered navigation is omitted, and make even subtle number-only styling obviously actionable.
never: Ship navigation that looks like static text, or a pager with no way to step through pages.

### PAG-03 · Disable controls that lead nowhere
rule: On the first page, disable or hide Previous; on the last page, disable or hide Next.
do: Treat both ends as dead ends so users don't click in vain.
never: Leave Previous clickable on page 1 or Next clickable on the final page.

### PAG-04 · Page numbers for direct access
rule: Offer numbered page links whenever a user may want a specific page.
do: Let users jump straight to a page when there are many pages of results.
never: Force step-by-step traversal through a long result set.

### PAG-05 · Make the current page unmistakable
rule: The active page is visually distinct and is not a link.
do: Style it differently — a different-colour background or bold text — and remove its link, so users get a clear "you are here" in the sequence.
never: Render the current page identically to its neighbours, or as a live link to itself.

### PAG-06 · Truncate long ranges with ellipses
rule: Never render every page number in a long set.
do: Show `1, 2, 3, … 10, 11, 12` — on the first page truncate the tail only, on the last page truncate the head only, in the middle truncate both ends.
never: Let the pagination bar grow until it clutters the interface or overwhelms the user.

### PAG-07 · Show the size of the set
rule: Tell users how much content they are facing.
do: Show the last page number, an explicit "Page 2 of 12", or the total results; show per-page and total counts especially in tables where users manage action items.
never: Leave users unable to judge how far they have to go, or whether to jump around or refine the search.

### PAG-08 · First/Last when the ends are hidden
rule: Add First and Last controls for large page sets, especially when truncation hides the end pages.
do: Prefer explicit First/Last buttons when the first and last numbers are not on screen; they improve clarity and accessibility.
never: Assume truncated numbers alone always make the ends reachable.

### PAG-09 · Place controls where the list ends
rule: Put pagination directly underneath the content it paginates — the good default.
do: For a very long list, such as a data table with 500 rows, also place controls above the list, fixed at the top while scrolling, or fix the bottom controls so they stay visible.
never: Make a user scroll to the end of a 500-row table just to reach navigation.

### PAG-10 · Let users set page size — and remember it
rule: Offer page size as a predefined drop-down selector where records are managed, and persist the choice.
do: If a user chooses 100 items per page, keep showing 100 per page as they navigate.
never: Reset page size or other preferences on every navigation.

### PAG-11 · Preserve position after actions
rule: Keep the user on the page they were on after an action or after returning to the list.
do: If a user deletes an item on page 3, they stay on page 3 rather than being kicked back to page 1.
never: Return the user to the first page after a delete, save, or return from an item detail.

### PAG-12 · Every page is a clean, linkable URL
rule: Pages must be deep-linkable and bookmarkable.
do: Give each page a clean URL so results can be bookmarked, shared and indexed — a stated reason to choose pagination.
never: Hold page position only in memory, so a reload or bookmark loses the user's place.

### PAG-13 · Jump-to-page for large sets
rule: Give a direct route to a specific page when page counts are high.
do: Numbered links, or an input where users type the page number — people estimate which page holds a result and refine the guess from the content.
never: Offer only incremental Previous/Next across dozens of pages.

### PAG-14 · Drop numbers when they add nothing
rule: Let the user's needs decide whether numbered navigation appears.
do: Calendars need only forward/back plus a way to jump to the present day; blogs and media sites usually need no numbers; some heavy data tables manage without them.
never: Add a full number strip by default to a list where direct page access is not a real task.

### PAG-15 · Constrain bulk selection across pages
rule: Selections may span pages, but scope must always be visible and confirmed.
do: Show how many items are selected and on what page; permit bulk actions on the current page only, unless an obvious confirmation dialog indicates exactly which items will be affected.
never: Run a bulk action over items the user cannot see, with no confirmation.
because: Cross-page selection is where pagination quietly breaks trust: the user acts on a set they never saw assembled.

## Hard numbers

| Constant | Value | Note |
|---|---|---|
| Search results per page | **10–20** | Typical search-engine page size, numbered links below |
| E-commerce items per page | **20–30** | Typical product listing chunk |
| Truncation / progress examples | **1, 2, 3, … 10, 11, 12** · **Page 2 of 12** | Ellipses at both ends; explicit label or last page number |
| Persisted page size example | **100 items per page** | Must survive navigation |
| Long-table threshold example | **500 rows** | Top-fixed controls instead of page-bottom only |
| Visible page-button count, tap targets, breakpoints, ARIA/keyboard semantics | unknown: true | None stated in source; tap targets owned by fitts-law-touch-targets |
| A/B results, conversion data, sample sizes | unknown: true | No measured evidence in source |

## Decision procedure

1. **Pattern** — decide this first; the controls come after:

| Pattern | Use when | Best for · avoid when |
|---|---|---|
| Pagination | Users are searching, comparing, or managing content. You need clean URLs and bookmarking. The experience benefits from structure and orientation. | Structured tasks, search, dashboards · avoid when users need fluid or passive content consumption |
| Infinite scroll | Content is casual, visual, or endless. You don't need deep linking or structured browsing. Engagement matters more than control. | Browsing, discovery, social feeds · avoid when users need structure, comparison, or orientation |
| Load more | You want smoother performance without full-page jumps. Content comes in groups (like cards or tiles). You need a lightweight pattern that doesn't overwhelm. | Modular layouts, chunked content · avoid when you need deep linking, SEO, or precise navigation |

2. **Page size** — 10–20 for search, 20–30 for products, user-chosen rows for tables, none needed for calendars and blogs.
3. **Controls** — Previous/Next always; numbers when direct access matters; ellipses when ranges are long; First/Last when ends are hidden; a typed jump field for large sets.
4. **Totals** — "Page 2 of 12" or total results; per-page plus total counts matter most in action tables, least in content lists.
5. **Placement** — under the list by default; above and fixed for long lists such as a 500-row table.
6. **State** — persist page size, preserve page position after actions, and give every page a clean deep-linkable URL.
7. **Bulk actions** — show selection count and page, and confirm scope before acting.

## Anti-patterns

- Infinite scroll under a task that requires finding, comparing or managing items.
- A clickable Previous on page 1 or Next on the final page.
- Current page styled like every other number, or left as a live link.
- Every page number rendered with no truncation.
- Deleting an item on page 3 and landing the user back on page 1.
- Page size or preferences silently reset on navigation.
- Controls buried below a 500-row table with nothing at the top.
- A bulk action that silently affects items on other pages.

## Review checklist

- [ ] Pattern matches the task: structure/compare/control vs. discovery
- [ ] Previous and Next present; dead ends disabled or hidden
- [ ] Current page highlighted, unlinked, "you are here"
- [ ] Long ranges truncated; first and last page reachable in one click
- [ ] Total pages or results shown ("Page 2 of 12")
- [ ] Page size selectable where records are managed, and remembered
- [ ] Controls under the list; top/fixed placement for long tables
- [ ] Clean, bookmarkable, deep-linkable URLs per page
- [ ] Position preserved after deletes, saves and returns to the list
- [ ] Cross-page selections show count and page; bulk action confirmed
- [ ] Controls look actionable even when styled subtly; numbers omitted where useless

## Caveats

- This is practitioner advice from two blog-style articles plus agency case examples; no A/B results, conversion data, sample sizes or study citations appear anywhere in the source — measured evidence: `unknown: true`.
- Cross-page bulk selection is flagged by the source itself as an open question it wants to investigate further; PAG-15 is its stated recommendation, not a settled standard.
- Back-button and return-from-item restoration are not addressed explicitly; only post-action position preservation is stated.
- Siblings: `chunking.md` owns grouping content for memory, `fitts-law-touch-targets.md` owns tap target sizes, `cognitive-load.md` owns choice reduction; the mobile commerce patterns skill owns listing/category screens.
