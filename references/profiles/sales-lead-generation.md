# Sales and lead generation

Surfaces whose job is to turn a visitor into an inquiry: contact, quote request, demo, call, message.

**Load when:** the conversion is a lead, not an online purchase: landing pages, sales pages, quote and contact flows.
**Skip when:** the user completes the purchase online (use `ecommerce`) or the surface is reference content with no conversion goal.
**Journey:** arrive → understand the offer → believe it → resolve doubts → take the lead action → know what happens next.
**Pair with (when present):** `patterns/forms`, `patterns/responsive-mobile`, `patterns/pricing-and-persuasion`, `patterns/visual-scale`; `profiles/service-business` or `profiles/b2b-marketing` for the surrounding site.

## Objectives

A visitor quickly understands what is offered, for whom and why it is credible, finds answers to the doubts that would stop them, and can make contact through the channel they prefer with as little friction as the business can afford. The persuasion is honest.

## Priority principles

1. **Clarity converts before persuasion does.** A visitor who cannot tell what is offered will not read the proof.
2. **One page, one main action.** Competing calls to action split attention; a consistent primary action with a lower-commitment alternative serves both the ready and the not-yet-ready visitor.
3. **Proof sits beside the claim it supports.**
4. **Every field is a cost.** Ask only what is needed to respond; say why sensitive details are needed.
5. **Honest pressure only.** Real deadlines and real availability may be stated. Manufactured ones are never acceptable.

## Checks

### Message, audience and offer
- The first screen states what is offered, who it is for, and the outcome, in plain words, with the primary action visible.
- The headline is specific to this business; it could not be pasted onto a competitor's page.
- A visitor arriving from an ad, a search or a referral sees wording that matches what brought them.
- The offer is concrete: what the visitor gets by acting (a quote within a day, a 30-minute call, a site visit, a price list).

### Call-to-action hierarchy
- One primary action per view, visually dominant, with the same wording everywhere on the page. It appears once per view: a header button and a hero button with the same label on one phone screen is a duplicate, and one of them moves (usually the header's, into the menu).
- The label names the action or its outcome: "Get a quote", "Book a call", "Chat on WhatsApp". Vague labels such as "Submit", "Learn more" or "Get started" do not tell the visitor what happens.
- A secondary, lower-commitment action exists for visitors who are not ready: view pricing, see case studies, download details.
- On long pages the primary action reappears at natural decision points (after the offer, after proof, after pricing, at the end), not after every paragraph.
- Navigation and footers do not offer a dozen equal-weight exits on a single-purpose landing page.

### Credibility and proof
- Testimonials are specific and attributed: name, role, company or location, ideally a photo, and what changed.
- Case studies show the situation, what was done and the result, with figures only where real.
- Client logos, certifications, awards, press mentions and review-site ratings are real, current and, where possible, link to the source.
- Numbers ("500 projects", "12 years") are accurate and not rounded into claims the business cannot support.
- The people or company behind the offer are identifiable.

### Objection handling
- The page answers what a reasonable buyer would ask before contacting: price or price range, what is included, how the process works, how long it takes, what is needed from them, guarantees or terms, who it is not for.
- Questions and answers are in the visitor's words and placed near the decision, not only on a separate FAQ page.
- Risk is reduced honestly: free consultation, no-obligation quote, cancellation terms.

### Pricing presentation
- A price, price range, starting price or typical scenario is shown wherever the business can state one. Hiding all pricing sends research-stage visitors elsewhere and reads as evasive.
- Where price truly depends on scope, the factors that drive it are explained and the quote step is positioned as the way to get an exact figure.
- Plans or packages are comparable: same attributes in the same order, differences highlighted, the recommended option marked without disguising the others.
- Taxes, minimum terms and extra fees are stated.
- Framing, anchoring, highlighted plans, "free", urgency and other selling techniques: `patterns/pricing-and-persuasion`.

### Inquiry and quote forms
- The form asks for the minimum needed to respond. Extra qualification questions are optional or come after first contact.
- The reason for phone number or other sensitive fields is given; the visitor can choose their preferred contact method where the business supports it.
- A free-text field lets the visitor describe their need in their own words.
- What happens after submission is stated before and after: who will reply, by what channel, how soon.
- Consent and privacy wording is present, unticked by default, and in plain language.
- Detail on labels, validation and errors: `patterns/forms`.

### Contact channels
- Phone numbers are text, tappable (`tel:`), with country code for international audiences and opening hours where relevant.
- Messaging links (WhatsApp and similar) open a chat with the right number and say that is what they do.
- Email is offered as an address or form, not only a `mailto:` that fails without a mail client.
- The channels offered are ones the business actually answers; stated response times are real.
- Chat widgets do not cover the primary action or the form, and can be dismissed.

### Confirmation
- Submission shows a clear success state that repeats what was sent, sets the expectation for a reply, and offers a useful next step.
- The visitor gets a copy by email or message where the system supports it.
- Failure keeps everything the visitor typed and offers another channel.

### Mobile lead generation
- Tap-to-call and tap-to-message are prominent; many mobile visitors would rather talk than type.
- A sticky action bar is appropriate on long pages if it holds one or two actions, leaves the content readable, and does not hide the focused field or sit over the keyboard.
- Forms use the right keyboards and `autocomplete`, and are short enough to finish on a phone.
- Proof and pricing are not collapsed out of sight on small screens.

### Landing and long-form sales pages
- Landing pages keep to one offer and one audience. Reduced navigation is acceptable when the page is a campaign destination; the visitor can still reach the main site and legal pages.
- Long pages have a scannable structure: descriptive headings, short sections, a visible logic (problem → solution → proof → price → action).
- Early-stage content (articles, service descriptions, FAQs) is not gated. Gating is reserved for substantial resources, with a short form and clear value shown outside the gate.

## Anti-patterns

- Countdown timers that reset, "3 spots left" with no real limit, "offer ends today" every day.
- Invented testimonials, reviews, logos or statistics.
- Decline links worded to shame.
- Pre-ticked consent; marketing consent bundled with the inquiry.
- Pop-ups asking for an email before any content is visible; exit pop-ups that block leaving.
- Ten-field forms for a first inquiry; mandatory phone with no explanation.
- "Submit" with no indication of what happens next.
- Three different primary buttons competing in one view.
- Auto-rotating hero carousels carrying the main message.
- Pricing replaced by "Contact us" when a range could be given.
- A phone number as an image, or a WhatsApp icon that opens nothing.
- Hiding the business identity until after the form.

## Exceptions and context

- **Enterprise or bespoke services** may not have list prices; ranges, typical engagements and pricing factors still help.
- **Regulated sectors** may require disclaimers, eligibility wording or identity fields. Keep them; improve their clarity and placement.
- **Qualification by design:** some businesses deliberately add form questions to filter leads. Treat it as a business decision; report the friction and let the owner choose.
- **Brand and awareness campaigns** may not aim for immediate contact; judge them against their actual goal.
- **Local and trade services** often convert best by phone or messaging; the "form" may rightly be secondary.

## Implementation cautions

- Removing, reordering or making fields optional changes what the CRM, email handler or validation receives. Recommend it; do not implement without approval.
- Hidden fields, UTM parameters, tracking attributes, form ids and conversion events must survive any restyling.
- Do not change phone numbers, messaging links, email recipients or form endpoints.
- Consent, privacy and legal wording belongs to the owner. Improve presentation only.
- Never write testimonials, statistics, client names, prices, guarantees or response times that the project does not already state. Where the page needs them, ask for them in the report.
- Do not add urgency, scarcity or social-proof widgets.

## Sources

- [NNG-28] Showing prices — ranges and typical scenarios when exact prices cannot be given
- [NNG-27] Gating content behind forms
- [NNG-12] B2B usability — research-stage needs, barriers created by forms
- [NNG-11] Credibility factors — upfront disclosure
- [NNG-34] Social proof
- [STAN-01] Web credibility guidelines
- [NNG-13] Deceptive patterns
- [FTC-01] Dark patterns report
- [NNG-26] Form usability recommendations
- [NNG-32] Sticky elements

CTA-hierarchy and repetition guidance combines the heuristics on recognition and minimalist design [NNG-01] with this skill's reasoning (evidence class: Judgment).
