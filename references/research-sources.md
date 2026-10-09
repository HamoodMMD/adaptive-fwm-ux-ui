# Research sources

The index of sources behind the rule modules. Modules cite entries by ID in their `Sources` section, for example `[NNG-09]`. An audit report does not need to cite these unless the user asks or a claim is likely to be challenged.

## How to read this index

**Type**

| Value | Meaning |
|---|---|
| normative | A formal standard. Its requirements can be passed or failed. |
| research | Findings from usability studies, benchmarks or peer-reviewed work. |
| design-system | Guidance published by a design system or platform owner. |
| implementation | Technical guidance on how to build something correctly. |

**Verified** — how each source was checked on the date shown.

| Value | Meaning |
|---|---|
| fetched | The page was retrieved and its content read. |
| search | The URL and a summary were returned by a web search; the page itself was not opened. |
| partial | The URL resolved, but the content could not be machine-read reliably (client-rendered page or landing page only). Guidance attributed to it rests on established knowledge of the document and should be re-read by a person. |
| blocked | The server refused automated access. Cited from established knowledge of the document. |

**Notes on use**

- Dates in parentheses after a title are the publication or last-updated dates shown by the source.
- Benchmark percentages published by research firms change with every update. The modules deliberately state principles and avoid quoting those figures.
- Nothing in the modules is drawn from uncited blogs, inspiration galleries or opinion pieces. Where no strong source exists, the module says the guidance is this skill's judgment.

## Agent Skills format

| ID | Source | Title / topic | URL | Type | Checked | Verified | Guidance derived |
|---|---|---|---|---|---|---|---|
| AS-01 | Agent Skills | Specification | https://agentskills.io/specification | normative | 2026-10-06 | fetched | Frontmatter fields and limits; name must match directory; progressive disclosure; SKILL.md under 500 lines; one-hop file references |
| AS-02 | Anthropic | Claude Code: skills | https://code.claude.com/docs/en/skills | implementation | 2026-10-06 | fetched | Skill locations; which frontmatter fields are portable; description truncation |
| AS-03 | OpenAI | Codex: build skills | https://learn.chatgpt.com/docs/build-skills | implementation | 2026-10-06 | fetched | `.agents/skills` discovery paths; front-load trigger words in the description |

## Universal usability

| ID | Source | Title / topic | URL | Type | Checked | Verified | Guidance derived |
|---|---|---|---|---|---|---|---|
| NNG-01 | Nielsen Norman Group | 10 Usability Heuristics for User Interface Design (1994, reviewed 2024) | https://www.nngroup.com/articles/ten-usability-heuristics/ | research | 2026-10-06 | fetched | Structure of the universal module |
| NNG-02 | Nielsen Norman Group | Progressive Disclosure (2006) | https://www.nngroup.com/articles/progressive-disclosure/ | research | 2026-10-06 | fetched | Frequent features first; no more than two levels; labels with clear scent |
| NNG-03 | Nielsen Norman Group | Response Times: The 3 Important Limits (1993) | https://www.nngroup.com/articles/response-times-3-important-limits/ | research | 2026-10-06 | fetched | 0.1 s, 1 s and 10 s thresholds for feedback |
| NNG-04 | Nielsen Norman Group | 8 Design Guidelines for Complex Applications (2020) | https://www.nngroup.com/articles/complex-application-design/ | research | 2026-10-06 | fetched | Learning by doing; flexible pathways; reduce clutter without removing capability |
| NNG-05 | Nielsen Norman Group | Skeleton Screens 101 (2023) | https://www.nngroup.com/articles/skeleton-screens/ | research | 2026-10-06 | fetched | Which loading indicator for which wait |
| NNG-06 | Nielsen Norman Group | Confirmation Dialogs Can Prevent User Errors — If Not Overused (2018) | https://www.nngroup.com/articles/confirmation-dialog/ | research | 2026-10-06 | fetched | Selective, specific confirmation; action-labeled buttons; undo |
| NNG-07 | Nielsen Norman Group | Error-Message Guidelines (2023) | https://www.nngroup.com/articles/error-message-guidelines/ | research | 2026-10-06 | fetched | Visible, plain, specific, constructive errors; preserve input |
| NNG-08 | Nielsen Norman Group | Designing Empty States in Complex Applications (2021) | https://www.nngroup.com/articles/empty-state-interface-design/ | research | 2026-10-06 | fetched | Empty states communicate status, teach, and offer a path |
| NNG-14 | Nielsen Norman Group | Onboarding Tutorials vs. Contextual Help (2023) | https://www.nngroup.com/articles/onboarding-tutorials/ | research | 2026-10-06 | fetched | Contextual help over upfront tours |
| NNG-23 | Nielsen Norman Group | Preventing User Errors: Avoiding Unconscious Slips (2015) | https://www.nngroup.com/articles/slips/ | research | 2026-10-06 | fetched | Constraints, suggestions, defaults, forgiving formats |
| NNG-31 | Nielsen Norman Group | Accelerators Maximize Efficiency in User Interfaces (2024) | https://www.nngroup.com/articles/ui-accelerators/ | research | 2026-10-06 | fetched | Shortcuts as additional paths; discoverability |
| NNG-35 | Nielsen Norman Group | Modal & Nonmodal Dialogs (2017) | https://www.nngroup.com/articles/modal-nonmodal-dialog/ | research | 2026-10-06 | fetched | When interruption is justified |
| ISO-01 | ISO | ISO 9241-11:2018 Ergonomics of human-system interaction — Usability: definitions and concepts | https://www.iso.org/standard/63500.html | normative | 2026-10-06 | blocked | Usability as effectiveness, efficiency and satisfaction in a specified context of use |

## Accessibility

| ID | Source | Title / topic | URL | Type | Checked | Verified | Guidance derived |
|---|---|---|---|---|---|---|---|
| W3C-01 | W3C | Web Content Accessibility Guidelines (WCAG) 2.2 | https://www.w3.org/TR/WCAG22/ | normative | 2026-10-06 | fetched | Every Level A and AA requirement in the accessibility module |
| W3C-02 | W3C WAI | What's New in WCAG 2.2 | https://www.w3.org/WAI/standards-guidelines/wcag/new-in-22/ | normative | 2026-10-06 | fetched | The nine added criteria; removal of 4.1.1 |
| W3C-03 | W3C WAI | Understanding 2.5.8 Target Size (Minimum) | https://www.w3.org/WAI/WCAG22/Understanding/target-size-minimum.html | normative | 2026-10-06 | fetched | 24 by 24 CSS pixels and the five exceptions |
| W3C-04 | W3C WAI | Understanding 2.4.11 Focus Not Obscured (Minimum) | https://www.w3.org/WAI/WCAG22/Understanding/focus-not-obscured-minimum.html | normative | 2026-10-06 | fetched | Sticky and overlay content must not fully hide focus |
| W3C-05 | W3C WAI | Understanding 4.1.3 Status Messages | https://www.w3.org/WAI/WCAG22/Understanding/status-messages.html | normative | 2026-10-06 | fetched | Roles for announcing results, progress and errors |
| W3C-06 | W3C WAI | Understanding 1.4.10 Reflow | https://www.w3.org/WAI/WCAG22/Understanding/reflow.html | normative | 2026-10-06 | fetched | 320 CSS pixels; exception for two-dimensional content |
| W3C-07 | W3C WAI | Understanding 1.4.11 Non-text Contrast | https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast.html | normative | 2026-10-06 | fetched | 3:1 for components and graphics; logo and inactive exemptions |
| W3C-08 | W3C WAI | Understanding 3.3.4 Error Prevention (Legal, Financial, Data) | https://www.w3.org/WAI/WCAG22/Understanding/error-prevention-legal-financial-data.html | normative | 2026-10-06 | fetched | Reversible, checked or confirmed |
| W3C-09 | W3C WAI | Understanding 1.4.13 Content on Hover or Focus | https://www.w3.org/WAI/WCAG22/Understanding/content-on-hover-or-focus.html | normative | 2026-10-06 | fetched | Dismissible, hoverable, persistent |
| W3C-10 | W3C WAI | Understanding 3.3.8 Accessible Authentication (Minimum) | https://www.w3.org/WAI/WCAG22/Understanding/accessible-authentication-minimum.html | normative | 2026-10-06 | fetched | Allow paste and password managers; no puzzle-only checks |
| W3C-11 | W3C WAI | Understanding 3.2.3 Consistent Navigation | https://www.w3.org/WAI/WCAG22/Understanding/consistent-navigation.html | normative | 2026-10-06 | fetched | Same relative order of repeated navigation |
| W3C-12 | W3C WAI | Understanding 3.1.2 Language of Parts | https://www.w3.org/WAI/WCAG22/Understanding/language-of-parts.html | normative | 2026-10-06 | fetched | Mark passages in another language |
| W3C-13 | W3C WAI | How to Meet WCAG (Quick Reference) | https://www.w3.org/WAI/WCAG22/quickref/ | normative | 2026-10-06 | fetched | Cross-check of criteria and levels |
| W3C-14 | W3C WAI | ARIA Authoring Practices Guide: Read Me First | https://www.w3.org/WAI/ARIA/apg/practices/read-me-first/ | design-system | 2026-10-06 | fetched | No ARIA is better than bad ARIA; a role is a promise |
| W3C-15 | W3C WAI | APG: Dialog (Modal) pattern | https://www.w3.org/WAI/ARIA/apg/patterns/dialog-modal/ | design-system | 2026-10-06 | fetched | Focus in, trap, Escape, focus return |
| W3C-16 | W3C WAI | APG: Tabs pattern | https://www.w3.org/WAI/ARIA/apg/patterns/tabs/ | design-system | 2026-10-06 | fetched | Roles and keyboard behavior for in-page tabs |
| W3C-17 | W3C WAI | Forms tutorial | https://www.w3.org/WAI/tutorials/forms/ | implementation | 2026-10-06 | fetched | Labeling, grouping, instructions, validation, notifications |
| W3C-18 | W3C WAI | Tables tutorial | https://www.w3.org/WAI/tutorials/tables/ | implementation | 2026-10-06 | fetched | Header cells, scope, captions, complex tables |
| W3C-19 | W3C WAI | Images tutorial: complex images | https://www.w3.org/WAI/tutorials/images/complex/ | implementation | 2026-10-06 | fetched | Short plus long description for charts |

## Performance and responsive implementation

| ID | Source | Title / topic | URL | Type | Checked | Verified | Guidance derived |
|---|---|---|---|---|---|---|---|
| WEB-01 | Google web.dev | Web Vitals (2024) | https://web.dev/articles/vitals | implementation | 2026-10-06 | fetched | LCP, INP, CLS thresholds at the 75th percentile |
| WEB-02 | Google web.dev | Interaction to Next Paint (2025) | https://web.dev/articles/inp | implementation | 2026-10-06 | fetched | What counts as an interaction; immediate visual feedback |
| WEB-03 | Google web.dev | Optimize Cumulative Layout Shift (2025) | https://web.dev/articles/optimize-cls | implementation | 2026-10-06 | fetched | Reserve space; causes of layout shift |
| WEB-04 | Google web.dev | Optimize Largest Contentful Paint (2025) | https://web.dev/articles/optimize-lcp | implementation | 2026-10-06 | fetched | Do not lazy-load the hero; make it discoverable and prioritized |
| WEB-05 | Google web.dev | How to create high-performance CSS animations | https://web.dev/articles/animations-guide | implementation | 2026-10-06 | fetched | Animate transform and opacity; use will-change sparingly |
| WEB-06 | Google web.dev | prefers-reduced-motion | https://web.dev/articles/prefers-reduced-motion | implementation | 2026-10-06 | fetched | Why and how to honor reduced motion; replace, do not just remove |
| WEB-07 | Google web.dev | Payment and address form best practices | https://web.dev/articles/payment-and-address-form-best-practices | implementation | 2026-10-06 | fetched | Autocomplete tokens, input types, single fields |
| WEB-08 | Google web.dev | Responsive web design basics | https://web.dev/articles/responsive-web-design-basics | implementation | 2026-10-06 | fetched | Viewport, content-driven breakpoints, do not hide content, line length |
| MDN-01 | MDN Web Docs | CSS logical properties and values | https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_logical_properties_and_values | implementation | 2026-10-06 | fetched | Flow-relative properties for RTL |

## Content, forms and service patterns

| ID | Source | Title / topic | URL | Type | Checked | Verified | Guidance derived |
|---|---|---|---|---|---|---|---|
| GOV-01 | GOV.UK Design System | Recover from validation errors | https://design-system.service.gov.uk/patterns/validation/ | design-system | 2026-10-06 | fetched | Validate on submit; error summary; page title; keep entered data |
| GOV-02 | GOV.UK Design System | Error message component | https://design-system.service.gov.uk/components/error-message/ | design-system | 2026-10-06 | fetched | Specific, plain error wording matched to the label |
| GOV-03 | GOV.UK Design System | Question pages | https://design-system.service.gov.uk/patterns/question-pages/ | design-system | 2026-10-06 | fetched | One thing per page; mark optional; hint text; simple progress |
| GOV-04 | GOV.UK Design System | Check answers | https://design-system.service.gov.uk/patterns/check-answers/ | design-system | 2026-10-06 | fetched | Review step with change links |
| GOV-05 | GOV.UK Design System | Dates | https://design-system.service.gov.uk/patterns/dates/ | design-system | 2026-10-06 | fetched | Typed dates for known dates; picker for looking dates up |
| GOV-06 | GOV.UK | Writing guidelines | https://guidance.publishing.service.gov.uk/writing-to-gov-uk-standards/writing-guidelines/ | design-system | 2026-10-06 | fetched | User needs, plain language, front-loading; specialists also prefer plain language |
| NNG-24 | Nielsen Norman Group | How Users Read on the Web (1997) | https://www.nngroup.com/articles/how-users-read-on-the-web/ | research | 2026-10-06 | fetched | Scanning; concise, scannable, objective writing |
| NNG-25 | Nielsen Norman Group | Placeholders in Form Fields Are Harmful (2014) | https://www.nngroup.com/articles/form-design-placeholders/ | research | 2026-10-06 | fetched | Why placeholders must not replace labels |
| NNG-26 | Nielsen Norman Group | Website Forms Usability: Top 10 Recommendations (2016) | https://www.nngroup.com/articles/web-form-design/ | research | 2026-10-06 | fetched | Fewer fields, single column, field sizing, marking, visible errors |
| NNG-22 | Nielsen Norman Group | Date-Input Form Fields (2017) | https://www.nngroup.com/articles/date-input/ | research | 2026-10-06 | fetched | Picker versus typing; ranges; ambiguous formats |

## Trust, credibility and deceptive patterns

| ID | Source | Title / topic | URL | Type | Checked | Verified | Guidance derived |
|---|---|---|---|---|---|---|---|
| STAN-01 | Stanford Persuasive Technology Lab | Stanford Guidelines for Web Credibility (Fogg, 2002) | https://credibility.stanford.edu/guidelines | research | 2026-10-06 | fetched | Ten credibility guidelines |
| NNG-11 | Nielsen Norman Group | Trustworthiness in Web Design: 4 Credibility Factors (2016) | https://www.nngroup.com/articles/trustworthy-design/ | research | 2026-10-06 | fetched | Design quality, upfront disclosure, current content, external connection |
| NNG-34 | Nielsen Norman Group | Social Proof in the User Experience (2014) | https://www.nngroup.com/articles/social-proof-ux/ | research | 2026-10-06 | fetched | When social proof helps and when it backfires |
| NNG-13 | Nielsen Norman Group | Deceptive Patterns in UX (2023) | https://www.nngroup.com/articles/deceptive-patterns/ | research | 2026-10-06 | fetched | Categories of deceptive design to avoid |
| FTC-01 | US Federal Trade Commission | Bringing Dark Patterns to Light (staff report, 2022) | https://www.ftc.gov/reports/bringing-dark-patterns-light | research | 2026-10-06 | partial | Regulator's account of manipulative design: false beliefs, hidden or delayed disclosure, unauthorized charges, subverted privacy choices |

## Ecommerce, apparel and booking

| ID | Source | Title / topic | URL | Type | Checked | Verified | Guidance derived |
|---|---|---|---|---|---|---|---|
| BAY-01 | Baymard Institute | Cart abandonment rate statistics (updated 2025) | https://baymard.com/lists/cart-abandonment-rate | research | 2026-10-06 | fetched | Stated reasons for checkout abandonment: extra costs, forced accounts, complexity, trust |
| BAY-02 | Baymard Institute | Checkout UX: pitfalls and best practices (updated 2025) | https://baymard.com/blog/current-state-of-checkout-ux | research | 2026-10-06 | fetched | Guest checkout, field marking, delivery dates, error messages |
| BAY-03 | Baymard Institute | Product Page UX: pitfalls and best practices (updated 2026) | https://baymard.com/blog/current-state-ecommerce-product-page-ux | research | 2026-10-06 | fetched | Variant buttons, in-scale images, shipping and returns on the product page |
| BAY-04 | Baymard Institute | Product List UX: pitfalls and best practices (updated 2025) | https://baymard.com/blog/current-state-product-list-and-filtering | research | 2026-10-06 | fetched | Combined variations, filters, applied-filter overview, sorting |
| BAY-05 | Baymard Institute | Usability Testing of Inline Form Validation (2024) | https://baymard.com/blog/inline-form-validation | research | 2026-10-06 | fetched | When validation should fire; remove errors when fixed |
| BAY-06 | Baymard Institute | Apparel: 10 Best Practices on Sizing (2022) | https://baymard.com/research-articles/apparel-size-information | research | 2026-10-06 | fetched | Size guide content and placement; model measurements |
| BAY-07 | Baymard Institute | 5 UX Best Practices for Apparel E-Commerce (updated 2025) | https://baymard.com/research-articles/apparel-5-best-practices | research | 2026-10-06 | fetched | Size buttons, human models, fit subscores, review images |
| BAY-08 | Baymard Institute | Travel Site UX: 5 Best Practices (2025) | https://baymard.com/blog/travel-site-ux-best-practices | research | 2026-10-06 | fetched | Prominent booking search, category-specific filters, complete detail, maps, independent reviews |
| BAY-09 | Baymard Institute | Mobile UX: 10 Best Practices (updated 2026) | https://baymard.com/blog/mobile-ux-ecommerce | research | 2026-10-06 | fetched | View all, applied filters, swatches, contextual errors, typo-tolerant suggestions |
| BAY-10 | Baymard Institute | E-Commerce Search usability research | https://baymard.com/research/ecommerce-search | research | 2026-10-06 | search | Search field, autocomplete, results and no-results design |
| BAY-11 | Baymard Institute | Mobile touch keyboard implementations | https://baymard.com/blog/mobile-touch-keyboards | research | 2026-10-06 | search | Correct keyboards; autocorrect off for names and emails; hit areas |
| BAY-12 | Baymard Institute | 5 Requirements for the Ratings Distribution Summary (2017, updated 2025) | https://baymard.com/blog/user-ratings-distribution-summary | research | 2026-10-06 | fetched | Rating with count; distribution as the most used review feature |
| BAY-13 | Baymard Institute | Travel accommodations UX research | https://baymard.com/blog/new-research-travel-accommodations | research | 2026-10-06 | search | Date pickers that show availability and price variation |

## Sales, B2B and service sites

| ID | Source | Title / topic | URL | Type | Checked | Verified | Guidance derived |
|---|---|---|---|---|---|---|---|
| NNG-12 | Nielsen Norman Group | B2B Usability (2006) | https://www.nngroup.com/articles/b2b-usability/ | research | 2026-10-06 | fetched | Long cycles, several stakeholders, layered content, cost of withholding information |
| NNG-27 | Nielsen Norman Group | When to Hide Content Behind Forms (2015) | https://www.nngroup.com/articles/content-behind-forms/ | research | 2026-10-06 | fetched | Do not gate early-stage content; short forms |
| NNG-28 | Nielsen Norman Group | State the Price to Give B2B Sites a Competitive Advantage (2013) | https://www.nngroup.com/articles/show-price/ | research | 2026-10-06 | fetched | Show prices, ranges or typical scenarios |
| NNG-29 | Nielsen Norman Group | "About Us" Information on Websites (2019) | https://www.nngroup.com/articles/about-us-information-on-websites/ | research | 2026-10-06 | fetched | What users look for; four levels of company detail |

## Navigation, search, tables and mobile

| ID | Source | Title / topic | URL | Type | Checked | Verified | Guidance derived |
|---|---|---|---|---|---|---|---|
| NNG-09 | Nielsen Norman Group | Data Tables: Four Major User Tasks (2022) | https://www.nngroup.com/articles/data-tables/ | research | 2026-10-06 | fetched | Find, compare, view or edit, act; frozen headers; non-modal editing |
| NNG-10 | Nielsen Norman Group | Mobile Tables (2017) | https://www.nngroup.com/articles/mobile-tables/ | research | 2026-10-06 | fetched | Lock the first column; scroll with a cue; let users choose columns |
| NNG-15 | Nielsen Norman Group | Breadcrumbs: 11 Design Guidelines (2018) | https://www.nngroup.com/articles/breadcrumbs/ | research | 2026-10-06 | fetched | Hierarchy not history; current page unlinked; mobile handling |
| NNG-16 | Nielsen Norman Group | Tabs, Used Right (2024) | https://www.nngroup.com/articles/tabs-used-right/ | research | 2026-10-06 | fetched | In-page versus navigation tabs; labels; single row |
| NNG-17 | Nielsen Norman Group | Hamburger Menus and Hidden Navigation Hurt UX Metrics (2016) | https://www.nngroup.com/articles/hamburger-menus/ | research | 2026-10-06 | fetched | Visible navigation on desktop; when hidden navigation is acceptable on mobile |
| NNG-18 | Nielsen Norman Group | 3 Guidelines for Search Engine "No Results" Pages (2014) | https://www.nngroup.com/articles/search-no-results-serp/ | research | 2026-10-06 | fetched | Make it obvious; offer recovery; plain tone |
| NNG-19 | Nielsen Norman Group | User Intent Affects Filter Design (2016) | https://www.nngroup.com/articles/applying-filters/ | research | 2026-10-06 | fetched | Interactive versus batch filtering; feedback while updating |
| NNG-20 | Nielsen Norman Group | Touch Targets on Touchscreens (2019) | https://www.nngroup.com/articles/touch-target-size/ | research | 2026-10-06 | fetched | About 1 cm by 1 cm, with spacing |
| NNG-30 | Nielsen Norman Group | Infinite Scrolling: When to Use It, When to Avoid It (2022) | https://www.nngroup.com/articles/infinite-scrolling-tips/ | research | 2026-10-06 | fetched | Unsuitable for goal-directed finding; load-more as an alternative |
| NNG-32 | Nielsen Norman Group | Sticky Headers: 5 Ways to Make Them Better (2021) | https://www.nngroup.com/articles/sticky-headers/ | research | 2026-10-06 | fetched | Keep small and opaque; partially persistent headers |
| NNG-33 | Nielsen Norman Group | Bottom Sheets: Definition and UX Guidelines (2023) | https://www.nngroup.com/articles/bottom-sheet/ | research | 2026-10-06 | fetched | Close button, back support, no stacking, brief tasks |

## Dashboards, data visualization and monitoring

| ID | Source | Title / topic | URL | Type | Checked | Verified | Guidance derived |
|---|---|---|---|---|---|---|---|
| GRAF-01 | Grafana Labs | Grafana dashboard best practices | https://grafana.com/docs/grafana/latest/dashboards/build-dashboards/best-practices/ | design-system | 2026-10-06 | fetched | Answer a question; general to specific; reduce cognitive load; USE and RED; drill-down hierarchies; alert on symptoms |
| NNG-21 | Nielsen Norman Group | Dashboards: Making Charts and Graphs Easier to Understand (2017) | https://www.nngroup.com/articles/dashboards-preattentive/ | research | 2026-10-06 | fetched | Operational versus analytical; length and position over angle and area |
| GOV-07 | UK Government Analysis Function | Data visualisation: charts (2022) | https://analysisfunction.civilservice.gov.uk/policy-store/data-visualisation-charts/ | design-system | 2026-10-06 | fetched | Chart choice by message; zero baseline for bars; limits on series; accessibility |
| SRE-01 | Google | Site Reliability Engineering: Monitoring Distributed Systems | https://sre.google/sre-book/monitoring-distributed-systems/ | research | 2026-10-06 | fetched | Symptoms versus causes; four golden signals; actionable, urgent alerts |
| PD-01 | PagerDuty | Ops guide: reduce noise | https://www.pagerduty.com/ops-guides/ops-practices/reduce-noise/ | implementation | 2026-10-06 | fetched | Deduplicate, group and suppress to prevent alert fatigue |
| CARB-01 | IBM Carbon Design System | Status indicator pattern | https://www.carbondesignsystem.com/patterns/status-indicator-pattern | design-system | 2026-10-06 | fetched | Status with more than color; attention levels; highest-attention state for a group; limit the number of indicators |
| CARB-02 | IBM Carbon Design System | Data table usage | https://carbondesignsystem.com/components/data-table/usage/ | design-system | 2026-10-06 | fetched | Density options, toolbar, batch actions, expandable rows, skeleton state |
| CARB-03 | IBM Carbon Design System | Empty states pattern | https://carbondesignsystem.com/patterns/empty-states-pattern/ | design-system | 2026-10-06 | fetched | No-data, user-action and error empty states |

## AI products

| ID | Source | Title / topic | URL | Type | Checked | Verified | Guidance derived |
|---|---|---|---|---|---|---|---|
| PAIR-01 | Google PAIR | People + AI Guidebook: Mental Models | https://pair.withgoogle.com/chapter/mental-models/ | research | 2026-10-06 | fetched | Set expectations; staged onboarding; caution with human-like framing |
| PAIR-02 | Google PAIR | People + AI Guidebook: Explainability + Trust | https://pair.withgoogle.com/chapter/explainability-trust/ | research | 2026-10-06 | fetched | Calibrated trust; when and how to show confidence |
| PAIR-03 | Google PAIR | People + AI Guidebook: Feedback + Control | https://pair.withgoogle.com/chapter/feedback-controls/ | research | 2026-10-06 | fetched | Say what feedback does; keep users in control where stakes are high |
| PAIR-04 | Google PAIR | People + AI Guidebook: Errors + Graceful Failure | https://pair.withgoogle.com/chapter/errors-failing/ | research | 2026-10-06 | fetched | Paths forward from failure; manual fallback; weigh stakes |
| HAX-01 | Microsoft Research | Guidelines for Human-AI Interaction (Amershi et al., CHI 2019) | https://www.microsoft.com/en-us/research/publication/guidelines-for-human-ai-interaction/ | research | 2026-10-06 | fetched | The peer-reviewed basis for the eighteen guidelines |
| HAX-02 | Microsoft | HAX Toolkit design library: the 18 guidelines | https://www.microsoft.com/en-us/haxtoolkit/library/ | research | 2026-10-06 | fetched | G1–G18, including capability clarity, efficient correction, consequences, global controls, change notices |
| NNG-36 | Nielsen Norman Group | AI Hallucinations: What Designers Need to Know (2025) | https://www.nngroup.com/articles/ai-hallucinations/ | research | 2026-10-06 | fetched | Communicating uncertainty; sources; avoiding false precision |
| NNG-37 | Nielsen Norman Group | Sycophancy in Generative-AI Chatbots | https://www.nngroup.com/articles/sycophancy-generative-ai-chatbots/ | research | 2026-10-06 | search | Agreement from a model is not evidence |
| APL-01 | Apple | Human Interface Guidelines: Generative AI | https://developer.apple.com/design/human-interface-guidelines/generative-ai | design-system | 2026-10-06 | partial | Supplementary platform guidance on transparency, expectations and control |

## RTL, internationalization and time

| ID | Source | Title / topic | URL | Type | Checked | Verified | Guidance derived |
|---|---|---|---|---|---|---|---|
| MAT-01 | Google Material Design | Bidirectionality | https://m2.material.io/design/usability/bidirectionality.html | design-system | 2026-10-06 | partial | What to mirror and what not to in RTL |
| APL-02 | Apple | Human Interface Guidelines: Right to left | https://developer.apple.com/design/human-interface-guidelines/right-to-left | design-system | 2026-10-06 | partial | Controls, icons, images and numerals in RTL |
| W3C-20 | W3C Internationalization | Structural markup and right-to-left text in HTML | https://www.w3.org/International/questions/qa-html-dir | implementation | 2026-10-06 | fetched | `dir` on `html`; `dir="auto"`; `bdi`; direction in markup, not CSS |
| W3C-21 | W3C | Arabic and Persian Layout Requirements | https://www.w3.org/TR/alreq/ | implementation | 2026-10-06 | fetched | Joining, justification, numerals, vertical extent, no italics or capitals |
| W3C-22 | W3C | Working with Time and Time Zones | https://www.w3.org/TR/timezone/ | implementation | 2026-10-06 | fetched | Zone identifiers over offsets; explicit zone context; daylight-saving pitfalls |

## Pricing, choice psychology and persuasion

Peer-reviewed studies are cited for what they found and for how well the finding has held up. Entries marked `search` were confirmed to exist with their abstract; the full papers were not read.

| ID | Source | Title / topic | URL | Type | Checked | Verified | Guidance derived |
|---|---|---|---|---|---|---|---|
| BEH-01 | Tversky & Kahneman | The Framing of Decisions and the Psychology of Choice (Science, 1981) | https://pubmed.ncbi.nlm.nih.gov/7455683/ | research | 2026-10-08 | search | The same outcome described as a gain or a loss shifts preference; a frame must leave a correct understanding |
| BEH-02 | Huber, Payne & Puto | Adding Asymmetrically Dominated Alternatives (Journal of Consumer Research, 1982) | https://scholars.duke.edu/publication/904415 | research | 2026-10-08 | search | The decoy (attraction) effect: a dominated option raises the share of the option that dominates it |
| BEH-03 | Simonson | Choice Based on Reasons: The Case of Attraction and Compromise Effects (Journal of Consumer Research, 1989) | https://www.gsb.stanford.edu/faculty-research/publications/choice-based-reasons-case-attraction-compromise-effects | research | 2026-10-08 | search | Options gain share when they become the middle of a set; stronger when the choice must be justified |
| BEH-04 | Frederick, Lee & Baskin | The Limits of Attraction (Journal of Marketing Research, 2014) | https://business.columbia.edu/faculty/research/limits-attraction | research | 2026-10-08 | search | The decoy effect often disappears when products are experienced or shown perceptually, not as numbers; practical value questioned |
| BEH-05 | Shampanier, Mazar & Ariely | Zero as a Special Price: The True Value of Free Products (Marketing Science, 2007) | https://ideas.repec.org/a/inm/ormksc/v26y2007i6p742-757.html | research | 2026-10-08 | search | A zero price raises demand far more than an equal price cut above zero |
| BEH-06 | Scheibehenne, Greifeneder & Todd | Can There Ever Be Too Many Options? A Meta-Analytic Review of Choice Overload (Journal of Consumer Research, 2010) | https://ideas.repec.org/a/oup/jconrs/v37y2010i3p409-425.html | research | 2026-10-08 | search | Across 50 experiments the mean effect of more options was near zero, with wide variation |
| BEH-07 | Chernev, Böckenholt & Goodman | Choice Overload: A Conceptual Review and Meta-Analysis (Journal of Consumer Psychology, 2015) | https://www.kellogg.northwestern.edu/faculty/research/detail/2015/when-product-assortment-leads-to-choice-overload-a-conceptual | research | 2026-10-08 | search | Overload appears with difficult tasks, complex sets, uncertain preferences and a goal of minimizing effort |
| BEH-08 | Brown, Imai, Vieider & Camerer | Meta-Analysis of Empirical Estimates of Loss Aversion (Journal of Economic Literature, 2024) | https://www.aeaweb.org/doi/10.1257/jel.20221698 | research | 2026-10-08 | search | Mean loss-aversion coefficient close to 2 across 607 estimates |
| BEH-09 | Gal & Rucker | The Loss of Loss Aversion: Will It Loom Larger Than Its Gain? (Journal of Consumer Psychology, 2018) | https://papers.ssrn.com/abstract=3049660 | research | 2026-10-08 | search | Loss aversion is not universal; it weakens for small stakes and has boundary conditions |
| BEH-10 | Gourville | Pennies-a-Day: The Effect of Temporal Reframing on Transaction Evaluation (Journal of Consumer Research, 1998) | https://ideas.repec.org/a/oup/jconrs/v24y1998i4p395-408.html | research | 2026-10-08 | search | Restating a cost as a small daily amount changes the comparison buyers make; later work reports limits and a risk of feeling misled |
| BEH-11 | Thomas & Morwitz | Penny Wise and Pound Foolish: The Left-Digit Effect in Price Cognition (Journal of Consumer Research, 2005) | https://ideas.repec.org/a/oup/jconrs/v32y2005i1p54-64.html | research | 2026-10-08 | search | Prices ending in 9 feel lower only when the leftmost digit changes |
| BEH-12 | Jachimowicz, Duncan, Weber & Johnson | When and Why Defaults Influence Decisions: A Meta-Analysis (Behavioural Public Policy, 2019) | https://collaborate.princeton.edu/en/publications/when-and-why-defaults-influence-decisions-a-meta-analysis-of-defa/ | research | 2026-10-08 | search | Defaults have a considerable average effect, larger in consumer settings |
| BEH-13 | Maier et al. | No Evidence for Nudging After Adjusting for Publication Bias (PNAS, 2022) | https://pmc.ncbi.nlm.nih.gov/articles/PMC9351501 | research | 2026-10-08 | search | Reported nudge effects shrink to little or nothing after bias correction; do not promise uplift |
| BEH-14 | Mathur et al. | Dark Patterns at Scale: Findings from a Crawl of 11K Shopping Websites (CSCW, 2019) | https://arxiv.org/abs/1907.07032 | research | 2026-10-08 | search | About 11% of shopping sites used dark patterns: sneaking, urgency, misdirection, social proof, scarcity, obstruction, forced action |
| NNG-38 | Nielsen Norman Group | The Anchoring Principle (2018) | https://www.nngroup.com/articles/anchoring-principle/ | research | 2026-10-08 | fetched | Anchors shape estimates; honest uses are sensible defaults, accurate expectations and real original prices |
| NNG-39 | Nielsen Norman Group | Prospect Theory and Loss Aversion: How Users Make Decisions (2016) | https://www.nngroup.com/articles/prospect-theory/ | research | 2026-10-08 | fetched | Losses outweigh gains; answer fears directly; make comparisons simple; test framing |
| NNG-40 | Nielsen Norman Group | Simplicity Wins over Abundance of Choice (2015) | https://www.nngroup.com/articles/simplicity-vs-choice/ | research | 2026-10-08 | fetched | More options raise effort and abandonment; keep options to those of real value |
| NNG-41 | Nielsen Norman Group | Scarcity Principle: Making Users Click Right Now or Lose Out (2014) | https://www.nngroup.com/articles/scarcity-principle-ux/ | research | 2026-10-08 | fetched | Scarcity works through loss aversion; use only true information, in moderation, and test it |
| NNG-42 | Nielsen Norman Group | Comparison Tables for Products, Services, and Features (2024) | https://www.nngroup.com/articles/comparison-tables/ | research | 2026-10-08 | fetched | Five items or fewer; consistent attributes; sticky headers; about two items on phones |
| NNG-43 | Nielsen Norman Group | Communicating Ecommerce Discounts and Promotions (2019) | https://www.nngroup.com/articles/communicating-discounts/ | research | 2026-10-08 | fetched | State restrictions upfront; show offers near the price and in the cart |
| NNG-44 | Nielsen Norman Group | How to Display Taxes, Fees, and Shipping Charges on Ecommerce Sites (2018) | https://www.nngroup.com/articles/ecommerce-taxes-fees/ | research | 2026-10-08 | fetched | Disclose nonstandard fees early, near the price, with an explanation |
| NNG-45 | Nielsen Norman Group | Clean the Sludge from Decision-Making Workflows (2024) | https://www.nngroup.com/articles/sludge-decisions/ | research | 2026-10-08 | fetched | Remove barriers to deciding; make plans easy to differentiate; recommendations help uncertain users |
| NNG-46 | Nielsen Norman Group | What B2B Designers Can Learn from B2C About Building Trust (2019) | https://www.nngroup.com/articles/b2b-trust-from-b2c/ | research | 2026-10-08 | fetched | Show prices or scenarios; explain tiers; comparable plans; trials without a card |
| NNG-47 | Nielsen Norman Group | The Reciprocity Principle: Give Before You Take in Web Design (2014) | https://www.nngroup.com/articles/reciprocity-principle/ | research | 2026-10-08 | fetched | Give value before asking; early data requests erode trust |
| BAY-15 | Baymard Institute | How to Display Price Discounts on the Product Page (4 pitfalls) | https://baymard.com/blog/product-page-price-discounts | research | 2026-10-08 | fetched | Price highly visible; discount next to price; one description per offer; show amount and percent |
| BAY-16 | Baymard Institute | Display "Price Per Unit" for Multiquantity Items | https://baymard.com/blog/price-per-unit | research | 2026-10-08 | search | Unit price lets shoppers compare pack sizes |

## Consumer protection rules on pricing and persuasion

Cited to show that these practices are regulated, not to give legal advice. Rules differ by country and change; the skill flags likely problems and refers the owner to a lawyer.

| ID | Source | Title / topic | URL | Type | Checked | Verified | Guidance derived |
|---|---|---|---|---|---|---|---|
| LAW-01 | US Federal Trade Commission | Guides Against Deceptive Pricing, 16 CFR 233.1: former price comparisons | https://www.law.cornell.edu/cfr/text/16/233.1 | normative | 2026-10-08 | fetched | A former price must be a genuine price offered in good faith for a substantial period |
| LAW-02 | US Federal Trade Commission | Guide Concerning Use of the Word "Free", 16 CFR 251.1 | https://www.law.cornell.edu/cfr/text/16/251.1 | normative | 2026-10-08 | fetched | Conditions stated clearly at the outset, beside the offer; no recovering the cost through the paid item |
| LAW-03 | US Federal Trade Commission | Rule on the Use of Consumer Reviews and Testimonials, 16 CFR Part 465 (in force 2024) | https://www.law.cornell.edu/cfr/text/16/part-465 | normative | 2026-10-08 | search | Fake, bought or selectively suppressed reviews and testimonials are prohibited |
| LAW-04 | European Union | Unfair Commercial Practices Directive 2005/29/EC, Annex I | https://eur-lex.europa.eu/eli/dir/2005/29/oj | normative | 2026-10-08 | partial | Practices always unfair include false limited-time claims, calling something free when it is not, bait offers and fake reviews |
| LAW-05 | European Union | Price Indication Directive 98/6/EC, Article 6a (as amended 2019) | https://eur-lex.europa.eu/eli/dir/1998/6/oj | normative | 2026-10-08 | search | An announced reduction must show the lowest price of at least the previous 30 days |
| LAW-06 | UK Competition and Markets Authority | Unfair commercial practices guidance under the Digital Markets, Competition and Consumers Act 2024 (CMA207, 2025) | https://www.gov.uk/government/publications/unfair-commercial-practices-cma207 | normative | 2026-10-08 | search | Drip pricing and fake reviews are banned; the headline price includes mandatory charges |
| LAW-07 | European Union | Digital Services Act, Regulation (EU) 2022/2065, Article 25 | https://eur-lex.europa.eu/eli/reg/2022/2065/oj | normative | 2026-10-08 | search | Platforms may not design interfaces that deceive, manipulate or impair free and informed decisions |
| LAW-08 | US Federal Trade Commission | .com Disclosures: How to Make Effective Disclosures in Digital Advertising (2013) | https://www.ftc.gov/os/2013/03/130312dotcomdisclosures.pdf | normative | 2026-10-08 | search | Disclosures as close as possible to the claim, prominent and unavoidable; material terms before billing details |

## Type, scale and proportion

| ID | Source | Title / topic | URL | Type | Checked | Verified | Guidance derived |
|---|---|---|---|---|---|---|---|
| USWDS-01 | US Web Design System | Typography | https://designsystem.digital.gov/components/typography/ | design-system | 2026-10-08 | fetched | Body at least 16px; 45 to 90 characters per line, about 66 for long text; body line height at least 1.5, headings 1 to 1.35; paragraph spacing |
| GOV-08 | GOV.UK Design System | Type scale | https://design-system.service.gov.uk/styles/type-scale/ | design-system | 2026-10-08 | fetched | 19px body on all screens; headings step down on small screens (48 to 32, 36 to 27) |
| W3C-23 | W3C WAI | Understanding 1.4.8 Visual Presentation (Level AAA) | https://www.w3.org/WAI/WCAG22/Understanding/visual-presentation.html | normative | 2026-10-08 | fetched | Lines of 80 characters or fewer, no justified text, line spacing of at least 1.5 (AAA, cited as a recommendation) |
| BAY-14 | Baymard Institute | Readability: The Optimal Line Length (2022) | https://baymard.com/blog/line-length-readability | research | 2026-10-08 | fetched | 50 to 75 characters per line; long lines are skipped; fatigue observed at 100 or more |
| BAY-17 | Baymard Institute | Homepage carousels | https://baymard.com/blog/homepage-carousel | research | 2026-10-08 | search | Auto-rotating carousels often fail; later slides go unseen |
| NNG-48 | Nielsen Norman Group | Scrolling and Attention (2018) | https://www.nngroup.com/articles/scrolling-and-attention/ | research | 2026-10-08 | fetched | 57% of viewing time above the fold, 74% in the first two screens; avoid false floors |
| WEB-09 | Google Chrome Developers | Lighthouse: document uses legible font sizes | https://developer.chrome.com/docs/lighthouse/seo/font-size | implementation | 2026-10-08 | fetched | Text under 12px is treated as illegible on mobile |
| APL-03 | Apple | Human Interface Guidelines: Typography | https://developer.apple.com/design/human-interface-guidelines/typography | design-system | 2026-10-08 | partial | 17pt default body and 11pt minimum on iOS; hierarchy through text styles |
| MAT-02 | Google Material Design 3 | Type scale tokens | https://m3.material.io/styles/typography/type-scale-tokens | design-system | 2026-10-08 | partial | 16px large body, 14px medium body; display and headline steps |

## Sales journey and selling strategies

| ID | Source | Title / topic | URL | Type | Checked | Verified | Guidance derived |
|---|---|---|---|---|---|---|---|
| NNG-49 | Nielsen Norman Group | How Long Do Users Stay on Web Pages? (2011) | https://www.nngroup.com/articles/how-long-do-users-stay-on-web-pages/ | research | 2026-10-09 | fetched | Most visits end in 10 to 20 seconds; pages that hold a visitor 30 seconds are kept much longer; state the value at once |
| NNG-50 | Nielsen Norman Group | The Aesthetic-Usability Effect (2024) | https://www.nngroup.com/articles/aesthetic-usability-effect/ | research | 2026-10-09 | fetched | Attractive design earns tolerance for small problems, not large ones |
| NNG-51 | Nielsen Norman Group | Information Scent: How Users Decide Where to Go Next (2020) | https://www.nngroup.com/articles/information-scent/ | research | 2026-10-09 | fetched | Specific labels; show relevance on the first screen; image-heavy landings with little text lose visitors |
| NNG-52 | Nielsen Norman Group | Minimize Cognitive Load to Maximize Usability (2013) | https://www.nngroup.com/articles/minimize-cognitive-load/ | research | 2026-10-09 | fetched | Remove clutter, build on existing mental models, offload tasks |
| NNG-53 | Nielsen Norman Group | Scrolljacking 101 (2023) | https://www.nngroup.com/articles/scrolljacking-101/ | research | 2026-10-09 | fetched | Altered scrolling disorients; keep it short, below the fold, without essential text, rarely on mobile |
| NNG-54 | Nielsen Norman Group | The Characteristics of Minimalism in Web Design (2015) | https://www.nngroup.com/articles/characteristics-minimalism/ | research | 2026-10-09 | fetched | What defines minimalist sites, and the risks: hidden clickability, low contrast, removed content |
| NNG-55 | Nielsen Norman Group | Top 10 Guidelines for Homepage Usability (2002) | https://www.nngroup.com/articles/top-ten-guidelines-for-homepage-usability/ | research | 2026-10-09 | fetched | State the purpose in one sentence; start points for the one to four main tasks; show real content |
| NNG-56 | Nielsen Norman Group | Login Walls Stop Users in Their Tracks (2014) | https://www.nngroup.com/articles/login-walls/ | research | 2026-10-09 | fetched | Give value before asking for an account; guest paths; ask after the task |
| NNG-57 | Nielsen Norman Group | The Role of Animation and Motion in UX (2020) | https://www.nngroup.com/articles/animation-purpose-ux/ | research | 2026-10-09 | fetched | Motion for feedback, state and orientation; irrelevant motion distracts |
| NNG-58 | Nielsen Norman Group | Video Usability (2014) | https://www.nngroup.com/articles/video-usability/ | research | 2026-10-09 | fetched | Video supplements text; avoid autoplay; show length; give controls |
| NNG-59 | Nielsen Norman Group | The Peak-End Rule: How Impressions Become Memories (2018) | https://www.nngroup.com/articles/peak-end-rule/ | research | 2026-10-09 | fetched | Experiences are remembered by their peaks and their end; finish well; no begging pop-ups |
| NNG-60 | Nielsen Norman Group | Popups: 10 Problematic Trends and Alternatives (2019) | https://www.nngroup.com/articles/popups/ | research | 2026-10-09 | fetched | No pop-ups before content or before interaction; never stacked; nonmodal alternatives |
| NNG-61 | Nielsen Norman Group | Interaction Cost: Definition (2013, reviewed 2024) | https://www.nngroup.com/articles/interaction-cost-definition/ | research | 2026-10-09 | fetched | Effort is reading, scrolling, looking, understanding, tapping, typing, waiting, remembering; people leave costly sites |
| NNG-62 | Nielsen Norman Group | End of Web Design: Jakob's Law (2000) | https://www.nngroup.com/articles/end-of-web-design/ | research | 2026-10-09 | fetched | Visitors expect a site to work like the other sites they know |
| NNG-63 | Nielsen Norman Group | Wizards: Definition and Design Recommendations (2017) | https://www.nngroup.com/articles/wizards/ | research | 2026-10-09 | fetched | Step-by-step flows help novices and rare tasks; show steps; keep answers; name the next step |
| NNG-64 | Nielsen Norman Group | UX Guidelines for Ecommerce Product Pages (2019) | https://www.nngroup.com/articles/ecommerce-product-pages/ | research | 2026-10-09 | fetched | Answer every product question; multiple views; true price; delivery and returns on the page; clear add-to-cart feedback |
| NNG-65 | Nielsen Norman Group | Customization vs. Personalization in the User Experience (2016) | https://www.nngroup.com/articles/customization-personalization/ | research | 2026-10-09 | fetched | Personalization is only as good as its guesses; neither fixes a broken site |
| NNG-66 | Nielsen Norman Group | The Illusion of Completeness (2016) | https://www.nngroup.com/articles/illusion-of-completeness/ | research | 2026-10-09 | fetched | Large heroes, full-width lines and gaps make a page look finished; let the next section show |
| NNG-67 | Nielsen Norman Group | Scroll-Triggered Text Animations Delay Users (2017) | https://www.nngroup.com/articles/scroll-animations/ | research | 2026-10-09 | fetched | Text that animates in is felt as load time; animate secondary content, once |
| NNG-68 | Nielsen Norman Group | The Impact of Tone of Voice on Users' Brand Perception (2016) | https://www.nngroup.com/articles/tone-voice-users/ | research | 2026-10-09 | fetched | Trust predicts desirability far more than friendliness; humor is risky |
| NNG-69 | Nielsen Norman Group | Banner Blindness Revisited (2018) | https://www.nngroup.com/articles/banner-blindness-old-and-new-findings/ | research | 2026-10-09 | fetched | Content that looks or sits like an advertisement is skipped, along with what is near it |
| NNG-70 | Nielsen Norman Group | Fitts's Law and Its Applications in UX (2022) | https://www.nngroup.com/articles/fitts-law/ | research | 2026-10-09 | fetched | Bigger, closer targets are faster; keep the action near where the visitor is |
| NNG-71 | Nielsen Norman Group | B2B vs. B2C Websites: Key UX Differences (2016) | https://www.nngroup.com/articles/b2b-vs-b2c/ | research | 2026-10-09 | fetched | Long cycles, several readers, integration detail, complex pricing |
| BAY-18 | Baymard Institute | Homepage UX best practices (2021) | https://baymard.com/blog/ecommerce-homepage-ux | research | 2026-10-09 | fetched | Show the range sold; avoid aggressive overlays; careful carousels; obvious search |
| BEH-15 | Lindgaard, Fernandes, Dudek & Brown | Attention Web Designers: You Have 50 Milliseconds to Make a Good First Impression! (Behaviour & Information Technology, 2006) | https://doi.org/10.1080/01449290500330448 | research | 2026-10-09 | search | Visual appeal is judged within about 50 milliseconds and the judgment persists |
| BEH-16 | Tuch et al. / Google Research | Users love simple and familiar designs (2012, summary of the visual complexity and prototypicality study) | https://research.google/blog/users-love-simple-and-familiar-designs-why-websites-need-to-make-a-great-first-impression/ | research | 2026-10-09 | fetched | Visually complex and unfamiliar-looking sites are judged less attractive within 17 to 50 milliseconds |
| BEH-17 | Reber, Schwarz & Winkielman | Processing Fluency and Aesthetic Pleasure (Personality and Social Psychology Review, 2004) | https://journals.sagepub.com/doi/10.1207/s15327957pspr0804_3 | research | 2026-10-09 | search | What is easier to process is liked more |
| BEH-18 | BJ Fogg | Fogg Behavior Model | https://behaviormodel.org/ | research | 2026-10-09 | fetched | A behavior happens when motivation, ability and a prompt coincide |
| WEB-10 | Google web.dev | Vodafone: a 31% improvement in LCP increased sales by 8% (2021) | https://web.dev/case-studies/vodafone | research | 2026-10-09 | fetched | A controlled test linking faster first paint to sales |
| WEB-11 | Think with Google | Page load time statistics | https://www.thinkwithgoogle.com/consumer-insights/consumer-trends/mobile-site-load-time-statistics/ | research | 2026-10-09 | search | Bounce probability rises about a third as load time goes from one to three seconds |
| UXM-01 | UXmatters (Hoober) | How Do Users Really Hold Mobile Devices? (2013) | https://www.uxmatters.com/mt/archives/2013/02/how-do-users-really-hold-mobile-devices.php | research | 2026-10-09 | fetched | About half of observed phone use was one-handed; the author later judged his reach diagrams inaccurate, so no reach zones are derived from it |

## Psychology of decisions, memory and motivation

Each entry notes how well the finding has held up. Entries marked `search` were confirmed with their abstract or a faithful summary; the full papers were not read.

| ID | Source | Title / topic | URL | Type | Checked | Verified | Guidance derived |
|---|---|---|---|---|---|---|---|
| BEH-19 | Iyengar & Lepper | When Choice is Demotivating: Can One Desire Too Much of a Good Thing? (Journal of Personality and Social Psychology, 2000) | https://doi.org/10.1037/0022-3514.79.6.995 | research | 2026-10-09 | search | The jam study: 24 jams drew more visitors but 3% bought, against 30% with 6. A choice-overload result, not evidence about defaults; later replications and meta-analyses did not confirm it |
| BEH-20 | Nunes & Drèze | The Endowed Progress Effect: How Artificial Advancement Increases Effort (Journal of Consumer Research, 2006) | https://doi.org/10.1086/500480 | research | 2026-10-09 | search | Car-wash cards needing eight purchases: 34% completed a ten-space card with two stamps given, 19% an empty eight-space card |
| BEH-21 | Kivetz, Urminsky & Zheng | The Goal-Gradient Hypothesis Resurrected (Journal of Marketing Research, 2006) | https://business.columbia.edu/faculty/research/goal-gradient-hypothesis-resurrected-purchase-acceleration-illusionary-goal | research | 2026-10-09 | search | Purchases accelerate as a reward nears; a head start has the same effect |
| BEH-22 | Norton, Mochon & Ariely | The IKEA Effect: When Labor Leads to Love (Journal of Consumer Psychology, 2012) | https://dash.harvard.edu/handle/1/12136084 | research | 2026-10-09 | search | People value what they built, only when they complete it successfully |
| BEH-23 | Sarstedt, Neubert & Barth | The IKEA Effect: A Conceptual Replication (Journal of Marketing Behavior, 2017) | https://ideas.repec.org/a/now/jnljmb/107.00000039.html | research | 2026-10-09 | search | The effect replicated; psychological ownership is the mechanism |
| BEH-24 | Kahneman, Knetsch & Thaler | Experimental Tests of the Endowment Effect and the Coase Theorem (Journal of Political Economy, 1990) | https://www.casact.org/abstract/experimental-tests-endowment-effect-and-coase-theorem | research | 2026-10-09 | search | Owners demand more to give something up than buyers will pay; later work finds it weakens with trading experience |
| BEH-25 | Vohs et al. | A Multisite Preregistered Paradigmatic Test of the Ego-Depletion Effect (Psychological Science, 2021) | https://discovery.dundee.ac.uk/en/publications/a-multisite-preregistered-paradigmatic-test-of-the-ego-depletion-/ | research | 2026-10-09 | search | 36 laboratories, 3,531 people: no reliable depletion effect; an earlier 23-laboratory replication found the same |
| BEH-26 | Buell & Norton | The Labor Illusion: How Operational Transparency Increases Perceived Value (Management Science, 2011) | https://ideas.repec.org/a/inm/ormnsc/v57y2011i9p1564-1579.html | research | 2026-10-09 | search | People value a service more when shown the work being done during a wait |
| BEH-27 | Conrad, Couper, Tourangeau & Peytchev | The Impact of Progress Indicators on Task Completion (Interacting with Computers, 2010) | https://pmc.ncbi.nlm.nih.gov/articles/PMC2910434 | research | 2026-10-09 | search | Slow early progress raises abandonment; encouraging feedback improves the experience more than completion |
| BEH-28 | Villar, Callegaro & Yang | Where Am I? A Meta-Analysis of Experiments on the Effects of Progress Indicators for Web Surveys (Social Science Computer Review, 2013) | https://research.google/pubs/where-am-i-a-meta-analysis-of-experiments-on-the-effects-of-progress-indicators-for-web-surveys/ | research | 2026-10-09 | search | Across 32 experiments a steady indicator did not reduce drop-off; fast-then-slow reduced it, slow-then-fast increased it |
| BEH-29 | Ghibellini & Meier | Interruption, Recall and Resumption: A Meta-Analysis of the Zeigarnik and Ovsiankina Effects (Humanities and Social Sciences Communications, 2025) | https://ideas.repec.org/a/pal/palcom/v12y2025i1d10.1057_s41599-025-05000-w.html | research | 2026-10-09 | search | No memory advantage for unfinished tasks; a general tendency to resume them |
| BEH-30 | Cowan | The Magical Number 4 in Short-Term Memory (Behavioral and Brain Sciences, 2001) | https://pmc.ncbi.nlm.nih.gov/articles/PMC2864034 | research | 2026-10-09 | search | Working memory holds about three to five chunks; seven was a loose estimate |
| NNG-72 | Nielsen Norman Group | Memory Recognition and Recall in User Interfaces (2024) | https://www.nngroup.com/articles/recognition-and-recall/ | research | 2026-10-09 | fetched | Show options instead of asking people to remember them |
| NNG-73 | Nielsen Norman Group | Short-Term Memory and Web Usability (2009) | https://www.nngroup.com/articles/short-term-memory-and-web-usability/ | research | 2026-10-09 | fetched | Limiting menus to seven items is a misconception; do not make people carry information between pages |
| NNG-74 | Nielsen Norman Group | Proximity Principle in Visual Design (2020) | https://www.nngroup.com/articles/gestalt-proximity/ | research | 2026-10-09 | fetched | Nearness signals relatedness; check groupings at every screen size |
| NNG-75 | Nielsen Norman Group | Hick's Law: Designing Long Menu Lists (video) | https://www.nngroup.com/videos/hicks-law-long-menus/ | research | 2026-10-09 | search | More choices take longer to decide among, logarithmically; organization makes long lists usable |
| LAW-09 | European Parliament | Resolution on addictive design of online services and consumer protection (12 December 2023) | https://howtheyvote.eu/votes/162206 | normative | 2026-10-09 | search | Non-binding: asks for action on endless scroll, default autoplay, recapture notifications and similar features |

## Own measurements

**SURVEY-01: computed styles of 28 commercial sites, measured 2026-10-08.** Cited by `patterns/visual-scale` and `patterns/pricing-and-persuasion` as *observed practice*.

- **Method.** Each page was loaded in Chrome at 1440 by 900 and at 390 by 844 with a phone user agent. A script read computed styles: text sizes and line heights of paragraphs, characters per line, the largest heading on the first screen, header height and stickiness, and the size and position of filled buttons on the first screen. Pricing pages were read for plan counts, marked plans, billing wording and urgency wording.
- **Sites.** Home, product or pricing pages of Stripe, Apple, Shopify, Slack, Notion, Basecamp, Squarespace, Mailchimp, Airbnb, Nike, HubSpot, Linear, monday.com, Wix, Zoom, Dropbox, Spotify, Netflix, Allbirds, Warby Parker, Booking.com, Webflow, Duolingo, Figma, Canva, IKEA, Asana and Grammarly, and the pricing pages of Slack, Notion, Shopify, Mailchimp, Dropbox, Figma, Canva, Asana, HubSpot, monday.com, Squarespace, Grammarly, Basecamp, Wix, Linear, Webflow, Jira, Semrush and The New York Times. Several other sites refused automated access and are not counted.
- **Limits.** One visit per page, from one country, by script: cookie banners, regional variants and A/B tests affect what was served. Popular is not the same as proven: these sites show what large design teams ship, not what was tested to work best. The figures are ranges to sanity-check a design against, never targets, and they will date.

**SURVEY-02: top-to-bottom walk of 66 selling pages, 2026-10-09.** Cited by `patterns/sales-journey` and `selling-strategies` as *observed practice*.

- **Method.** Each page was loaded in Chrome at 390 by 844 (phone user agent) and at 1440 by 900, scrolled to the end, and read by script: first-screen headline, word count, actions, media share, inputs and overlays; page length; headings; every filled button and how often it repeats; sticky bars; images, videos and running animations; distinct text sizes and colors; wording for guidance, trials, guarantees, proof and urgency; load timings and transfer size. Phone first screens were also captured and viewed.
- **Sites.** Product, home or buy pages of Apple (four pages), Dyson, Rivian, Tesla, Sonos, Oura, Dollar Shave Club, Function of Beauty, Lemonade, Noom, Warby Parker, Allbirds (three pages), Everlane, Glossier, Stripe, Plaid, Vercel, Twilio, Cloudflare, Linear, Raycast, Resend, Cursor, Arc, Canva, Figma, Typeform, Calendly, Duolingo, Notion, Loom, Grammarly, Casper, Ridge, AG1, Mint Mobile, Harry's, Basecamp, HEY, Patagonia, Airbnb, Booking.com, Uber, Thumbtack, Wise, OpenTable, Toptal, Pentagram, IDEO, Shopify and HubSpot. Fifty-six phone loads were usable; several sites refused automated access or served a block page and are not counted.
- **Limits.** One scripted visit per page from one country, with a cold cache and no consent given, so regional dialogs, consent layers, seasonal sales and A/B variants shaped what was seen. Load timings are a single sample, not field data. Counts found by text matching miss what is worded differently. Grouping the sites into selling strategies is this skill's interpretation, not something the sites state.

## Known gaps

Areas where strong, openly accessible sources were thin when this index was built. The corresponding modules mark such guidance as judgment.

- **Selling strategies.** No published study validates the thirteen-strategy grouping in `selling-strategies.md`; it is an interpretation of observed sites supported by research on the individual techniques, and the survey covered large brands only: small-business and local-service sites were not measured. Configurators and product quizzes in particular lack open research (the main studies are paywalled).
- **Marketplaces and directories.** Little open usability research specific to two-sided platforms was found; the module adapts ecommerce list, credibility and reviews research.
- **Agentic AI.** Published human-AI guidance largely predates widely deployed agents that act on a user's behalf; approval-boundary guidance is reasoned from control and error-prevention principles.
- **Service-business sites.** Guidance is assembled from credibility, content and B2B research rather than a dedicated study.
- **Ready-size versus made-to-measure apparel flows.** No dedicated published study was found.
- **Mirroring rules.** The two platform references marked `partial` could not be machine-read reliably; the mirroring table should be re-read against them by a person.
- **ISO 9241-11.** The standard is paywalled and its page refused automated access; only its widely cited definition of usability is used.

## Updating this index

1. Re-open each URL, starting with entries marked `search`, `partial` or `blocked`.
2. Update the `Checked` date and `Verified` value for each entry you re-read.
3. Where a source has changed, update the module that cites it and note the change in `CHANGELOG.md`.
4. Add new sources with the next free number in the family, cite them from the module's `Sources` section.
5. Prefer standards, primary research and design-system owners. Do not add uncited blog posts.
