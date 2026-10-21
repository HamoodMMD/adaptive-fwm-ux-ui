# Motion and animation

Transitions, micro-interactions, entrance effects, scroll effects, parallax, carousels, autoplaying media and animated illustrations. Motion is useful when it explains what changed; otherwise it costs time and attention, and for some people it causes physical discomfort.

**Load when:** the surface animates: page or panel transitions, hover and press effects, entrance or scroll-triggered animation, parallax, carousels or auto-advancing content, autoplaying video, animated illustrations, or a motion library is in use.
**Skip when:** nothing on the surface moves except native scrolling and focus.
**Pair with (when present):** `core/accessibility` (2.2.2 and reduced motion), `core/performance`, `core/brand-preservation`, `patterns/loading-empty-error-states`, `patterns/component-libraries`.

## Objectives

Every animation has a job: confirm an action, show where something came from or went, show a change of state, or point to something that needs attention. It is short enough that nobody waits for it, it never blocks input, and it stops or simplifies for people who asked for less motion. Nothing moves on its own for long without a way to stop it.

## Priority principles

1. **Motion must have a purpose.** Feedback, state change, orientation or a signal of what can be done. Decoration alone is not a purpose on a working screen.
2. **Short and quick to start.** The shortest duration that does not look abrupt. Long animations are the more common mistake.
3. **The more often it plays, the subtler it is.** Something seen a hundred times a day should be barely noticeable.
4. **Never make people wait for it.** Input works during and after an animation; nothing important appears only after a slow reveal.
5. **Respect the setting and the brand.** Reduce motion when asked; keep the brand's signature motion where it serves a purpose.

## Checks

### Purpose
- Each animation can be named by its job: feedback (a press, a toggle, a saved state), a change of state or mode, orientation (where a panel came from, where an item went), or a signifier (that a card can be swiped). If it has none, it is a candidate for removal on frequent paths.
- Motion is never the only way information is shown: a change also appears as text, an icon or a state.
- Animation that draws attention is kept for things that need it; several moving elements on one screen compete and distract.

### Timing and easing
- Simple feedback (a checkbox, a toggle, a button press) takes about 100 ms.
- Larger changes (a dialog, a panel, a menu) take about 200–300 ms.
- Large movements across big screens take up to about 400 ms; longer is rarely justified in a working interface.
- Elements entering ease out (start fast, then slow); elements leaving ease in, and leave slightly faster than they arrived.
- Motion follows the gesture that caused it: a sheet pulled down from the top is dismissed by pushing it back up, not sideways.

### Never blocking
- Controls respond at once; the user can act, cancel or move on without waiting for an animation to finish.
- Content is readable without the entrance animation finishing: scroll-triggered reveals do not hide text from people who scroll fast, print, use reader mode or have scripts blocked.
- No scroll-jacking: the page scrolls at the speed and distance the user scrolls.
- Animated loading is covered by `patterns/loading-empty-error-states`; motion does not replace real progress information.

### Reduced motion and safety
- With the reduced-motion setting on, non-essential movement (sliding, zooming, parallax, scaling) is removed or replaced with a fade or an instant change. This is WCAG 2.3.3 (AAA) and treated by this skill as strongly recommended.
- Anything that starts by itself, moves for more than five seconds and sits beside other content (carousels, tickers, background video, animated illustrations) has a pause or stop control (2.2.2, Level A). Auto-updating content needs a way to pause or control it regardless of duration.
- Nothing flashes more than three times a second (2.3.1).
- Parallax and large background movement are optional, off with reduced motion, and checked for comfort on a large screen.

### Performance
- Animations use `transform` and `opacity`, run smoothly on a low-powered phone, and do not shift layout (`core/performance`).

## Anti-patterns

- A 600 ms page transition on every navigation.
- Content that fades in only after it is scrolled into view, leaving blank space for fast scrollers.
- A hero carousel that advances every three seconds with no pause.
- Bouncing, shaking or pulsing used to demand attention for something that does not need it.
- A button that cannot be pressed again until its animation finishes.
- Scroll-jacked storytelling pages that ignore the scroll wheel.
- A reduced-motion setting honored by the site's own CSS but ignored by its animation library or video.

## Exceptions and context

- **Brand and storytelling pages** may use richer, longer motion at a few signature moments. Keep it off forms, checkout and other task paths, and give it a reduced-motion version.
- **Games, creative and animation tools** use motion as content; the essential exception applies to the motion that is the function.
- **Data and monitoring products:** animate changes in values briefly or not at all; constantly moving numbers and charts make reading harder.
- **Native platforms** already animate standard controls; custom motion on top of them is usually unnecessary.

## Implementation cautions

- Safe UI work: shortening durations, changing easing, adding a reduced-motion variant, adding a pause control to existing auto-advancing content, switching an animated property to `transform` or `opacity`, making content visible without the entrance animation.
- Functional work, recommend only: removing a carousel or a signature animation, changing a page-transition system, adding or replacing a motion library.
- Record the brand's motion language in the inventory first (`core/brand-preservation`) and change durations within it, not to a generic default.

## Sources

- [NNG-57] Purposes of motion: feedback, state change, navigation, signifiers; distraction
- [NNG-103] Durations of about 100 ms for feedback, 200–300 ms for larger changes, up to 400 ms for big movements; ease-out to enter, ease-in to leave; frequent means subtle
- [APL-05] Purposeful, optional, brief motion; avoid motion on frequent interactions; let people cancel
- [W3C-33] Animation from interactions (2.3.3) and the essential exception; [W3C-34] Pause, stop, hide (2.2.2)
- [W3C-01] Three flashes or below threshold (2.3.1)
- [LIB-07] Reduced motion in an animation library
