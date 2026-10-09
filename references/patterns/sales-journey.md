# The sales journey: the site as a salesperson

A selling site does the job a good salesperson does in a shop: greets, works out what the visitor wants, shows the right thing, answers doubts, makes buying easy and follows up. A site that is confusing or hard to get around is a bad salesperson, and visitors leave the way customers walk out of a shop.

**Load when:** the surface exists to sell, sign up or win a lead: home pages of commercial sites, landing and sales pages, product and pricing pages, quote and booking entry points.
**Skip when:** the visitor is already a signed-in user doing work, or the surface is reference content with no commercial goal.
**Pair with (when present):** [selling-strategies](../selling-strategies.md) for which kind of salesperson this site is trying to be, `patterns/pricing-and-persuasion`, `patterns/visual-scale`, `patterns/forms`, `core/performance`.

## Objectives

A first-time visitor, on a phone, with no prior knowledge of the brand, can tell within seconds what is offered and that they are in the right place, can get to what they came for without hunting, finds each doubt answered before it stops them, and can act with little effort at the moment they are ready. Nothing in the interface gives them a reason to leave that the offer itself did not.

## Priority principles

1. **Lower the effort before raising the desire.** A visitor acts when motivation, ability and a prompt meet. Motivation mostly arrives with the visitor; ability and the prompt are the interface's job.
2. **Every reason to leave is either the offer's or the interface's.** The audit hunts the second kind: confusion, hunting, waiting, interruption, surprise.
3. **The first seconds decide whether the rest is seen.** Most visits end within 10 to 20 seconds; pages that hold a visitor for 30 are usually kept much longer.
4. **Familiar is easy.** Visitors spend most of their time on other sites. Conventional placement and wording cost them nothing; novelty costs effort that must buy something.
5. **A good-looking site gets patience, not forgiveness.** Polish makes small problems tolerable. It does not rescue a visitor who cannot find the price or the button.
6. **One salesperson, one manner.** A page has one lead selling strategy (see selling-strategies). Other strategies may serve a single stage, such as proof at the answer stage or a quiz for guiding, without changing the page's manner.

## Checks

### The walk-out test (do this first)
Open the surface as a first-time visitor, starting with the device the classification says most visitors use (a phone when unknown), then the other. Go from arrival to the main action without using prior knowledge. Write down every moment a reasonable visitor could give up, and what caused it: *did not understand*, *could not find*, *could not tell what would happen*, *had to wait*, *was interrupted*, *was surprised*, *was steered*, *had to work*, *did not believe*, *could not finish*.

- Each moment caused by the interface or by missing content is a finding. Priority follows the usual rule (impact on the main task, SKILL.md Step 7): a dead end at the close can be the worst problem on the page, because the visitors it loses are the ones who had decided. Use the stage only to order findings of equal impact, earliest first.
- A moment caused by the offer itself (the price, a long commitment, no refunds) is not an interface finding. List it separately for the owner as "the offer's own reasons to leave", and check only that it is stated honestly.
- Show the result as a short table in the report: stage, moment, cause.

### 1. Greet: the first screen
A good salesperson says hello and lets you look. A bad one blocks the door.
- Within the first screen the visitor can answer: what is this, is it for me, what can I do here.
- The headline says what is offered in plain words. A clever line is fine when the line beneath it is plain.
- Nothing covers the offer on arrival. Consent, region, app-install, newsletter and promotional layers are the smallest the law and the business allow, do not stack, and do not hide the headline or the main action. Email capture waits until the visitor has seen something of value.
- The first screen is light enough to appear fast: the main image or headline is the first thing painted, with no layout jump.
- The visitor who arrived from an ad, a search or a link sees the words that brought them.
- The look matches what visitors expect of this kind of site and is visually calm: both shape the instant impression.

### 2. Guide: find out what they want and point the way
A good salesperson asks what you are looking for. A bad one makes you search the whole shop.
- The main routes are visible and named in the visitor's words: the one to four things most visitors come to do.
- Navigation labels carry scent: specific, plain, no internal or brand-only names. Each link delivers what its label promised.
- Where visitors differ by need, the site asks or lets them choose (a segment switch, a short quiz, categories, a search box), and the choice changes what they see.
- Search is easy to find wherever there is more to offer than fits a menu.
- A visitor is never more than one obvious step from the next thing: no dead ends, no orphan pages, no section that looks like the end of the page when more follows.
- Category and product listings let the visitor judge and act from the list where the product allows it.

### 3. Show: present the thing
A good salesperson puts the product in your hands. A bad one talks about the company.
- The product or service is shown, not only described: real images, the real interface, real examples of the work.
- Each section answers the question the previous one raised, in the order a buyer asks them: what is it, what does it do for me, how does it work, what does it cost, why believe you, what do I do next.
- Sections are short, headed by a line that carries the point on its own, and scannable; most text is never read.
- Motion and video support the showing. They do not delay reading, hijack scrolling, autoplay with sound or hide the content from people who do not wait.
- The price, or how pricing works, appears before the visitor has to ask.

### 4. Answer: remove the doubts
A good salesperson hears the objection and answers it there. A bad one changes the subject.
- The doubts a reasonable buyer has (cost, fit, quality, risk, effort, what happens next) are each answered at the point they arise, not only on a separate page.
- Proof sits next to the claim it supports and near the action: ratings, named customers, numbers, guarantees and return terms that the project really has.
- Delivery, returns, cancellation and commitment terms are visible before the visitor commits.
- Tone fits the purchase: trust matters more than charm, and humor is a risk where money or health is involved.

### 5. Close: make acting easy
A good salesperson has the till open when you are ready. A bad one sends you to queue somewhere else.
- The main action is on the first screen and stays in reach down the page. Two limits apply together: never two instances of it visible at the same time, and never more than about two phone screens of scrolling without one in view. Meet both by repeating it at decision points, or by a compact action in a sticky header or slim bottom bar that does not duplicate a button already on screen.
- The label says what happens ("Check our prices", "Start with a quiz", "Send money now").
- The step after the click is the one the label promised, with no account wall before value. Guest paths exist; sign-up comes after the visitor has received something.
- The action asks for the least possible: few fields, sensible defaults, sign-in shortcuts where supported, no information requested twice.
- On phones the action sits where a thumb reaches it and is large enough to hit without care.
- A lower-commitment alternative exists for visitors who are not ready.

### 6. After: finish well
The last moment is the one remembered.
- The confirmation says what happened, what happens next and when, and gives a useful next step.
- Errors keep what the visitor entered and say how to recover.
- Leaving is not punished: no exit pop-ups, no guilt wording.

### Ease of getting around (applies at every stage)
- **Effort:** count what the main journey costs in reading, scrolling, looking, deciding, tapping, typing, waiting and remembering. Remove steps that buy nothing.
- **Convention:** logo, navigation, search, cart, account and buttons are where visitors expect them and look like what they are.
- **Clutter:** the page uses a small, consistent set of sizes and colors, and nothing important is styled like an advertisement.
- **Speed:** the page feels fast on a mid-range phone. Detail: `core/performance`.
- **Recovery:** back works, the visitor always knows where they are, and a sticky header or menu offers a way out of long sections.

### Observed practice
Sixty-six pages of established selling sites were walked top to bottom in October 2026; 56 loaded usably on a phone-sized screen and are counted here (SURVEY-02 in the source index). Context for judgment, not targets.

| Measure | Middle half of sites | Median |
|---|---|---|
| Page length | 7.5 to 17 screens | 11 |
| Words on the first screen | 25 to 65 | 42 |
| Headline length | 4 to 7 words | 5 |
| Real actions on the first screen | 1 to 3 | 2 |
| Words per screen down the page | 56 to 113 | 79 |
| Repeats of the main action on the page | 1 to 4 | 2 |
| Sticky header height | 46 to 81px | 65px |
| Distinct rendered text sizes, small labels included | 7 to 10 | 9 |
| Largest paint (one cold visit) | 1.6 to 4.1s | 2.3s |

- 48 of 56 put a real action on the first screen. Most of the rest were store home pages that lead with products.
- 24 of 56 greeted a first-time visitor with a layer over the first screen (consent, region choice, app prompt or promotion). On several, it covered the headline or the main action. This is the most common "blocked door" among otherwise excellent sites.
- Only 5 of 56 used any urgency wording, and only on real, dated offers.
- 8 kept a slim action bar fixed to the bottom of the phone screen, usually the product name, price and one button.

## Anti-patterns

- A headline that could belong to any company.
- A full-screen image or video with the offer below it.
- A dialog, banner or game over the page before the visitor has seen anything.
- Two or three stacked layers on arrival.
- Menu labels only an employee understands.
- "Learn more" as the only action.
- A sign-up wall before any value.
- A long scroll-driven animation the visitor must sit through to reach the price.
- Text that fades in after the visitor arrives at it.
- The main button visible only at the very top or the very bottom of a long page.
- Proof on a separate page nobody visits.
- A different tone, layout and button style in every section.
- An exit pop-up begging the visitor to stay.

## Exceptions and context

- **Legally required layers** (consent, age checks) stay. Their size, placement and wording are still interface decisions.
- **Returning and expert visitors** want speed, not a greeting; keep direct routes to sign-in, reorder and search.
- **Brand and awareness pages** may not aim for an immediate action; judge them by their real goal.
- **Considered and business purchases** span many visits and people. The "close" is often a smaller step (pricing, a demo, a shareable summary).
- **Small sites.** The observed figures come from large brands with long pages. A two-screen page for a local business is not an outlier to fix; apply the stages, ignore the lengths. For a single-page site, read this module and, in the strategy catalog, only the identification table and the one strategy that matches.
- **Pricing, product and checkout pages** are one stage of a larger journey. Judge them as that stage and take the strategy from the site they belong to.
- **Luxury and display-led brands** deliberately slow the visitor down. Respect it; check only that the routes and the action exist and work.
- **The evidence.** Checks on first impressions, dwell time, link wording, pop-ups, account walls, scroll effects, video, tone and speed rest on published research (evidence class: Research). The six stages, the walk-out test and the two-screen reach limit are this skill's way of organizing them (Judgment).
- **Rule of record.** This module tells you where a visitor is lost; the detailed rule usually lives elsewhere. Cite that module in the finding: first screen and sizes in `patterns/visual-scale`; message, proof, objections and contact channels in `profiles/sales-lead-generation` or `profiles/service-business`; claims and disclosure in `core/content-and-trust`; prices and offers in `patterns/pricing-and-persuasion`; forms and confirmation in `patterns/forms`; menus in `patterns/navigation`. Report each problem once.

## Implementation cautions

- Reordering sections, moving proof near an action, tightening a first screen and fixing labels are presentation. So is showing an action that already exists at a width where it was hidden, or repeating an existing link to the same destination at a decision point. Adding a new component (a quiz, search, a purchase bar with its own logic, guest checkout, a new section) is functional or content work: recommend it.
- Motion that is part of the identity stays. When it delays reading, shorten it and exempt prices, actions and forms from it; do not remove it.
- Consent and region layers are often third-party scripts with legal settings. Restyle only through their supported options; never suppress or auto-dismiss one.
- Removing a pop-up, changing when it fires or what it captures changes marketing behavior. Report it; change presentation only.
- Shortening or rewriting copy must not change a claim, a price or a promise. Words that do not exist in the project are requested from the owner, not written.
- Navigation labels may be tied to routes, analytics and translation keys. Change visible text only after checking what depends on it.
- After any change to the first screen, repeat the walk-out test on a phone.
- Never report that a change will raise conversion. Report which reason to leave it removes.

## Sources

- [NNG-49] How long visitors stay; [BEH-15], [BEH-16] first impressions in milliseconds, visual complexity and familiarity
- [BEH-18] Behavior needs motivation, ability and a prompt; [NNG-61] interaction cost
- [NNG-62] Visitors expect sites to work like other sites; [NNG-52] cognitive load; [BEH-17] ease of processing and liking
- [NNG-50] The aesthetic-usability effect and its limits
- [NNG-51] Information scent; [NNG-55] home page guidelines; [BAY-18] home page research; [NNG-69] content that looks like advertising is ignored
- [NNG-48] Attention down the page; [NNG-66] the illusion of completeness
- [NNG-60] Pop-ups; [NNG-56] login walls; [NNG-47] give before asking
- [NNG-53] Scrolljacking; [NNG-67] scroll-triggered text; [NNG-57] motion; [NNG-58] video
- [NNG-64] Product pages; [NNG-68] tone and trust; [NNG-11] credibility
- [NNG-59] Peak-end rule; [NNG-70] target size and distance; [UXM-01] how phones are held
- [WEB-10], [WEB-11] Speed and sales; [BAY-01] reasons for abandoning a purchase
- Used with the strategy catalog: [NNG-54] minimalism, [NNG-63] step-by-step flows, [NNG-65] personalization, [NNG-71] business buyers

The salesperson stages, the walk-out test and the "Observed practice" table (SURVEY-02) are this skill's own work (evidence class: Judgment for the first two, own measurement for the third).
