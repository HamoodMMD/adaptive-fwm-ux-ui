# Charts and data visualization

Charts, sparklines, gauges and other graphical encodings of data.

**Load when:** the surface contains any chart.
**Skip when:** numbers are shown only as text or tables (use `tables`).

## Objectives

A viewer grasps the chart's message quickly and correctly, can read values and units without guessing, is not misled by scale or decoration, and can get the same information without seeing color or without seeing the chart at all.

## Priority principles

1. **Start from the question.** A chart exists to show a comparison, a trend, a distribution, a relationship or a composition. If you cannot name which, it should not be a chart.
2. **Position and length are read most accurately;** angle, area and color intensity far less so. Prefer bars, lines and dots.
3. **The scale must not lie.**
4. **Color is a second channel, not the only one.**
5. **Remove what does not carry data.** Decoration costs attention and adds nothing.

Do not recommend a chart merely because data exists. Often a number with context, or a table, is the better display.

## Checks

### Choosing the form
| Message | Usually best | Notes |
|---|---|---|
| Compare categories | Bar chart (horizontal for long labels) | Sort by value unless the categories have a natural order |
| Change over time | Line chart; bars for few discrete periods | Time runs along the horizontal axis |
| Part of a whole | Stacked bar, or a pie or donut for very few parts | Avoid pies beyond about five slices or when slices are similar |
| Distribution | Histogram, box plot | |
| Relationship between two measures | Scatter plot | |
| Exact values, many attributes | Table | |
| One key figure | The number, with comparison and trend | Not a gauge |
| Progress to a target | Bar with target marker | |

- The chart type matches the message above; unusual chart types are used only where the audience knows them.
- A single chart carries one main message. Two messages are two charts.

### Scale and axes
- Bar charts start at zero: bar length encodes the value, so a truncated axis exaggerates differences.
- Line charts may use a non-zero baseline to show variation, with the axis clearly labeled.
- Charts meant to be compared with each other share the same scale, or say prominently that they do not.
- Logarithmic scales are labeled as such.
- Dual vertical axes are avoided; they invite false conclusions from where lines happen to cross. Use two aligned charts instead.
- Axes are labeled with what is measured and its unit. Tick labels are few, round and readable; rotated or overlapping labels are fixed by reducing ticks, abbreviating or switching to horizontal bars.
- Gridlines are light and sparse, behind the data.
- Time axes show the granularity and time zone where that matters, and mark incomplete periods.

### Labels and legends
- The title says what the chart shows: measure, scope and period. An insight-style headline is appropriate in reports.
- With few series, label them directly at the line or bar instead of using a separate legend.
- Where a legend is needed, its order matches the visual order of the series and it sits close to the data.
- Limit the number of series: about four lines on a line chart is a practical ceiling before it becomes unreadable; group the rest as "Other" or use small multiples.
- Numbers use consistent formatting, locale-appropriate separators, sensible precision and consistent abbreviations.

### Color
- Color is never the only way to tell series or states apart: add direct labels, different marker shapes, line styles or patterns. (WCAG 1.4.1, Level A.)
- Graphical elements needed to understand the chart have at least 3:1 contrast against adjacent colors. (WCAG 1.4.11, Level AA.)
- Palettes are chosen to remain distinguishable with common color-vision deficiencies; red and green are not the sole distinction.
- Categorical data uses distinct hues; ordered data uses a sequential ramp of one hue; data with a meaningful midpoint uses a diverging ramp.
- The same category has the same color in every chart on the surface.
- Semantic colors (red for bad, green for good) are reserved for that meaning and not reused for neutral series.
- Brand colors are used where they work; add shape or label cues before replacing a brand palette.
- Emphasis is created by muting the rest, not by adding more colors.

### Annotation, comparison and outliers
- Targets, thresholds, averages and previous-period values are drawn in when they are what gives the data meaning.
- Notable events (a release, a campaign, an incident) are marked on time series where the data exists.
- Outliers are shown, not silently clipped; if the axis is capped, the cap is indicated.
- Comparison series are visually subordinate to the primary series.

### Missing, empty and partial data
- Gaps in data are shown as gaps, not drawn as zero and not smoothed over, unless interpolation is stated.
- A chart with no data says so, and why (no data for this range, not yet configured, failed to load).
- Small samples and estimated values are indicated.
- Loading uses a placeholder of the chart's size; the layout does not jump when data arrives.

### Tooltips and interaction
- Essential information is readable without hovering. Tooltips add precision; they are not the only way to learn what a point is.
- Tooltips are reachable by keyboard and touch, do not cover the point they describe, can be dismissed, and stay while the pointer moves onto them. (WCAG 1.4.13, Level AA.)
- Interactive elements (legend toggles, zoom, range selection) look interactive and can be reset.
- Hover on one chart may highlight the same moment on related charts where the product supports it.

### Accessibility
- Every chart has a text alternative: a short description of what it shows, and access to the underlying values through an adjacent table, a "view as table" option or a longer description.
- The key message is stated in text near the chart, so the conclusion does not depend on seeing it.
- Charts are not flattened into images of text; text within them is real text that scales.
- Animated or live-updating charts can be paused. (WCAG 2.2.2, Level A.)
- Focusable chart elements have meaningful names.

### Responsive behavior
- Charts keep a readable minimum height and a sensible aspect ratio; they are not simply scaled down.
- On narrow screens: fewer ticks and labels, abbreviated values, legends moved below or replaced by direct labels, horizontal bars instead of vertical ones with long category names.
- Dense time series scroll horizontally within their container, or show a shorter default range.
- Below a width where the chart no longer communicates, offer the key numbers or a table instead.
- Touch targets for points and legend items are large enough to tap.

### Motion
- Entrance animations are brief and not repeated on every refresh.
- Transitions between states help track change; they do not delay reading.
- Reduced-motion preferences are honored.
- Live charts keep axes stable so that values are not constantly rescaling under the viewer.

## Anti-patterns

- Charts for decoration, or because a data source exists.
- Bar charts with a truncated axis.
- Pie charts with many slices, or several pies side by side for comparison.
- Gauges and dials for a single number.
- 3D effects, heavy gradients, drop shadows, background images.
- Dual axes implying a correlation.
- Rainbow palettes for ordered data.
- Red versus green as the only distinction.
- Legends far from the data, in a different order from the series.
- Unlabeled axes; missing units.
- Hover-only values.
- Missing data drawn as zero.
- A different color for the same series on each chart.
- Ten overlapping lines.
- Charts scaled down until labels overlap.
- Charts as static images with no alternative.

## Exceptions and context

- **Expert analytical tools** can use denser and more specialized charts (heat maps, candlesticks, flame graphs) that their users know.
- **Marketing and editorial graphics** may use illustrative styling; the scale must still be honest and the text alternative present.
- **Sparklines** deliberately omit axes and labels; they sit beside the number they summarize and are never the sole source of the value.
- **Operational displays** read at a distance favor large numbers and status color with icons over detailed charts.
- **Small multiples** are preferable to one crowded chart when there are many series.
- **Pies and donuts** are acceptable for two to five clearly different parts of one whole, when an approximate share is all that is needed.

## Implementation cautions

- UI-safe: titles, axis labels, units, number formatting, tick density, gridline weight, legend placement and order, direct labels, color assignment within the existing palette, marker shapes and line styles, minimum sizes, reduced-motion handling, text alternatives and summary text describing data already shown.
- Functional, recommend: changing what data is queried, aggregated, sampled or compared; adding series, targets, annotations or thresholds that are not in the data; adding a data-table view if no data access exists for it; changing refresh behavior.
- Changing chart type is presentation only when the same data is shown without loss; verify nothing is dropped or re-aggregated, and say so.
- Changing an axis baseline changes the impression the chart gives. Do it where the current baseline misleads, and state it in the report.
- Charting libraries own their DOM. Configure through options and themes; avoid overriding generated markup.
- Canvas-rendered charts expose nothing to assistive technology by default; an alternative is required, and adding one may need data access that is functional work.
- Summary text must describe the data, not interpret beyond it; never write conclusions the data does not show.
- In RTL interfaces, charts are generally not mirrored: time still runs left to right unless the product's locale convention says otherwise. See `rtl-bilingual`.

## Sources

- [GOV-07] Government Analysis Function chart guidance — choosing by message, zero baseline for bars, limits on series, gridlines, color and accessibility, text alternatives
- [NNG-21] Dashboards — length and position are read accurately; pies and gauges are not; color for categories
- [GRAF-01] Dashboard practices — normalized axes, consistent color, reducing cognitive load
- [W3C-19] Text alternatives for complex images
- [W3C-07] Non-text contrast for graphical objects
- [W3C-09] Content on hover or focus
- [W3C-01] WCAG 2.2 — 1.1.1, 1.4.1, 1.4.11, 1.4.13, 2.2.2
- [CARB-01] Status color with shape and text
- [MAT-01] Bidirectionality — charts are not mirrored
- [WEB-06] Reduced motion
