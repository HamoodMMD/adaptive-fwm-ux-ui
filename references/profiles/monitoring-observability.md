# Monitoring and observability

Interfaces for watching the health of systems, sites or services, being told when something is wrong, and finding out why.

**Load when:** the surface shows uptime, health, incidents, alerts, checks, logs, metrics or traces.
**Skip when:** "status" means business status (orders, tickets) with no system-health meaning.
**Journey:** detect → assess severity and impact → locate → diagnose → act → confirm recovery → review.
**Pair with (when present):** `profiles/dashboard-analytics`, `patterns/charts-data-viz`, `patterns/tables`, `patterns/loading-empty-error-states`; `profiles/high-stakes` for actions that change production.

A monitoring interface is not a marketing page. Its users are often under time pressure, and a calm, spacious layout that hides the failing component is a failure of the interface.

## Objectives

In seconds a user can tell whether anything is wrong, what is affected and how badly. In minutes they can move from the symptom to the evidence that explains it. At no point can they mistake "we do not know" for "everything is fine".

## Priority principles

1. **Worst first.** The most severe current problem is the most prominent thing on the screen.
2. **Unknown is not healthy.** No data, stale data, paused checks and failed collection each have their own unmistakable state.
3. **Symptoms before causes.** Lead with what users or the business experience; let diagnostics sit one step below.
4. **Every alert shown should deserve attention.** Noise trains people to ignore the interface.
5. **Keep context through the investigation.** Time range, scope and selection travel with the user as they drill down.
6. **Density is a feature** for expert users; legibility is not negotiable.

## Checks

### Overall health
- The landing view answers "is anything wrong right now?" before anything else: a summary of current state by severity, with counts.
- Problems are listed worst-first by default; healthy items do not push failing ones off-screen.
- A group or parent shows the state of its worst child, so nothing failing is hidden inside a green group.
- When everything is healthy, the view says so explicitly, with the time of the last check.

### Status vocabulary and differentiation
- A small, fixed set of states is used consistently everywhere: for example operational, degraded, down, unknown or no data, maintenance, paused. Each has one name, one color, one icon.
- Status is never conveyed by color alone: each state has a distinct icon or shape and a text label, and the pairs remain distinguishable for color-blind users and in grayscale.
- "Unknown", "no data", "paused" and "pending first check" look clearly different from "operational".
- Severity levels are few, ordered and defined. The same level means the same thing across the product.
- Alert colors are reserved for alert meanings and not reused for branding or decoration.

### Incidents and alerts
- Each incident shows: severity, what is affected, when it started, how long it has lasted, its current state (open, acknowledged, investigating, resolved), and who owns it where ownership exists.
- An alert says what happened, where, since when and how badly, in a sentence a person can act on, with a link to the evidence and to any runbook that exists.
- Repeated occurrences of the same problem are grouped, with a count and first and last occurrence, instead of flooding the list.
- Acknowledged, muted and snoozed items are visibly different from active ones and say until when.
- Flapping (repeated fail and recover) is recognizable as such.
- Resolved incidents remain findable, with resolution time.

### Affected resources and impact
- From any problem the user can see which service, site, host, check or customer is affected and what depends on it.
- Scope is quantified where data exists: how many checks, regions, users or requests.
- For mixed audiences there is a plain-language statement of impact ("Checkout is slow for some customers") alongside the technical detail ("p95 latency 4.2 s on payments-api"). Client-facing and status-page views lead with the plain statement.

### Time, freshness and history
- Every status and value shows when it was last checked or updated.
- Timestamps give absolute time with time zone, and relative time for recency; the zone used is stated and consistent.
- Stale data is flagged prominently when collection stops, instead of the last good value being shown as current.
- History is available: state changes, uptime over selectable periods, past incidents.
- Timelines place events in order with durations, and mark changes such as deployments or configuration edits where the data exists.

### Drill-down and diagnosis
- There is a clear path from overview to service to component to individual check to raw evidence.
- Drilling down keeps the time range and filters; coming back restores the previous view.
- Related signals are shown together around the same moment, on a shared time axis.
- Charts draw thresholds and mark the incident window; units are labeled. Detail: `patterns/charts-data-viz`.
- Identifiers, error messages and values can be copied exactly.

### Logs and events
- Monospaced, aligned, with timestamp, level and source distinguishable; level shown by text as well as color.
- Filtering by level, source and time, and text search, are available where the product supports them, and the active filter is visible.
- Live streams can be paused, do not move content the user is reading, and show when new entries are waiting.
- Long lines can be wrapped or expanded; structured entries can be expanded to fields.
- Large volumes are paginated or virtualized, with a clear position.

### Alert fatigue as a presentation problem
- Notification and list views distinguish urgent from informational.
- Counts and badges reflect items needing attention, not total events.
- Low-priority noise can be filtered out of view without being lost.
- Any recommendation to change thresholds, grouping or routing is a functional recommendation.

### Density and legibility
- Compact rows, small margins and many values per screen are appropriate. Do not inflate into cards.
- Dark themes are common and legitimate; contrast requirements still apply, including for secondary text and chart lines.
- Numbers use tabular figures and consistent units so columns compare.
- Wall-display modes use larger type and no hover-dependent information.

### Refresh and live behavior
- Automatic refresh is indicated, can be paused, and never steals focus, resets scroll, collapses expanded rows or closes what the user is reading.
- A new critical event is announced without hijacking the view.
- Loss of connection to the backend is shown as its own state.

### Recovery
- Recovery is shown as clearly as failure: what recovered and when.
- Duration and impact summaries are available after resolution.

## Anti-patterns

- A calm "All systems operational" banner above a list containing failures.
- Gray "no data" that reads as fine.
- Last known value displayed with no indication the feed stopped an hour ago.
- Status as a colored dot only.
- Five shades of orange for five severities.
- Hundreds of identical alerts, ungrouped.
- Timestamps with no time zone, or relative-only ("3h ago") with no exact time.
- Drill-down that resets the time range to the default.
- Log view that jumps while being read.
- Large friendly cards showing six monitors per screen for a user who has four hundred.
- Hero illustrations and marketing whitespace on an incident page.
- Auto-refresh that discards a half-typed filter.
- Technical jargon on a customer-facing status page; vague reassurance on an engineer's view.

## Exceptions and context

- **Public status pages** serve non-technical readers: plain language, current state, affected services, updates in time order, how to subscribe. Diagnostic detail is omitted.
- **Client or agency reporting views** summarize impact and trend; they are closer to `dashboard-analytics`.
- **Small deployments** with a handful of monitors do not need grouping, heavy filtering or dense tables.
- **Security monitoring** has stricter needs for provenance and audit; add `high-stakes`.
- **Mobile on-call use** is triage, not investigation: severity, what, since when, acknowledge. Deep diagnosis can require a larger screen and may say so.

## Implementation cautions

- Never change thresholds, check intervals, alert rules, grouping or deduplication logic, severity mapping, incident state transitions, notification routing, retention or scan behavior.
- Renaming or recoloring a state is display-only when the mapping from underlying state to label stays one-to-one. Do not merge or split states in the UI.
- Sorting worst-first is UI when it is a client-side ordering of existing data; changing a server query is functional.
- Do not synthesize health scores, uptime percentages or impact figures in the front end.
- Relative-time formatting and time-zone display are UI; changing which zone data is stored or queried in is not.
- Grouping duplicate alerts in the list view requires stable keys from the backend; if absent, recommend.
- Actions that touch production (restart, mute, acknowledge, resolve) are high-stakes; do not alter their handlers.

## Sources

- [SRE-01] Monitoring distributed systems — symptoms versus causes, golden signals, alerts that are actionable and urgent
- [GRAF-01] Dashboard best practices — USE and RED methods, drill-down hierarchies, alerting on symptoms
- [PD-01] Reducing alert noise — deduplication, grouping, suppression
- [CARB-01] Status indicators — more than color, severity levels, show the highest-attention state for a group
- [NNG-21] Operational dashboards
- [NNG-04] Complex applications
- [W3C-22] Time zones — explicit zone context for displayed times
- [W3C-01] WCAG 2.2 — 1.4.1 Use of Color, 1.4.11 Non-text Contrast, 2.2.2 Pause, Stop, Hide, 4.1.3 Status Messages

Guidance on stale and unknown states, log presentation and investigation context is reasoned from visibility of system status [NNG-01] and the sources above (evidence class: Judgment).
