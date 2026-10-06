# Universal UX

Rules that apply to every surface. Profiles may raise or lower their weight; none of them switches these off.

**Load when:** always.

## Objectives

Usability is the extent to which specific users can reach specific goals with effectiveness, efficiency and satisfaction in a specific context of use. Every check below is a way of asking whether *these* users can do *this* task, so judge against the classification, not against an abstract ideal.

## Priority principles

1. People should always be able to tell what the system is doing and what state things are in.
2. People should be able to predict what a control will do before using it, and undo it afterwards.
3. The interface should prevent the errors it can, and explain the ones it cannot.
4. What users need often is visible; what they need rarely is findable.
5. Nothing on screen competes with the task without earning its place.

## Checks

### System status and feedback
- Every user action produces a visible response. A press that changes nothing visible reads as a broken control.
- Match feedback to the wait: under about 0.1 s feels instant and needs only the result; up to about 1 s the delay is noticed, so show that the action registered; beyond about 10 s attention is lost, so show progress and offer a way to cancel or carry on elsewhere.
- Persistent state is visible without interaction: what is selected, active, saved, unsaved, enabled, filtered, sorted, in progress, failed.
- Background changes that affect the user (data refreshed, session expiring, connection lost) are announced, not silent.
- Feedback appears near the thing that caused it, or in one consistent place.

### User control and freedom
- Every dialog, overlay, mode and multi-step flow has a clearly marked exit that does not discard work without warning.
- Back works: browser back, in-app back and Escape do what a user would expect and do not lose entered data.
- Reversible actions offer undo in preference to a confirmation. Irreversible ones say so before the user commits.
- Nothing starts on its own that the user cannot stop: autoplay, carousels, auto-advance, timed logouts without warning.
- User input is never discarded by an error, a validation failure, a timeout or navigation the user did not intend.

### Consistency and predictability
- The same action has the same name, appearance and position everywhere it appears. Different actions do not share a label or icon.
- Links navigate; buttons act. Controls look like what they are.
- Platform and domain conventions are followed unless there is a reason users will benefit from breaking them (logo links home, cart top-end, search uses a magnifier, underlined text is a link).
- Focusing or changing a control does not cause an unexpected change of context such as a navigation, a submission or a new window.
- Terminology is stable: one word per concept across navigation, headings, buttons and messages.

### Error prevention
- Constrain input where rules are known: pickers instead of free text for constrained values, disabled impossible options, sensible defaults.
- Accept forgiving formats (spaces in card numbers, either date separator, any phone grouping) instead of rejecting them.
- Dangerous actions are visually and spatially separated from routine ones and are never the default.
- Confirmation is reserved for serious, hard-to-reverse actions, names the specific object and consequence, and uses buttons labeled with the action ("Delete 3 invoices" / "Keep them"), not Yes/No.

### Error recovery
- An error message says, in plain language, what happened, whether anything was lost, and what to do next. No codes without explanation, no blame.
- It appears next to the problem and stays until the problem is fixed.
- It uses more than color to stand out.
- Where the system can suggest the fix, it does ("Did you mean…", "Use at least 8 characters").

### Recognition over recall
- Options, commands and current values are visible or one obvious step away; users are not asked to remember information from an earlier screen.
- Icons that are not universally understood carry a text label. Icon-only controls always have an accessible name and, on pointer devices, a tooltip.
- Recently used items, saved choices and suggestions are offered where the task repeats.
- Formats, units and constraints are shown before input, not only after failure.

### Hierarchy and readability
- Each view has an evident purpose and one primary action. Visual weight follows importance: if everything is emphasized, nothing is.
- Related items are grouped by proximity and alignment; unrelated items are separated. Group before adding borders or boxes.
- Headings describe their content and form a logical outline.
- Text is sized, spaced and contrasted to be read comfortably for the expected length of reading; long-form body text has a measured line length.
- Density suits the task: generous for persuasion and reading, compact for comparison and monitoring.

### Discoverability and progressive disclosure
- Features needed in most sessions are visible without hovering, scrolling a menu or guessing at an icon.
- Rare or advanced options are tucked behind a clearly labeled control whose label tells users what they will find.
- Disclosure goes one or two levels deep, not more.
- Hidden navigation is a last resort on wide screens.

### Efficiency and flexibility
- Frequent tasks take few steps. Defaults reflect the most common choice.
- Repetitive work has accelerators that novices can ignore: keyboard shortcuts, bulk actions, saved views, duplicate, recent items.
- Shortcuts are discoverable (shown in menus or tooltips) and do not override browser or assistive-technology keys.
- Preferences and context persist: the product remembers where the user was and how they like to see it.

### Learnability and help
- A new user can start the main task without a tutorial. Guidance appears in context, when it is needed, and can be dismissed and found again.
- Empty states explain what belongs there and how to add it.
- Help and contact routes are easy to find and in the same place on every page.
- Unfamiliar terms are explained where they appear, not in a glossary elsewhere.

### Cross-references
Accessibility, performance as perceived by users, content clarity and trust are universal too; they have their own core modules. Responsive behavior and state handling are in the pattern modules.

## Anti-patterns

- Silent buttons: no pressed state, no spinner, no result.
- Modal on top of modal.
- "Are you sure?" on routine, reversible actions, training users to click through.
- Yes/No or OK/Cancel buttons on a consequential choice.
- Clearing a form after a failed submit.
- Icon-only toolbars with no labels, names or tooltips.
- The same thing called three different names across the product.
- Three "primary" buttons in one view.
- Features reachable only by hover, long-press or a gesture nobody was told about.
- Forced product tours before any use.
- Errors shown as a toast that disappears before it can be read.

## Exceptions and context

- **Expert, high-frequency tools** rightly favor efficiency and density over first-use obviousness, provided labeled paths still exist.
- **Marketing and brand surfaces** may trade efficiency for narrative pacing; they still owe feedback, exits and clarity about the next step.
- **Convention versus consistency:** when a product's own established pattern differs from the outside convention and users are trained on it, internal consistency usually wins.
- **Confirmations** become more appropriate as the consequence of an error rises; see `profiles/high-stakes.md`.
- **The response-time limits** are perceptual thresholds from long-standing research, not service-level targets. Use them to choose feedback, not to grade the backend.

## Implementation cautions

- Adding feedback (pressed state, spinner, status text) for a state the code already tracks is UI. Adding a new state, timer, retry or undo mechanism is functional: recommend it.
- Changing a label is safe; changing an identifier, route, event name or translation key is not.
- Reordering content inside a view is usually safe; reordering form fields that post to a backend may not be.
- Replacing a confirm dialog with undo requires undo to exist. If it does not, improve the dialog's wording and recommend undo.

## Sources

- [NNG-01] Ten usability heuristics — the structure of this module
- [ISO-01] ISO 9241-11 — definition of usability in a context of use
- [NNG-03] Response-time limits — feedback thresholds
- [NNG-02] Progressive disclosure — what to show first, depth of disclosure
- [NNG-04] Complex applications — learning by doing, flexible pathways
- [NNG-06] Confirmation dialogs — selective, specific confirmation; undo
- [NNG-07] Error-message guidelines
- [NNG-23] Slips — constraints, defaults, forgiving formats
- [NNG-14] Contextual help over upfront tutorials
- [NNG-31] Accelerators
- [NNG-17] Hidden navigation and discoverability
- [NNG-35] Modal and nonmodal dialogs
