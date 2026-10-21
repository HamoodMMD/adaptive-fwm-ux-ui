# Component libraries

Ready-made, free UI component libraries: which kind suits which project and page type, what each one gives you for accessibility and right-to-left layouts, and what to check before relying on one. A good library saves the hardest work (keyboard behavior, focus, screen reader support), but it does not make a product usable or accessible by itself.

**Load when:** planning a new build or a new section, the user asks which library to use, or a fix needs a complex component (dialog, combobox, menu, date picker, data grid, toast) that the project does not have yet.
**Skip when:** the project already has a component library or design system and the task is an audit or fix pass inside it. Then audit how it is used, with the other modules.
**Pair with (when present):** `core/accessibility`, `core/brand-preservation`, `patterns/rtl-bilingual`, `patterns/tables`, `patterns/charts-data-viz`, `patterns/notifications`, `patterns/visual-scale`.

## Objectives

The project uses one coherent set of components that matches its framework, its brand freedom, its language direction and its page type. Complex widgets come from a well-maintained, tested library instead of being hand-built. The license fits the use, paid features are known before anyone depends on them, and the team still tests the finished product.

## Priority principles

1. **Use what the project already has.** An existing library or design system is part of the brand inventory. Fix how it is used; never replace it in a fix pass.
2. **One component system per product.** Two libraries that each style buttons and dialogs produce two looks and two sets of keyboard behavior.
3. **Borrow behavior, own the look.** Where the brand is distinctive, prefer an unstyled (headless) library that supplies behavior and leaves styling to the project. Where speed matters more than a distinctive look, a styled library is fine.
4. **An accessible library is a starting point, not a result.** Libraries supply accessible parts; the team still supplies labels, names, order, contrast and content, and still tests.
5. **Check license, upkeep and direction before choosing.** These change. Confirm them on the day you recommend a library, and say when you last checked.

## Checks

### Choosing the kind of library

| What the project needs | Kind to prefer | Free examples (framework) |
|---|---|---|
| A distinctive brand and full control of styling | Unstyled behavior primitives | React Aria, Radix Primitives, Base UI, Ariakit, Headless UI (React); Reka UI (Vue); Bits UI (Svelte); Angular CDK (Angular) |
| Ready-looking components the team can edit as its own code | Copied-in components on top of primitives | shadcn/ui (React, on Base UI, Radix or React Aria) |
| A full styled kit for an app, admin tool or dashboard | Styled component library | Mantine, Material UI, Ant Design, Chakra UI, HeroUI, Fluent UI (React); Vuetify, PrimeVue, Element Plus, Quasar, Nuxt UI (Vue); Angular Material (Angular) |
| Styling only, any framework, with plain HTML | Tailwind class library | daisyUI, Flowbite. Interactive behavior still has to come from somewhere accessible |
| A public service where trust and plain use matter most | Government design system | GOV.UK Frontend (UK), USWDS (US). Their patterns are reusable; their branding is not |
| A company design system to follow closely | Published design system | Carbon (IBM), Fluent (Microsoft), Primer (GitHub) |
| Framework-free or several frameworks | Web components | Web Awesome (successor to Shoelace) |
| One hard widget only | Focused library | TanStack Table or AG Grid Community (tables); Recharts or Apache ECharts (charts); React DayPicker (dates); Sonner (toasts); cmdk (command menu); Floating UI (positioning); Motion (animation) |

### Matching the page type
- **Marketing, landing and store pages:** the look carries the brand, so prefer unstyled primitives or copied-in components, and animation used with restraint (`patterns/visual-scale`). A large styled kit tends to make a marketing page look like an admin panel.
- **Software products, admin tools and dashboards:** a styled kit with a strong table, form and date set saves the most time. Check its data table against `patterns/tables` before committing.
- **Data-heavy screens:** choose the table and chart libraries first, because they are the hardest to replace later. Note which features are paid (below).
- **High-stakes and public services:** prefer a library with published accessibility testing, or a government design system's patterns.
- **Arabic, Hebrew and other right-to-left products:** confirm right-to-left support before choosing. React Aria and Mantine state it as built in; shadcn/ui converts classes to logical start and end values through its tool for newer projects, with some components migrated by hand. Then check the result with `patterns/rtl-bilingual`.

### Before recommending a library
- **Framework and version** match the project's.
- **License** is known. Most libraries here are MIT or Apache 2.0. Some have paid tiers inside the same family: AG Grid Enterprise (grouping, pivoting, Excel export, server-side rows and more), MUI X Pro and Premium data grid packages. Name the paid features the design would need.
- **Upkeep:** recent releases and an active repository. Archived or unmaintained projects are a finding for new work. In the snapshot below, Shoelace is archived (its successor is Web Awesome), and the Vaul drawer says it is unmaintained.
- **Accessibility evidence:** what the library claims and how it tests. Claims vary from "extensively tested with many popular screen readers and devices" (React Aria) to a one-line "fully accessible" with no detail. Prefer evidence over adjectives.
- **Reduced motion:** animation libraries respect the user's setting. Motion follows the operating-system setting when `reducedMotion="user"` is set and offers `useReducedMotion` for manual control.
- **Theming:** colors, type, spacing and radius come from tokens the project controls, so the brand is not overridden by library defaults.

### After choosing
- Run the same checks as for hand-built components: names and labels, focus order, keyboard behavior, contrast, zoom and reflow, and a screen reader pass on the key flows (`core/accessibility`).
- Use components for their stated purpose. A menu component used for site navigation, or a dialog used as a page, breaks the keyboard and screen reader behavior its role promises.
- Keep one source for each component type; remove duplicates as functional work.

## Anti-patterns

- Replacing a project's existing library during a UX fix.
- Mixing two styled kits in one product.
- Hand-building a combobox, date picker or dialog when a tested library is available, then shipping it without keyboard support.
- Picking a data grid for a demo, then finding grouping and export are paid features.
- Building a public marketing site on an admin kit's default look.
- Adopting an archived or unmaintained package for new work.
- Treating "built on an accessible library" as proof the product is accessible.

## Exceptions and context

- **Existing design systems win.** A company system with its own components is used even where a public library is stronger; report gaps instead of swapping.
- **Tiny sites** may need no library: native HTML elements (buttons, links, `details`, `dialog`, form controls) are accessible by default and are often enough.
- **Mobile apps** use their platform's native components first (SwiftUI, Jetpack Compose, Flutter's Material and Cupertino widgets); this module is about the web.
- **Government design systems** are free to reuse as code, but not as identity. GOV.UK Frontend documents how a service outside GOV.UK uses it: a generic header, its own font instead of GDS Transport, its own icons and sharing image, and its own brand color instead of GOV.UK blue.

## Implementation cautions

- Recommend only: choosing, adding, upgrading or replacing a library, and adding a paid tier. These change dependencies, bundle size and behavior.
- Safe UI work inside an existing library: using the component it already provides for the job, passing the labels and props it needs for accessibility, and setting theme tokens.
- Facts in this module are a snapshot taken on 2026-10-21. Re-check license, version and maintenance status before recommending, and say the date you checked.

## Snapshot (checked 2026-10-21)

License from the npm registry, activity from the GitHub repository. "Active" means a commit within the last month.

| Library | License | Status |
|---|---|---|
| shadcn/ui, Radix Primitives, Base UI, Ariakit, Material UI, Mantine, Chakra UI, Ant Design, Fluent UI, Primer React | MIT | Active |
| React Aria Components, Carbon, HeroUI, Apache ECharts | Apache 2.0 | Active |
| Headless UI | MIT | Last commit April 2026 |
| Reka UI, Bits UI, Nuxt UI, Vuetify, Element Plus, Quasar, Angular CDK and Material | MIT | Active |
| PrimeVue, PrimeReact | MIT (repository) | Last commit September 2026 |
| daisyUI | MIT | Active |
| Flowbite | MIT | Last commit June 2026 |
| GOV.UK Frontend | MIT | Active |
| USWDS | Public domain, with some parts under other licenses (see its license file) | Active |
| TanStack Table, Recharts, React DayPicker, Floating UI, Motion, Web Awesome | MIT | Active |
| AG Grid Community | MIT (Enterprise packages are commercial) | Active |
| Sonner | MIT | Last commit August 2026 |
| cmdk | MIT | Last commit October 2025 |
| Tremor | Apache 2.0 | Last commit October 2025 |
| Vaul | MIT | Unmaintained (stated in its README) |
| Shoelace | MIT | Archived; replaced by Web Awesome |

## Sources

- [LIB-01] shadcn/ui: code copied into the project; [LIB-02] shadcn/ui changelog: Base UI, Radix and React Aria bases; [LIB-03] shadcn/ui right-to-left support
- [LIB-04] React Aria: testing, internationalization and right-to-left; [LIB-05] Radix Primitives; [LIB-06] Base UI; [LIB-08] Headless UI; [LIB-09] Ariakit; [LIB-10] Reka UI; [LIB-11] Bits UI
- [LIB-12] Mantine right-to-left; [LIB-13] Ant Design; [LIB-14] daisyUI; [LIB-15] Material UI
- [LIB-07] Motion and reduced motion; [LIB-16] AG Grid Community and Enterprise; [LIB-17] Vaul maintenance notice; [LIB-18] license and activity snapshot from the npm registry and GitHub
- [CARB-05] Accessible components do not make an accessible product; [W3C-14] a role is a promise, and test before production; [LIB-19] using GOV.UK Frontend without GOV.UK branding

The "kind of library" table and page-type advice are this skill's synthesis (evidence class: Judgment); the snapshot is a dated measurement.
