---
name: desktop-app-design
title: Desktop App Design — Windows Rules
description: Rules for designing Windows desktop apps — resizable multi-window layouts, multi-modal input, platform conventions, and app lifecycle. Load when designing a Windows/desktop UI, porting a mobile design to desktop, or reviewing a Windows app for layout, input, windowing, theming, accessibility, or install behavior.
applies_when: [windows app design, desktop ui, resizable and multi-window layouts, keyboard navigation, context menus, dpi scaling, snap layouts, desktop accessibility, packaging and lifecycle]
priority: supporting
rules: 18
---

# Desktop App Design — Windows Rules

## Core principle

A desktop app runs inside a frame the user controls — resized, snapped, moved between monitors — and is driven by mouse, touch, keyboard, and pen through conventions Windows already taught them. Follow the platform's styles and standard behaviors and users never have to re-learn interaction patterns; deviate and every deviation reads as broken, even when it technically works.

## Rules

### DAP-01 · Serve the complete input range
rule: Every interaction must work with mouse, touch, keyboard, and pen.
do: Pair each action with on-object commands (context menus, swipe commands) and keyboard shortcuts, then verify it in all four modalities.
never: Ship a gesture-only or mouse-only path.
because: Users expect Windows apps to work with a complete range of inputs and to use design and interaction patterns that look and feel native on current and future devices.

### DAP-02 · Layout that survives resizing
rule: The UI must work as expected when the window is resized down to small dimensions.
do: Use responsive layout techniques; test panes and pages across a variety of dimensions, devices, window sizes, DPI settings, and scale settings.
never: Design to one window size and assume it holds.

### DAP-03 · Handle per-monitor DPI explicitly
rule: Support per-monitor DPI scaling for whatever framework you ship.
do: WinUI applications scale automatically per display; implement per-monitor DPI support yourself on Win32, WinForms, and WPF.
never: Ship a non-WinUI app without DPI work — it appears blurry or incorrectly sized.

### DAP-04 · Scrolling recovers what resizing hides
rule: Users can freely resize the window and push controls out of view; scrolling must bring them back.
do: Support panning and scrolling via keyboard, mouse or trackpad, touch, and pen on every page, no matter how small the window gets.
never: Build a fixed screen whose controls become unreachable at small window sizes.

### DAP-05 · Commands live on the object
rule: Offer context menus, swipe commands, and keyboard shortcuts for the object being acted on.
do: Use platform-provided context menus; on Windows 11 keep Cut/Copy/Paste/Delete at the top, group Open with Open with, and group app extensions below shell verbs — legacy commands stay reachable via Show more options (Shift + F10 or the keyboard menu key).
never: Invent a context-menu style or bury common file commands below app-specific ones.

### DAP-06 · Text is always selectable and copyable
rule: Wherever there is text, users expect to select and copy it; editable text must also cut and paste.
do: Provide the standard shortcuts across keyboard, mouse or trackpad, touch, and pen; WinUI text controls expose cut/copy/paste automatically — wire equivalent commands into other controls.
never: Ship text that cannot be selected, or editing without the standard clipboard shortcuts.

### DAP-07 · Right material for the right lifetime
rule: Acrylic for transient surfaces, Mica for long-lived surfaces.
do: Use Acrylic on context menus, flyouts, and other light-dismiss surfaces; use Mica on the base layer and title bar to communicate the app's active or inactive state.
never: Put Acrylic on a persistent surface or Mica on a transient one.

### DAP-08 · Ship Dark and Light themes
rule: Support both themes and let the user switch between them.
do: Use WinUI XAML theme resources; on Win32 adapt the title bar manually because it does not automatically follow the Dark theme; use Windows 11's softer tones that avoid pure white and pure black.
never: Hard-code a single theme or leave the title bar stuck in light while the app goes dark.

### DAP-09 · Platform controls, icons, and type first
rule: Prefer platform common controls over custom controls unless your scenario requires behavior the platform does not provide.
do: Use Segoe Fluent Icons and Segoe UI Variable (specify Segoe UI Variable rather than Segoe UI in XAML); common controls carry current styling, input behavior, and built-in accessibility support.
never: Hand-build a control the platform already ships, or hard-code outdated icons and fonts.

### DAP-10 · Let Windows draw the window frame
rule: Use the system-provided title bar, caption buttons, border, shadow, and rounded corners.
do: Let the system draw your border and shadow; where customization is unavoidable, use Windows App SDK windowing APIs and platform-drawn caption buttons so behavior stays standard.
never: Custom-draw borders and shadows — that can prevent the system from rounding the window corners.

### DAP-11 · Design for Snap Layouts
rule: The layout must work when the window occupies 1/2, 1/3, or 1/4 of the screen.
do: Test in the Snap Layout menu, opened by hovering the mouse over the maximize button or pressing Win + Z; check three side-by-side windows on large landscape screens and top/bottom stacked windows on portrait screens.
never: Assume the window is always maximized or a single fixed size.

### DAP-12 · Notifications answer user intent
rule: Personalize notifications, make them actionable, and send only what users want — not what you want them to know.
do: Selecting a notification launches the app in that notification's context (except buttons attached to background tasks, such as a quick reply); clear old notifications so Notification Center stays tidy.
never: Send noisy interruptions — users turn the channel off — or use notification channels to send advertisements.

### DAP-13 · Measure before optimizing
rule: Define your key interaction scenarios, add ETW events to measure them, and set goals based on the interaction class associated with user expectations.
do: Measure cold and warm launch, critical interactions, and regressions on representative lower-end and Arm64 hardware; record traces with Windows Performance Recorder and analyze them with Windows Performance Analyzer before optimizing.
never: Optimize without a recorded trace from representative hardware.

### DAP-14 · Stay lean in memory, disk, and background
rule: Reduce foreground memory usage, minimize background work, release resources while in the background, and don't leak memory.
do: Don't wake the CPU or use system resources while backgrounded; size caches efficiently; optimize binary sizes; use push notifications to wake the app instead of keeping it running.
never: Keep a background process alive or ship a silent memory leak.

### DAP-15 · Build natively for Arm64
rule: For best performance, build native ARM64 binaries.
do: .NET apps can target win-arm64 with no code changes; for large C/C++ codebases, Arm64EC lets you incrementally recompile performance-critical modules to native ARM64 while remaining x64 code runs under emulation, all in one binary.
never: Plan for x64 emulation on an app you can rebuild — reserve it for legacy apps that cannot be rebuilt and light workloads.

### DAP-16 · Install, update, and uninstall cleanly
rule: Support per-user install without elevated permissions or reboots, a silent install option, and a complete uninstall.
do: Appear in Apps > Installed Apps; on uninstall remove Start menu entries, files, directories, registry entries, and temporary files; keep user-created content in locations like Documents; download only changed components on update; restart for updates when it's convenient for the user.
never: Leave temporary files behind, or require administrative privileges to install or run the app.

### DAP-17 · Accessibility is a release criterion
rule: Build accessibility into design, implementation, and release criteria.
do: Make every interaction available from the keyboard with a visible keyboard focus indicator; expose accurate accessible names, roles, states, and values through UI Automation; test contrast themes, layouts at 200% text scaling, and critical workflows with Narrator and Accessibility Insights; run automated checks in CI and treat critical accessibility regressions as release-blocking.
never: Communicate meaning through color alone, or ship a control only a mouse can reach.

### DAP-18 · Secure and private by default
rule: Don't require administrative privileges to install or run, and collect the least amount of personal data needed.
do: Sign all executables and DLLs; keep credentials in platform or service credential stores; use TLS for all network communication; get consent before collecting personal data and give the user an easy way to reverse it; isolate privileged features in their own processes.
never: Embed secrets in source code or configuration, or make a consent dialog's "Yes" button larger or more prominent than "No".

## Hard numbers

| Constant | Value | Note |
|---|---|---|
| Snap Layout test sizes | **1/2, 1/3, 1/4 screen** | Also 3 side-by-side on large landscape, stacked top/bottom on portrait |
| Snap Layout invocation | Hover maximize button, or **Win + Z** | Windows 11 |
| Legacy context menu | **Shift + F10** or keyboard menu key | Opens the "Show more options" menu |
| Accessibility scaling test | **200% text scaling** | Required test, alongside contrast themes |
| Windows 11 design principles | **5**: Effortless, Calm, Personal, Familiar, Complete + Coherent | Source's stated principles |
| UX focus areas | **5**: Layout, UI interaction, Visual style, Window behavior, Shell integration | |
| Minimum window size | `unknown: true` | Source says "small dimensions", gives no px/emu value |
| Windows touch-target minimum | `unknown: true` | Not stated anywhere in source; do not import 44 pt / 48 dp figures |
| DPI scaling values | `unknown: true` | Per-monitor DPI required; no specific scaling percentages given |
| Launch-time / memory thresholds | `unknown: true` | Source says set goals by "interaction class", gives no numbers |

## Decision procedure

Review a Windows/desktop design in this order:

1. **Frame** — does it survive resizing small and snapping to 1/2, 1/3, 1/4 (DAP-02, DAP-04, DAP-11)?
2. **Input** — walk every action through mouse, touch, keyboard, and pen (DAP-01, DAP-06).
3. **Keyboard** — reach every control with a visible focus indicator (DAP-17).
4. **Conventions** — context menus, title bar, materials, icons, themes match the platform (DAP-05, DAP-07 through DAP-10).
5. **Rendering** — check at multiple DPI and scale settings for blur or wrong sizing (DAP-03).
6. **Measurement** — traces recorded on lower-end and Arm64 hardware before any optimization (DAP-13, DAP-14, DAP-15).
7. **Lifecycle** — install, update, uninstall, privacy, and accessibility verified end to end (DAP-16 through DAP-18).

## Anti-patterns

- Mobile port: fixed single-viewport layout with no resize or scroll handling.
- A control reachable only by mouse, only by touch, or only by gesture.
- Custom window border/shadow that kills rounded corners or Snap Layouts.
- Custom-drawn control where the platform ships one.
- Single-theme UI, or a Win32 title bar that stays light in Dark theme.
- Layout verified only at 100% scaling on the developer's own monitor.
- Notification blasts, or ads pushed through notification channels.
- Installer needing admin rights, leaving temp files, or missing from Apps > Installed Apps.

## Review checklist

- [ ] Works resized small and snapped to 1/2, 1/3, 1/4
- [ ] Every action works with mouse, touch, keyboard, and pen
- [ ] Every control keyboard-reachable with a visible focus indicator
- [ ] Scrolling recovers all controls at any window size
- [ ] No blur or mis-sizing at any DPI/scale setting
- [ ] Platform context menus, title bar, and caption buttons used
- [ ] Acrylic on transient surfaces; Mica on title bar/base layer
- [ ] Dark and Light themes both correct
- [ ] Segoe Fluent Icons and Segoe UI Variable used
- [ ] Notifications contextual, actionable, and quiet
- [ ] Cold/warm launch measured on lower-end and Arm64 hardware
- [ ] Accessibility tested with Narrator, contrast themes, 200% text scaling
- [ ] Per-user install, silent option, clean uninstall, no admin required
- [ ] Least data collected, consent reversible, binaries signed

## Caveats

- Scope: this file is the **Windows/desktop counterpart** of the mobile hub skill (which owns 44×44 pt / 48×48 dp / 24×24 CSS px); target sizing lives in `fitts-law-touch-targets.md`, effort reduction in `cognitive-load.md`.
- Vendor guidance: this is Microsoft product documentation — its recommendations (WinUI, Windows App SDK, MSIX, Microsoft Store, Windows on Arm) also serve Microsoft's platform and store interests, so treat framework, packaging, and store mandates as vendor preference rather than neutral findings.
- Measured evidence: `unknown: true` — the source reports no usability study results, sample sizes, or effect sizes; its research claims (users "have high expectations", rounded geometry makes UI "much easier to scan") are attributed to unnamed research with no methodology given.
- Most rules are conventional platform guidance, not controlled comparative results; the numbers above are specifications to satisfy, not measured outcome targets.
- The scrape also contained unrelated third-party marketing/blog content (a generic desktop-dev beginner's guide and a vendor promo), dropped as out of scope.
