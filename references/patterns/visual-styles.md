# Expressive visual styles and effects

Distinctive styles and effects that give a product its character: particles, liquid morphing, neon glow, Y2K chrome, kinetic type, paper cutout, holographic foil, isometric scenes, ASCII art, clay 3D, retro VHS, comic book, split-flap displays, hand-drawn, blueprint, physics, pixel art, Bauhaus, Art Deco, neo-brutalism, glassmorphism and others. None of them is wrong. Each one fails in its own predictable ways, and this module names those failures so the style can be kept while the problems are fixed.

**Load when:** the surface uses, or a build plan asks for, a named visual style or a decorative effect: animated backgrounds, canvas or WebGL scenes, text effects, textures, glows, retro or illustrated looks, 3D, or a strongly stylized brand.
**Skip when:** the interface is plainly styled and nobody asked about style.
**Pair with (when present):** `patterns/motion` (anything that moves), `core/brand-preservation`, `core/accessibility`, `core/performance`, `patterns/visual-scale`, `patterns/dark-mode-and-themes`.

## Objectives

The style carries the brand and the mood. People still read every word, find every control, finish every task, and are never harmed or slowed by the effect. The style lives mainly on surfaces that set the mood (heroes, headings, illustrations, empty states, transitions between sections), and task areas stay calm and conventional.

## Priority principles

1. **The style is part of the brand.** Keep it. Fix contrast, legibility, motion and performance inside the style before suggesting a plainer one.
2. **Style the surface, not the task.** A stylized look is safest in visual design; navigation, forms, checkout and data stay conventional underneath. Antidesign that makes tasks harder backfires except in entertainment or for audiences of designers.
3. **Text stays text.** Effects are applied to live text with CSS where possible, so it can be read aloud, translated, zoomed and selected. Images of text are for logos only.
4. **Decoration is invisible to assistive technology; meaning is not.** Purely decorative layers are hidden from screen readers; anything that carries meaning has a text equivalent.
5. **Attractive is not the same as usable.** People rate good-looking interfaces as easier to use even when they struggled, so test tasks, not impressions.

## Checks

### For every style

- **Contrast:** text meets 4.5:1 (3:1 for large text) and controls and focus indicators meet 3:1 against the actual pixels behind them, including over gradients, textures, glows, video and moving backgrounds. Check the worst point, not the average.
- **Controls look like controls:** buttons, links and inputs have clear signifiers in the style's own language (a border, a fill, an underline, a shadow).
- **Live text:** headings and copy are real text; letters are not split into separately animated elements that screen readers read one by one or skip. Where text must be split, test with real screen readers.
- **Decoration hidden:** canvases, background animations, ornaments and ASCII drawings that carry no meaning are hidden from assistive technology (`aria-hidden="true"`, empty `alt`); meaningful ones get a text alternative.
- **Motion:** everything in `patterns/motion` applies: a purpose, a pause control for anything that moves by itself for more than five seconds, and a still or simple version under reduced motion.
- **Flashing:** nothing flashes more than three times a second, including glitch, flicker, strobe and VHS effects; saturated red flashes are the strictest case.
- **Performance:** effects run smoothly on a mid-range phone, pause when off-screen or when the tab is hidden, do not delay the main content, and are lighter or still on low-power devices.
- **Zoom and reflow:** the style survives 200% zoom and a 320 px wide screen without text being cut, overlapping or hidden behind decoration.
- **User settings:** where the platform offers increased contrast, reduced transparency or forced colors (Windows high contrast), the interface stays usable with them on.

### Style by style

| Style | Fits best | Typical failures to check |
|---|---|---|
| **Particles** (dust, sparks, stars, confetti) | Heroes, celebrations, games | Constant movement behind text; battery and CPU drain; no pause; particles crossing text and lowering contrast. Keep counts modest, pause off-screen and when the tab is hidden, stop under reduced motion |
| **Liquid morph** (blobs, metaballs, morphing shapes) | Heroes, transitions, music and creative brands | Large shapes moving behind text; morphing too slowly to feel responsive; heavy shaders. A still frame under reduced motion |
| **Neon glow** | Nightlife, gaming, entertainment, dark brands | Glow blurring letter edges at small sizes; saturated colors that vibrate on dark backgrounds; glow counted as contrast when the core text color fails. Use glow on large display text; body text stays crisp |
| **Y2K chrome** (metallic gradients, bubbly type, gloss) | Fashion, music, youth brands | Metallic gradients with light and dark bands so the same text passes in one spot and fails in another; reflective buttons whose label contrast varies |
| **Kinetic type** (moving, scaling, scrolling words) | Headlines, launches, storytelling | Words that cannot be read while moving; text revealed letter by letter that screen readers miss; meaning that depends on timing. The final, still state is readable and present in the markup from the start |
| **Paper cutout / layered paper** | Children, education, craft, food, illustration-led brands | Shadows creating fake depth on non-interactive pieces so they look clickable; textured backgrounds behind text |
| **Holographic / iridescent foil** | Fashion, beauty, collectibles, crypto | Shifting rainbow gradients behind text; color-only states lost in the shimmer; motion tied to pointer or device tilt with no still option |
| **Isometric illustration** | Technology, explainers, games, maps | Detailed scenes that carry information with no text equivalent; small labels inside the drawing; heavy images on mobile |
| **ASCII art** | Developer tools, retro, terminal brands | Screen readers reading every character. Mark the drawing as an image with a text description (`role="img"` and a label) or hide it if decorative; a fixed-width drawing that overflows small screens |
| **Clay 3D** (soft rendered 3D objects) | Friendly consumer apps, onboarding, empty states | Heavy images or WebGL slowing the first screen; soft low-contrast shading used for controls; 3D objects that look tappable but are not |
| **Retro VHS / CRT** (scan lines, noise, chromatic shift) | Music, film, gaming, nostalgia brands | Flicker and rolling bars that flash; scan lines and noise over text; color-shifted text that doubles letter edges. Keep effects off body text and under the flash thresholds |
| **Comic book** (panels, halftones, speech bubbles, bold outlines) | Entertainment, children, playful brands | Hand-lettered all-caps faces used for long text; halftone dots behind text; reading order across panels that differs from the code order |
| **Split-flap display** (flipping letters, departure boards) | Travel, counters, launches, data headlines | Each flip announced to screen readers; the final value appearing late; constant flipping. Announce only the final value, if at all, and keep the flips short |
| **Hand-drawn / sketch** | Personal brands, education, creative tools, wireframe looks | Hand-drawn icons that are hard to recognize; scribbled underlines read as links; handwriting faces for long text or small sizes |
| **Blueprint / technical drawing** | Engineering, architecture, developer and hardware products | Thin light lines and small labels on blue failing contrast; grids behind text; monospace at small sizes |
| **Physics** (draggable, falling, bouncing objects, gravity) | Playful heroes, games, portfolios | Content that must be chased or dragged to read; no keyboard equivalent for drag; motion that never settles. The content is readable without interacting with the simulation |
| **Pixel art** | Games, retro, indie brands | Sprites blurred when scaled (scale by whole multiples with `image-rendering: pixelated`); pixel fonts used at sizes where letters are ambiguous; pixel fonts for body text |
| **Bauhaus** (primary colors, geometric shapes, strict grids) | Culture, design, education, architecture | Geometric shapes overlapping text; primary yellow with white text failing contrast; decorative shapes read as buttons |
| **Art Deco** (ornament, gold, condensed display type) | Hospitality, luxury, events, drinks | Thin, condensed or high-contrast display faces at small sizes; gold on cream or black failing contrast; ornament crowding the content |
| **Neo-brutalism** (thick borders, hard shadows, flat bright colors, raw type) | Startups, creative tools, youth products | Hard shadows on non-interactive cards that look like buttons; very bright color fields tiring on long pages; raw layouts that break the reading order. Keep navigation and task flows conventional |
| **Brutalism / antidesign** | Art, fashion, designer audiences, entertainment | Deliberately hard navigation; hidden controls; unusual scrolling. Acceptable only where the audience accepts the challenge and no essential task depends on it |
| **Glassmorphism** (frosted translucent panels) | Overlays, media apps, operating-system-like interfaces | Text over changing or busy backgrounds; too little blur. Use more blur on busy backgrounds, plan for the worst background, honor reduced transparency, use sparingly |
| **Neumorphism** (soft extruded surfaces) | Small control panels, decorative cards | Very low contrast between control and background; pressed and unpressed states that look alike. Controls need borders or contrast that meet 3:1 |
| **Skeuomorphism** (real-world materials and objects) | Audio and music tools, games, learning | Metaphors that confuse (tilt or drag actions with unclear results); clutter and weight. Use a metaphor only where it explains the function |
| **Flat / minimal** | Most products | Weak signifiers: links and buttons that look like plain text or plain boxes. Add just enough depth, borders or underlines to show what is clickable |
| **Aurora and mesh gradients, grain, noise** | Technology and SaaS heroes | Text over the brightest or busiest part of the gradient; animated gradients behind body text; grain lowering effective contrast |
| **Glitch** | Gaming, music, technology launches | Flashing and rapid shifts beyond three per second; glitched text that is unreadable or announced as nonsense. Glitch decorative layers only, briefly |
| **Typewriter / terminal reveal** | Developer tools, AI products, storytelling | Text that takes seconds to appear; screen readers announcing each character; a cursor that blinks forever. Show the full text at once under reduced motion |
| **Marquee / ticker** | News, announcements, fashion | Text moving too fast to read; no pause (2.2.2); important information only in the moving strip |
| **Cursor effects** (custom cursors, trails, magnetic buttons) | Portfolios, agencies, creative brands | The real pointer position unclear; effects that do nothing on touch screens or with a keyboard; magnetic buttons that move away from the pointer |
| **3D and WebGL scenes, scroll storytelling** | Product reveals, launches, storytelling | A blank or frozen first screen while the scene loads; scroll-jacking; content only inside the canvas. Provide the content as HTML and a still fallback |
| **Memphis, vaporwave, cyberpunk, maximalism** | Youth, music, gaming, events | Clashing patterns behind text; neon colors failing contrast; too many competing focal points. Keep one focal point per screen |
| **Swiss / International** (grids, sans-serif, asymmetric layouts) | Corporate, culture, editorial | Usually low risk; check that large type and asymmetry keep a clear reading order and that thin weights stay legible |
| **Bento grid** (card mosaics) | Feature overviews, dashboards, portfolios | Unclear reading order across tiles; tiles that look clickable but are not; layout that collapses badly on phones |
| **Dithering, duotone and halftone images** | Editorial, music, retro brands | Product images that no longer show the real product, color or detail; text placed over the pattern |

## Anti-patterns

- Replacing a stylized brand with a generic look to fix one contrast failure.
- Body text set in a display, pixel, handwriting or Art Deco face.
- Splitting headline letters into separate animated elements without testing screen readers.
- A canvas of particles or a WebGL scene running at full speed behind a form.
- A glitch or VHS effect that flickers over the whole screen.
- Decorative shapes with shadows and borders that look exactly like the buttons.
- An ASCII banner read aloud character by character.
- A style chosen because the team is bored, on a product people use to get work done.

## Exceptions and context

- **Entertainment, games, art and fashion** can carry much more style, and some friction is part of the experience. Purchase, sign-in, settings and support still follow normal rules.
- **Logos and brand marks** may use any effect, including images of text.
- **Short launch moments** (a hero, an intro, a celebration) can be richer than the screens people use every day.
- **Data, finance, health, government and admin tools** keep expressive styles to marketing and empty or celebration states.

## Implementation cautions

- Safe UI work: raising contrast within the style (a darker overlay, a solid backing behind text, a stronger core color under a glow), hiding decorative layers from assistive technology, adding text alternatives, adding reduced-motion and reduced-transparency versions, pausing effects off-screen, lowering particle counts, scaling pixel art by whole multiples, replacing split letters with whole-word or whole-line animation.
- Functional work, recommend only: removing a signature effect, replacing a WebGL scene, changing the brand typeface or palette, rebuilding a page in a different style.
- When building something new in a chosen style, decide where the style lives (hero, headings, illustrations, transitions) and where it does not (forms, tables, navigation, checkout) before building.

## Sources

- [NNG-104] Brutalism belongs in visual design; antidesign backfires outside entertainment and designer audiences; [NNG-50] the aesthetic-usability effect masks problems in testing
- [NNG-105] Glassmorphism: blur, busy backgrounds, contrast, user settings, sparing use; [NNG-106] flat design and weak signifiers; [NNG-107] skeuomorphism: metaphors that clarify, clutter, confusing gestures
- [W3C-35] Text alternatives for ASCII art; [W3C-36] images of text and the logotype exception; [W3C-37] three flashes, red flashes and area thresholds; [W3C-33] animation from interactions; [W3C-34] pause, stop, hide
- [WEB-18] Splitting words into letters fails with most screen readers
- [SF-01] Motion accessibility in a design system: vestibular harm, a site-wide setting for non-essential animation, no loops without control
- [MDN-03] Reduced transparency setting; [MDN-04] scaling pixel art; [MDN-05] pausing work when the page is hidden; [WEB-19] canvas performance for particle effects

The style table is this skill's synthesis: each failure follows from the cited requirements and research applied to that style (evidence class: Judgment).
