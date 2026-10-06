# Dashboard and analytics

Views that summarize data so people can see what is happening, notice change and decide what to look at next.

**Load when:** metric cards, charts, reports or summary tables are the main content.
**Skip when:** a page merely contains one chart as illustration.
**Journey:** scan → notice what changed or stands out → compare → drill into the cause → act or report.
**Pair with (when present):** `patterns/charts-data-viz`, `patterns/tables`, `patterns/search-filter-sort`, `patterns/loading-empty-error-states`; `profiles/monitoring-observability` when the data is system health.

## Objectives

A viewer can answer the dashboard's question at a glance, trust what each number means, see what deserves attention, and move from summary to detail without losing context.

## Priority principles

1. **A dashboard answers a question for someone.** If you cannot say whose decision it supports, neither can its users. Data is not shown merely because it exists.
2. **Overview first, detail on demand.** Arrange from general to specific.
3. **A number without context is noise.** Unit, period, comparison and freshness turn a value into information.
4. **Reduce the work of reading.** Consistent scales, units, colors and positions let the eye compare instead of decode.
5. **Know which kind it is.** Operational dashboards serve time-critical monitoring at a glance. Analytical dashboards serve unhurried exploration. They want different density and interaction.

## Checks

### Purpose and structure
- The dashboard has a title that states its subject and scope; a newcomer can tell what it is for.
- Content is ordered by importance from the reading start corner: headline indicators first, supporting breakdowns next, detail last.
- Related panels are grouped under headings; unrelated ones are not interleaved.
- The number of panels is limited to what serves the purpose; secondary material lives on a linked detail view.
- Layout is stable: panels do not rearrange themselves between visits unless the user moved them.

### Metric cards
- Each shows a label in plain words, the value, its unit, and the period it covers.
- A comparison gives the value meaning: against the previous period, target, or average, with the basis stated ("vs last 7 days").
- Direction of change is not confused with good or bad: a rise in errors is not shown in the same positive styling as a rise in revenue. Meaning is conveyed by icon or text as well as color.
- Precision is appropriate: no false decimals, consistent abbreviation (K, M), locale-appropriate formatting.
- Sparklines, where used, share a sensible scale and are supplementary to the number.
- Definitions of non-obvious metrics are available in place.

### Time range and comparison
- The active time range is always visible and applies predictably; it is clear whether it controls the whole dashboard or one panel.
- Presets cover common ranges, with custom range available. Time zone is stated where it could differ.
- Comparison periods are explicit and aligned.
- Incomplete current periods (today so far, this month to date) are marked, so a partial bar is not read as a drop.

### Filters and segmentation
- Global filters sit together at the top; panel-level filters sit on their panel. Which filters apply to which panels is evident.
- Active filters are visible at all times and can be cleared individually or all at once.
- Filter, range and view state persist while navigating within the dashboard and, where the product supports it, in the URL so a view can be shared. Detail: `patterns/search-filter-sort`.

### Drill-down
- Elements that lead to detail look interactive and say where they lead.
- Drilling down carries the current range and filters with it, and there is an obvious way back to the same state.
- Detail is available without leaving the page where that helps: tooltips, expandable rows, side panels.

### Charts and tables
- A chart is used when shape, trend or comparison matters; a table when exact values matter; a single number when there is only one thing to say.
- Chart type fits the message. Detail: `patterns/charts-data-viz`.
- The same measure uses the same color, unit and scale conventions everywhere on the dashboard.
- Axes are labeled with units; legends are ordered to match the chart or replaced by direct labels.
- Tables in dashboards are sortable and show totals where they help. Detail: `patterns/tables`.

### Emphasis and anomalies
- Emphasis is reserved for what needs attention: thresholds crossed, significant change, missing data. Most of the dashboard is visually calm so that exceptions stand out.
- Thresholds and targets are drawn on charts where they exist.
- Alert colors are used only for alert meanings.

### Density
- Operational views are compact, high-contrast and readable at a distance if shown on wall screens.
- Analytical views give charts room to be read and allow interaction.
- Whitespace separates groups; it is not spread evenly between every element.

### States and freshness
- Each panel handles loading, empty, error and partial data independently; one failing panel does not blank the page.
- Loading keeps the previous data visible, or uses skeletons of the final shape, instead of collapsing the layout.
- "No data for this period" is distinguished from "not configured" and from "failed to load".
- The time of last update is shown; stale data is flagged.
- Automatic refresh is indicated, can be paused, and does not reset scroll position, selections or open tooltips.

### Responsive behavior
- On narrow screens panels stack in priority order, headline indicators first.
- Charts keep a readable minimum height and reduce tick labels instead of shrinking into illegibility.
- Wide tables scroll within their own region with the identifying column fixed.
- Controls for range and filters stay reachable, typically collapsing into one panel.

### Export and sharing (where present)
- Exports reflect the current range and filters and say so.
- Shared links reproduce the view.

## Anti-patterns

- A wall of charts with no stated question.
- Charts added because a data source exists.
- Numbers with no unit, period or comparison.
- Green up-arrows on metrics where up is bad.
- Gauges and pie charts where a number or bar would be read faster.
- A different color for the same series on every chart.
- Dual-axis charts that invite false correlation.
- 3D, gradients and decoration.
- A full-page spinner while one slow query runs.
- Auto-refresh that closes the tooltip being read or scrolls the page.
- Partial "today" bar that looks like a collapse.
- Filters whose scope nobody can determine.
- Mobile layout that shrinks a twelve-column desktop grid to fit.

## Exceptions and context

- **Executive summaries** want very few indicators with commentary; density is wrong there.
- **Exploratory analytics tools** may show many controls by default; their users expect it.
- **Wall-mounted displays** have no interaction: no hover, no drill-down, larger type, automatic rotation acceptable.
- **Embedded customer-facing dashboards** serve less expert viewers; favor explanation and fewer metrics.
- **Regulated reporting** may fix the content and layout; improve legibility around it.
- **Customizable dashboards** put layout in users' hands; judge defaults and the editing experience.

## Implementation cautions

- Never change queries, aggregations, metric definitions, time-zone handling, rounding logic, thresholds or sampling. How a correct number is formatted and labeled is UI.
- Do not add comparisons, targets, deltas or sparklines that the data layer does not already supply; recommend them.
- Changing chart type is presentation only if the same data and series are shown; verify nothing is dropped or re-aggregated.
- Color changes must keep each series and status distinguishable and consistent across every panel that shares them.
- Charting libraries control much of the markup; configure through their options instead of overriding generated DOM.
- State persistence in URLs or storage is functional if it does not already exist.
- Auto-refresh intervals and data-freshness logic are functional.

## Sources

- [GRAF-01] Dashboard best practices — answer a question, general to specific, reduce cognitive load, consistency, drill-down hierarchies
- [NNG-21] Dashboards — operational versus analytical; which encodings are read accurately at a glance
- [NNG-04] Complex applications — bridging primary and secondary information, highlighting critical information
- [GOV-07] Chart guidance — chart choice, axes, limits on series, accessibility
- [NNG-09] Data tables
- [CARB-01] Status indicators — more than color; limit the number of indicators
- [W3C-01] WCAG 2.2 — 1.4.1 Use of Color, 1.4.11 Non-text Contrast, 2.2.2 Pause, Stop, Hide (auto-updating content)
- [NNG-05] Loading indicators
