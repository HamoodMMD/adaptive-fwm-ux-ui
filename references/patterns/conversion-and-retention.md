# Conversion, retention and business impact

What ease of use is worth to a business, what actually moves conversion and retention, how to measure it, and how to talk about it honestly.

**Load when:** the user asks about conversion, retention, churn, business impact, return on investment or "high-converting" design; a report needs to justify UX work to a business owner; or metrics and experiments are being planned.
**Skip when:** the request is a plain usability or accessibility review with no business framing.
**Pair with (when present):** `patterns/sales-journey`, `patterns/onboarding`, `patterns/pricing-and-persuasion`, `patterns/ux-psychology`, `core/performance`.

## Objectives

The owner gets a truthful account of how a design problem costs them customers and what fixing it is likely to change, with a way to measure it. Recommendations aim at the experience a visitor has, and the conversion or retention figure is treated as the result to observe, not the thing to design for directly.

## Priority principles

1. **Conversion is a consequence.** People convert when they understand the offer, believe it, can afford the effort and are asked at the right moment. Design for those; the rate follows.
2. **Retention is earned after the sale.** People stay when the product keeps delivering what was promised with little effort. No interface trick holds a customer the product has failed.
3. **Remove effort before adding persuasion.** Reducing what a task costs the user is the best-supported lever in this field.
4. **Most ideas do not work.** At companies that test everything, roughly a third of changes improve the metric they aimed at. State mechanisms and uncertainty, and recommend measuring.
5. **Never trade tomorrow for today.** A tactic that lifts this week's conversion by misleading people raises refunds, complaints, churn and legal risk. Count the whole journey.
6. **No invented numbers.** Do not quote an uplift, a benchmark or a statistic you cannot source, and never predict a figure for this product.

## Checks

### Where customers are being lost
Find the losses before proposing gains. For each key journey (first visit to purchase, sign-up to first value, trial to paid, month one to month three), look for:
- **Understanding:** can a newcomer say what this is and what it costs?
- **Effort:** how many fields, decisions, screens and waits stand between intent and outcome? Which could be removed?
- **Surprise:** costs, requirements or commitments that appear late.
- **Trust:** missing identity, proof, policies or security cues at the moment of commitment.
- **Dead ends:** errors with no recovery, steps that need something the user does not have, account walls.
- **Speed:** slow first paint or sluggish response on a mid-range phone.
- **Exclusion:** barriers that stop people with disabilities, older devices or other languages from completing at all.

Rank them by how many people meet the problem and how completely it stops them.

### Conversion: what the evidence supports
- **Fewer fields and steps in the path to purchase.** Checkouts average over eleven fields where about eight suffice. Forced account creation and late extra costs are the most reported reasons for abandoning.
- **The full price early.** See `patterns/pricing-and-persuasion`.
- **A fast first screen.** A controlled test tied faster rendering to more sales; see `core/performance`.
- **Guest and low-commitment paths.** Let people act before asking them to register.
- **Clear first screen and a visible action.** See `patterns/sales-journey`.
- **Real reviews and visible policies** at the point of decision.
- **Accessibility.** People who cannot use the page cannot buy from it.

### Retention: what the evidence supports
- **Reach first value quickly.** See `patterns/onboarding`. In one controlled trial, shorter free trials produced more subscribers than longer ones, because people who stayed inactive did not convert.
- **Low effort in every repeat task.** In a large service study, low-effort experiences went with far higher stated intent to buy again; trying to delight added little.
- **Reliability and honest status.** Errors that lose work and unexplained failures are remembered.
- **Useful returns, not nagging.** Reminders the user set, saved work, real updates.
- **Easy leaving.** A customer who can cancel easily can also come back. Obstructed cancellation is penalized by regulators and resented by customers.
- **Habits take time and repetition.** The often-quoted "66 days" is an average from a small study with a range of 18 to 254 days. Do not design to a number.

### Measuring
- Tie each change to one journey and one observable behavior: task completion, time, errors, drop-off at a step, support contacts, repeat use.
- Use more than one kind of measure: what people do (completion, drop-off, retention curves), what they say (a standard questionnaire), and what they report struggling with.
- **Standard questionnaires:** the System Usability Scale averages 68 across about 500 studies; above 80 is the top tenth. A single effort question after a task tracks loyalty in service settings. A recommend-likelihood score is easy to collect and easy to misread: it needs large samples, hides why, and is swayed by price and lack of alternatives.
- A framework such as Happiness, Engagement, Adoption, Retention and Task success, with a goal, a signal and a metric for each, keeps measurement tied to what the product is for.
- Record a baseline before changing anything.

### Experiments
- Where traffic allows, test changes against the current version with a decided-in-advance metric, sample size and duration.
- Watch a guardrail as well as the target: refunds, cancellations, complaints, support load.
- A surprising win is more often a measurement error than a discovery; check it before celebrating.
- Small sites cannot run meaningful split tests. Use usability testing with a handful of people, before-and-after comparison with caution, and direct observation.
- Results from another company's test do not transfer. They are ideas to test, not evidence about this product.

### Talking about business impact
- State the mechanism: "visitors cannot see the total until the last step; late costs are the most reported reason for abandoning a purchase."
- State what to watch: "drop-off between cart and payment."
- State confidence honestly: verified on this product, supported by research elsewhere, or a judgment.
- Give the owner the cost side too: what the change needs, and what could go wrong.
- Do not promise a percentage. Do not import a benchmark as a target.

### Popular business figures to handle with care

| Figure | What is known |
|---|---|
| "Every dollar spent on UX returns a hundred" | No traceable study. It appears to blend a software-defect cost rule with an old vendor claim. |
| "A 5% rise in retention lifts profit 25% to 95%" | From a 1990 business article built on an illustrative example, with "5%" meaning percentage points. Not a measured law. |
| "Acquiring a customer costs 5 to 25 times more than keeping one" | A range quoted without a named study; it varies by industry. |
| "Design-led companies outperform by X%" | Consultancy studies show a correlation between design maturity scores and revenue growth among large listed companies. Correlation, not proof that design caused it. |
| "Usability redesigns improve metrics by 83%" | An average across 72 published case studies in 2008, which over-represent successes; gains were already shrinking. |
| "A conversion rate of N% is good" | Rates depend on traffic source, price, product and how conversion is counted. Compare a product with its own past. |
| "Trial with a card converts three times better" | Vendor benchmarks agree card-required trials convert a higher share of fewer sign-ups. The net effect differs by product. |

## Anti-patterns

- A report that leads with a promised uplift.
- Quoting another company's test result as proof.
- Optimizing one step so the next step fails (more sign-ups, fewer activated users).
- Raising conversion by hiding costs, pre-selecting extras or obstructing cancellation.
- Counting clicks or time on page as success.
- A redesign with no baseline.
- Declaring a winner from a few dozen visitors.
- A single satisfaction number used to judge a specific screen.
- "Best practice" applied without checking it fits this audience.

## Exceptions and context

- **Low-traffic and business-to-business products** rarely have the volume for experiments; qualitative evidence is the right tool.
- **Considered purchases** convert over weeks and several people. Judge pages by whether they move a buyer one step, not by same-visit conversion.
- **Regulated and high-stakes flows** should sometimes add friction (review, confirmation). Lower conversion there can be the correct outcome.
- **Mature, heavily optimized products** see small gains per change. Early-stage products have larger, cruder problems.
- **Evidence classes.** Field experiments and usability benchmarks cited here are Research. Consultancy correlations and vendor benchmarks are weaker and are labeled where used. The loss-finding list and the reporting rules are this skill's judgment.

## Implementation cautions

- Analytics events, experiment flags and tracking parameters are protected. Do not add, rename or remove them; recommend what to instrument.
- Do not start, stop or alter an experiment.
- Removing fields, adding guest checkout, changing trial terms or cancellation flow are functional or commercial decisions: recommend them with the evidence.
- When restyling a step that is being measured, tell the owner, because the change will affect their numbers.
- Never fabricate a metric, a baseline or a benchmark in a report. If the project has no data, say so and say what to collect.

## Sources

- Measuring whether a change worked (procedure in `measuring-results.md`): [NNG-88] conversion rate; [NNG-89] study sizes; [NNG-90] five users; [NNG-91] analytics; [GOV-09] completion rate; [NNG-102] choosing a research method; [BEH-50] regression to the mean
- [NNG-77] Return on usability work across case studies; [BEH-44] design maturity and financial performance
- [BEH-45] How often tested ideas succeed
- [BAY-21] Checkout form fields; [BAY-01] reasons for abandoning a purchase; [BAY-03] product page benchmarks
- [WEB-10] Speed and sales; [BEH-35] hidden fees experiment
- [BEH-46] Effort and loyalty; [BEH-47] trial length field experiment; [BEH-48] habit formation
- [UXR-01] System Usability Scale benchmarks; [UXR-02] the HEART framework; [NNG-78] recommend-likelihood scores
- [W3C-24] The business case for accessibility
- [BEH-49] Origins of the retention-profit and acquisition-cost figures; [BEH-13] publication bias
- [LAW-13] Enrollment and cancellation enforcement

The loss-finding checklist, the reporting rules and the table of figures to handle with care are this skill's own work (evidence class: Judgment), built on the sources above.
