# Search, filter and sort

Finding things in a set: site and in-app search, facets and filters, sort controls, and the results they produce.

**Load when:** the surface has search, filters or sorting.
**Skip when:** the collection is small enough to scan and has none of these controls (and do not recommend adding them by reflex).

## Objectives

Users can express what they are looking for, see at once what the system understood and how many results there are, narrow or widen without getting lost, never hit a dead end, and come back to the same results later.

## Priority principles

1. **Always show the current query state:** what was searched, which filters are on, how results are ordered, how many there are.
2. **No dead ends.** Zero results is a moment to help, not to stop.
3. **Filters describe the content.** The right filters depend on what is being filtered.
4. **Match interaction to intent and speed:** instant updates for exploring on fast connections, batch-and-apply where each update is slow or the user knows what they want.
5. **State survives navigation.**

## Checks

### Search field
- Where search is a main route to content, the field itself is visible, wide enough for typical queries, and in a conventional place. Hiding it behind an icon is acceptable only where search is secondary or space is very tight.
- It has an accessible label; placeholder text may hint at scope ("Search orders by number, name or email") but is not the label.
- A visible submit button accompanies the field; Enter also submits.
- What is searched is clear when it is not everything: this section, these fields, this workspace.
- The user's query remains in the field on the results page, ready to edit.
- A clear control empties the field in one action.

### Suggestions and autocomplete
- Suggestions appear quickly and are limited to a scannable number.
- Types of suggestion (queries, categories, direct results) are visually distinguished.
- The matching or the completing part is emphasized consistently.
- Arrow keys move through suggestions and copy the active one into the field; Escape closes; the list is exposed to assistive technology as a combobox with a listbox.
- Misspellings still produce useful suggestions where the engine supports it.
- Suggestions never block submitting what the user actually typed.

### Results
- The page states the query and the number of results.
- Each result shows enough to judge relevance: title, a snippet or key attributes, type or location, with the matching terms visible where the system provides them.
- Corrections are transparent: "Showing results for … Search instead for …".
- When results include partial or broadened matches, they are labeled and separated from exact matches.
- Result updates are announced to assistive technology as a status message with the new count.

### Zero results
- The page says clearly and prominently that nothing matched, repeating the query.
- The query stays in the field for editing.
- It offers ways forward suited to the case: check spelling, use fewer or different words, remove a named filter (with one-click removal), search a wider scope, browse categories, popular or related items, contact or request.
- If filters caused the empty result, say so and offer to clear them, instead of blaming the query.
- The tone is plain and helpful; humor at the user's expense is avoided.
- It does not present unrelated items as if they were results.

### Filters
- Filters reflect the attributes of the content being filtered, and change with category where content differs.
- The most used filters come first; long lists of filter groups are collapsible, with the important ones open.
- Each filter option shows how many results it would yield where the data supports it. Options that would yield none are disabled or removed consistently, not left to produce an empty page.
- Options within a group can be combined (multi-select) where that makes sense; how groups combine is the conventional "any within a group, all across groups" unless stated.
- Long option lists are searchable or truncated with "show more".
- Ranges (price, date, size) offer sensible presets as well as free entry; sliders also accept typed values and are operable by keyboard.
- Filter controls are real form controls with labels; a group has a group label.

### Applied-filter state
- All applied filters are summarized in one place near the results, each removable individually, with a "clear all".
- The filter panel also shows which options are selected, and a group shows when it has active selections even if collapsed.
- A count of active filters appears on the control that opens the filter panel on small screens.
- The result count updates with every change.

### Interactive versus batch filtering
- **Instant application** (results update on each selection) suits exploration when updates are fast.
- **Batch application** (select several, then Apply) suits slow connections, small screens and users who know their criteria. The Apply button shows the resulting count where possible ("Show 42 results").
- While results update, the old results stay visible and dimmed with a progress indicator; the page does not flash blank.
- The page does not jump to the top after each filter click while the user is still working in the filter panel; focus stays where it was.

### Filters on small screens
- Filters open in a full-height panel or sheet from a clearly labeled button that shows the active count.
- The panel has a visible close, a "clear all", and an apply action with the result count.
- Sort is a separate control from filter, not buried inside it.
- The applied-filter summary remains visible above the results after the panel closes.

### Sorting
- The current sort order is always visible on the control.
- Options are named by what they do ("Price: low to high", "Newest first"), not by internal field names.
- The default order is sensible and, where it is an algorithm ("Recommended", "Relevance"), explained briefly.
- Sorting is distinct from filtering in placement and wording.
- Changing the sort keeps the filters and returns to the first page.

### Persistence
- Query, filters, sort and page are reflected in the URL where the product supports it, so results can be bookmarked, shared and restored with the back button.
- Opening an item and returning restores the same results and scroll position.
- Whether filters persist between sessions is a deliberate, visible choice: persistent filters must be obvious, or users will think data is missing.
- Saved searches or views, where present, are named, listed and easy to apply and edit.

### Advanced search and discoverability
- Advanced options are disclosed on request, not shown to everyone by default.
- Query syntax, if supported, is documented in place with examples; the simple path still works without it.
- If important content can be reached only by search, that is a navigation problem to report.

## Anti-patterns

- A magnifier icon as the only sign of search on a search-led site.
- Results page that forgets the query.
- "No results" and nothing else.
- Filters applied but invisible, so the list looks mysteriously short.
- One generic filter set for every category.
- Filter options that lead to empty pages.
- Page reloading and scrolling to the top on every checkbox.
- Sort hidden inside the filter panel.
- "Sort by: Default" with no explanation.
- Filters reset when the user returns from an item or changes page.
- Filters that silently persist from a previous session.
- Autocomplete that replaces what the user typed when they press Enter.
- Range sliders with no numeric input and no keyboard support.
- Unrelated "recommended" items shown as though they matched.
- Result count missing or wrong.

## Exceptions and context

- **Small collections** need no search or filters; a well-ordered list is enough.
- **Expert tools** can default to more filters open, saved views and query syntax.
- **Editorial search** emphasizes snippets and dates over facets.
- **Location-based search** adds area, radius and map state to the query state that must be visible.
- **Instant client-side filtering** is fine for small in-memory sets.
- **Regulated or audited searches** may need to show exactly what criteria were used.

## Implementation cautions

- UI-safe: labels and accessible names, submit button, visibility and placement of existing controls, applied-filter summary built from existing state, result-count display where the count is available, wording of zero-result pages, dimming and busy indicators on existing loading state, status announcements, focus handling, the mobile presentation of existing filters.
- Functional, recommend: search relevance, typo tolerance, synonyms, suggestions, facet counts, new filters or sort options, combining logic, URL persistence, saved searches, pagination changes.
- Never add a filter, sort option, count or suggestion that the backend does not supply. Never filter or sort on the client a result set that the server paginates.
- Changing instant filtering to batch (or the reverse) changes behavior and request patterns; recommend, or implement only with approval.
- Query parameter names are contracts with bookmarks, shared links, analytics and search engines.
- Third-party search and filter widgets are styled through their supported options.

## Sources

- [NNG-18] No-results pages — make it obvious, offer ways forward, keep the tone respectful
- [NNG-19] Filter design and user intent — interactive versus batch, feedback while updating, avoiding scroll jumps
- [BAY-04] Product list UX — category-specific filters, applied-filter overview, multi-select, essential sort options
- [BAY-10] Ecommerce search research — field, autocomplete, results and no-results design
- [BAY-09] Mobile — visible search submit, persistent applied filters, typo-tolerant suggestions
- [BAY-08] Category-specific filters in travel
- [NNG-09] Discoverable, transparent filters on tables
- [NNG-30] Position loss on return from an item
- [W3C-05] Status messages — announcing result counts
- [W3C-01] WCAG 2.2 — 1.3.1, 2.1.1, 2.4.5, 3.2.2, 3.3.2, 4.1.2
