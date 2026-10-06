# Admin and back-office

Internal tools where staff manage records all day: orders, customers, products, content, users, tickets, inventory.

**Load when:** the users are staff or administrators doing frequent, repetitive work over business records.
**Skip when:** customers manage a few of their own records (use `saas-application` account sections).
**Journey:** find the record(s) → inspect → edit or act → confirm → next record, many times a day.
**Pair with (when present):** `patterns/tables`, `patterns/search-filter-sort`, `patterns/forms`, `patterns/loading-empty-error-states`; `profiles/high-stakes` for destructive, financial or permission actions.

The usual mistake with admin tools is to "simplify" them: bigger cards, fewer columns, more steps. For people who use the tool for hours, that is a slowdown presented as an improvement.

## Objectives

An experienced operator can find any record quickly, see what they need without opening it, change one or many records with few actions, and never be surprised by a destructive result. A new colleague can still work out what things do.

## Priority principles

1. **Efficiency for frequent users comes first.** Count steps, pointer travel and waits for the commonest tasks.
2. **Density is appropriate.** More rows and columns per screen means fewer scrolls and better comparison. Keep it legible, not sparse.
3. **Tables are the workspace.** Most work starts from a list; the list must carry search, filter, sort, selection and actions well.
4. **Keep context while editing.** Do not hide the list behind a modal when the user needs it for reference.
5. **Guard the dangerous actions, and only those.**
6. **Make results accountable.** Show what changed, for how many records, and whether all succeeded.

## Checks

### Layout and density
- Compact row heights and tight spacing are the default; a density control is a bonus where the product has one.
- The work area uses the available width; content is not confined to a narrow centered column.
- Pointer targets still meet the 24 by 24 CSS pixel minimum or the spacing exception.
- Typography favors legibility at small sizes; numbers use tabular figures.
- Persistent navigation is slim and collapsible; the page title and record count are visible.

### Finding records
- Search is prominent on every list, states what it searches (name, id, email), and accepts identifiers pasted from elsewhere.
- Filters cover the fields staff triage by (status, date, owner, type); active filters are visible and removable; common combinations can be saved or are offered as presets where the product supports it.
- Sorting is available on the columns people order by; the current sort is shown.
- List state (search, filters, sort, page) survives opening a record and coming back. Detail: `patterns/search-filter-sort`.

### Tables
- The first column identifies the record in human terms and links to it; it stays in view when scrolling horizontally.
- Columns are ordered by importance for triage. Status uses text with an icon or shape, not color alone.
- Numeric and date columns are aligned and formatted for comparison.
- Column headers stay visible while scrolling long lists.
- Users can hide or reorder columns where the product supports it; columns people need are not removed to make the table look lighter.
- Detail: `patterns/tables`.

### Pagination
- Total count, current range and page size are shown; page size can be changed.
- Pagination is preferred to endless scrolling for work lists, because position and totals matter.

### Selection and bulk actions
- Rows are selectable with checkboxes; the header checkbox selects the visible page.
- When more records match than are on the page, the scope is explicit: "50 on this page selected. Select all 1,243 that match?"
- The number selected is always visible, and available bulk actions appear when something is selected.
- Before running, a bulk action states what will happen and to how many records.
- Afterwards it reports the outcome exactly: how many succeeded, how many failed, which ones and why, with a way to retry the failures.
- Selection is cleared or preserved predictably after an action.

### Row actions
- One or two frequent actions are available directly on the row; the rest sit in an overflow menu in a consistent position.
- Actions are reachable by keyboard and touch, not revealed only on hover.
- Icon-only actions have accessible names and tooltips.

### Viewing and editing
- Opening a record for a quick look or edit uses a side panel, expandable row or split view where the product has one, keeping the list in sight. Full pages are for substantial editing.
- Inline editing, where present, shows clearly which cell is editable, how to commit and cancel, and whether the change saved.
- Forms are laid out for speed: logical tab order, sensible defaults, related fields grouped, the commonest fields first. Detail: `patterns/forms`.
- Validation is specific and points to the field. Entered data survives errors.
- Save state is unambiguous: saved, saving, unsaved changes, failed.
- "Save and next", "Save and add another" and duplicate options exist where work is sequential.

### Destructive and sensitive actions
- Delete, cancel, refund, suspend, change role, publish and similar are labeled with the specific verb and separated from routine actions.
- Confirmation is specific: it names the record or the count and the consequence, with buttons labeled by the action. Typed confirmation is reserved for the gravest, hardest-to-reverse cases.
- Where undo, soft-delete or a recycle bin exists, it is offered in preference to a confirmation, and its time limit is stated.
- Irreversibility is stated when true.
- See `profiles/high-stakes.md`.

### Permissions and audit
- A user who cannot perform an action learns why, and who can.
- Controls that are never available to a role are omitted; those blocked by state are disabled with the reason given.
- Where history exists, each record shows who changed what and when; recent activity is easy to reach.
- Acting on behalf of another user or tenant is permanently and prominently indicated.

### Keyboard efficiency
- Everything is reachable by keyboard in a sensible order; focus is visible; Escape closes overlays and focus returns to where it was.
- Enter submits forms; Tab order matches visual order.
- Shortcuts for the most frequent actions (search focus, new record, save, next and previous record) are provided where the product supports them, shown in tooltips or menus, and do not override browser or assistive-technology keys.
- Lists support keyboard row navigation and selection where the component allows.

### Long-running operations
- Imports, exports, bulk updates and syncs run in the background where possible, show real progress or at least an activity state, and report completion with a result.
- The user can keep working and find the job's status later.
- Import errors are reported per row with reasons, and the file does not need to be re-prepared from scratch.

### Feedback
- Success is confirmed without blocking: a brief status message that is announced to assistive technology.
- Errors stay visible until dealt with and say what to do.
- Counts, totals and statuses update after an action without a manual reload, or the stale state is indicated.

## Anti-patterns

- Replacing a table with large cards, showing eight records where forty fit.
- Removing columns to look cleaner.
- A wizard for a task staff do fifty times a day.
- Modal editing that hides the list being worked through.
- Row actions visible only on hover.
- "Select all" that silently means "all on this page", or silently means "all 10,000".
- Bulk action that reports "Done" when a third failed.
- "Are you sure?" on every save.
- Delete beside Save, same size, same style.
- Filters and page reset after each edit.
- Infinite scroll through thousands of records.
- Marketing-style hero headers and illustrations in a work tool.
- Mobile-first layouts imposed on a tool used on desktops.

## Exceptions and context

- **Occasional users** (a manager who approves monthly) need more guidance than daily operators; role-specific views can serve both.
- **Field or warehouse staff on tablets or handhelds** need large targets and scanning workflows; that is a different surface from the desk tool.
- **Small data volumes** (dozens of records) do not need saved filters, bulk actions or virtualized tables.
- **Regulated operations** may require confirmations, reasons or dual approval that look like friction; keep them.
- **Generated admin frameworks** limit what can be customized; work within the framework's extension points.

## Implementation cautions

- Permission logic, validation rules, bulk-operation scope, audit logging and soft-delete behavior are functional. Present them better; do not change them.
- "Select all matching" must be backed by a server-side selection; never simulate it by selecting loaded rows and implying more.
- Client-side sort and filter of a paginated server list gives wrong results; only restyle what the server already does.
- Changing a modal to a side panel is presentation if the same form, validation and submission are reused; verify.
- Keyboard shortcuts add behavior and can conflict with browser, extension and assistive-technology keys. Recommend and scope carefully.
- Preserve element ids, test ids and class hooks used by end-to-end tests and internal scripts.
- Do not change export formats, column order in exports or import parsers.

## Sources

- [NNG-09] Data tables — find, compare, view or edit a row, act on records; side panels over modals; batch actions
- [NNG-04] Complex applications — flexible pathways, reduce clutter without removing capability
- [NNG-31] Accelerators
- [NNG-06] Confirmation dialogs — specific, selective; undo
- [NNG-23] Slips — constraints and defaults for expert users
- [NNG-30] Pagination versus infinite scrolling
- [CARB-02] Data table — density, batch actions, toolbar
- [CARB-01] Status indicators
- [W3C-03] Target size minimum and its spacing exception
- [W3C-01] WCAG 2.2 — 2.1.1 Keyboard, 2.1.4 Character Key Shortcuts, 3.3.4 Error Prevention, 4.1.3 Status Messages

Guidance on bulk-selection scope, partial-success reporting and long-running jobs is reasoned from visibility of system status and error prevention [NNG-01] (evidence class: Judgment).
