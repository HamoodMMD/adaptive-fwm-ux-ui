# Tables

Data tables and dense lists: anywhere rows of records with the same attributes are shown for finding, comparing or acting.

**Load when:** the surface has a data table, grid or dense record list.
**Skip when:** the "table" is a layout device or a short definition list.

## Objectives

Users can find the row they want, compare values across rows and columns without holding them in memory, inspect or edit a record without losing the rest, and act on one or many records with confidence.

## Priority principles

1. **Tables exist for comparison.** Anything that breaks the alignment of like values across rows breaks the point of the table.
2. **Support the four tasks:** find records, compare data, view or edit a single row, take actions on records.
3. **Keep orientation.** Headers and the identifying column stay in view while the rest scrolls.
4. **Do not turn tables into cards by reflex.** Cards suit reading one record at a time; they destroy comparison.
5. **Density is a setting, not a flaw.** Fit it to the task and the user.

## Checks

### Is a table the right form?
- Use a table when records share attributes and users compare across them or scan for a value.
- Use a list or cards when each item is read on its own and has little structured data.
- Use a chart when the pattern matters more than exact values.

### Columns and headers
- The first column identifies the record in human-readable terms (name, title, number) and usually links to it.
- Columns are ordered by importance to the task, and columns that are compared sit next to each other.
- Headers are short (one or two words), in consistent capitalization, with units in the header instead of repeated in every cell.
- Headers stay visible when the table body scrolls vertically.
- Only columns that serve the tasks are shown by default; others are available through a column chooser where the product has one. Do not remove columns users rely on to make the table look lighter.

### Alignment and formatting
- Text aligns to the reading start edge. Numbers that are compared are right-aligned (and stay right-aligned in RTL layouts, see `rtl-bilingual`) with the same number of decimals, using tabular (fixed-width) figures so digits line up by place value.
- Headers align with their column's content.
- Dates and times use one consistent format, sortable by eye; time zone is stated once if needed.
- Status cells use text plus an icon or shape, not color alone.
- Empty cells use a consistent, quiet placeholder (such as an en dash) that is distinguishable from zero.
- Long text truncates with an ellipsis only when the full value is reachable (expand, tooltip that also works by keyboard and touch, or detail view). Identifiers are never truncated ambiguously.
- Negative and exceptional values are distinguishable without relying on color alone.

### Scanning aids
- Rows are separated by subtle borders or alternating backgrounds, light enough not to compete with the data.
- The row under the pointer or with keyboard focus is highlighted.
- Row height suits the task: compact for scanning many records, taller where cells hold two lines or controls. A density control helps where users differ.
- Group headers or subtotals break up long tables where the data has natural groups.

### Sorting
- Sortable columns show that they are sortable; the sorted column shows its direction.
- The default sort is meaningful (most recent, most urgent, alphabetical) and visible.
- Sorting applies to the whole data set, not just the loaded page.
- Sorted state is exposed with `aria-sort`, and sort controls are real buttons inside the header cells.

### Filtering and search
- Filters and search sit directly above the table and are visibly connected to it.
- Active filters are shown and removable; the result count updates.
- An empty result from filtering is distinguished from a table with no data at all.
- Detail: `search-filter-sort`.

### Pagination and loading more
- The total number of records and the range being shown are stated.
- Page size is adjustable where volumes vary.
- Pagination suits work lists and anything where position, totals or return visits matter. Continuous loading suits casual browsing; use a "load more" control in preference to automatic infinite scroll.
- Returning from a record restores page, sort, filter and scroll position.

### Selection and bulk actions
- A checkbox column selects rows; the header checkbox selects the rows on the current page and shows a mixed state when only some are selected.
- If more records match than are on the page, selecting all asks explicitly whether to extend to all matching records and states the number.
- The count of selected rows is visible, and bulk actions appear in a consistent bar when anything is selected.
- Bulk actions state their scope before running and report results precisely afterwards, including partial failure.
- Selection is not lost by sorting or paging unless the user is told.

### Row actions
- One or two frequent actions may sit inline at the end of the row; further actions go in an overflow menu in the same position on every row.
- Actions are available to keyboard and touch users; they are not revealed only on hover.
- Icon-only actions have accessible names that include what they act on ("Delete invoice 1042"), and tooltips.
- Clicking a row has one predictable result; rows that are clickable look and behave like it, and do not conflict with links or controls inside them.

### Viewing and editing a record
- Quick inspection and edits open in an expandable row or a non-modal side panel, so the table remains visible for reference. Modal dialogs hide the data the user is working from.
- Inline-editable cells are recognizable, show how to commit or cancel, validate in place, and confirm saving.
- Adding a record does not push the user away from the table when a quick-add row or panel would do.

### Horizontal overflow
- When columns do not fit, the table scrolls horizontally inside its own container; the page itself does not scroll sideways.
- The identifying first column stays fixed during horizontal scroll.
- A cut-off column or a shadow at the edge signals that more exists.
- The scrolling container is reachable and scrollable by keyboard, with an accessible name.

### Responsive behavior
Choose by task, in roughly this order of preference:

1. **Prioritize columns.** Show the most important few; make the rest available by expanding the row or choosing columns.
2. **Scroll horizontally** with a fixed first column and a visible cue, when comparison across many columns matters.
3. **Let users pick** which columns or which items to compare.
4. **Collapse to a stacked or card layout** only when rows are read individually and not compared. Each card then repeats the labels and keeps the same order of fields.

Data tables are an explicit exception to the WCAG reflow requirement: two-dimensional scrolling of the table itself is acceptable, provided the surrounding page still reflows.

### States
- Loading shows skeleton rows of the right shape or keeps the old rows visible with a subtle busy indicator; the table does not collapse and jump.
- "No records yet", "no results for these filters", "you do not have access" and "failed to load" each have their own message and action. Detail: `loading-empty-error-states`.
- After an action, changed rows update in place and are briefly identifiable.

### Accessibility
- Real table markup: `table`, `thead`, `tbody`, `th` with `scope`, and a `caption` or other accessible name.
- Complex headers that span or nest associate cells with headers explicitly.
- Layout is never done with table elements; data tables are never built from unlabeled `div`s.
- `role="grid"` is reserved for spreadsheet-like widgets with cell-by-cell keyboard navigation; an ordinary table with a few buttons is still a table.
- Every control in a row has a distinct accessible name.
- Interactive targets meet the minimum size or spacing even in compact density.

## Anti-patterns

- Converting every table to cards on mobile.
- Numbers left-aligned, or centered, with varying decimals.
- Headers that scroll away.
- First column scrolling out of sight so rows cannot be identified.
- Row actions that appear only on hover.
- "Select all" with unclear scope.
- Truncated cells with no way to read the full value.
- Sorting only the visible page of a larger data set.
- Modal edit dialogs that cover the table.
- Heavy zebra stripes and thick borders that shout louder than the data.
- Status shown only as a colored dot.
- Page-level horizontal scroll.
- Infinite scroll through thousands of work items.
- `div` grids with no table semantics.
- Empty table body with no explanation.

## Exceptions and context

- **Small, simple tables** (a few rows and columns) need no sorting, filtering, pagination or sticky headers.
- **Pricing and feature comparison tables** on marketing pages are read column by column; on mobile, letting users choose which plans to compare, or fixing the feature column, preserves the comparison.
- **Read-only reference tables** in articles need good markup, captions and overflow handling but no row actions.
- **Spreadsheet-like editors** are their own pattern with grid semantics and keyboard conventions.
- **Record lists on phones for field staff** may legitimately be cards, because the task is one record at a time.
- **Wide analytical tables** may need both column pinning and column grouping; simplify by letting users choose, not by deleting.

## Implementation cautions

- UI-safe: alignment, tabular numerals, spacing and density styles, header stickiness, first-column pinning via CSS, overflow container and its cues, semantic markup, `scope`, `caption`, `aria-sort` reflecting existing sort state, accessible names, visible-on-focus row actions, empty-state wording.
- Functional, recommend: adding sorting, filtering, pagination, selection, bulk actions, column choosers, inline editing, virtualization or state persistence; changing server queries.
- Client-side sorting or filtering of server-paginated data is wrong data, not a UI improvement.
- Table libraries generate their own markup and manage state; configure them through their options and theming before overriding DOM or styles that updates may break.
- Sticky headers and pinned columns interact with overflow containers, z-index and virtualized rows; test scrolling in both directions.
- Row markup, ids and test ids are used by end-to-end tests and scripts.
- In RTL, column order mirrors and the pinned column is on the right. See `rtl-bilingual`.

## Sources

- [NNG-09] Data tables — four user tasks, frozen headers and columns, non-modal editing, batch actions
- [NNG-10] Mobile tables — locked first column, horizontal scroll with cut-off cue, letting users choose columns
- [CARB-02] Data table usage — density, toolbar, batch actions, expandable rows, skeleton state
- [NNG-30] Pagination versus infinite scrolling
- [W3C-18] WAI tables tutorial — headers, scope, captions, complex tables
- [W3C-06] Reflow — exception for data tables
- [W3C-03] Target size minimum
- [W3C-01] WCAG 2.2 — 1.3.1, 1.4.1, 1.4.10, 2.1.1, 4.1.2
- [NNG-08] Empty states
- [GOV-07] Presenting numbers and tables for comparison
