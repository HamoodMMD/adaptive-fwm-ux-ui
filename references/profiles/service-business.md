# Service business

Sites for companies that sell services: agencies, consultancies, contractors, clinics, studios, trades, professional and local services.

**Load when:** the site's job is to explain what a service company does, show it is competent and trustworthy, and lead to contact.
**Skip when:** the product is self-serve software or goods sold online.
**Journey:** arrive → understand what they do and whether it is for me → check competence and trust → find how to engage → contact.
**Pair with:** `profiles/sales-lead-generation` for the conversion mechanics; `profiles/b2b-marketing` when the buyers are companies; `patterns/navigation`, `patterns/forms`, `patterns/responsive-mobile`.

This profile covers the information a service site must carry and how it is organized. The mechanics of calls to action and inquiry forms are in `sales-lead-generation`.

**Selling surfaces:** read `patterns/sales-journey` and `selling-strategies.md` for home, landing, product and pricing pages.

## Objectives

Within moments a visitor knows what the company does, for whom and where. Within minutes they can judge whether the company is real, capable and a fit, understand how working together goes, and reach a person.

## Priority principles

1. **Say what you do, plainly, first.** Visitors look for four things: what the organization does, who is behind it, how to contact it, and whether it can be trusted.
2. **Services are the product.** Each one deserves a page that answers a buyer's questions, not a paragraph of adjectives.
3. **Show the work.** Real projects, real people and real outcomes outweigh any claim.
4. **Make contact easy and human.** A service is a relationship; the route to a person should never be more than one step away.
5. **Layer the detail.** A one-line statement on the home page, a summary page, deeper pages for those who want them.

## Checks

### What the company does and for whom
- The home page states the service category, the audience and the location or reach in its first screen.
- The services offered are listed by name, in customers' terms, on the home page or one step from it.
- Who the company serves is explicit: industries, company sizes, consumer segments, or "not a fit for" where that saves everyone time.
- Navigation labels are plain: Services, Work, About, Contact, or the local equivalents, not invented names.

### Services
- Each significant service has its own page covering: what it is, who it is for, what is included and excluded, how it is delivered, typical timeline, what the client needs to provide, indicative price or pricing model, and proof specific to that service.
- Related services are cross-linked; packages or tiers are comparable side by side.
- The page ends with a next step relevant to that service.
- A services overview lets visitors compare and choose without opening every page.

### Service area and availability
- Where location matters, service areas are named in text (cities, regions, countries), not only drawn on a map.
- Opening hours, appointment requirements and response times are stated and current.
- Multi-location businesses give each location its own address, hours, phone and directions.
- Remote or international delivery is stated where it applies, with time zones and languages served.

### Process
- "How it works" is shown as a short sequence of named steps, from first contact to delivery, with what happens and who does what at each.
- Timeframes and decision points are indicated honestly.
- What happens immediately after an inquiry is spelled out.

### Credibility
- Legal or trading name, registration or license details where the sector expects them, and a real address or stated service base.
- Years in operation, team size and notable clients only as far as they are true and current.
- Certifications, accreditations, memberships and insurance where relevant, linked to the issuing body where possible.
- Reviews on independent platforms are linked, not only quoted.
- Photography shows the actual team, premises and work in preference to stock imagery.

### Portfolio and case studies
- Work is presented with context: the client or type of client, the problem, what was done, and the result.
- Visitors can filter or browse by service, industry or project type when there are more than a handful.
- Each case study links to the service it demonstrates, and each service page links back to relevant work.
- Dates or years show that the work is recent.
- Confidential work is described without naming the client, and says so.

### Team and company
- An About page explains who is behind the company, its story in brief, and what it values, without displacing practical information.
- Key people have names, roles and photos; credentials where they matter (clinics, legal, engineering).
- Company information is layered: tagline on the home page, summary on About, detail on sub-pages, key facts in the footer.

### Contact
- Contact details are reachable from every page, in the same place.
- Several channels are offered (phone, messaging, email or form, address), each working and each labeled with when it is answered.
- The contact page includes a map or directions where visits happen, and parking or access notes where useful.
- Forms state what happens next and how soon. Detail: `sales-lead-generation`, `patterns/forms`.

### Quote and request flows
- The route to a quote is visible on service pages and says what the visitor will get and when.
- Longer request forms are staged, show progress, allow attachments where the work needs them, and let the visitor review before sending.
- The confirmation repeats the request and names the next step.

### Questions and policies
- Common questions are answered where they arise (pricing, timelines, guarantees, cancellations), and collected on an FAQ page.
- Terms that affect the decision are summarized in plain language.

## Anti-patterns

- A home page that says "We deliver innovative solutions" and nothing else.
- Services listed only as icons with one-word labels.
- No prices, ranges or pricing model anywhere.
- Portfolio as an image wall with no context.
- Stock photos passed off as team or clients.
- Contact reachable only through a form, with no phone, address or hours.
- "Our process" as generic buzzwords: Discover, Design, Deliver.
- Case studies from many years ago with no dates.
- A map embed as the only statement of location.
- Separate, near-duplicate pages per city written for search engines instead of people.
- Team page with names and no roles, or none at all.

## Exceptions and context

- **Solo practitioners and very small firms** do not need a deep site; one clear page with services, proof and contact can be right.
- **Emergency and trade services** should lead with phone and availability, not narrative.
- **Healthcare, legal and financial practices** have rules about claims, testimonials and advertising that vary by jurisdiction. Keep within what the project already publishes and flag anything that looks like a regulated claim; give no legal advice.
- **Confidential or enterprise work** may prevent named case studies; anonymized ones with real substance still count.
- **Creative studios** may lead with work instead of words. That is a valid identity; check that what they do and how to hire them is still findable.
- **Bilingual markets:** both languages should carry the full content, not a reduced second version. See `patterns/rtl-bilingual.md`.

## Implementation cautions

- Content structure and wording are UI-safe to edit, but most service sites keep content in a CMS; change templates and report content gaps instead of hard-coding copy into components.
- Never invent services, prices, clients, case results, team members, credentials, addresses or hours. Request missing facts in the report.
- Do not change contact details, form recipients, map coordinates or structured-data fields.
- Reorganizing navigation or URLs is a routing and search-visibility change. Recommend it with a redirect plan; do not implement it as a UI fix.

## Sources

- [NNG-29] About Us information — what users look for, four levels of detail
- [STAN-01] Web credibility guidelines — real organization, expertise, contact
- [NNG-11] Credibility factors — upfront disclosure, comprehensive and current content
- [NNG-28] Showing prices
- [NNG-12] B2B usability — research-stage information needs
- [NNG-24] Scannable, objective writing
- [NNG-34] Social proof

Guidance on service-page content, process sections and portfolio structure applies these credibility and content findings to service sites by reasoning (evidence class: Judgment).
