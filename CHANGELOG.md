# Changelog

All notable changes to this skill are recorded here. Versions follow [Semantic Versioning](https://semver.org/): a major version changes how the skill routes or what it protects, a minor version adds modules or rules, a patch corrects or clarifies.

The version is also recorded in `SKILL.md` under `metadata.version`.

## 1.2.0 - 2026-10-09

The site as a salesperson: a walk of 66 real selling pages and a review of research on why visitors stay or leave.

### Added
- `patterns/sales-journey`: six stages a selling site must handle (greet, guide, show, answer, close, after), each with checks and the way a bad salesperson fails it; a walk-out test that records every moment a first-time visitor could give up; ease-of-getting-around checks; observed figures from 56 phone page loads.
- `references/selling-strategies.md`: thirteen selling strategies (immersive storytelling, guided choice, quiet catalog, authority by depth, the site is the demo, try it now, proof first, offer first, the letter, build your own, task first, portfolio and conversation, plain dealing). For each: the logic, what it looked like on real sites, what to check and how it fails; plus tables for identifying a strategy and for which strategy suits which offer.
- Classification now records the selling strategy a surface is attempting and whether it suits the offer.
- 32 sources on first impressions, dwell time, effort, information scent, pop-ups, login walls, scrolling effects, minimalism, tone, speed and sales.

### Changed
- The primary action now has two limits that apply together: never two instances visible at once, and never more than about two phone screens without one in view.
- Audit template: a sales-journey block with the walk-out table, "Content the owner needs to supply" and strategy recommendations.
- A blind test of the first draft led to: priority by impact with stage only as a tie-break, a rule for pricing and product pages, a small-site path, a rule of record to avoid duplicate findings, and handling for "make mine sell like <brand>".

### Rules
- The strategy belongs to the owner: the skill judges a site against its own manner and helps it execute. Recommending a different strategy is allowed; switching it is not.
- Named sites are evidence, never templates. No site is restyled toward another brand.
- A strategy is never built from invented material; missing imagery, proof or content is requested from the owner.

## 1.1.0 - 2026-10-08

Two new pattern modules, from a review of published research and a measurement of real commercial sites.

### Added
- `patterns/visual-scale`: text size, line length, line height, type scale, header height, first screen and hero, buttons and targets. Separates requirements (WCAG), published guidance and observed practice, with a table of what 28 established commercial sites ship at desktop and phone sizes.
- `patterns/pricing-and-persuasion`: price display, framing, anchoring and contrast, three options and decoys, number of choices, "free", loss framing, urgency and scarcity, affordability framing, defaults, risk reduction. Each effect is listed with how well the research supports it.
- The offer inventory: every price, plan, discount, free item, guarantee, deadline and proof element is listed with its source before any change, and only inventory items may appear in the work.
- A three-level action table for selling changes: what a fix pass may rearrange, what must be recommended to the owner, and what is never done.
- 43 sources: peer-reviewed studies on choice psychology (including the replications and critiques), usability research on pricing and comparison, consumer-protection rules on former prices, "free", reviews, drip pricing and urgency, and typography guidance.

### Changed
- Ground rule 6 and "Nothing fake" now cover the offer itself: no invented or altered price, plan, tier, feature, discount, former price, free item, trial, guarantee, deadline or stock level.
- The primary action appears once per screen; a header that does not fit one row on a phone moves an item into the menu.
- README limitations updated to describe the testing actually done.

## 1.0.3 - 2026-10-07

### Added
- Harmful side-effect exception: a fix pass may remove a side effect that destroys the user's own input (a form cleared on a failed submit, choices discarded on going back) when five conditions hold, including verified identical output. Every use is reported under its own heading.
- Rule for existing content that cannot be verified: report it, ask the owner, do not alter it; evident placeholder content is at least P1.

### Changed
- Reordering one region on narrow screens so the primary action is reachable no longer needs a question, if all content is kept and wider layouts are unchanged.

## 1.0.2 - 2026-10-07

Changes from running the skill end to end (audit, then fix) on three demo pages.

### Added
- `docs/examples/`: before and after screenshots of five demo pages, with what was found, fixed and deliberately left alone.
- Fallback when the user cannot be asked: take the conservative option, leave the contested change unmade, record the decision.
- Functional recommendations are numbered FR1, FR2.
- Implementation report: a "Decisions taken without asking" section.

### Changed
- "UI-only?" may be answered "partly".
- A recommended change that needs a handler edit must say so.
- The helper-file rule also covers fix mode; screenshots cited as evidence may be kept outside the project.
- README redesigned with an examples section.

## 1.0.1 - 2026-10-07

Clarifications from the first real audit and a blind test of 23 scenarios.

### Added
- Read-only audits leave the project untouched: helper scripts and captures go outside the repository, are named in the report and removed; no real forms, orders or payments are submitted to reach a state.
- Findings are numbered F1, F2 and recommended changes R1, R2; the skill offers to save a full audit to a file.
- Exclusions: an excluded area is neither audited nor edited, and shared components it uses are not changed without asking.
- A direct request for a new feature is treated as functional work: confirm scope, then build it for real or not at all.

### Changed
- Modes combine (scope and editing are separate choices) and "full audit" is defined.
- The classification reference is always read.
- `high-stakes` on a checkout is consistently scoped to the payment step.
- An unknown device mix on a public surface is treated as mixed.
- With a description only, classify and plan first, then ask for access.
- Reports follow the user's language, including headings.
- Added rules for landing pages on product sites, attached blogs, provider tools, restaurant reservations and chosen pickup or delivery slots.

### Fixed
- Brand fix ladder: contrast is calculated first; a color below 3:1 cannot be text at any size, and underlining does not fix contrast.
- Numeric table columns stay right-aligned in RTL (the tables and RTL modules disagreed).
- Fashion module referred to section names that did not exist.

## 1.0.0 — 2026-10-06

Initial release.

### Router
- `SKILL.md`: modes, evidence order, surface-based classification, module loading tables, workflow-first audit procedure, priority and evidence classes, implementation and verification steps.

### Routing references
- `references/classification.md`: fourteen classification dimensions, evidence signals with counter-signals, rules for primary and secondary profiles, route-level classification, confidence model, hard cases, fallback when no profile fits.
- `references/conflict-resolution.md`: order of precedence and resolutions for recurring rule conflicts.
- `references/implementation-safety.md`: protected functionality, change boundary, no fake functionality, secrets handling, implementation procedure.

### Core modules (5)
- `universal-ux`, `accessibility` (WCAG 2.2 Level A and AA requirements separated from recommendations), `performance`, `content-and-trust`, `brand-preservation`.

### Profile modules (14)
- `ecommerce`, `fashion-apparel`, `sales-lead-generation`, `service-business`, `informational-content`, `b2b-marketing`, `saas-application`, `dashboard-analytics`, `monitoring-observability`, `admin-backoffice`, `ai-product`, `booking-reservation`, `marketplace-directory`, `high-stakes`.

### Pattern modules (8)
- `forms`, `navigation`, `tables`, `search-filter-sort`, `charts-data-viz`, `loading-empty-error-states`, `responsive-mobile`, `rtl-bilingual`.

### Research
- `references/research-sources.md`: 109 indexed sources with type, date checked and verification status, plus a list of known gaps.

### Templates
- `assets/classification-template.md`, `assets/ux-audit-template.md`, `assets/implementation-report-template.md`.

### Changes from the originally proposed structure
- Reference modules are grouped into `core/`, `profiles/` and `patterns/` instead of one flat folder, so that adding a module is one file plus one table row.
- Classification, conflict resolution and implementation safety are routing documents at the top of `references/`, not numbered rule modules.
- Functionality preservation moved out of the router into `implementation-safety.md`, loaded only when editing; the router keeps the non-negotiable summary.
- Core modules are loaded by mode instead of all five on every invocation.
