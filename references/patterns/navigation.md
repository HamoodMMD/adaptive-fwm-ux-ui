# Navigation

How people know where they are, what else exists and how to get there: global and local navigation, breadcrumbs, tabs, mobile menus, deep links.

**Load when:** navigation is under review, or the audit covers a whole site or application.
**Skip when:** reviewing a single component or screen whose navigation is out of scope.

## Objectives

From any page a user can tell where they are, see the main places they can go, reach any important destination in a predictable way, and get back. Someone who arrives on a deep page from outside is oriented without visiting the home page.

## Priority principles

1. **Visible beats hidden.** Navigation that is out of sight is used less and found more slowly, on desktop especially.
2. **Labels are the navigation.** If the words do not tell users what is behind them, no layout will.
3. **One place, one name, one route in the menu.** Duplicates and near-synonyms make users doubt.
4. **The current location is always marked.**
5. **Stability.** The same navigation in the same place and order on every page.

## Checks

### Global navigation
- On wide screens the top-level destinations are visible, across the top or down the side, not collapsed behind a menu icon.
- The set of top-level items is short enough to scan and covers what most users come for; low-traffic items move to a footer, a "More" group or a utility area.
- Items are ordered by importance or by the natural sequence of the task, consistently on every page.
- The logo links to the home or main page.
- Utility navigation (account, cart, language, help, search) is separate from content navigation and in a conventional place.
- A skip link lets keyboard users bypass repeated navigation.

### Labels and naming
- Labels use the audience's words, are specific, and are distinct from one another. "Solutions", "Resources" and "Products" side by side usually fail this.
- Branded or invented names are avoided for navigation, or paired with a plain description.
- A link's label matches the title of the page it opens.
- Labels are short, in sentence or title case consistently, and not truncated.
- Icons accompany text in primary navigation; icon-only navigation is limited to universally understood symbols and still has accessible names and tooltips.

### Active state and orientation
- The current section is marked in the global navigation and the current page in local navigation, by more than color alone (weight, indicator bar, background).
- The mark is exposed to assistive technology (`aria-current`).
- The page heading confirms where the user is and matches the navigation label.
- Parent sections stay marked when a child page is open.

### Hierarchy and local navigation
- Sections with several pages have local navigation showing siblings and children.
- Depth is kept shallow where content volume allows; users can see the level above.
- Local navigation is placed consistently (sidebar or sub-navigation bar) and collapses sensibly on small screens.
- Large menus (mega menus) are organized into labeled groups, open on click or after a deliberate hover, stay open while the pointer moves toward them, and are fully keyboard operable.

### Breadcrumbs
- Used on sites with three or more levels; unnecessary on flat sites.
- They show the site hierarchy, not the user's click history.
- They start with the home or top level; the current page is last and is not a link.
- They supplement the main navigation and never replace it.
- A page reachable by several paths shows one consistent path.
- On small screens they do not wrap onto several lines: shorten to the parent level or scroll horizontally, with adequately sized tap targets.

### Tabs
- **In-page tabs** switch between related views of the same object without leaving the page. They use the ARIA tabs pattern, with arrow-key movement.
- **Navigation tabs** go to different pages. They are links styled as tabs, with the current one marked; they do not use ARIA tab roles.
- Tabs suit a small number of parallel, clearly named sections that users do not need to see at the same time.
- Labels are one or two words; tabs sit in a single row; the selected tab is unmistakable and visually connected to its content.
- The most used tab is first and selected by default.
- On small screens, too many tabs scroll horizontally with a visible cue, or become a select or accordion; they never wrap into several rows.
- The selected tab is reflected in the URL where users would expect to link or return to it.

### Mobile navigation
- With four or five top-level destinations or fewer, show them all: a tab bar or a visible row.
- With more, a menu button is acceptable. It is labeled "Menu" (not only an icon) where space allows, has an accessible name and expanded state, and the most important destinations are also linked directly in the page.
- The open menu covers enough of the screen to be clearly a new layer, has an obvious close control, traps focus while open, closes with Escape and the back gesture, and returns focus to the button.
- Nested levels are navigated with clear back controls or accordions; the user can see which level they are in.
- Bottom tab bars hold primary destinations only, mark the current one, and do not hide on scroll in a way that surprises.
- The current section is highlighted inside the menu.

### Sticky headers
- A sticky header is justified where navigation, search or key actions are needed mid-page.
- It is as short as it can be, has an opaque background that separates it from content, and does not animate distractingly.
- It never hides the element that has keyboard focus, and anchor links land below it.
- On small screens consider a header that hides on scroll down and returns on scroll up.

### Deep links, URLs and history
- Every page and significant view has its own URL that can be bookmarked and shared.
- Browser back and forward work as expected, including through filters, tabs and overlays where users would expect a history step.
- Refreshing does not lose the user's place.
- Titles of pages are specific and distinct, so tabs and history entries are identifiable.

### Contextual navigation
- Related pages, next and previous steps, and "up" links are offered where the task continues.
- In-page links for long pages are near the top and reflect the headings.
- Links within content describe their destination.
- Footers provide a secondary route to important and legal pages and are reachable (not pushed away by endless loading).

### Settings and account navigation
- Settings have their own local navigation grouped by scope and topic, with the current section marked.
- Account controls are in a conventional corner and labeled with the user's name or avatar plus an accessible name.

### Consistency and multiple routes
- Repeated navigation appears in the same relative order on every page. (WCAG 3.2.3, Level AA.)
- The same destination has the same label everywhere; the same label never leads to different places. (WCAG 3.2.4, Level AA.)
- There is more than one way to find a page within a site: navigation plus search, a sitemap or an index. (WCAG 2.4.5, Level AA.)
- The same destination is not listed twice in one menu under different names.

## Anti-patterns

- A menu icon hiding five links on a wide desktop screen.
- Navigation labels that only insiders understand.
- No indication of the current page.
- Two menu items that lead to the same place.
- Hover menus that vanish as the pointer travels to them, or that cannot be opened by keyboard.
- Breadcrumbs showing click history, or with the current page as a link to itself.
- Tabs wrapping into two or three rows.
- ARIA tab roles on what are really page links.
- An unlabeled menu icon as the only way in on mobile.
- Menus that open without moving or trapping focus.
- Sticky headers taking a third of a phone screen.
- State that only exists in memory: no URL, lost on refresh, broken back button.
- Navigation order that changes between pages.
- `role="menu"` on ordinary site navigation.

## Exceptions and context

- **Single-purpose landing pages** may reduce navigation on purpose; a route to the main site and legal pages remains.
- **Focused flows** (checkout, onboarding, booking) correctly remove global navigation to reduce exits, keeping a way out and back.
- **Applications with many areas** may use a collapsible sidebar; the collapsed state still shows recognizable icons with tooltips and accessible names.
- **Very small sites** need neither breadcrumbs nor local navigation nor search.
- **Immersive or editorial experiences** may hide navigation while reading and reveal it on interaction, provided it is reliably recoverable.
- **Expert tools** can add a command palette or shortcuts as accelerators, never as the only route.

## Implementation cautions

- UI-safe: labels (text only), visual treatment of active state, `aria-current`, skip links, landmark roles, focus management for an existing menu, spacing, ordering within a menu where order is not data-driven, responsive presentation of an existing menu.
- Functional, recommend: changing URLs, routes, redirects or information architecture; adding search, breadcrumbs backed by new data, or URL-persisted state; changing which items appear for which roles.
- Reordering or renaming navigation affects analytics, documentation, support scripts and user habit; flag it even when implementing.
- Navigation is often driven by a CMS, a route config or a permissions map. Change the template and report data-level issues.
- Renaming a label is not renaming its route or key.
- Converting hover menus to click, or adding focus trapping, changes event handling: keep it minimal and test with keyboard and touch.
- Sticky positioning interacts with anchor offsets, modals and the on-screen keyboard; check all three.

## Sources

- [NNG-17] Hidden navigation hurts discoverability; when to show navigation on mobile
- [NNG-15] Breadcrumbs — eleven guidelines
- [NNG-16] Tabs — in-page versus navigation tabs, labels, single row, selected state
- [NNG-32] Sticky headers
- [NNG-33] Sheets and overlays — dismissal, back support, no stacking
- [W3C-16] APG tabs pattern
- [W3C-15] APG modal dialog pattern — focus handling for overlays
- [W3C-11] Consistent navigation
- [W3C-04] Focus not obscured
- [W3C-01] WCAG 2.2 — 2.4.1, 2.4.2, 2.4.4, 2.4.5, 2.4.6, 3.2.3, 3.2.4, 4.1.2
- [BAY-09] Mobile — highlighting the current scope in navigation, "view all" at each level
- [NNG-12] B2B — audience segmentation in navigation confuses more than it guides
