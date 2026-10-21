# Changelog

All notable changes to this skill are recorded here. Versions follow [Semantic Versioning](https://semver.org/): a major version changes how the skill routes or what it protects, a minor version adds modules or rules, a patch corrects or clarifies.

The version is also recorded in `SKILL.md` under `metadata.version`.

## 1.10.0 - 2026-10-21

### Added
- `patterns/visual-styles`: expressive styles and effects (particles, liquid morph, neon glow, Y2K chrome, kinetic type, paper cutout, holographic, isometric, ASCII art, clay 3D, retro VHS, comic book, split-flap, hand-drawn, blueprint, physics, pixel art, Bauhaus, Art Deco, neo-brutalism, glassmorphism, neumorphism, glitch, typewriter, marquee, cursor effects, WebGL and more), where each fits and the failures to check, with the rule that the style is kept and fixed from within.
- 13 sources.

## 1.9.0 - 2026-10-21

### Added
- `patterns/account-security`: sign-in, passwords, one-time codes, passkeys, recovery, session expiry, security settings and API keys, built on current authentication standards and accessible-authentication rules.
- `patterns/notifications`: a loudness ladder from badge to dialog, toasts, banners, confirmations versus undo, email and push, and alerting products.
- Cognitive accessibility (Part D of `core/accessibility`), from W3C's guidance on cognitive and learning disabilities, and full keyboard behavior for command menus and comboboxes in Part C.
- A "user skill and confidence" dimension in classification.
- Consent and privacy choices in `core/content-and-trust`.
- Hidden versus disabled controls, offline sync, download sizes and double submission in `patterns/loading-empty-error-states`.
- Which research method answers which question, in `measuring-results.md`, and an optional "validate with" field on findings.
- `patterns/component-libraries`: which kind of free UI library suits which project and page type (unstyled primitives, copied-in components, styled kits, government systems, focused widgets), what to check before choosing (license and paid tiers, upkeep, accessibility evidence, right-to-left, reduced motion), and a dated license and maintenance snapshot of 44 libraries. It never replaces a library a project already uses.
- `patterns/dark-mode-and-themes`: follow the system appearance, switchers with a System option, no flash on load, dark surfaces and desaturated accents, contrast in every theme, logos, images, charts and embeds.
- `patterns/motion`: what motion is for, durations and easing, never blocking input, scroll-triggered reveals, carousels and autoplay (2.2.2), reduced motion (2.3.3) and flashing.
- 47 sources.

## 1.8.1 - 2026-10-14

### Fixed
- A blind test missed a headline whose lines collided: the descender of "p" in one line merged into the "h" below it. `patterns/visual-scale` now requires that lines of a heading never touch at any breakpoint, explains which typefaces and layouts collide first, and says how to fix it in a display-led brand. The verification step in `SKILL.md` now requires looking at enlarged captures of large headings, not only measuring them.

## 1.8.0 - 2026-10-14

### Added
- `patterns/visual-scale`: four new groups of checks. Typeface, case and weight; contrast, text over images and dark surfaces; fluid sizes that still zoom; spacing and grouping.
- 11 sources on typefaces and reading speed, low-contrast text, text over images, light and dark surfaces, viewport-unit type and zoom, visual hierarchy and spacing scales.
- From a blind test on a page built with a design skill: very large display text that does not zoom, fixing a too-tall sticky header, forms that show success but send nothing, which selling modules count against the reading budget, priority for low-impact requirement failures, and tips for testing in a headless browser.
- Rules in `conversion-pass.md` for the cases two blind test runs found unclear: owner instructions that outrank a rule, form defaults, sticky headers on phones, and which action-placement limit gives way.

### Changed
- The README is now a short overview. Usage, selling, how it works, installation, and questions moved to their own pages under `docs/`.

## 1.7.0 - 2026-10-14

### Added
- `references/measuring-results.md`: how to record a baseline, which method a site's traffic allows, how to read a before-and-after comparison without fooling yourself, and what may honestly be reported.
- A copyable checklist in `references/conversion-pass.md`, and three closing checks in Step 9: reconcile every owner answer against the page, trace every number and promise back to the facts ledger, then repeat the walk-out test.
- A reading budget in the router and a short reading list for the conversion pass, so narrow tasks load fewer modules.
- A contents list at the top of the long reference files.
- 7 sources on measurement, small-sample testing and skill authoring.

### Changed
- The first example in the README is now a conversion pass on a service-business homepage.

## 1.6.0 - 2026-10-13

### Added
- `references/conversion-pass.md`: an eleven-step procedure for turning an ordinary page into one that sells. It separates what the page can fix alone (being understood, being easy) from what needs the owner's real material (being believed), and adds a facts ledger, seven questions to ask the owner once, rules for what may and may not be rewritten, and a content brief.
- A "Conversion pass" mode in the router.
- Writing rules in `core/content-and-trust` (concise, scannable, objective; most important first; real photographs) and a single-column rule in `patterns/forms`.
- 7 sources on web writing, photographs and form layout.

## 1.5.0 - 2026-10-11

Conversion, retention and the pages where they are decided, from a fourth research round and two new measurements of real sites.

### Added
- `patterns/product-page`: first screen, images, price and offers, options, availability and delivery, the buy action, description, reviews and related products, with figures from 18 real product pages on a phone.
- `patterns/onboarding`: before sign-up, the sign-up form, verification, first-run setup, the first real task, guidance, permissions, trials in the first session and coming back, with figures from the sign-up pages of 22 software products.
- `patterns/conversion-and-retention`: where customers are lost, what the evidence supports for conversion and for retention, measuring, experiments, how to talk about business impact, and a table of popular business figures to handle with care.
- `pricing-and-persuasion`: the pricing page as a whole.
- 16 sources, including a password standard, usability benchmarks, a trial-length field experiment and the origins of several widely quoted business statistics.

### Rules
- Conversion and retention are outcomes to observe. A report states the mechanism and what to watch; it never predicts a figure or imports a benchmark as a target.
- No account was created on any site during the sign-up survey; only public first steps were read.

## 1.4.0 - 2026-10-09

A consistency pass across all modules, and a third research round on selling psychology, including virtual items.

### Added
- `patterns/virtual-goods`: real-money pricing for virtual currency and items, what the buyer gets, randomized rewards and odds, the purchase act, passes and renewals, engagement pressure, children. Built from enforcement actions, consumer-authority principles and research on loot boxes and payment.
- `ux-psychology`: ease of use as a predictor of adoption, and a table of popular claims that do not hold up (eight-second attention span, three-click rule, seven-item menus, "red buttons convert", the three-second figure, perfect ratings, trust badges, social-norm messages).
- `pricing-and-persuasion`: ratings and their spread, joining and leaving a subscription, and the evidence on hidden fees and split prices.
- 22 sources.

### Fixed (contradictions between modules)
- Existing fake urgency or scarcity: one rule, "Existing pressure that the code proves false", says when a fix pass may remove it. Previously the examples removed it while the written rules said to leave unverified content alone.
- "Recommended" plans: the lead-generation profile implied the skill should mark one; it now defers to the owner, as the pricing module requires.
- Line length: two modules gave different upper bounds; both now say 50 to 75 characters with 80 as the limit.
- Progress indicators: the forms rule (show the step) and the psychology evidence (mixed effect on completion) are reconciled as orientation versus persuasion.
- Seven new entries in `conflict-resolution.md` for conflicts the newer modules created.
- Implementation report: a "Deceptive elements removed" section.

## 1.3.0 - 2026-10-09

Psychology in interface decisions, from checking a set of widely repeated claims against the studies behind them.

### Added
- `patterns/ux-psychology`: defaults, progress and momentum, giving before asking, ownership and effort, loss and consequences, honest comparison, memory and attention, waiting, engagement and habit. Each effect is listed with how well the research has held up.
- A five-step check for any psychology claim (which study, the right effect, has it held up, does the situation match, is the example honest) and a disclosure test: would the visitor feel helped or tricked if they saw how the element works.
- 17 sources, including the original studies and the replications or meta-analyses that qualify them.

### Rules
- The honest version of every effect uses true facts: real progress, real availability, real consequences, comparisons in the same units.
- No invented threats, shaming decline options, fake delays, inflated progress or compulsion mechanics.

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
