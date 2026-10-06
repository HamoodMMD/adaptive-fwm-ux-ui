# RTL and bilingual interfaces

Right-to-left languages (Arabic, Hebrew, Persian, Urdu), interfaces offered in more than one language, and content that mixes directions.

**Load when:** the surface uses an RTL language, offers more than one language, or has a language switcher.
**For a single-language RTL product:** skip the language-switching section; everything else applies.

**Contents:** [Foundations](#foundations) · [What mirrors](#what-mirrors-and-what-does-not) · [Mixed-direction text](#mixed-direction-text) · [Numbers, dates and time](#numbers-dates-and-time) · [Typography](#typography) · [Components](#components) · [Language switching](#language-switching) · [CSS](#css-techniques)

## Objectives

An RTL user gets an interface that reads and flows naturally in their direction, not a left-to-right design viewed in a mirror with the exceptions broken. A bilingual user can switch language without losing their place, and sees complete, correctly rendered content in both.

## Priority principles

1. **Setting `direction: rtl` is the start, not the result.** It flips text flow and some layout, and leaves icons, positioning, shadows, animations and mixed-direction strings wrong.
2. **Mirror what expresses direction of reading or movement. Do not mirror what expresses the physical world, time on a clock, or media.**
3. **Direction belongs in the markup** (`dir`), not only in CSS, so it survives without styles and informs assistive technology.
4. **Isolate opposite-direction text.** Phone numbers, emails, URLs, code and Latin product names inside Arabic need explicit handling or they reorder unpredictably.
5. **Both languages are first-class.** The second language is not a reduced or machine-flipped copy.

## Checks

### Foundations
- `dir="rtl"` and the correct `lang` are set on the `html` element for RTL pages, and both change when the language changes.
- Direction is set in markup. CSS `direction` is not used as a substitute for the `dir` attribute.
- Layout CSS uses logical properties and values (`margin-inline-start`, `padding-inline-end`, `inset-inline-start`, `border-inline-start`, `text-align: start`) instead of physical left and right, so one stylesheet serves both directions.
- Flex and grid layouts follow the document direction on their own; they are not forced with reversed order hacks.
- Passages in another language are marked with `lang` (WCAG 3.1.2, Level AA), and with `dir` when their direction differs.

### What mirrors and what does not

| Mirror in RTL | Do not mirror |
|---|---|
| Overall layout: sidebars, columns, primary alignment | Logos and brand marks |
| Navigation order; tab order; breadcrumb order and separators | Photographs, illustrations and product images |
| Back and forward arrows, chevrons, "next/previous" controls | Media playback controls and the media timeline (play, rewind, fast-forward, scrubber) |
| Icons that show reading direction or forward movement: send, reply, list bullets, indent, open-in-new, text alignment | Clocks and anything circular that turns clockwise (refresh, history, timers) |
| Progress bars, steppers and sliders that show progress through a sequence: they fill from the right | Check marks |
| Carousels and paged content: next is to the left | Numerals and the order of digits within a number |
| Position of leading icons, trailing icons, badges, close buttons | Phone numbers, emails, URLs, code, file paths |
| Text-field icons and the side on which clear or reveal controls sit | Charts and graphs: axes keep their orientation |
| Table column order (first column on the right) | Icons of real-world objects with no reading direction: camera, lock, cup, magnifier |
| Checkboxes and radios relative to their labels | Slashes and symbols whose direction is part of their meaning |
| Tooltip and popover anchoring | Icons that contain text or letters: localize them instead |
| Drawer and panel entry side; swipe directions for navigation | Maps and geographic directions (left turn stays left) |

Notes:
- Help icons that show a question mark are mirrored for Arabic and Persian, whose question mark is reversed (؟), and not for Hebrew.
- A volume control with a speaker icon and a slider is a UI control, not media: it mirrors.
- A rating or count sequence reverses its order (1 to 5 from the right); the digits themselves never flip.
- Animations and transitions that move along the inline axis reverse.

### Mixed-direction text
- Inline runs in the opposite direction (a Latin brand name, a product code, a username in an Arabic sentence) are wrapped in an isolating element (`bdi`, or `dir` on a `span`) so that surrounding punctuation and numbers do not reorder.
- Text of unknown direction, such as user-generated content, names and search queries, uses `dir="auto"` so each item takes the direction of its own content.
- Inputs that accept either language use `dir="auto"`.
- Strings are not built by concatenating translated fragments and variables; each language has a complete template with placeholders, so word order and direction can differ.
- Punctuation at the end of a mixed sentence lands at the correct side (a full stop after a Latin word at the end of an Arabic sentence appears on the left).
- Parentheses, quotes and list markers appear correctly oriented.
- Truncation puts the ellipsis at the end of the text in its own direction.

### Numbers, dates and time
- The choice of digits (Western 0–9 or Arabic-Indic ٠–٩) follows the locale and the product's decision, and is consistent across the interface, including inputs, charts and messages.
- Digits within a number always run left to right in both systems. Numbers, ranges ("10–20"), versions and measurements are isolated so that minus signs, percent signs and separators stay in place.
- Currency symbols and codes, and unit placement, follow the locale.
- **Phone numbers** are displayed left to right with the plus sign and country code first, in an isolated LTR run, and are never reversed.
- **Emails, URLs, usernames, code, file paths, IBANs and card numbers** are LTR. Their inputs have `dir="ltr"`; alignment within the field is a design choice applied consistently.
- Dates use the locale's order and month names; the calendar system (Gregorian, Hijri) is whatever the product supports for that locale and is stated where ambiguous. Do not add a calendar system the product does not support.
- The first day of the week and the weekend follow the locale.
- Time ranges and date ranges read in the document direction ("from … to …") while each number stays LTR.
- Calendars mirror their day order; "next month" is to the left.

### Typography
- Arabic script generally needs a larger size and more line height than Latin text at the same nominal size to be equally legible: it has taller ascenders, deeper descenders and stacked marks. Check body and small text in particular.
- No letter-spacing (tracking) on Arabic script; it breaks the joining of letters.
- No italic for emphasis and no reliance on uppercase: Arabic has neither convention. Use weight, size or color with a second cue. `text-transform: uppercase` has no effect and all-caps labels lose their distinction.
- The font stack names a typeface that properly supports the script, with matching weights for both scripts so that bold and regular look balanced in mixed text.
- Justified Arabic text needs care; start-aligned text is safer for UI.
- Line breaking is by word; long Latin strings inside RTL text (URLs) must still wrap or scroll.
- Diacritics and marks are not clipped by tight line heights or `overflow: hidden`.
- Text containers flex: translations differ in length in both directions. Fixed-width buttons, tabs and labels are a defect in any bilingual interface.

### Components
- **Navigation and breadcrumbs:** order mirrors; separators and chevrons point the other way; the active indicator moves to the mirrored edge.
- **Forms:** labels align to the start edge (right); required marks, help icons and error icons sit on the mirrored side; error text aligns with the field; field order in a row mirrors. Fields for LTR-only data keep `dir="ltr"`. Validation accepts the digits and characters users of that language actually type, or the limitation is stated (changing validation is a functional recommendation).
- **Tables:** the first column is on the right and is the pinned column; text aligns to the start edge. Numeric columns stay aligned so that digits line up by place value, which means physically right-aligned in both directions. Horizontal scroll starts from the right.
- **Steppers and progress:** steps run right to left; completed portions fill from the right.
- **Pagination:** "previous" is on the right, "next" on the left; arrows mirror; page numbers keep LTR digits in mirrored order.
- **Carousels and sliders:** direction of travel reverses; swipe gestures reverse.
- **Dialogs, drawers and toasts:** the close button moves to the mirrored corner; drawers enter from the mirrored side; button order in action rows mirrors.
- **Icons with labels:** the icon sits on the start side of its text in both directions.
- **Charts:** not mirrored; axis labels and legends are translated and their text is correctly directed; legends may move to the start side.
- **Maps, code blocks, terminals:** not mirrored.
- **Keyboard:** left and right arrow keys follow visual direction in mirrored components such as tabs, menus, sliders and carousels.

### Language switching
- The switcher is easy to find, in a consistent place on every page, and available before sign-in.
- Each language is named in its own language and script ("العربية", "English"), with the option's `lang` set, not represented by a flag.
- Switching keeps the user on the equivalent page, with their place, form input and cart or session preserved as far as the product supports.
- The choice persists across pages and visits.
- After switching, `lang`, `dir`, fonts, number formats and date formats all change together, and focus is not lost.
- If a page has no translation, the user is told, instead of being sent silently to the home page or shown mixed languages.
- Both languages carry the same content and functions. Untranslated strings, images containing text in the other language, and English-only error messages and emails are defects to report.

### CSS techniques
- Replace physical properties with logical ones; in utility frameworks use the logical utilities (start/end variants) or direction variants instead of left/right.
- Audit the things `dir` does not flip for you: absolute positioning with `left`/`right`, `transform: translateX()`, `float`, `text-align: left/right`, `background-position`, linear-gradient directions, box-shadow horizontal offsets, border-radius on specific corners, and JavaScript that computes horizontal positions or scroll offsets.
- Flip directional icons with a single rule (for example mirroring a marked class under `[dir="rtl"]`), applied only to icons that should mirror.
- Horizontal scroll position and `scrollLeft` behave differently in RTL; test scrollable regions.

## Anti-patterns

- `body { direction: rtl; }` and nothing else.
- Mirroring everything, including logos, photos, media controls, clocks, charts and check marks.
- Back arrows still pointing left; chevrons pointing into the text.
- Phone numbers displayed reversed or with the plus sign at the wrong end.
- English brand names scrambling the punctuation of Arabic sentences.
- Hard-coded `left`/`right` in layout, so half the interface stays in LTR positions.
- Flags as language options; languages named in the wrong language.
- Switching language sends the user to the home page or logs them out.
- Half-translated screens; English error messages in an Arabic interface.
- Letter-spaced or uppercase-styled Arabic labels.
- Arabic text at a size chosen for Latin, cramped and clipped.
- Fixed-width buttons that truncate the longer language.
- Concatenated strings ("You have " + n + " items").
- Mixed digit systems on one screen.
- Progress bars filling from the left in an RTL flow.
- Images with embedded text in one language used for both.

## Exceptions and context

- **Conventions vary by locale and product.** Digit system, calendar, weekend and some mirroring choices (for example whether a timeline chart runs right to left) are decided per market. Follow the project's existing convention and flag inconsistency rather than imposing one.
- **Technical and developer tools** keep code, logs, terminals and identifiers LTR even when the surrounding interface is RTL.
- **Media-centric interfaces** keep playback controls and timelines LTR.
- **Hebrew, Arabic, Persian and Urdu differ** in digits, question mark, fonts and conventions; do not assume one RTL language's rules for another.
- **Bilingual pages showing both languages at once** need per-block `lang` and `dir`, and a clear visual hierarchy between the two.
- **You cannot review copy you cannot read.** Check structure, direction, rendering and completeness; flag wording for a competent reader of the language.

## Implementation cautions

- UI-safe: `dir` and `lang` attributes that reflect the existing language state, logical CSS properties, icon mirroring rules, isolation markup around existing strings, `dir="ltr"` on LTR-only inputs, font stacks using fonts already in the project, line-height and size adjustments for the script, flexible widths.
- Functional, recommend: adding a language, a locale-routing scheme, language persistence, number or date localization logic, a calendar system, validation that accepts additional digit systems, restructuring strings in translation files, translating missing content.
- Never write or "fix" translations in a language you cannot verify; never machine-translate into the product.
- Changing translation keys or message structure affects every language and the translation workflow.
- Converting physical to logical properties is safe when done completely for a component; a half-converted component can be worse than either state. Verify in both directions.
- Shared components serve both directions: test LTR after every RTL fix.
- Third-party widgets (maps, payment fields, chat, date pickers) may have their own RTL and locale settings; use them instead of overriding their layout.
- Adding a font is a dependency and a performance cost; recommend it instead of adding it unasked.

## Sources

- [MAT-01] Material Design bidirectionality — what to mirror and what not to
- [APL-02] Platform right-to-left guidance — controls, icons and numerals
- [W3C-20] Structural markup and right-to-left text in HTML — `dir` on `html`, `dir="auto"`, `bdi`, markup over CSS
- [W3C-21] Arabic and Persian layout requirements — joining, justification, numerals, line height, absence of italics and capitals
- [MDN-01] CSS logical properties and values
- [W3C-12] Language of parts
- [W3C-22] Time and time zones across locales
- [W3C-01] WCAG 2.2 — 3.1.1, 3.1.2, 1.3.2 Meaningful Sequence, 1.4.12 Text Spacing

Table-alignment, typography-size and language-switcher guidance beyond these sources is practical judgment (evidence class: Judgment). The two platform references could not be machine-read reliably when checked; see the note in `research-sources.md`.
