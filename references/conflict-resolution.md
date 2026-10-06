# Conflict resolution

Rules collide because surfaces differ. Read this when two modules, or a module and the existing design, point in different directions.

## Order of precedence

Work down the list and stop at the first level that settles it.

1. **Hard limits.** Protected functionality, nothing fake, no deception, no exposed secrets. The user can widen the functionality limit by explicitly authorizing functional work or a rebrand. Nothing widens the honesty limits.
2. **Accessibility requirements.** WCAG 2.2 Level A and AA success criteria. A visual or brand preference never outranks one; find a design that satisfies both.
3. **The surface's primary task.** The rule from the surface's own profile beats a generic default, because it was written for that task.
4. **Error prevention and recovery,** weighted by the consequence of a mistake on that surface.
5. **Efficiency for the people who use it most.**
6. **Brand expression.**
7. **Consistency with the project's existing patterns.** Prefer the project's established way over an outside convention unless the established way causes a problem at levels 1–5.
8. **Aesthetic preference.** Never a finding on its own.

When a conflict is settled by judgment rather than by this list, say so in the finding.

## Recurring conflicts

### Marketing whitespace versus operational density
Promotional surfaces benefit from generous spacing because the task is to take in one message at a time. Admin tables and dashboards need compact density because the task is to compare many values. Apply density per surface. A shared spacing token set can serve both through different component sizes; one global "comfortable" setting cannot.

### Progressive disclosure versus discoverability
Hide what is rare; show what is frequent. Use real usage where it is known, otherwise the task analysis from the audit. Anything needed in most sessions stays visible. Never bury the only path to a function behind hover, a long-press or an unlabeled icon. More than two levels of disclosure is usually a sign the grouping is wrong.

### Minimalism versus technical completeness
"Aesthetic and minimalist design" means removing what is irrelevant to the user, not what is unfamiliar to the designer. In expert tools, timestamps, identifiers, units, raw values and diagnostic detail are the content. Reduce noise by grouping, alignment and hierarchy before removing information.

### Mobile cards versus tabular comparison
Turn rows into cards only when users read one record at a time. When they compare across rows, keep the table: freeze the identifying column, prioritize columns, allow horizontal scroll inside the table region with a visible cue. WCAG reflow explicitly allows two-dimensional scrolling for data tables.

### Brand accent versus contrast
Keep the brand token. Change where and how it is used first: larger text, fills, borders and icons instead of small body text; a different background pairing; an added non-color cue. Introduce a derived accessible shade only when usage changes cannot work, and flag it for the brand owner. See [core/brand-preservation.md](core/brand-preservation.md).

### Visual effects versus readability and performance
Glass, blur, gradients and shadows that belong to the identity stay where they are legible and cheap. Reduce or replace them only on the specific elements where text contrast fails or interaction lags, such as text over a blurred hero or a blurred sticky header on low-end phones.

### Animation versus performance and reduced motion
Keep motion that explains a change of state or location. Remove motion that only decorates when it costs responsiveness. Honor `prefers-reduced-motion` by replacing movement with an instant change or a short fade, not by removing the feedback itself.

### Conversion versus accessibility and trust
Never raise conversion by removing information users need (full price, fees, policies), by blocking exits, or by manufacturing urgency. When a growth pattern and an honest pattern compete, the honest one wins and the trade-off is reported, not hidden.

### Inline validation versus validate-on-submit
Sources genuinely differ: ecommerce research supports validating a field when the user leaves it; GOV.UK validates on submit unless research shows a benefit. They agree on what matters: never show an error while the user is still typing a first attempt, always validate on submit, and clear an error as soon as it is fixed. Keep the project's existing timing unless it is premature or missing.

### Marking required versus marking optional
One body of guidance marks only optional fields; another marks both. Either works if it is explicit, consistent across the product and not conveyed by color or an unexplained asterisk alone. Keep the project's convention; fix it only where it is ambiguous.

### Confirmation versus flow
Confirmations protect only when rare. For reversible actions prefer undo. Reserve confirmation dialogs for serious, hard-to-reverse actions, and make them specific. On high-stakes surfaces the balance shifts toward review and confirmation.

### Dense interfaces versus target size
The 24 by 24 CSS pixel minimum (or equivalent spacing) still applies in compact tables and toolbars, and it is compatible with dense rows. Larger targets are a recommendation for primary touch controls, not a reason to inflate a desktop admin tool.

### Sticky elements versus visible focus and small screens
Sticky headers and bottom action bars help reach. They must not hide the focused element, cover form fields when the keyboard opens, or take so much height that content becomes a slot between two bars. Shrink or un-stick before removing the action.

### Consistency versus a better local pattern
A locally better pattern used once is an inconsistency. Either adopt it everywhere the same situation occurs or keep the existing one. Recommend the system-wide change; do not create a one-off.

### Novice clarity versus expert speed
Do not choose. Keep the visible, labeled path for new users and add accelerators for frequent ones: shortcuts, bulk actions, saved views, sensible defaults. Remove a guided path only when evidence shows nobody uses it.

### Profile rule versus universal rule
A profile may strengthen, weaken or reinterpret a universal rule for its context, and then the profile wins. A profile never overrides an accessibility requirement or a hard limit.

### Two profiles on one surface
Use the primary profile for structure and priority, the secondary for domain details. If they give opposite advice about the same element, the surface probably needs splitting; see [classification.md](classification.md#route-level-classification).

### The user's instruction versus a rule
The user decides. Apply their instruction, and if it conflicts with an accessibility requirement or creates a real risk, say so once, clearly, and continue with what they asked. The exceptions are the honesty limits in level 1.
