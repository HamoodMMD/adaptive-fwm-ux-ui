# Performance as users feel it

Only the performance issues that change the experience. This is not a performance-engineering guide.

**Load when:** full audits; media-heavy or animated surfaces; any report of slowness, jank or content jumping.
**Skip when:** reviewing copy or a static component with no loading, media or motion.

## Objectives

The interface appears quickly, stays still while loading, and responds at once when touched. A surface that looks finished but shifts under the finger or ignores a tap for half a second has a UX defect, however good it looks in a screenshot.

## Priority principles

1. **Stability first.** Content that moves after it appears causes mis-taps and lost reading position.
2. **Acknowledge every interaction on the next frame.** Slow work is tolerable when the press is visibly registered.
3. **Show the most important content first,** and never make it wait behind decoration.
4. **Honest feedback beats fast-looking feedback.** No invented progress.
5. **Measure before claiming.** Report a metric value only if it was measured, and say whether it is lab or field data.

## Checks

### The three user-centered metrics
Core Web Vitals thresholds, assessed at the 75th percentile of real page loads, separately for mobile and desktop:

| Metric | What the user feels | Good | Poor |
|---|---|---|---|
| Largest Contentful Paint (LCP) | "Has the main content appeared?" | ≤ 2.5 s | > 4.0 s |
| Interaction to Next Paint (INP) | "Did my tap or key press do anything?" | ≤ 200 ms | > 500 ms |
| Cumulative Layout Shift (CLS) | "Did the page jump?" | ≤ 0.1 | > 0.25 |

Use these as the vocabulary for findings. From source alone you can identify likely causes, not scores.

### Layout stability
- Images, video, embeds and ads reserve their space: `width` and `height` attributes or CSS `aspect-ratio`.
- Banners, consent notices, promo bars and "new content" notices do not push existing content down after it has rendered. Reserve the space or overlay them.
- Late-loading content (recommendations, reviews, personalized blocks) has a placeholder of the final size.
- Web fonts do not cause a visible re-layout: a metrically similar fallback, `font-display` chosen deliberately, critical fonts preloaded.
- Skeletons match the size and structure of what replaces them.
- Animations move with `transform`, not by changing `top`, `left`, `width`, `height` or margins.

### First meaningful content
- The largest above-the-fold element (usually the hero image or headline) is present in the initial HTML, not injected by client-side script after hydration.
- The hero image is not lazy-loaded, is sized for the viewport (responsive `srcset`/`sizes`), is in a modern format, and is prioritized (`fetchpriority="high"` or a preload).
- Below-the-fold images and iframes are lazy-loaded.
- Text is visible while fonts load.
- Decorative video, carousels and heavy widgets do not block the primary content.

### Interaction responsiveness
- Pressing a control gives an immediate visual change (pressed state, spinner on the button, optimistic highlight) even when the result takes longer.
- Typing in inputs, especially search and filters, never lags behind the keys.
- Opening menus, drawers, dialogs and accordions is immediate.
- Long lists and tables do not freeze scrolling; very large ones are paginated or virtualized.
- Handlers do not block the main thread with heavy synchronous work before the UI can update.

### Costly visual effects
- Large `backdrop-filter` or `filter: blur()` areas, especially on sticky or scrolling elements, are a common cause of scroll and interaction jank on mid-range phones. Check them first when a glass-style interface feels slow.
- Animate only `transform` and `opacity` where possible. Avoid animating properties that trigger layout or paint.
- `will-change` is applied sparingly and only where a measured problem exists.
- Many simultaneous animations, parallax tied to scroll, and large animated gradients or shadows are checked on a low-powered device, not only a developer laptop.
- Motion honors `prefers-reduced-motion`.

### Perceived speed
- Under about 1 s: no loading indicator; a flash of spinner is worse than nothing.
- About 1–10 s: a skeleton for a whole page or large region, a spinner for a single module or control.
- Over about 10 s: a determinate progress indicator based on real progress, with a way to cancel or leave and return.
- Keep already-loaded content visible during a refresh instead of replacing it with a blank or a full-page spinner.
- Show cached or partial content while the rest arrives, clearly marked if it may be stale.

## Anti-patterns

- Hero image loaded lazily or by JavaScript.
- Images without dimensions.
- A cookie or promo bar that drops in and shifts the page a second after load.
- Full-page spinner for a single widget.
- Fake progress bars or percentages not tied to real progress.
- Skeletons that look nothing like the final layout, or that flash for 100 ms.
- Blur and glass effects on every scrolling surface.
- Buttons with no pressed or pending state, inviting double submits.
- Auto-playing background video on mobile data.
- Reporting "LCP is 1.8 s" from reading the code.

## Exceptions and context

- **Internal tools on known hardware and networks** can accept heavier pages; interaction responsiveness still matters, because staff use them all day.
- **Media-led brand and fashion surfaces** legitimately spend bytes on imagery. Optimize delivery (sizing, format, priority) instead of reducing the imagery.
- **Data-heavy dashboards** are judged on interaction latency and stability during refresh more than on first load.
- **Lab numbers** from a fast machine do not represent users. Field data, where the project has it, outranks lab data.

## Implementation cautions

UI-safe, normally within scope:
- Adding image dimensions or `aspect-ratio`; `loading="lazy"` below the fold; removing lazy loading from the hero; `fetchpriority`; `srcset`/`sizes` where variants already exist.
- Reserving space for late content; sizing skeletons.
- Swapping layout-triggering animations for `transform`/`opacity`; adding a reduced-motion variant.
- Reducing blur radius or area on a specific problem element while keeping the visual language.
- Adding a pressed or pending style for a state that already exists.

Functional, report under the not-implemented heading:
- Changing data fetching, caching, server rendering, code splitting, bundling or hydration strategy.
- Introducing virtualization, pagination, debouncing or optimistic updates.
- Changing image pipelines, CDNs or third-party scripts.
- Adding new loading or pending state to components that do not track it.

## Sources

- [WEB-01] Web Vitals — metrics, thresholds, 75th percentile
- [WEB-02] Interaction to Next Paint — what counts, immediate feedback
- [WEB-03] Optimize Cumulative Layout Shift — causes and fixes
- [WEB-04] Optimize Largest Contentful Paint — hero image and discoverability
- [WEB-05] High-performance CSS animations — transform and opacity
- [WEB-06] prefers-reduced-motion
- [NNG-03] Response-time limits
- [NNG-05] Skeleton screens — when to use which indicator
