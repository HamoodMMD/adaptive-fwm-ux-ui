# B2B marketing

Public sites that market a product or service to organizations, where buying is slow, researched and decided by several people.

**Load when:** the audience is business buyers evaluating a product, platform or service for their company.
**Skip when:** the buyer is an individual consumer, or the surface is the logged-in product itself.
**Journey:** discover → understand what it is and whether it fits → compare and validate → build an internal case → engage (trial, demo, contact) → return several times with colleagues.
**Pair with:** `profiles/sales-lead-generation` for demo and contact mechanics; `profiles/service-business` when what is sold is a service; `profiles/informational-content` for docs and resource libraries; `patterns/navigation`, `patterns/forms`.

**Selling surfaces:** read `patterns/sales-journey` and `selling-strategies.md` for home, landing, product and pricing pages.

## Objectives

A researcher can work out what the product does and whether it suits their situation without talking to anyone, collect the facts their colleagues will ask for, trust the company enough to shortlist it, and take the next step in the way their organization buys.

## Priority principles

1. **Research dominates.** B2B visitors compare on many criteria over many visits. A site that withholds information loses them to one that provides it.
2. **Several readers, one site.** The person who will use the product, the person who will approve the budget and the people who will vet security and procurement all need different content. Serve each without making any of them self-identify first.
3. **Layer the content.** A plain overview for first contact, depth for evaluation, hard evidence for the business case.
4. **Price is the most wanted and most withheld information.** Give it, or the best honest proxy.
5. **Real things only.** Real screenshots, real customers, real integrations, real numbers.

## Checks

### Positioning
- The home page states what the product or service is, in category terms a newcomer recognizes, who it is for and the problem it solves, before any slogan.
- Differentiation is concrete: what it does that alternatives do not, or for whom it is a better fit.
- The ideal customer is visible: industries, company size, team or role, use cases. Visitors can quickly decide "this is for organizations like mine" or "it is not".
- Jargon and coined product names are explained on first use.

### Content for different readers
- **Decision-makers** find outcomes, business impact, risk, total cost and proof from comparable organizations.
- **Practitioners** find what it actually does, how it works, how it fits their current tools, limits, and documentation.
- **Technical and security reviewers** find architecture or approach, security and compliance information, data handling, availability commitments and support terms.
- **Procurement** finds legal entity, terms, pricing model and contact.
- These are reachable from navigation organized by product, use case or solution. Role-based entry points are offered as an extra, not as a gate visitors must pass through.

### Product and service explanation
- Pages show the real product: actual interface screenshots, short demonstrations, concrete examples of input and output. Abstract illustrations support but do not replace them.
- Features are tied to the task they enable and the outcome that follows.
- "How it works" is explained in steps a newcomer can follow.
- Limits, requirements and prerequisites are stated.
- Comparison content is fair and specific; it does not misstate competitors.

### Proof
- Case studies name the customer where permitted, describe their situation, what was implemented and the measured result, with the period and the basis for the numbers.
- Customer logos are current customers shown with permission; the page says if they are illustrative of a segment.
- Quotes carry a name, role and company.
- Independent validation is linked: review platforms, analyst coverage, certifications, awards.
- Proof is matched to the page: the same industry or use case as the page it appears on.

### Pricing
- A pricing page exists, or pricing is explained, wherever the business model allows: plans, the unit of pricing, what each tier includes, typical totals.
- Where pricing is quote-based, the page gives ranges, starting points, example configurations or the factors that set the price, and says how to get a figure and how long that takes.
- Plan comparison tables use the same attributes in the same order, mark differences clearly, and remain readable on small screens. Detail: `patterns/tables`.
- Billing period, minimum commitment, overage, taxes and what happens at the end of a trial are stated.

### Integrations and ecosystem
- Only integrations that exist are listed. Each says what the integration does, not just a logo.
- Large directories are searchable and categorized.
- Planned or partner-built integrations are labeled as such.

### Trust for organizations
- Security, privacy and compliance information is easy to find and written to be read; certifications are named only if held, with dates or reports available on request.
- Service status, support channels, service levels and data location are stated where relevant.
- Company information is findable: who runs it, where, how long, how to reach people.
- Documentation, changelog and help center are linked from the marketing site, so evaluators can judge the product's maturity.

### Engagement paths
- The primary action matches how the product is actually bought: start a trial, book a demo, talk to sales, get a quote. It says what will happen and how long it takes.
- A self-serve path is offered where one exists; visitors are not forced through a sales call to see a product that has a free tier.
- Demo and contact forms ask only what is needed to route the request. Detail: `sales-lead-generation`.
- Early-stage material (overviews, feature pages, most guides, pricing) is open. Gating is limited to substantial resources and uses a short form.

### Supporting a long buying cycle
- Pages are shareable and self-contained: a colleague opening a link cold can understand it.
- Key material can be saved, printed or downloaded as a summary.
- Returning visitors can pick up where they left off: stable URLs, consistent navigation, no forced re-entry of details.
- No dead ends: every page offers a relevant next step for someone still researching, not only "Contact sales".

## Anti-patterns

- A headline about "transforming the future of work" with no statement of what the product is.
- No pricing information of any kind.
- Every useful document behind a lead form.
- Forcing visitors to choose an industry or role before showing anything.
- Stylized mockups that hide what the product looks like.
- Logo walls of companies that are not customers.
- Case studies with no numbers, dates or names.
- A security page that says "enterprise-grade security" and nothing else.
- Integration logos for integrations that do not exist yet.
- Only one call to action, "Book a demo", on every page including documentation.
- Chatbots that interrupt reading and block content.
- Feature lists with no explanation of what the features are for.

## Exceptions and context

- **Enterprise-only products** with negotiated contracts may truly lack list prices; pricing factors, minimums and typical deployments are the honest alternative.
- **Regulated or defense markets** restrict what can be published about customers and capabilities.
- **Early-stage companies** have little proof. Showing the product, the team and the roadmap honestly beats inflated claims.
- **Product-led products** bought by individuals inside companies lean toward trial and documentation; sales-led products lean toward demo and proof. Follow the actual motion.
- **Developer-facing products**: documentation quality is the marketing; lead with it.

## Implementation cautions

- Never write or alter claims, customer names, figures, certifications, integrations, prices or service levels. Use only what the project already states; request the rest.
- Marketing sites are usually CMS-driven; adjust templates and components, and list content gaps for the owners.
- Forms feed CRM and marketing automation: fields, hidden values, ids and events are contracts. Recommend changes.
- Navigation and URL restructuring affects search visibility and inbound links: recommend with a redirect plan.
- Third-party scripts (chat, scheduling, analytics, consent) have their own markup and behavior; restyle only through their supported options.

## Sources

- [NNG-12] B2B usability — long buying cycles, multiple stakeholders, layered content, the cost of withholding information
- [NNG-28] Showing prices — the most wanted information; ranges and scenarios when exact prices cannot be given
- [NNG-27] Gating content — when it is acceptable and how short the form should be
- [NNG-11] Credibility factors
- [STAN-01] Web credibility guidelines
- [NNG-34] Social proof
- [NNG-29] Company information
- [NNG-13] Deceptive patterns

Guidance on serving different reader roles and on trust content for organizations applies these findings by reasoning (evidence class: Judgment).
