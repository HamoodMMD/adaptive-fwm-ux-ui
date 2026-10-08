# Visual scale: type, headers, heroes and buttons

The measurable details of a page: how large the text is, how long the lines run, how tall the header is, how much of the first screen the hero takes, how big the buttons are.

**Load when:** a public, marketing, sales, content or store surface is audited in full; the user asks about font sizes, spacing, header or banner size, or "the details"; a first screen is being judged.
**Skip when:** the surface is a dense internal tool (its density rules are in `profiles/admin-backoffice`, `profiles/dashboard-analytics` and `patterns/tables`).
**Pair with (when present):** `core/brand-preservation`, `core/accessibility`, `patterns/responsive-mobile`.

## Objectives

Text is comfortable to read at every width, the hierarchy is visible at a glance, the header leaves the screen to the content, and the first screen says what the page is and offers its main action. Sizes are judged against requirements first, published guidance second and common practice last.

## Priority principles

1. **Three kinds of number, never mixed up.** A *requirement* can be failed (WCAG). *Guidance* comes from research or a design system. *Observed practice* is what established sites ship. Say which one a finding rests on.
2. **A project's scale is part of its brand.** Do not move sizes toward a typical value because it is typical. Change a size when it fails a requirement, harms reading, or breaks the page's own system.
3. **Judge the rendered result,** at a phone width and a desktop width, not the stylesheet.
4. **Hierarchy comes from contrast between levels,** not from every level being large.
5. **The first screen has a job:** say what this is and offer the main action. Decoration yields to that on small screens.

## Checks

### Requirements (WCAG 2.2, Level AA)
- Text can be resized to 200% without loss of content or function (1.4.4).
- Content reflows at 320 CSS pixels wide with no horizontal scrolling (1.4.10).
- Nothing breaks when a user sets line height to 1.5, paragraph spacing to 2 times the font size, letter spacing to 0.12 and word spacing to 0.16 times the font size (1.4.12).
- Pointer targets are at least 24 by 24 CSS pixels, or have equivalent spacing (2.5.8).
- Text contrast is at least 4.5:1, or 3:1 for large text (1.4.3). Detail: `core/accessibility`.

### Body text
- Running text is at least 16px. Smaller sizes are for captions, footnotes and dense interface labels.
- No text a visitor is expected to read is below 12px.
- Form inputs are at least 16px on phones; smaller inputs make iOS Safari zoom the page on focus.
- Sizes are set in relative units so the visitor's browser setting is respected.

### Line length and spacing
- Paragraphs run about 50 to 75 characters per line; up to 90 is tolerable, over 100 tires readers. Constrain the text column (`max-width` near `70ch`), not the whole page.
- Marketing copy in narrow columns is often shorter than this; that is fine above roughly 30 characters. On phones, 30 to 45 characters is normal.
- Body line height is about 1.5; headings sit between 1.0 and 1.35 and tighten as they grow.
- Paragraphs are separated by 0.5 to 1.5 times the font size. The space above a heading is clearly larger than the space below it.
- Text is not justified. Long passages are not centered.

### Type scale and hierarchy
- A small set of sizes is used consistently: commonly five to seven steps from caption to display.
- Each level is distinguishable from the next by size, weight or color; two levels that differ by a pixel or two read as a mistake.
- The page has one main headline, and it is the largest text on the first screen.
- Headings step down on small screens: a headline that works at 64px on a desktop usually needs to be 32 to 42px on a phone to avoid one-word lines.
- Headline length suits its size: at display sizes, about a dozen words or fewer.
- Uppercase, light weights and tight letter-spacing are kept to short text at sizes where they stay legible.

### Header
- The header is as short as its content allows while keeping readable text and comfortable targets.
- A sticky header takes a small share of the screen: on a phone held upright, roughly a tenth of the height or less. Check landscape and 400% zoom, where a sticky header can cover most of the view.
- Promotional bars, cookie notices and app banners count toward that height when they stack with the header.
- A sticky header has an opaque background, does not hide focused elements or in-page anchors (`scroll-padding-top`), and does not animate distractingly.
- If a header does not fit in one row on a phone, something moves into the menu; it does not wrap into a second row. Where no menu exists (adding one is functional work), tighten spacing first; a non-sticky header may wrap as a last resort to avoid horizontal scrolling, and the missing menu is reported.

### First screen and hero
- At both phone and desktop sizes the first screen shows: what is offered, in plain words; the primary action; and a sign that the page continues.
- The primary action appears once on the first screen, with at most one quieter alternative beside it.
- Images, illustrations and video in the hero do not push the headline or the action off the first screen on a phone.
- A hero does not fill the screen so exactly that the page looks finished; part of the next section, or a clear cue, is visible.
- Auto-rotating carousels do not carry the main message.
- Banners and announcement bars state one thing, can be dismissed when they are not essential, and do not shift the layout when they load.

### Buttons and targets
- Primary buttons are comfortably larger than the 24px requirement: 44 to 48px high on touch screens is the platform guidance.
- Button text is the body size or close to it, and the label fits on one line at phone width.
- The primary button is visibly dominant; secondary actions are quieter; no two different actions look equally primary in one view.
- Adjacent targets have space between them; text links inside dense lists are not the only way to act.

### Observed practice
What 28 established commercial sites shipped in October 2026 (SURVEY-01 in the source index). Use these to notice an outlier, not as targets.

| Measure | Desktop, 1440 wide | Phone, 390 wide |
|---|---|---|
| Body text size | 14 to 20px, most often 16 to 18 | 12.5 to 18px, most often 14 to 16 |
| Body line height | 1.4 to 1.75, typically 1.5 | the same |
| Characters per line in marketing copy | typically 35 to 65 | typically 30 to 40 |
| Main headline on marketing pages | 32 to 128px, middle half 48 to 80, median 64 | 27 to 56px, middle half 32 to 42, median 38 |
| Headline line height | 0.95 to 1.25 | 1.0 to 1.25 |
| Headline length | 1 to 16 words, median 6 | the same |
| Section headings | typically 40 to 64px | typically 24 to 36px |
| Header height, single bar | 52 to 96px, median 72 | 48 to 80px, median 64 |
| Header stays visible on scroll | about two thirds of sites | about half |
| Primary button height | 33 to 60px, median about 52 | 33 to 60px, median about 46 |
| Primary button text | 14 to 18px, most often 16 | the same |
| Primary button on the first screen | every marketing page measured | every marketing page measured |
| Actions in the hero | one or two | one or two, often stacked full width |
| Page length | 5 to 20 screens, median about 9 | 5 to 37 screens, median about 12 |

Store home pages are a different pattern: their main heading is small (20 to 28px) because products and navigation lead. Headers with stacked promotional bars reached 100 to 180px on phones; treat that as a problem to report, not a precedent.

## Anti-patterns

- Body text at 12 or 13px on a public page; gray text on gray.
- Lines that span the full width of a wide screen.
- A phone headline at desktop size, breaking into one word per line.
- Six heading sizes within a few pixels of each other.
- A sticky header, a promo bar and a cookie bar together covering a third of a phone screen.
- A two-row sticky header on a phone.
- A hero image that fills the first phone screen with the headline below it.
- The same primary button twice on one screen.
- A full-height hero with no hint that anything follows.
- Buttons 30px high on a touch screen; links as the only targets in a tight list.
- Resizing type to match a competitor.

## Exceptions and context

- **Dense applications** (admin, dashboards, tables, monitoring) legitimately use 13 to 14px interface text and compact controls for expert, desktop users. Apply the requirements only.
- **Editorial and long-form reading** benefits from larger body text (18 to 21px) and a strict measure.
- **Display-led brands** use very large or very small headline type on purpose. Preserve it; check only legibility, wrapping and the first-screen job.
- **Non-Latin scripts** differ: Arabic, CJK and Indic text often need larger sizes and more line height than Latin at the same nominal size, and character counts per line do not transfer. See `patterns/rtl-bilingual`.
- **Older or low-vision audiences** warrant larger defaults.
- **Legal and regulatory text** may have minimum sizes set by rule.

## Implementation cautions

- Type scale, weights, spacing scale and header design are brand assets. Use the project's tokens; add a step beside the existing ones only as a flagged change, as described in `core/brand-preservation`.
- Fix failures of a requirement or of reading comfort. Report differences from observed practice as observations (P3) unless they cause a concrete problem.
- A size change in a shared token or component affects every place it is used. Check them all, including areas outside the scope.
- Changing header height or stickiness changes anchor offsets, focus visibility and any script that measures the header. Re-test in-page links and the open menu.
- After moving or resizing anything on the first screen, re-capture phone and desktop and confirm the primary action appears once.
- Never state a size as "what converts best". No source in this index supports that for a specific pixel value.

## Sources

- [W3C-01] WCAG 2.2: 1.4.3, 1.4.4, 1.4.10, 1.4.12; [W3C-03] target size; [W3C-23] visual presentation (AAA, as a recommendation)
- [USWDS-01] Body size, measure, line height and spacing
- [GOV-08] A public-service type scale and its small-screen steps
- [BAY-14] Line length research
- [WEB-09] The 12px legibility floor
- [APL-03], [MAT-02] Platform type scales (could not be machine-read; cited from established knowledge)
- [NNG-20] Touch target size; [NNG-32] sticky headers
- [NNG-48] Attention above and below the fold; [BAY-17] homepage carousels

The "Observed practice" table is this skill's own measurement (SURVEY-01), with the limits recorded in the source index. The header share of a tenth of the screen, the first-screen job and the once-per-screen rule for the primary action are this skill's judgment, informed by those measurements.
