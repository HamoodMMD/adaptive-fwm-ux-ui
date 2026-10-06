# Brand preservation

The existing identity is a constraint to work within, not a draft to improve.

**Load when:** always, before recommending or making any visual change.

## Objectives

After the work, the product is easier to use and still unmistakably itself. Two different businesses audited with this skill should come out looking as different from each other as they went in.

## Priority principles

1. **Inventory before opinion.** Know what the brand is before judging anything visual.
2. **Separate identity from execution.** The brand's purple is identity. Purple used for 12 px body text on a lilac background is execution. Fix execution.
3. **Change usage before changing the element.** Almost every usability conflict with a brand can be solved without touching the brand element itself.
4. **No house style.** This skill has no preferred radius, font, palette, card, navbar or layout. Model-default aesthetics are not improvements.
5. **Brand changes are the owner's decision.** Propose; never apply silently.

## Checks

### Inventory
Record what exists, with the file it comes from. Sources: brand or style documentation, design tokens, CSS custom properties, theme files, Tailwind or equivalent config, component library theme, font files and font loading, logo assets, image directories, Storybook or equivalent.

| Element | What to record |
|---|---|
| Logo | Variants, minimum size and clear space if documented, where it appears, backgrounds it sits on |
| Color | Primary, secondary and accent values; neutrals; semantic colors (success, warning, error, info); how each is used |
| Typography | Families (per script if multilingual), weights, the size scale, line heights, heading treatment |
| Spacing | The scale and base unit; section and component rhythm |
| Shape | Corner radius values and where each applies; border weights |
| Elevation | Shadow or layering system; blur, glass or gradient treatments |
| Motion | Durations, easing, what moves and why |
| Imagery | Photography or illustration style, crops, treatment, iconography set |
| Components | Library in use; custom components; button, input and card variants |
| Modes | Light, dark, high-contrast; how they are switched |
| Voice | Tone of headings, buttons and messages |

Then note **coherence**: where the system is applied consistently, and where it has drifted (five grays that should be two, three button radii, off-scale spacing). Drift is fair to fix toward the system's own dominant values. That is consolidation, not redesign.

### Classifying a visual problem
Before recommending a visual change, decide which it is:

- **Usability or accessibility defect** — unreadable text, an indistinguishable state, a target too small, focus invisible. Fix it, by the ladder below.
- **Inconsistency with the brand's own system** — off-token values, mixed radii. Align to the system.
- **Preference** — "this would look more modern". Not a finding. Leave it.

### The fix ladder
When a brand element causes a usability problem, climb only as far as needed:

1. **Change where it is used.** Keep the brand color for large text, fills, borders, icons and accents; stop using it for small body text or thin lines where it fails.
2. **Change what it is paired with.** A different existing background or foreground token from the same palette.
3. **Add a second cue.** An icon, underline, weight, border or label so color is no longer carrying the meaning alone.
4. **Adjust the treatment, not the element.** Lower blur behind text, add a scrim under text on imagery, increase weight or size, thicken a border.
5. **Add a derived variant.** A darker or lighter step of the same hue for text or borders, added alongside the original token and named in the system's convention. Flag it for the brand owner.
6. **Recommend changing the base element.** Report only. Never implement without explicit approval.

Worked examples:

| Situation | Preserve | Change |
|---|---|---|
| Brand purple fails contrast as small text on white | The purple, everywhere it works: buttons, headings, large text, accents | Use the neutral text color for body copy; purple for links only with an underline; or add a darker text step of the same hue |
| Glass panels are part of the identity, but a pricing table on glass is hard to read | Glass on navigation, cards, hero | Raise the panel's opacity or lower blur behind the table; give dense text a solid surface inside the glass frame |
| Thin elegant typeface is the brand voice, but fails at small sizes | The typeface for headings and display | Heavier weight or a paired text face from the same family for small UI text; minimum size raised |
| Pale gold accent used for the focus ring is invisible | Gold as an accent | Focus ring in a high-contrast neutral with a gold inner or offset ring |
| Signature long animations delay every interaction | The motion language for page-level moments | Shorter durations for frequent interactions; reduced-motion variant |
| Luxury layout with very low density hides the size selector below the fold on mobile | The spacious feel | Reorder and tighten that one region so the purchase controls are reachable |
| Dark neon theme has insufficient contrast for disabled and secondary text | The theme and palette | Raise secondary text one step within the existing gray scale |

### Things not to do to a brand
Do not convert a project toward any of these unless the user asks for that specific outcome:

- Generic SaaS styling: blue primary, gray cards, rounded-lg everything.
- Framework defaults: stock Tailwind, Bootstrap or Material look in place of custom components.
- A platform's native look on a product that has its own.
- Trend treatments: glassmorphism, neon, gradients, bento grids, oversized type, where they are not already the identity.
- Minimal white interfaces replacing a rich or dark identity, or the reverse.
- A different icon set, typeface or illustration style because it is "cleaner".

Equally, do not strip an identity element because it is unfashionable. Preserve it where it is usable.

### When there is no coherent system
If the project has no tokens, no consistent scale and no documented identity:

1. Say so in the brand assessment, with evidence.
2. Derive working values from what is already most common in the code (the dominant colors, sizes and radii) and use those.
3. Do not introduce a new visual language. Creating a design system is separate work that needs the user's explicit request.

### Light, dark and themed modes
- Audit each mode the project supports; a fix in one mode must not break another.
- Use semantic tokens where they exist instead of hard-coded values, so modes stay in sync.
- Do not add a mode that does not exist.

### Per-surface variation
One brand can legitimately be spacious on its marketing pages and compact in its admin tool. Preserve the identity (color, type, shape, voice) across surfaces and let density and emphasis follow each surface's task.

## Anti-patterns

- Replacing custom components with a component library's defaults "for consistency".
- Swapping the brand font for a system font to "improve performance" without being asked.
- Normalizing every radius, shadow and spacing value to a new scale of your own.
- Changing a brand color's hex value to pass contrast when changing its usage would have worked.
- Removing gradients, textures, illustrations or motion that are part of the identity.
- Recoloring the logo or placing it on a new background.
- Rewriting the brand's voice into neutral corporate copy.
- Introducing a second accent color.

## Exceptions and context

- **The user asks for a rebrand, restyle or new design system.** Then this module becomes the baseline to depart from deliberately; still record the inventory first.
- **An accessibility requirement cannot be met by any step short of changing the element.** Report it, with the evidence and the smallest change that would work, and let the owner decide.
- **Legacy drift.** Old pages that predate the current system can be aligned to the current system; confirm which one is current.
- **Third-party embeds** (payment fields, maps, chat) may not be restylable; note it and move on.
- **Logos are exempt** from the WCAG contrast requirements; do not recommend altering a logo on contrast grounds. Recommend a different placement or background treatment if it is illegible.

## Implementation cautions

- Edit token *usage* in components freely; edit token *values* only on rungs 5–6 of the ladder and with the caveats above.
- Add derived tokens beside the originals, following the project's naming, in every theme file where the original is defined.
- Search for every use of a value before changing it; shared tokens affect surfaces you were not asked to audit.
- Do not add dependencies (fonts, icon sets, UI kits) for visual reasons.
- In the report, the `BRAND` section lists what was preserved, what was aligned to the existing system, any derived variants added, and any base-element changes recommended for the owner's decision.

## Sources

- [W3C-01] WCAG 2.2 — contrast thresholds and the logotype exemption
- [W3C-07] Understanding non-text contrast — brand-mandated logo treatment versus author-chosen low contrast
- [NNG-11] Design quality and consistency as credibility factors
- [STAN-01] Professional, purpose-appropriate design as a credibility guideline
- [NNG-32] Opaque versus translucent sticky surfaces and legibility
- [WEB-05] Cost of visual effects and animation

The fix ladder and the prohibition on house style are this skill's own policy (evidence class: Judgment), derived from the requirement to preserve identity.
