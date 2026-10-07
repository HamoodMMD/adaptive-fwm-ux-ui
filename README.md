# adaptive-fwm-ux-ui

An Agent Skill for auditing and safely improving the UX and UI of any website or application.

Most UX checklists apply the same rules to everything. This skill starts by working out what it is looking at — a store, an agency site, a monitoring dashboard, an admin tool, an AI workspace, a booking flow — and who uses it for what. Then it loads only the rules that fit, audits against them, and, if asked, makes the changes that are safe to make. It will not alter how the product works or what the brand looks like unless you tell it to.

**Version:** 1.0.1 · **Format:** [Agent Skills](https://agentskills.io/specification) · **Target:** WCAG 2.2 Level AA

## What it does

- Classifies each *surface* of a product (not just the project, and never just the industry) across fourteen dimensions such as user goal, business goal, audience, environment, risk, device and language.
- Composes one primary profile, up to two secondary profiles, and the pattern modules for what is actually on the screen.
- Audits user workflows first, then individual screens, against evidence-based rules.
- Reports findings with a priority, the evidence, the rule and what kind of rule it is: a WCAG requirement, an established principle, published research, design-system guidance, or a judgment call.
- Records what already works under "Strengths / preserve", so good parts are not redesigned.
- Separates safe UI changes from recommendations that need functional work, and implements only the former.
- Verifies accessibility, responsive behavior and regressions after any change.

## Installation

A skill is a folder. Put this one where your agent looks for skills, keeping the folder name `adaptive-fwm-ux-ui` (the Agent Skills format requires the folder name to match the skill name).

| Agent | Personal (all projects) | Project (this repository) |
|---|---|---|
| Claude Code | `~/.claude/skills/adaptive-fwm-ux-ui/` | `.claude/skills/adaptive-fwm-ux-ui/` |
| Codex | `~/.agents/skills/adaptive-fwm-ux-ui/` | `.agents/skills/adaptive-fwm-ux-ui/` |
| Other Agent Skills-compatible tools | See the tool's documentation for its skills directory | |

Clone straight into place:

```bash
git clone https://github.com/HamoodMMD/adaptive-fwm-ux-ui.git ~/.claude/skills/adaptive-fwm-ux-ui
```

or copy the folder. Only `SKILL.md`, `references/` and `assets/` are needed at run time.

The skill uses only the portable frontmatter fields (`name`, `description`, `metadata`), has no dependencies, and needs no network access to run.

## Usage

Ask in plain language. There is no command syntax.

**Audit only** — nothing is modified:

> Audit this ecommerce store for UX/UI problems but do not change functionality.

> Check my website UX.

**Audit and fix** — safe UI changes are implemented, everything else is reported:

> Review this dashboard using the adaptive UX skill and fix safe UI issues.

**One screen, component or flow:**

> Audit only the checkout.

**A focus pass:**

> Check this Arabic/English service website for mobile and accessibility issues.

> Review this AI workspace with emphasis on generation, feedback, and user control.

**A design plan before building:**

> We're adding a booking flow to this clinic site. Plan the UX before I build it.

Requests that say *audit*, *review* or *check* are read-only. The skill edits files only when asked to *fix*, *improve*, *implement* or *apply*. When it is unclear, it audits and offers the list of safe fixes.

## How classification works

1. **Evidence, in order.** What you said; earlier conversation; project docs; the repository; routes and navigation; UI copy; data models; component names; APIs; inference; and only then questions.
2. **Surfaces.** The project is split into groups of screens that share users and a goal. One fashion brand might have a store, a customer account area and a staff admin, each classified separately.
3. **Dimensions.** Each surface is described by user goal, business goal, audience, environment, interaction model, frequency, complexity, error consequence, device context, content density, language, AI involvement, transaction model and roles.
4. **Profiles and patterns.** One primary profile, up to two secondary, plus pattern modules for the interface elements present.
5. **Confidence.** High: proceed. Medium: state the classification and the alternative, and proceed if both lead to compatible advice. Low: ask at most three to five short questions. Confidence is qualitative; the skill never invents a percentage.

Examples:

| Product | Profiles | Typical patterns |
|---|---|---|
| Fashion store | ecommerce + fashion-apparel | search-filter-sort, forms, responsive-mobile |
| Agency website | service-business + sales-lead-generation + b2b-marketing | forms, navigation |
| Monitoring SaaS | saas-application + monitoring-observability + dashboard-analytics | charts-data-viz, tables |
| AI workspace | saas-application + ai-product | forms, loading-empty-error-states |
| Internal admin tool | admin-backoffice | tables, search-filter-sort, forms |
| Booking marketplace | booking-reservation + marketplace-directory | search-filter-sort, forms |

If nothing fits, the skill says so and audits with the core and pattern modules alone instead of forcing a profile.

## Modules

**Core** — apply to every surface: `universal-ux`, `accessibility`, `performance`, `content-and-trust`, `brand-preservation`.

**Profiles** — chosen by classification: `ecommerce`, `fashion-apparel`, `sales-lead-generation`, `service-business`, `informational-content`, `b2b-marketing`, `saas-application`, `dashboard-analytics`, `monitoring-observability`, `admin-backoffice`, `ai-product`, `booking-reservation`, `marketplace-directory`, `high-stakes`.

**Patterns** — chosen by what is on the screen: `forms`, `navigation`, `tables`, `search-filter-sort`, `charts-data-viz`, `loading-empty-error-states`, `responsive-mobile`, `rtl-bilingual`.

Every module has the same shape: when to load it, objectives, priority principles, concrete checks, anti-patterns, exceptions, implementation cautions, and sources.

## Brand preservation

Before judging anything visual, the skill takes an inventory of the existing identity: logo, colors, type, spacing, radius, shadows, motion, imagery, components and modes. All of it is preserved by default.

When a brand element causes a usability problem, the skill changes how the element is *used* before it considers changing the element. A brand purple that fails contrast as small text stays the brand purple; it stops being used for small text. Changes to a base brand element are recommended to the owner, never applied silently.

The skill has no house style. It will not turn a product into generic SaaS, stock Tailwind, Material, or whatever is fashionable.

## Functionality safety

Unless you explicitly authorize functional work, the skill does not change APIs, schemas, data, routes, authentication, permissions, pricing, tax, inventory, checkout, payment, booking, monitoring or alert logic, AI prompts or model behavior, analytics contracts, background jobs or integrations.

Improvements that would need such changes are listed under `FUNCTIONAL UX RECOMMENDATIONS — NOT IMPLEMENTED` for you to decide on.

It also never adds fake functionality: no search box that does not search, no chart of invented data, no progress bar driven by a timer. And it never recommends deceptive patterns such as fake scarcity, hidden costs or obstructed cancellation.

When implementing, it records the git state, runs a baseline, changes things in small groups, checks the diff, re-runs the checks, and does not commit or push unless asked. Details: [`references/implementation-safety.md`](references/implementation-safety.md).

## Reports

- **Audit report** — executive summary, classification, workflows, strengths to preserve, findings by priority, accessibility, responsive behavior, brand, recommended changes, functional recommendations not implemented, order of work, and the limits of the audit.
- **Implementation report** — baseline, files changed, changes by workflow, accessibility and responsive verification, functionality and brand preservation, tests compared with the baseline, anything not verified, and remaining issues.

Priorities: **P0** blocks a primary task or locks out a group of users; **P1** does major damage to completion, comprehension or error risk; **P2** is meaningful friction; **P3** is polish.

## Limitations

- **It predicts; it does not observe users.** Findings rest on published research and standards. They are not a substitute for testing with your own users.
- **What it can verify depends on access.** From source code alone it cannot confirm rendered contrast, real layouts or focus order; it marks such findings as inferred. Give it a running app or screenshots for more.
- **Not a conformance certificate.** It finds WCAG problems; it cannot prove there are none, and it gives no legal advice.
- **Not performance engineering.** It covers performance only where users feel it.
- **Not a rebrand or redesign tool.** It works within the existing identity.
- **Copy in languages the agent cannot verify** is checked for structure and rendering, not wording.
- **Some guidance is judgment.** Where no strong published source exists (marketplaces, agentic AI, made-to-measure apparel flows), the modules say so. See "Known gaps" in [`references/research-sources.md`](references/research-sources.md).
- **Research ages.** Sources were checked on the dates recorded in the index.
- **Scenario testing so far is a desk check** by the author against the written rules, not a set of independent agent runs.

## Repository layout

```text
adaptive-fwm-ux-ui/
├── SKILL.md                      router: workflow, loading tables, rules that always hold
├── references/
│   ├── classification.md         dimensions, signals, primary/secondary, routes, hard cases
│   ├── conflict-resolution.md    what wins when rules disagree
│   ├── implementation-safety.md  what may be edited, and the procedure
│   ├── research-sources.md       source index
│   ├── core/                     5 modules for every surface
│   ├── profiles/                 14 modules chosen by classification
│   └── patterns/                 8 modules chosen by what is on screen
├── assets/                       classification, audit and implementation report templates
├── README.md
└── CHANGELOG.md
```

## License

No license has been chosen yet. Until one is added, default copyright applies and others may not reuse this work.
