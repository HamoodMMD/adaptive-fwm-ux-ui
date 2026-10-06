# Accessibility

Target: **WCAG 2.2 Level AA**, unless the project states a stricter requirement.

**Load when:** always.

This module is split so that a requirement is never confused with advice. Part A lists what WCAG 2.2 requires at Level A and AA. Part B is recommended practice beyond AA. Part C covers expected behavior of common components.

**Contents:** [Reporting rules](#reporting-rules) · [Part A: requirements](#part-a--requirements-wcag-22-level-a-and-aa) · [Part B: recommended](#part-b--recommended-beyond-aa) · [Part C: components](#part-c--component-behavior) · [Anti-patterns](#anti-patterns)

## Objectives

People who use a keyboard, a screen reader, magnification, voice control, a switch, high zoom or reduced motion can perceive every piece of content, operate every function and understand every state. On most products this is the largest group of users being silently locked out, which is why accessibility failures on a primary task are P0 or P1.

## Priority principles

1. Native elements first. A real `button`, `a`, `input`, `select`, `dialog`, `table` brings its role, keyboard behavior and states for free. ARIA is for what HTML cannot express.
2. No ARIA is better than bad ARIA. A role is a promise to implement the matching keyboard behavior; ARIA that contradicts reality misleads assistive technology.
3. Everything a mouse can do, a keyboard can do, and you can see where you are while doing it.
4. Meaning is never carried by color, position, shape or sound alone.
5. Verify in the rendered interface. Source review finds likely failures; it cannot confirm contrast, focus order or announcements.

## Reporting rules

- "**Fails SC x.y.z**" only when the failure was observed in the rendered UI or is unambiguous in code (an `img` with no `alt`, an input with no label).
- "**Likely fails SC x.y.z — verify**" when inferred from code or a screenshot (contrast from token values, focus order from DOM order).
- "**Recommendation (not a WCAG failure)**" for anything in Part B or any usability advice.
- Never claim conformance. A review finds problems; it does not prove their absence.

## Checks

### Part A — Requirements (WCAG 2.2 Level A and AA)

**Keyboard**
- All functionality is operable by keyboard alone. (2.1.1 A)
- Focus can always move away from a component using the keyboard. (2.1.2 A)
- Single-character shortcuts can be turned off, remapped, or are active only when the component has focus. (2.1.4 A)

**Focus**
- Focus order follows a sequence that preserves meaning and operability. (2.4.3 A)
- The keyboard focus indicator is visible. (2.4.7 AA) Removing outlines without a replacement fails.
- A focused component is not entirely hidden by author-created content such as sticky headers, footers, cookie banners or non-modal panels. (2.4.11 AA)
- Receiving focus does not trigger a change of context. (3.2.1 A)

**Structure and names**
- Structure and relationships conveyed visually are also in the markup: headings, lists, tables, form groups, landmarks. (1.3.1 A)
- Reading order in the DOM matches the meaningful visual order. (1.3.2 A)
- Instructions do not rely only on shape, color, size, position or sound ("the green button on the right"). (1.3.3 A)
- A mechanism exists to skip repeated blocks. (2.4.1 A) Pages have descriptive titles. (2.4.2 A)
- Link purpose is clear from the link text or its context. (2.4.4 A)
- More than one way exists to locate a page within a set, except steps in a process. (2.4.5 AA)
- Headings and labels describe topic or purpose. (2.4.6 AA)
- Every interactive component exposes a name, role and state. (4.1.2 A) Icon-only buttons need an accessible name.
- The accessible name contains the visible label text. (2.5.3 A)
- Non-text content has a text alternative; decorative images are hidden from assistive technology. (1.1.1 A)
- The page language is set, and passages in another language are marked. (3.1.1 A, 3.1.2 AA)

**Forms**
- Labels or instructions are provided when input is required. (3.3.2 A)
- Errors are identified in text and the item in error is described. (3.3.1 A) A red border alone fails.
- Where a correction is known, it is suggested. (3.3.3 AA)
- For legal, financial or data-changing submissions, the action is reversible, or input is checked, or the user can review and confirm. (3.3.4 AA)
- Fields collecting the user's own information identify their purpose programmatically, in practice with `autocomplete` tokens. (1.3.5 AA)
- Information already entered in the same process is auto-populated or selectable, not asked again. (3.3.7 A)
- Authentication does not depend on a cognitive function test such as memorizing or transcribing, unless there is an alternative or help. In practice: allow paste and password managers, allow pasting one-time codes, no puzzle CAPTCHA without an alternative. (3.3.8 AA)
- Changing a setting does not cause an unexpected change of context unless the user was told beforehand. (3.2.2 A)

**Status messages**
- Messages about results, progress or errors that do not take focus are exposed through a role or property so assistive technology announces them: `role="status"`, `role="alert"`, `role="log"`, or an equivalent live region. (4.1.3 AA)

**Color and contrast**
- Color is not the only means of conveying information, indicating an action or distinguishing an element. (1.4.1 A)
- Text contrast is at least 4.5:1, or 3:1 for large text (at least 18 pt, or 14 pt bold; about 24 px and 18.7 px). Inactive components, pure decoration and logotypes are exempt. (1.4.3 AA)
- User-interface components, their states, and graphics needed to understand content have at least 3:1 contrast against adjacent colors. A boundary is not required when text or an icon already identifies the control. (1.4.11 AA)
- Text is not presented as an image where real text would do. (1.4.5 AA)

**Pointer and targets**
- Pointer targets are at least 24 by 24 CSS pixels, unless: spacing means a 24 px circle centered on each undersized target does not intersect another target or its circle; an equivalent control on the page meets the size; the target is inline in a sentence; the size is set by the browser; or the size is essential. (2.5.8 AA)
- Functions that use dragging have a single-pointer alternative. (2.5.7 AA)
- Multipoint or path-based gestures have a single-pointer alternative. (2.5.1 A)
- Actions complete on the up-event and can be aborted or undone. (2.5.2 A)
- Functions triggered by device motion also have a UI control and can be disabled. (2.5.4 A)

**Reflow, zoom and spacing**
- Content reflows to a width of 320 CSS pixels without loss of content or function and without scrolling in two directions. Content that needs two dimensions (data tables, maps, diagrams, video, toolbars that must stay in view) is excepted, but only that content, not the page around it. (1.4.10 AA)
- Text can be resized to 200% without loss of content or function. (1.4.4 AA) Do not disable zoom.
- Nothing is lost when users set line height to 1.5, paragraph spacing to 2, letter spacing to 0.12 and word spacing to 0.16 times the font size. (1.4.12 AA) Fixed-height text containers usually fail.
- Content is not locked to one orientation unless essential. (1.3.4 AA)
- Content that appears on hover or focus can be dismissed without moving the pointer or focus, can itself be hovered, and stays until dismissed or no longer valid. (1.4.13 AA)

**Time, motion and media**
- Time limits can be turned off, adjusted or extended, with warning. (2.2.1 A)
- Anything that moves, blinks or scrolls automatically for more than five seconds alongside other content, or auto-updates, can be paused, stopped or hidden. (2.2.2 A)
- Nothing flashes more than three times in one second. (2.3.1 A)
- Audio that plays automatically for more than three seconds can be paused or muted. (1.4.2 A)
- Prerecorded video has captions and audio description; live video has captions; audio-only and video-only content has an alternative. (1.2.1–1.2.5 A/AA)

**Consistency**
- Repeated navigation appears in the same relative order across pages. (3.2.3 AA)
- Components with the same function are identified consistently. (3.2.4 AA)
- Help mechanisms that repeat across pages appear in the same relative order. (3.2.6 A)

### Part B — Recommended beyond AA

These improve real use. Report them as recommendations, never as failures.

- **Motion preference.** Honor `prefers-reduced-motion` by removing or replacing non-essential animation. (2.3.3 is AAA; vestibular harm is real, so treat as strongly recommended.)
- **Focus appearance.** A focus indicator at least as large as a 2 CSS pixel perimeter with 3:1 contrast between focused and unfocused states. (2.4.13 AAA)
- **Focus fully visible.** No part of the focused component is obscured. (2.4.12 AAA)
- **Larger touch targets.** About 44 to 48 CSS pixels for primary controls on touch surfaces; 24 is the floor, not the goal. (2.5.5 AAA; platform guidance)
- **Readable measure.** Body text lines of no more than about 80 characters, not fully justified. (1.4.8 AAA)
- **Confirmation for all submissions,** not only legal and financial ones, where the cost of error is real. (3.3.6 AAA)
- **Error summaries** at the top of long forms, linked to the fields, with focus moved to the summary on failed submit.
- **Visible labels at all times,** including when a field has a value.
- **Do not disable submit buttons** as the only signal that something is missing; disabled controls are skipped by keyboard and give no reason.
- **Announce politely.** Use polite live regions for results and progress; reserve assertive alerts for errors that need immediate attention.

### Part C — Component behavior

Expected keyboard and semantics for common patterns (ARIA Authoring Practices).

- **Modal dialog.** `role="dialog"` with `aria-modal="true"` and an accessible name. Focus moves into the dialog on open, Tab and Shift+Tab cycle within it, Escape closes it, and focus returns to the control that opened it. A native `dialog` opened with `showModal()` provides most of this.
- **Tabs (in-page).** `tablist` / `tab` / `tabpanel`; arrow keys move between tabs, Home and End jump to the ends, Tab moves into the panel; `aria-selected` marks the active tab. Activate on focus only when panels render instantly. Tabs that navigate to other pages are links, not ARIA tabs.
- **Navigation menus.** Site navigation is a `nav` landmark containing links, with disclosure buttons using `aria-expanded` for submenus. The ARIA `menu` roles are for application-style command menus and bring arrow-key expectations; do not put them on ordinary navigation.
- **Disclosure and accordion.** A `button` with `aria-expanded` controlling the region.
- **Tables.** `th` for headers with `scope`, a `caption` or other accessible name, `aria-sort` on sorted columns. Never use tables for layout.
- **Custom selects, comboboxes, date pickers.** If a native control can do the job, use it. Otherwise implement the full published pattern, not part of it.
- **Toasts and inline status.** `role="status"` for confirmations; `role="alert"` for errors. Do not move focus to them. Do not auto-dismiss anything the user must act on.
- **Tooltips.** Supplementary only; never the sole place for essential information; must satisfy 1.4.13.

## Anti-patterns

- `outline: none` with no replacement focus style.
- Clickable `div` or `span` with no role, name or keyboard handler.
- Placeholder used as the only label.
- Errors shown only by a red border or icon.
- Positive `tabindex` values that scramble focus order.
- `aria-label` on a non-interactive element, or ARIA roles that contradict the element.
- `aria-hidden="true"` on something focusable.
- `user-scalable=no` or `maximum-scale=1` in the viewport meta.
- Paste blocked on password or one-time-code fields.
- Carousels that auto-advance with no pause control.
- Status conveyed by a colored dot with no text or icon.
- Sticky headers or chat widgets that cover the focused element.
- Heading levels chosen for size instead of structure.

## Exceptions and context

- Contrast rules exempt logos, disabled controls and purely decorative elements. A brand color that fails as body text can still be used where it is large, decorative or paired differently; see `brand-preservation.md`.
- The reflow exception for tables, maps and diagrams covers the two-dimensional content itself, not the surrounding page.
- The target-size requirement has five exceptions; check them before reporting a failure.
- WCAG 4.1.1 (Parsing) was removed in WCAG 2.2; do not report it.
- Legal obligations vary by country and sector. This module describes the technical standard and gives no legal advice.

## Implementation cautions

- Replacing a `div` with a `button` changes default behavior: add `type="button"` inside forms and confirm the existing handler still runs once.
- Adding focus management to an existing dialog is usually UI; replacing the dialog library is not.
- Adding `autocomplete` attributes, labels, `alt` text, `lang`, landmarks and `aria-*` states that reflect existing state is safe. Do not invent state.
- Fix contrast by changing usage or pairing before changing a brand token.
- Do not add an accessibility overlay or widget. They do not fix the underlying markup.
- Test changes with the keyboard at minimum; with a screen reader where one is available.

## Sources

- [W3C-01] WCAG 2.2 — the normative text for Part A
- [W3C-02] What's new in WCAG 2.2
- [W3C-13] How to Meet WCAG (Quick Reference)
- [W3C-03] Understanding 2.5.8 Target Size (Minimum)
- [W3C-04] Understanding 2.4.11 Focus Not Obscured (Minimum)
- [W3C-05] Understanding 4.1.3 Status Messages
- [W3C-06] Understanding 1.4.10 Reflow
- [W3C-07] Understanding 1.4.11 Non-text Contrast
- [W3C-08] Understanding 3.3.4 Error Prevention
- [W3C-09] Understanding 1.4.13 Content on Hover or Focus
- [W3C-10] Understanding 3.3.8 Accessible Authentication (Minimum)
- [W3C-11] Understanding 3.2.3 Consistent Navigation
- [W3C-12] Understanding 3.1.2 Language of Parts
- [W3C-14] APG: Read Me First — no ARIA is better than bad ARIA
- [W3C-15] APG: Modal dialog pattern
- [W3C-16] APG: Tabs pattern
- [W3C-17] WAI forms tutorial
- [W3C-18] WAI tables tutorial
- [WEB-06] prefers-reduced-motion
- [GOV-01] Error summary and validation pattern
