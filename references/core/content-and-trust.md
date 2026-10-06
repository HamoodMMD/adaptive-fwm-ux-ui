# Content and trust

Whether people understand what they read and believe what they are told.

**Load when:** full audits; any surface that asks for money, personal data or commitment; any copy review.
**Skip when:** auditing a purely structural or behavioral issue with no copy in question.

## Objectives

Users understand what this is, what they can do, what it will cost them and what happens next, in words they would use themselves. They can verify that the organization is real and that its claims are true. Nothing in the interface works by misleading them.

## Priority principles

1. Start from the user's need: who they are, what they are trying to do, and why. Content that serves the organization's structure instead of that need is the most common content failure.
2. People scan before they read. Put the conclusion first and make structure visible.
3. Plain language is not dumbing down. Specialists also read plain language faster; keep technical terms where the audience needs them and drop the rest.
4. Say the uncomfortable things early: price, fees, limits, commitments, what data is needed and why.
5. Trust is earned by being verifiable and lost by being evasive.

## Checks

### Clarity
- The page or screen states its purpose in its title and first lines. A first-time visitor can say what the organization or product does within seconds.
- The most important information comes first (inverted pyramid). One idea per paragraph; short sentences; active voice.
- Headings are descriptive statements of what follows, not clever or generic labels, and work when read on their own.
- Lists, tables and short paragraphs are used where content is a set, a comparison or a sequence.
- Words match the audience's vocabulary. Internal names, codenames and unexplained abbreviations are replaced or explained in place.
- Technical surfaces keep precise technical terms; consumer surfaces do not borrow them.
- Numbers carry their units, currency and period. Dates are unambiguous for an international audience (month named, or a clearly stated format). Time shows its time zone where that could matter.

### Actions and links
- Button and link text says what will happen or where it leads: "Download invoice", "Request a quote", not "Submit" or "Click here".
- The same action has the same label everywhere.
- A call to action that starts a commitment says so: "Start free trial — card required" is honest; "Get started" hiding a payment form is not.
- Links are distinguishable from surrounding text by more than color.
- Destructive actions are labeled with the verb and the object.

### Microcopy and messages
- Field labels are nouns or short questions; help text explains format or reason before the user needs it.
- Error messages say what went wrong and how to fix it, in the terms used by the label. No blame, no jokes, no bare codes.
- Success messages confirm what happened and state the next step or expectation ("We'll reply within one working day").
- Empty states explain what belongs here and how to start.
- Tone is consistent with the brand and appropriate to the moment: calm for errors, plain for money, never playful about a user's failure.

### Credibility
- A real organization is evident: legal or trading name, physical address or service area, contact routes that work, and the people behind it where that is appropriate.
- Expertise is shown, not asserted: credentials, authorship, methods, references, real work.
- Claims are verifiable: figures have a source or basis; testimonials are specific and attributed; third-party proof links out where possible.
- Content is current: dates on time-sensitive material, no stale offers, no "© three years ago" on an active site, no dead links.
- Promotional content is restrained and clearly separated from editorial or product information. Sponsored placements are labeled.
- The site is free of the small errors that undermine confidence: typos, broken images, placeholder text, mismatched data.

### Upfront disclosure
- Full price, mandatory fees, taxes and delivery or service charges are visible before the user commits, as early as they can be known.
- Subscription terms (amount, cadence, renewal, how to cancel) are stated at the point of sign-up.
- Policies that affect the decision (returns, cancellation, refunds, guarantees, data use) are linked where the decision is made, in plain words.
- When personal data is requested, the reason is given, especially for phone number, date of birth, ID and location.
- Limitations are stated: stock, availability, service area, eligibility, what the product does not do.

### Honest persuasion
Legitimate: real urgency (an actual deadline, actual remaining stock from live data), real social proof, clear benefits, risk reversal that is honored.

Never recommend or implement:
- Fake scarcity or countdown timers that reset.
- Fabricated reviews, ratings, logos, user counts or "someone just bought" notices.
- Confirmshaming: decline options worded to shame ("No thanks, I don't like saving money").
- Hidden costs revealed at the last step; drip pricing.
- Items or add-ons placed in the cart without the user choosing them.
- Pre-ticked consent or marketing opt-ins.
- Asymmetric choices: a prominent "Accept" beside a buried or disguised "Decline".
- Obstructed cancellation: signing up online but cancelling only by phone; extra steps designed to exhaust.
- Trick wording, double negatives, disguised ads, nagging that ignores a previous "no".
- Forced continuity without clear notice before the first charge.

If any of these already exist in the project, report them as findings (P1 where they affect money or consent) with the trust and regulatory risk stated plainly. Do not give legal advice; do say that regulators treat several of these as deceptive practices.

## Anti-patterns

- A hero headline that could belong to any company.
- "Welcome to our website."
- Headings such as "Solutions", "Overview", "Learn more" with nothing specific under them.
- Walls of undifferentiated text.
- "Click here", "Read more", "Submit".
- Jargon and internal product names in navigation.
- Stock photos of anonymous people presented as the team or customers.
- Testimonials with no name, role or company.
- Price hidden behind "Contact us" when a price or range exists.
- Error text such as "Something went wrong" with no next step.

## Exceptions and context

- **Specialist and expert tools** should use the field's own terms; plain language means clear structure and no needless words, not avoiding necessary vocabulary.
- **Brand voice** may be distinctive. Voice governs how something is said, never whether the essential facts are present.
- **Regulated text** (legal notices, consent wording, financial or medical disclaimers) may be mandated. Do not rewrite it; improve its placement, hierarchy and surrounding explanation, and flag anything unreadable for the owner.
- **Pricing that truly varies** (enterprise, custom work) cannot always be shown exactly. Ranges, starting prices, typical scenarios or the factors that drive price still help.
- **Translated content** must be reviewed by a competent reader of the language; do not judge or rewrite copy in a language you cannot verify. See `patterns/rtl-bilingual.md`.

## Implementation cautions

- Copy changes are UI-safe, but check whether the string lives in a translation file, a CMS or a shared constant, and change it at the source in every language you can verify. Flag the languages you could not.
- Do not change translation keys, analytics labels or text that tests assert on without updating those references and confirming it is in scope.
- Never write claims you cannot verify from the project: no invented statistics, customer names, awards, certifications, prices or guarantees. Use only what the project already states, and mark anything needed from the owner as a placeholder request in the report, not in the product.
- Legal, consent and compliance wording is the owner's decision. Recommend; do not edit.

## Sources

- [GOV-06] GOV.UK writing guidelines — user needs, plain language, front-loading
- [NNG-24] How users read on the web — scanning, concise objective writing
- [STAN-01] Stanford guidelines for web credibility
- [NNG-11] Four credibility factors — design quality, upfront disclosure, current content, connection to the wider web
- [NNG-34] Social proof
- [NNG-13] Deceptive patterns
- [FTC-01] Bringing Dark Patterns to Light
- [NNG-07] Error-message guidelines
- [GOV-02] Writing error messages
- [NNG-28] Showing prices
