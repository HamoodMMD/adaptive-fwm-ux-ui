# Responsive and mobile

How an interface adapts across screen sizes, input methods and orientations.

**Load when:** device context is mobile-dominant or mixed, or the user asks about responsiveness.
**For desktop-dominant internal tools:** load only to check that the tool degrades honestly at narrower widths; do not redesign it for phones.

## Objectives

On every supported screen, users can read the content, reach the controls, complete the same tasks and understand the same information. Small screens get a different arrangement, not a lesser product.

## Priority principles

1. **Responsive does not mean "stack everything".** Stacking is one tool among several: reprioritize, collapse, scroll within a region, move off-canvas, reorder. Choose per component by what the user does with it.
2. **Prioritize; do not amputate.** Content and functions that matter on desktop matter on mobile. Change their position and presentation, not their existence.
3. **Design for fingers and for the keyboard that covers half the screen.**
4. **Let content decide the breakpoints,** not a list of devices.
5. **Never trap zoom, orientation or scroll.**

## Checks

### Content priority
- At each width the most important content and the primary action for that surface come first, without scrolling past decoration.
- Order on small screens is chosen deliberately; it is not simply the desktop source order collapsed.
- Nothing essential is hidden on small screens. Secondary material may be collapsed behind a clearly labeled control.
- Long pages use headings, in-page links or collapsible sections to keep scrolling manageable.

### Layout and breakpoints
- The viewport meta tag sets `width=device-width, initial-scale=1` and does not disable zoom.
- The page never scrolls horizontally at any width down to 320 CSS pixels. Only content that is inherently two-dimensional (data tables, maps, diagrams, code, wide charts) may scroll sideways, inside its own container. (WCAG 1.4.10, Level AA.)
- Breakpoints are placed where the content stops working, and intermediate widths (small tablets, split screens, large phones in landscape) are checked, not only the classic three.
- Layout uses flexible units and intrinsic sizing; fixed pixel widths and heights on containers are a common cause of overflow and clipping.
- Text containers grow with their content; text is not clipped when it wraps, is translated, or is enlarged.
- Body text keeps a comfortable line length on wide screens by limiting measure, and a comfortable size on small ones.
- Full-height layouts account for mobile browser toolbars that appear and disappear (dynamic viewport units or equivalent), and for device safe areas.

### Touch targets and input
- Pointer targets are at least 24 by 24 CSS pixels or spaced so that 24-pixel circles around them do not overlap. (WCAG 2.5.8, Level AA.)
- For primary touch controls, aim higher: roughly 44 to 48 CSS pixels, about a centimeter on screen, with space between neighbors. This is a recommendation beyond the requirement.
- The tappable area matches or exceeds the visible control; small icons get padding.
- Nothing depends on hover: information and actions revealed on hover have a tap and keyboard equivalent.
- Gestures (swipe, pinch, drag, long-press) have a visible single-tap alternative. (WCAG 2.5.1, 2.5.7.)
- Destructive actions are not placed where an accidental touch is likely, such as beside the primary action or at the screen edge.

### Reach
- Where one-handed phone use is typical, frequent actions sit in the lower part of the screen and rarely used or destructive ones further away. Treat this as a judgment for consumer mobile surfaces, not a universal rule.
- Controls that must be at the top (back, close) have generous targets.

### Navigation
- Few top-level destinations are shown directly; many collapse into a labeled menu, with key destinations still linked in the page.
- Detail: `navigation`.

### Sticky and fixed elements
- Sticky headers, bottom bars, chat buttons and cookie notices together leave most of the viewport for content.
- A sticky call-to-action bar is appropriate on long transactional pages when it holds one or two actions and repeats, not replaces, the in-page control.
- Fixed elements never cover the element that has focus, the field being typed in, or the last content on the page. Add bottom padding equal to the bar's height. (WCAG 2.4.11.)
- When the on-screen keyboard opens, the focused field and its label and error remain visible, and fixed bars do not float over the form.
- Overlapping fixed elements (chat widget over the pay button) are resolved.

### Forms
- Single-column layout; labels above fields; full-width fields with adequate height.
- Correct input types and `inputmode` call up the right keyboard; `autocomplete` enables autofill.
- Input text is at least 16 CSS pixels on iOS to avoid automatic zoom on focus; the fix is the font size, never disabling zoom.
- Selects with many options, date pickers and steppers are comfortable to operate by touch.
- The submit action is reachable after the last field without being hidden by the keyboard.
- Detail: `forms`.

### Tables
- Do not convert tables to cards by default. Prioritize columns, pin the identifying column, allow horizontal scroll within the table with a visible cue, or let users choose columns. Use a stacked layout only when rows are read one at a time.
- Detail: `tables`.

### Charts
- Keep a readable minimum height; reduce ticks and labels; move or replace legends; switch orientation for long category names; offer the key figures or a table when the chart no longer communicates.
- Detail: `charts-data-viz`.

### Images and media
- Images are served at sizes appropriate to the viewport (`srcset`/`sizes` or equivalent) and reserve their space to prevent layout shift.
- Art direction is used where a wide image loses its subject when narrowed: a different crop, not a tiny version.
- Text is not baked into images that become unreadable when scaled down.
- Galleries swipe horizontally with a visible position indicator and controls that also work without swiping; they do not capture vertical scrolling.
- Video does not autoplay with sound, has controls, and does not force full screen.

### Drawers, sheets and dialogs
- On small screens, dialogs become full-screen or near-full-screen sheets with a visible close control; their content scrolls inside them and the page behind does not.
- Bottom sheets hold brief, contextual tasks. They have a visible close button as well as swipe-to-dismiss, respond to the system back action, and are never stacked on each other.
- Long or complex tasks get a full page, not a sheet.
- Opening and closing manage focus as for any dialog.

### Orientation and zoom
- Content works in portrait and landscape; orientation is not locked unless essential. (WCAG 1.3.4.)
- Landscape on phones, with very little height, still shows the content between any fixed bars.
- Pinch zoom is allowed, and text can be enlarged to 200% without loss. (WCAG 1.4.4.)
- At 400% zoom on a desktop (equivalent to a 320-pixel-wide viewport) the page reflows as on a phone.

### Performance on mobile
- The first screen does not wait on heavy media or scripts; effects such as large blurs and scroll-linked animation are checked on a mid-range phone. See `core/performance.md`.

### Checking
Check at least: 320 and 360–390 CSS pixels wide (phones), about 768 (tablet portrait), about 1024 (tablet landscape or small laptop), 1280 and wider, plus one very wide screen; phone landscape; 200% and 400% zoom; with the on-screen keyboard open on forms. State which of these were actually verified in a rendered environment and which were inferred from code.

## Anti-patterns

- `user-scalable=no` or `maximum-scale=1`.
- Horizontal scrolling of the whole page.
- Hiding features, content or whole sections on mobile with `display: none`.
- Every multi-column layout collapsed to one long column, including tables and comparisons.
- Desktop layout scaled down to fit.
- Tiny icon buttons packed together.
- Hover-only menus, tooltips and actions.
- Sticky header plus sticky footer plus cookie bar leaving a letterbox of content.
- Fixed bar covering the submit button or the focused field.
- Modals taller than the screen that cannot scroll.
- Sheets on top of sheets.
- Fixed pixel widths; `100vh` panels cut off by browser chrome.
- Text in images.
- Carousels that swallow vertical swipes.
- Breakpoints only at three device widths, with a broken layout between them.
- 12-pixel input text that triggers zoom, "fixed" by disabling zoom.

## Exceptions and context

- **Expert desktop tools** (dense admin, analytics, editors) may define a minimum supported width. Below it, behave honestly: keep content reachable with scrolling and say that a larger screen is recommended, instead of shipping a broken phone layout or a crippled one.
- **Tasks that are truly unsuited to phones** (complex configuration, wide data analysis) may offer a reduced mobile scope focused on monitoring and quick actions, as a product decision that is stated to the user.
- **Mobile-first consumer products** can drop hover refinements and desktop density considerations, but must still work with keyboard and at large sizes.
- **Kiosk and embedded displays** have fixed dimensions and input; apply target-size and legibility checks only.
- **Native-app webviews** follow the host platform's conventions for navigation and safe areas.
- **Print** is a separate medium; consider it only where users print (invoices, tickets, reports).

## Implementation cautions

- UI-safe: CSS layout, breakpoints, spacing, sizing, overflow containers, target padding, responsive image attributes where variants already exist, viewport meta corrections, safe-area and dynamic-viewport handling, reordering with CSS where reading and focus order stay logical.
- Reordering visually with CSS (`order`, grid placement) while leaving DOM order unchanged can break focus and reading order. Prefer changing the DOM order where it is safe, or keep visual and DOM order aligned.
- Showing different components at different widths may duplicate ids, handlers, form fields and analytics events; hide one from assistive technology and from submission, and verify nothing fires twice.
- Functional, recommend: a separate mobile navigation model, mobile-specific flows, new image variants or pipelines, column choosers, virtualization, offline support.
- Changing a shared component's responsive behavior affects every surface using it; check them.
- Test on real devices or accurate emulation where possible; say when you could not.

## Sources

- [WEB-08] Responsive web design basics — viewport, content-driven breakpoints, not hiding content, line length
- [W3C-06] Reflow — 320 CSS pixels, two-dimensional exceptions
- [W3C-03] Target size minimum — 24 CSS pixels and exceptions
- [NNG-20] Touch targets — about one centimeter, spacing
- [NNG-10] Mobile tables — preserving comparison
- [NNG-17] Navigation visibility on mobile
- [NNG-32] Sticky headers — size, opacity, partially persistent headers
- [NNG-33] Bottom sheets — close button, back support, no stacking, brief tasks only
- [NNG-35] Modal dialogs
- [W3C-04] Focus not obscured
- [BAY-09] Mobile ecommerce practices; [BAY-11] touch keyboards and hit areas
- [WEB-07] Input types and autofill on mobile
- [W3C-01] WCAG 2.2 — 1.3.4, 1.4.4, 1.4.10, 2.4.11, 2.5.1, 2.5.7, 2.5.8

The reach guidance, the 16-pixel input note and the list of widths to check are practical judgments, not requirements (evidence class: Judgment).
