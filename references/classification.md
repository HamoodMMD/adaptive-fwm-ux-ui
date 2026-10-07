# Classification

How to decide which rules apply. Read this before auditing anything that has more than one surface, mixed signals, or no obvious profile.

**Contents:** [The unit is the surface](#the-unit-is-the-surface) · [Dimensions](#dimensions) · [Signals](#signals) · [Primary and secondary](#choosing-primary-and-secondary-profiles) · [Pattern modules](#pattern-modules) · [Route-level classification](#route-level-classification) · [Confidence and questions](#confidence-and-questions) · [Hard cases](#hard-cases) · [No profile fits](#when-no-profile-fits) · [Output](#output)

## The unit is the surface

A **surface** is a set of routes or screens that share the same users and the same goal. Classify each surface separately. Never classify by industry: "fashion" tells you nothing about whether you are looking at a store, a lookbook, a wholesale portal or an inventory tool, and those need different rules.

Start by listing surfaces. Useful boundaries: public versus authenticated; customer versus staff; route prefixes (`/shop`, `/account`, `/admin`, `/app`, `/docs`); separate layouts or navigation shells; separate role guards.

## Dimensions

Record each of these per surface. Unknown is an acceptable value; a guess presented as fact is not.

| Dimension | Typical values |
|---|---|
| Primary user goal | buy, browse, compare, contact, request quote, book, learn, monitor, analyze, manage, configure, create, troubleshoot, approve, collaborate |
| Business goal | ecommerce revenue, lead generation, activation, retention, self-service, operational efficiency, bookings, information delivery, support, internal productivity |
| Audience | consumer, business buyer, existing customer, staff, administrator, developer, technical specialist, agency, mixed |
| Environment | public marketing, ecommerce, public information, authenticated SaaS, customer portal, staff portal, admin system, internal operations, hybrid |
| Interaction model | browse, transact, configure, analyze, monitor, create, converse, manage, search, compare |
| Frequency | one-time, infrequent, recurring, daily, high-frequency |
| Complexity | simple, moderate, complex, expert |
| Error consequence | low, medium, high |
| Device context | mobile-dominant, desktop-dominant, mixed, unknown |
| Content density | promotional, editorial, transactional, operational, data-heavy |
| Language | LTR, RTL, bilingual, multilingual |
| AI involvement | none, assistive, generative, agentic |
| Transaction model | none, lead, ecommerce, subscription, booking, payment, marketplace |
| Roles | anonymous, customer, member, staff, manager, admin, super admin, agency, client, domain-specific |

Three dimensions switch modules on directly, whatever the profile:

- **Error consequence = high** → add `high-stakes`.
- **AI involvement ≠ none** → add `ai-product`.
- **Language = RTL, bilingual or multilingual** → add `patterns/rtl-bilingual`.

Apply `high-stakes` and `ai-product` where the condition actually holds. When it holds only for particular actions or panels inside a surface (the payment step, a delete action, an AI summary panel), scope the module to those and do not count it toward the two-secondary limit. Count it as a secondary only when it characterizes the whole surface, such as an AI workspace or a payments console. An ordinary card payment is enough to scope `high-stakes` to the pay step; routine, reversible team or settings changes are not. Record a scoped overlay in the notes for the surface, and mark it conditional if you have not yet confirmed the action exists.

## Signals

Evidence that suggests a profile. One signal is a hint; agreement between routes, copy and models is a classification. The right-hand column is what should stop you.

| Evidence | Suggests | But not if… |
|---|---|---|
| `/products`, `/cart`, `/checkout`; cart or order models; payment SDK; price and stock fields | ecommerce | the "products" are plans of a single SaaS (that is pricing on a marketing surface) |
| Size and color variants, size guide, fit copy, lookbook or collection pages | fashion-apparel | there is no garment-like product; variants alone are just ecommerce |
| "Get a quote", "Book a call", "Request a demo", contact forms, WhatsApp or phone links, landing pages with one offer | sales-lead-generation | the form is a support ticket or newsletter only |
| Services pages, process, portfolio or case studies, team, service areas, opening hours | service-business | the company sells self-serve software or physical goods online |
| Articles, guides, docs, knowledge base, policies, long-form pages, publication dates | informational-content | the articles are a small blog attached to a product site (classify the blog as its own surface) |
| Solutions or industries pages, integrations, security or compliance pages, demo and pricing tiers, case studies aimed at companies | b2b-marketing | the buyer is an individual consumer |
| Login, workspaces or organizations, onboarding, settings, billing, invitations, roles | saas-application | the users are staff managing business records (that is admin-backoffice). A customer account area is still saas-application, but only its account and settings sections apply |
| Metric cards, charts, date-range pickers, reports | dashboard-analytics | a single decorative chart on a marketing page |
| Uptime, incidents, alerts, severity, health checks, logs, traces, status pages | monitoring-observability | "status" means order status |
| CRUD tables over business entities, bulk actions, staff roles, audit logs, `/admin` | admin-backoffice | the users are customers managing their own few records |
| Prompt inputs, chat, generation, model or provider config, AI history, "regenerate" | ai-product | AI is mentioned only in marketing copy |
| Availability, calendars, time slots, appointments, reservations, party size | booking-reservation | dates are only delivery dates of an order |
| Many sellers or providers, listings, seller profiles, reviews of providers, location search | marketplace-directory | all listings belong to one seller (that is ecommerce or service-business) |
| Payments or transfers, deletion of important data, permission changes, legal or medical records, production controls | high-stakes | the consequence of an error is trivial and undoable |

Do not infer from filenames alone when copy or data models disagree. `Dashboard.tsx` in a store is usually an account page, not an analytics product.

## Choosing primary and secondary profiles

The **primary** profile describes what kind of surface the user is in: its environment and dominant task. **Secondary** profiles add a domain, a capability or a risk level on top.

1. Ask what the user mainly came to this surface to do. The profile whose "main job" (see the table in SKILL.md) matches is the primary.
2. Profiles that describe a domain or capability are normally secondary when a broader environment profile also applies:

| Usually primary | Usually secondary or overlay |
|---|---|
| ecommerce, service-business, informational-content, b2b-marketing, saas-application, admin-backoffice, booking-reservation, marketplace-directory | fashion-apparel (overlay on a store or brand site), sales-lead-generation (conversion layer on a service or B2B site), dashboard-analytics (a view type inside an app), monitoring-observability (a domain inside an app), ai-product (a capability), high-stakes (a risk level) |

   Two "usually primary" profiles can also combine. A company selling *services* to businesses is `service-business` primary with `b2b-marketing` secondary; a company selling a *product or platform* to businesses is `b2b-marketing` primary. A store that also takes bookings is `ecommerce` or `booking-reservation` primary according to which transaction dominates.

   A landing or pricing page that belongs to a business product's site is `b2b-marketing` primary with `sales-lead-generation` secondary; only a standalone campaign page is `sales-lead-generation` primary. A blog attached to a commercial site is its own `informational-content` surface even though it exists partly to sell. A provider's or seller's own tool is `saas-application`; a tool where staff process other people's records is `admin-backoffice`.

3. A normally-secondary profile becomes primary when nothing broader applies: a standalone landing page is `sales-lead-generation`; a standalone chat tool with no workspace features is `ai-product`; a standalone metrics page is `dashboard-analytics`.
4. Keep at most two secondaries. If more than two qualify, first check whether the surface is really two surfaces that should be split, and whether `high-stakes` or `ai-product` applies only to part of it (then scope it to that part, as described under Dimensions). If more than two still qualify, keep the two that change the most recommendations and say which one was left out.
5. When two primaries are equally plausible and their rules agree, pick either, say so, and move on. Ask only if they would lead to different recommendations.

Worked compositions:

| Product | Primary | Secondary | Patterns likely present |
|---|---|---|---|
| Fashion store | ecommerce | fashion-apparel | search-filter-sort, forms, responsive-mobile, loading-empty-error-states |
| Agency website | service-business | sales-lead-generation, b2b-marketing | forms, navigation, responsive-mobile |
| Monitoring SaaS | saas-application | monitoring-observability, dashboard-analytics | charts-data-viz, tables, loading-empty-error-states |
| AI workspace | saas-application | ai-product | forms, loading-empty-error-states |
| Booking marketplace (one search-and-book flow; split into surfaces for a whole-product audit, see Hard cases) | booking-reservation | marketplace-directory | search-filter-sort, forms, responsive-mobile |
| Internal operations tool | admin-backoffice | — | tables, search-filter-sort, forms |
| Documentation site | informational-content | — | navigation, search-filter-sort |

## Pattern modules

Pattern modules follow the interface, not the profile. Load one when its element is actually present on the surface being audited:

- a form with more than a search box → `forms`
- site or app navigation in scope → `navigation`
- a data table or dense list → `tables`
- search, facets, filters or sort controls → `search-filter-sort`
- any chart → `charts-data-viz`
- data fetched asynchronously, or any app-like surface → `loading-empty-error-states`
- mobile or mixed use, or the user asked about responsiveness → `responsive-mobile`
- `dir="rtl"`, Arabic, Hebrew, Persian or Urdu content, translation files, or a language switcher → `rtl-bilingual`

For a desktop-dominant internal tool, `responsive-mobile` is loaded only to check that the tool degrades honestly at narrower widths, not to redesign it for phones.

## Route-level classification

Give a project-level summary, then override per surface. Example for one fashion brand:

| Surface | Routes | Primary | Secondary | Notes |
|---|---|---|---|---|
| Home and campaigns | `/`, `/collections/*` | ecommerce (discovery) | fashion-apparel | Visual-led; marketing whitespace is appropriate |
| Product | `/product/*` | ecommerce | fashion-apparel | Size, fit, variant imagery |
| Checkout | `/cart`, `/checkout/*` | ecommerce | — | `high-stakes` scoped to the payment step only |
| Customer account | `/account/*` | saas-application (account and settings sections only) | ecommerce (orders, returns) | No onboarding or team rules |
| Staff admin | `/admin/*` | admin-backoffice | — | Density and efficiency preserved; desktop-dominant |

Rules for route-level work:

- A finding belongs to one surface. Do not carry a rule from one surface to another: whitespace guidance for the home page says nothing about the admin tables.
- Shared components (header, buttons, form fields) are judged against every surface that uses them. If one component cannot serve both a marketing page and an admin table well, say so rather than forcing one style.
- When the user scopes the request ("audit the checkout"), classify only that surface, but note the neighbors if the flow crosses into them.
- Brand inventory is project-wide; density and tone may legitimately differ per surface.

## Confidence and questions

- **High** — routes, copy and data model agree. Proceed.
- **Medium** — state the classification and the alternative you considered; proceed if both lead to compatible recommendations.
- **Low** — ask.

Ask only what remains unresolved, at most 3–5 questions, each with options:

1. What is the main thing users should accomplish here? (buy · contact or request a quote · book · learn · use an application · monitor or analyze · manage operations · other)
2. Who is the primary user? (consumer · business customer · existing customer · staff · administrator · technical specialist · mixed)
3. Is this mainly public, authenticated, internal or mixed?
4. What is the most important business outcome? (sales · leads · bookings · activation or retention · efficiency · comprehension)
5. Are users mainly on mobile, desktop or both?

Device context is usually answerable from evidence (analytics notes in docs, mobile-first CSS, a native-app shell, an admin tool with wide tables). Ask about it last.

## Hard cases

| Situation | Classify as | Why |
|---|---|---|
| Fashion company with no store | informational-content or sales-lead-generation as primary (by goal: read about the brand, or find stockists and inquire), fashion-apparel secondary for imagery and collections only | No cart means no ecommerce rules; never recommend adding fake "add to bag" |
| Store selling digital software licenses | ecommerce; not fashion; skip shipping, stock and delivery sections | Replace them with license terms, delivery method, system requirements and refund terms |
| Marketing home page plus admin app | Two surfaces: b2b-marketing or service-business for the site, admin-backoffice or saas-application for the app | One rule set would damage one of them |
| B2B service company with online checkout | service-business primary; ecommerce secondary on the checkout surface only | The purchase is a step inside a consultative journey |
| Technical dashboard with a public landing page | Landing page: b2b-marketing or sales-lead-generation. App: saas-application + dashboard-analytics (and monitoring-observability if it is about system health) | Never apply marketing whitespace to the dashboard |
| AI product with no dashboard | ai-product primary; add saas-application only if there are accounts, workspaces or settings to audit | Do not go looking for dashboards that are not there |
| Marketplace with booking | Discovery surfaces: marketplace-directory. Reservation flow: booking-reservation. Provider tools: saas-application or admin-backoffice | Two-sided products are always several surfaces |
| Restaurant with online ordering | ecommerce primary for the ordering flow (menu as catalog, modifiers as variants); booking-reservation secondary for the chosen pickup or delivery slot; a table reservation page is its own surface with booking-reservation primary; service-business for the brochure pages | Skip shipping-by-courier and returns rules |
| Arabic-only store | ecommerce + `rtl-bilingual` (RTL sections; skip language-switching) | RTL correctness is needed even with one language |
| Bilingual admin app | admin-backoffice + `rtl-bilingual` + tables | Mirrored tables and mixed-direction data are the main risks |
| Mobile-first consumer app | Profile by task as usual (a signed-in app people return to is saas-application); `responsive-mobile` weighted heavily; desktop rules about hover and density dropped | Device context changes weighting, not the profile |
| Wholesale or B2B ordering portal | ecommerce primary with saas-application secondary; fashion-apparel only if buyers choose garments by size and color | Speed of reordering and account pricing matter more than visual discovery; sign-in before purchase is legitimate |
| A fashion company's inventory or operations tool | admin-backoffice; not fashion-apparel | The industry does not decide the profile; the task does |
| Desktop-heavy internal operations tool | admin-backoffice; `responsive-mobile` only for honest degradation | Do not trade expert efficiency for phone layouts nobody uses |
| Customer account area of any store or service | saas-application, using only its account, settings and self-service sections | The onboarding, team and activation rules do not apply |
| Seller or provider dashboard inside a marketplace | saas-application or admin-backoffice | It is a work tool, not a discovery surface |
| Public status page of a monitoring product | monitoring-observability primary with a non-technical audience; content-and-trust weighted | Business-readable explanation matters more than diagnostics |
| Pricing page of a SaaS | b2b-marketing or sales-lead-generation | It has prices but no cart; ecommerce checkout rules do not apply until a real checkout begins |
| Consumer landing page whose goal is sign-up or an app install | sales-lead-generation, treating the sign-up or install as the lead action | Skip the quote, contact-channel and B2B sections |
| Portfolio or personal site | service-business if it sells the person's services; otherwise no profile, core modules only | Do not invent a sales funnel for a site that only presents work |
| Internal analytics or reporting tool for staff | dashboard-analytics primary | There are no records to manage, so admin-backoffice adds little |
| A product that qualifies for many profiles at once (for example a monitoring SaaS with AI summaries and a "restart service" action) | Surface: saas-application + monitoring-observability + dashboard-analytics. AI panel: ai-product, scoped to the panel. Restart action: high-stakes, scoped to the action | Scoped overlays do not count toward the two-secondary limit |
| The request names something the code calls a "dashboard" | Classify by what the screen does, not by its name | A store's "dashboard" is usually an account page; a SaaS "dashboard" may be a home screen with no metrics |

## When no profile fits

Some surfaces match nothing here: a game, a social feed, a media player, a learning platform, a developer CLI's web console. Do not stretch a profile to cover them.

1. Say that no profile fits and name the closest one and why it was rejected.
2. Audit with the core modules and whichever pattern modules apply.
3. Borrow individual sections of a profile only where the task genuinely matches (for example the checkout section of `ecommerce` for a course purchase), and say that you did.
4. Report the gap under "Classification" so the maintainer knows a new profile may be worth adding.

## Output

Report the classification with [assets/classification-template.md](../assets/classification-template.md). For a scoped review, three lines are enough:

```
Surface: checkout (/cart, /checkout/*) — ecommerce; high-stakes scoped to the payment step; patterns: forms, responsive-mobile
Users and goal: consumers completing a purchase, mostly on mobile
Confidence: high (cart and order models, payment SDK, checkout routes)
```
