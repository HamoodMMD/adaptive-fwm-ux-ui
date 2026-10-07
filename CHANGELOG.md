# Changelog

All notable changes to this skill are recorded here. Versions follow [Semantic Versioning](https://semver.org/): a major version changes how the skill routes or what it protects, a minor version adds modules or rules, a patch corrects or clarifies.

The version is also recorded in `SKILL.md` under `metadata.version`.

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
