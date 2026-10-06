# Changelog

All notable changes to this skill are recorded here. Versions follow [Semantic Versioning](https://semver.org/): a major version changes how the skill routes or what it protects, a minor version adds modules or rules, a patch corrects or clarifies.

The version is also recorded in `SKILL.md` under `metadata.version`.

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
