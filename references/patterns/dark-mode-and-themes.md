# Dark mode and themes

Light and dark appearances, theme switchers, dark-only brands and high-contrast settings. A dark theme is not an inverted light theme: it has its own surfaces, colors and contrast problems, and every screen has to work in each theme the product offers.

**Load when:** the surface has a dark theme, a theme switcher, follows the system appearance, or is dark by design; or the user asks about dark mode.
**Skip when:** the product offers one light appearance and nobody asked about themes.
**Pair with (when present):** `core/accessibility` (contrast), `core/brand-preservation`, `patterns/visual-scale` (contrast and dark surfaces), `patterns/charts-data-viz`, `patterns/component-libraries`.

## Objectives

Each person sees the appearance they chose, from the first frame, on every screen. Text, controls, focus indicators, charts and images keep their contrast and meaning in every theme. Switching is easy to find on the web, remembered, and never fights the system setting.

## Priority principles

1. **Follow the system setting by default.** People set their appearance once for the whole device and expect every product to respect it.
2. **Every theme meets the same contrast rules.** A dark theme is not exempt from 4.5:1 for text and 3:1 for controls and focus.
3. **Design the dark palette; do not invert.** Dark surfaces, lighter and less saturated accents, and different ways of showing depth.
4. **Light is the safer default for reading.** For people with typical vision, dark text on a light background performed better in reading and proofreading studies, and the gap grows as text gets smaller. Offer dark as an option rather than forcing it, unless the brand or the use is dark by design.
5. **The theme is part of the brand.** A dark-only brand is preserved; only legibility problems are fixed.

## Checks

### Choosing and switching
- Without a saved choice, the product follows the system appearance (`prefers-color-scheme` on the web, the system appearance in native apps).
- **Websites and web apps** may add their own switcher. When they do, it offers Light, Dark and System (or Automatic), shows the current state, is reachable from every page (usually in the header, footer or settings), and the choice is remembered across visits and, for signed-in users, across devices where the product supports it.
- **Native apps** generally do not add their own appearance setting: Apple advises against it because people then have to change two settings and may think the app is broken. A reading, media or editing app may still offer a reading theme for its content.
- The right theme shows from the first frame. A flash of light before dark (or the reverse) on load is a defect; on the web, `<meta name="color-scheme" content="light dark">` and a theme applied before first paint prevent it.

### Surfaces and color
- Dark surfaces are dark gray rather than pure black (Material uses #121212 as a base), with off-white rather than pure white text for long reading, because full contrast causes glare and smearing for some readers.
- Depth is shown with lighter surfaces for higher layers, not shadows alone, because shadows disappear on dark backgrounds.
- Accent and brand colors use lighter, less saturated variants in dark mode; saturated colors appear to vibrate against dark gray and often fail contrast as text.
- Semantic colors keep their meaning in every theme: error, warning, success and selected states stay distinguishable, still with an icon or a word as well as color.
- Colors are defined as named tokens with a value per theme, not hard-coded, so nothing stays light inside a dark screen.
- Browser-drawn parts follow the theme: `color-scheme` makes form controls, scrollbars and the page canvas match.

### Contrast and legibility in every theme
- Text, icons, borders of inputs, focus indicators and chart lines are checked in each theme separately. Secondary and disabled text and thin borders fail in dark mode most often.
- Small and light-weight text is the first thing to check on a dark surface.
- With the system's increased-contrast or reduced-transparency settings on, text stays readable.

### Images, logos, charts and embeds
- Logos and illustrations have a variant for dark backgrounds where the light one disappears (dark text in a logo, transparent images with dark lines).
- Images with white backgrounds are dimmed slightly or framed so they do not glow on a dark page.
- Charts have a dark palette that still separates series and meets the contrast rules (`patterns/charts-data-viz`).
- Embedded content (maps, videos, payment fields, third-party widgets) is checked: a white block inside a dark page is a finding when it can be themed.
- Emails and documents sent from the product look right in both modes of mail clients that darken them.

## Anti-patterns

- A dark theme made by inverting colors, so photos, brand colors and status colors invert too.
- Gray secondary text that passes in light mode and fails in dark mode.
- A switcher with only Light and Dark, so the user can never go back to following the system.
- A white flash on every page load in dark mode.
- A logo that disappears on the dark background.
- A modal, menu or dropdown left in the light theme.
- Saturated brand blue used for text links on near-black.

## Exceptions and context

- **Dark by design:** media viewers, games, creative tools, some monitoring screens and brands built on darkness may be dark-only. Preserve it; check contrast and small text.
- **Long reading** (news, documentation, books): offering a dark or sepia reading theme is recommended; the default stays light unless the brand says otherwise.
- **Low vision:** some people, for example with cataracts, read better on dark backgrounds, so offering dark is an accessibility benefit, not only a preference.
- **Regulated and printed outputs** (invoices, statements, certificates) print in a light theme whatever the screen uses.

## Implementation cautions

- Safe UI work: adding a missing dark variant to a token that already has a light value, fixing contrast of a token in one theme, adding `color-scheme`, swapping in a dark logo asset the brand already has, dimming images.
- Functional work, recommend only: adding a dark theme where none exists, adding a theme switcher, storing the choice on the server, theming third-party embeds.
- Never change the brand's light palette while fixing the dark one; record each token changed and its before and after contrast.

## Sources

- [NNG-95] Light mode performs better for most readers; offer dark as an option
- [APL-04] Follow the system appearance; avoid an app-specific setting; contrast 4.5:1 minimum and 7:1 for small custom text; test with increased contrast
- [MAT-03] Dark gray base surface, lighter overlays for elevation, lighter and less saturated colors, no pure white text
- [WEB-17] prefers-color-scheme, an override that includes the system setting, saved choice, no flash, dimmed images
- [MDN-02] color-scheme for browser-drawn controls, and the meta tag that prevents a flash
- [W3C-01] Contrast requirements apply in every theme
