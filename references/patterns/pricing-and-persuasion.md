# Pricing, offers and persuasion

How prices, plans, discounts, free offers and proof are presented, and how the well-known effects of choice psychology apply to an interface without deceiving anyone.

**Load when:** the surface shows a price, a plan or package choice, a discount, a free offer, a trial, a guarantee, urgency or scarcity wording, or exists to sell or generate leads.
**Skip when:** nothing is offered for money or commitment (internal tools, dashboards, reference content).
**Pair with (when present):** `core/content-and-trust`, `profiles/ecommerce`, `profiles/sales-lead-generation`, `profiles/b2b-marketing`, `patterns/visual-scale`.

## Objectives

A visitor can see what is offered, what it costs in total, how the options differ and which one suits them, and can decide without being rushed or misled. The page presents the owner's real offer as clearly and favorably as the facts allow. It never improves the offer by inventing one.

## Priority principles

1. **Arrange the offer; never author it.** Prices, plans, tiers, features, discounts, free items, trials, guarantees, deadlines, stock levels and proof belong to the owner. You may change how existing ones are ordered, grouped, labeled and emphasized. You may not create, change or remove one.
2. **Every persuasive element must be true, current and checkable** from the project or from the owner.
3. **These effects are aids to deciding, not levers.** Use them to make a real difference visible. A technique that only works if the visitor misunderstands is deception.
4. **The evidence is uneven.** Several famous effects are weaker or more conditional in practice than their reputation. Never promise a conversion gain; recommend testing.
5. **The total price is part of the interface.** A presentation that makes the price look smaller than what will be charged is a defect, whatever effect it borrows.

## Checks

### Step one: the offer inventory
Before judging or changing anything, list every commercial fact on the surface and where it comes from:

- products, plans or packages, and what each includes
- every price, its currency, billing period, tax treatment and mandatory fees
- discounts: the former price, the saving, the start and end dates, the conditions
- anything described as free, included, bonus or trial, and its conditions
- guarantees, refund and cancellation terms
- deadlines, limited quantities, availability
- proof: ratings, review counts, customer numbers, logos, awards

Mark each as *stated in the project*, *confirmed by the owner* or *unverified*. "Stated in the project" includes what the code demonstrably does: a total the page already calculates, or a field the form already sends, is a fact you may describe. Only inventory items may appear in your work. Unverified items are findings (see "Existing content that cannot be verified" in `implementation-safety.md`).

### Price display
- The price is easy to find, near the action it belongs to, and visually stronger than the surrounding detail.
- Currency, billing period ("per month", "per user per month"), tax inclusion and minimum term are stated beside the price, not in a footnote.
- Mandatory fees are in the headline price or shown beside it before the visitor commits. Optional extras are labeled as optional and are not pre-selected.
- A plan billed yearly but shown per month says so next to the figure ("billed annually") and shows the amount actually charged. The charged amount is at least as prominent as the per-period figure: enlarging one means enlarging both.
- Where pack sizes or quantities differ, a unit price lets visitors compare.
- Quote-based services show a range, a starting price or the factors that set the price, when the owner has provided them.

### Framing
The same fact reads differently depending on how it is put.
- Describe outcomes in the terms the visitor cares about, using figures the project already states.
- Use one frame consistently for comparable options; do not describe one plan by what it includes and the next by what it lacks.
- A frame must leave the visitor with a correct understanding. "From" prices state what the starting configuration is. Percentages and absolute amounts both appear when a saving is claimed.

### Anchoring and the contrast effect
The first figure seen, and the figures nearby, shape how a price is judged.
- Any reference price (a former price, a list price, a competitor price, a higher tier) is real, current and sourced. A former price is one the item was actually offered at for a meaningful period.
- When both a former and a current price appear, the current price is the visually dominant one, the former is clearly marked as former, and the saving sits next to them.
- Plan order is deliberate and consistent across the page, the comparison table and the checkout. Either direction is acceptable.
- No decorative large number sits near the price to act as an anchor.

### Three options, the middle choice and decoys
People often choose a middle option when options are easy to compare, and a clearly inferior option can make its neighbor look better.
- Where the owner offers several tiers, they are shown side by side with the same attributes in the same order and the differences made obvious.
- A "recommended" or "most popular" mark is used only when the owner says which plan it is and, for "popular", that the claim is true. One plan is marked, not several.
- The marked plan is emphasized without hiding, shrinking or graying the others, and cheaper or free options stay as easy to select.
- A page with one or two real options is not a defect. Never propose a tier whose purpose is to be rejected. If a third tier would help buyers, say so as a recommendation to the owner.

### Number of choices
Too many similar options can stall a decision, but the effect depends on how hard the options are to tell apart, not on the count alone.
- Options are few enough to compare at a glance, or are grouped, filtered or staged when there are many.
- Each option says who it is for.
- A comparison table covers about five items or fewer and only the attributes buyers care about; on phones, about two at a time.
- Reducing choice means better organization. Removing a real option from sale is the owner's decision.

### "Free" and the zero price
A price of zero attracts far more than a very low price, which is why the word is regulated.
- "Free" is used only for something the project states is free. Every condition (purchase required, shipping, time limit, card required, auto-renewal) is stated beside the offer.
- A free trial says how long it lasts, whether a card is needed, what is charged afterwards and how to cancel, before any payment details are requested.
- Something already included in the price is described as included, not as a free gift.
- A free tier or trial that exists is easy to find; it is not hidden to steer visitors to paid plans.

### Loss framing, urgency and scarcity
People weigh losses more heavily than equal gains, so deadlines and limits move decisions.
- A deadline, limited quantity or "ending soon" message appears only when it is real, and comes from the system or the owner, with the actual date or number.
- Countdown timers reflect a real end time and do not restart.
- Loss wording describes a real consequence ("your cart is held for 15 minutes" when it is). It does not shame or alarm.
- What the visitor would lose by cancelling or downgrading is stated factually and never blocks the way out.

### Making a price feel affordable
Dividing a cost into smaller periods, or pricing just below a round number, changes how large it feels.
- A per-day, per-month or per-use figure appears only alongside the amount actually charged and the billing period, with equal or greater prominence for what is charged.
- Instalment and pay-later messages state the number of payments, the total, and any interest or fees.
- Price endings (.99, .95, round numbers) are the owner's pricing; leave them as they are.

### Defaults
Pre-selected options are accepted far more often than chosen ones.
- Defaults favor the visitor: the cheapest adequate option, the most common real choice, or none.
- Nothing that costs money, extends a commitment or shares data is pre-selected: no pre-ticked add-ons, insurance, donations, upgrades or marketing consent. A pre-selected paid extra is at least P1.
- The styling that shows the visitor's current selection is different from a "recommended" mark, so a default selection does not read as an endorsement.
- A pre-selected billing period is visible as a selection and the alternative is one tap away.

### Reducing risk and giving first
- Guarantees, free returns, cancellation terms and "no card required" statements that the project already offers sit near the action they reassure.
- Useful content (pricing, specifications, examples) is available before contact details are requested.

### Proof near the price
- Ratings, review counts and customer numbers near a price are real, current and attributed. Detail: `core/content-and-trust`.

### One action, once per view
- A view carries one instance of the primary action. After any change, check that the same button does not now appear twice on one screen (for example in a header and a hero on a phone). Removing a duplicate must not leave the action out of reach: no more than about two phone screens of scrolling without one in view (`patterns/sales-journey`, Close).

### Observed practice
What 19 established subscription pricing pages showed in October 2026 (SURVEY-01 in the source index; found by reading page text, so "not found" is not proof of absence). These describe what those companies really offer. They are context for an audit, never a reason to add something the owner does not offer.

| Element | What was found |
|---|---|
| Plans side by side | 3 to 5, most often 4: commonly a free plan, two paid plans and a "contact sales" plan |
| Order | Cheapest first on nearly every page |
| One plan marked | 12 of 19. "Recommended" or "Best value" on 10, "Most popular" on 2. Usually the third of four; never the cheapest |
| Free plan or free trial | Nearly all. "No credit card required" stated on 5 |
| Monthly and yearly billing | Most offer both, with a stated saving for yearly (17% to 40%). Yearly plans are shown as a monthly figure with "billed annually" beside it; one page also printed the yearly total |
| Price size | 18 to 48px, around 30 typical: prominent, rarely the largest text on the page |
| Crossed-out former price | 4 of 19, each tied to a stated offer |
| "Limited time" wording | 3 pages, in the offer terms |
| Countdown timers, stock or activity notices | None found |
| Cost restated per day or week | 1 page (a newspaper, per week). A phone maker showed a monthly instalment beside the full price |
| Proof near the plans | Customer logos on about half; a customer count on 3 |

## Anti-patterns

- A crossed-out price that was never charged, or a "sale" that never ends.
- "Free" with a condition in a footnote; a trial that takes a card without saying what happens next.
- A fee that first appears at the last step.
- A monthly figure in large type for a plan that can only be paid yearly, with the yearly charge in small print.
- A plan that exists only to make another look better.
- "Most popular" on a plan nobody has measured.
- Countdown timers that reset; "only 2 left" from a fixed string; "12 people are viewing this" from a random number.
- Pre-ticked paid extras; a decline option worded to shame.
- The cheapest or free option shrunk, grayed or placed where it will not be seen.
- Reviews filtered to hide the negative ones.
- A report that promises a conversion increase.

## Exceptions and context

- **Jurisdictions differ.** Rules on reference prices, "free", fees, reviews and urgency vary by country; several are cited below. Flag a likely problem and tell the owner to take legal advice. Do not state that a page is or is not compliant.
- **Regulated products** (credit, insurance, health, gambling, alcohol) carry their own disclosure rules. Keep every required statement; improve only its clarity.
- **Real scarcity is information.** Genuine low stock, real booking deadlines and true seat limits help buyers and should be shown plainly.
- **B2B and enterprise** pricing is often negotiated. Ranges and pricing factors replace list prices.
- **Experts and repeat buyers** are less affected by these effects and want facts and speed.
- **Strength of the evidence** (state this when an owner asks whether a change will "work"):

| Effect | What the research supports |
|---|---|
| Framing, anchoring | Reliable in experiments; size in real purchases varies. |
| Middle-option preference | Supported when options are easy to compare. |
| Decoy (a dominated option) | Disputed: it often fails when products are experienced or shown realistically, not as rows of numbers. |
| Zero price | Supported in experiments; weaker when people deliberate. |
| Loss aversion | Real on average, smaller or absent for small amounts and for knowledgeable buyers. |
| Per-day price framing | Supported for small amounts; can leave buyers feeling misled. |
| Left-digit pricing | Supported when the leftmost digit changes. |
| Choice overload | The average effect across studies is near zero; it appears when options are complex and preferences are unclear. |
| Defaults | Among the strongest effects, which is why paid defaults are treated as deceptive. |
| Nudges in general | Published results overstate the effect; after correcting for publication bias, little remains on average. |

## Implementation cautions

Three levels of action. Apply them to every change in this module.

| You may do in a fix pass | Recommend to the owner; do not do | Never |
|---|---|---|
| Reorder, group and align existing plans and prices | Add, remove, rename or reprice a plan or tier | Invent a price, range, discount, saving or former price |
| Make the current price and the billing terms more prominent | Mark a plan "recommended" or "most popular" | Invent a plan, feature, bonus or limit |
| Move existing conditions, fees and guarantees next to the price | Add a guarantee, trial, free item or free tier | Write "free", "included" or "no card needed" where the project does not say so |
| Put an existing saving beside the prices it comes from | Show a derived figure (per-day cost, yearly saving, percent off) | Add urgency, scarcity, countdowns or activity notices |
| Remove pre-selection from a paid extra only when no handler or total depends on it; otherwise recommend | Change a default plan, billing period or quantity | Add testimonials, ratings, counts, logos or awards |
| Rewrite a price label so it states the period and tax already documented in the project | Add a price range or starting price for a quote-based service | State or imply an expected uplift |

- A derived figure is arithmetic on the owner's prices, but rounding, tax and currency make it a claim. Give the owner the calculation and let them approve the number. A figure the project already produces (a total its own code calculates and displays) is not derived; you may move it, label it and make it prominent.
- A pre-selected paid extra or a pre-selected dearer plan usually feeds a total, so unticking it changes what is charged and is not yours to change, even though it is a deceptive default. When it cannot be changed: report it at P1 or higher as the first functional recommendation, and in the fix pass make it impossible to miss, with a plain label, its price, the word "optional" where true, and its effect on the total shown next to it.
- Factual labels are allowed: calling a checkbox "optional", or stating the billing period the code applies, describes the project and adds no claim.
- Price, discount, tax, fee and trial logic are protected. Changing what number appears, when a discount applies or what is pre-selected in a way that alters a total is not interface work.
- When the page would sell better with something that does not exist (a real testimonial, a starting price, a guarantee), write it under "Content the owner needs to supply" with what is needed and why. Leave the space empty or omit the section; do not fill it with sample content.
- Wording changes must not strengthen a claim. "Reply within two working days" may not become "fast reply"; "from 49" may not become "only 49".

## Sources

- [BEH-01] Framing of decisions
- [NNG-38] Anchoring; [NNG-39] prospect theory and loss aversion
- [BEH-02] Asymmetric dominance; [BEH-03] compromise effect; [BEH-04] limits of the attraction effect
- [BEH-05] Zero as a special price
- [BEH-06], [BEH-07] Choice overload meta-analyses; [NNG-40] simplicity and choice; [NNG-45] removing sludge from decisions
- [BEH-08], [BEH-09] Loss aversion: meta-analysis and critique
- [BEH-10] Pennies-a-day framing; [BEH-11] left-digit effect
- [BEH-12] Defaults meta-analysis; [BEH-13] publication bias in nudge research
- [BEH-14] Dark patterns across shopping sites; [NNG-13] deceptive patterns; [FTC-01] dark patterns report
- [NNG-41] Scarcity; [NNG-47] reciprocity; [NNG-34] social proof
- [NNG-42] Comparison tables; [NNG-43] communicating discounts; [NNG-44] taxes and fees; [NNG-46] pricing, trials and trust; [NNG-28] showing prices
- [BAY-15] Price and discount display; [BAY-16] price per unit
- [LAW-01] Former-price comparisons; [LAW-02] use of the word "free"; [LAW-03] reviews and testimonials; [LAW-04] practices always considered unfair; [LAW-05] prior price in reductions; [LAW-06] drip pricing and fake reviews; [LAW-07] interface manipulation on platforms; [LAW-08] disclosures before billing

The three-level action table and the offer inventory are this skill's own rules (evidence class: Judgment), built to keep persuasion inside what the owner actually offers.
