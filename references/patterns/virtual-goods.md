# Virtual items, in-app purchases and digital goods

Selling things that exist only on a screen: virtual currency, in-game and in-app items, cosmetic upgrades, passes, credits, digital downloads, and randomized rewards.

**Load when:** the surface sells or spends virtual currency, credits, tokens or points; offers in-app or in-game purchases, passes or digital items; or contains randomized paid rewards (loot boxes, packs, gacha, spins).
**Skip when:** the product sells only physical goods or ordinary subscriptions with no virtual currency or items (use `profiles/ecommerce` or `patterns/pricing-and-persuasion`).
**Pair with (when present):** `patterns/pricing-and-persuasion`, `patterns/ux-psychology`, `profiles/high-stakes` scoped to the purchase step, `core/content-and-trust`.

## Objectives

A buyer always knows what an item costs in real money, what exactly they will get, whether the outcome is certain or a chance, and how to stop. Buying takes a deliberate act. Nothing about the interface relies on the buyer losing track of how much they have spent, and children are not sold to as if they were adults.

## Priority principles

1. **Real money is the unit.** A virtual currency is a convenience for the product. It must never make a price harder to understand.
2. **A purchase is a decision, not an accident.** No purchase completes from a single ambiguous press.
3. **Chance is stated as chance.** A randomized reward shows its odds and its cost before the buyer pays.
4. **The risks here are documented, not hypothetical.** Regulators have fined large publishers for exactly these patterns, and spending on randomized rewards is associated with problem gambling. Treat this surface with the care of a payment step.
5. **Who is buying matters.** Where children can use the product, every rule tightens.

## Checks

### Price in real money
- Every item priced in a virtual currency also shows its real-money cost, at the item and at the point of purchase.
- Currency packs show the real price, the amount received and the rate. Bonus amounts are stated as amounts, not only as percentages.
- The balance and what it is worth are visible while shopping.
- Where there is more than one currency, each exchange rate is stated, and the path from real money to the item is shown as one figure.
- If an item costs more than the buyer holds, the shortfall and the smallest purchase that covers it are shown. Pack sizes that always leave a remainder are a finding.

### What the buyer gets
- The item is shown and described accurately: what it does, where it works, whether it changes gameplay or is cosmetic.
- Limits are stated before purchase: expiry, account or platform binding, whether it can be transferred, refunded or lost if the service closes.
- Time-limited items say when they end, with a real date. Rotating "last chance" offers that return are a finding.
- After purchase the item arrives at once, the confirmation says what was bought and for how much in real money, and the receipt is easy to find.

### Randomized rewards
- The odds of each outcome or rarity tier are shown before purchase, in plain numbers, at the place the purchase is made.
- The real-money cost of one attempt is shown, and where a guaranteed outcome exists after a number of attempts, that number and its total cost are shown.
- Where the product offers it, a direct purchase of the item stands beside the randomized route.
- Near-miss animations, escalating celebrations and "one more try" prompts after a loss are flagged.
- Opening or spinning is never the default action after a purchase of currency.

### The purchase act
- Buying needs a clear, separate confirmation that states the item and the price. Preview, equip, inspect and buy are distinct controls that look distinct and sit apart.
- The same button does not change from a harmless action to a purchase between screens.
- Accidental purchases can be cancelled or refunded through a visible route, and disputing a charge does not lock the account.
- Saved payment methods require re-authentication or a confirmation for each purchase where the platform allows it.
- Spending so far in the session or period is available to the buyer.

### Passes, subscriptions and renewals
- A pass or subscription states its price, period, renewal and what is lost on lapse, before payment details are requested.
- Joining requires an explicit act; declining is as visible as accepting.
- Cancelling is as easy to find and complete as joining was, with no chain of retention screens before the control.
- Progress or items already earned under a pass are described accurately: what is kept and what is locked on expiry.

### Engagement pressure
- Daily rewards, streaks and login bonuses do not punish a missed day with the loss of things already earned or bought.
- Notifications about offers are opt-in and can be turned off in one place.
- Progress bars toward a paid reward show real progress and the real remaining cost.
- Social pressure (showing what friends bought, gifting prompts, rankings by spend) is flagged where minors may be present.

### Children and vulnerable buyers
- Where children may use the product: purchases require a parent's approval, spending limits exist and are easy to set, and offers are not addressed directly to the child.
- Age gates and parental controls are easy to find and work as described.
- No element urges a child to ask an adult to buy.

## Anti-patterns

- Prices only in gems, coins or credits.
- Two or three currencies between the card and the item.
- Packs of 500 when everything costs 600.
- Odds hidden behind a link, given only as "rare", or not given.
- A purchase triggered by the same button that previewed the item on the previous screen.
- "Only today" on an offer that returns every week.
- A character crying or a streak burning down when the buyer declines.
- A cancellation path several screens deeper than the sign-up.
- Locking an account after a chargeback.
- A spending total that is impossible to find.
- Purchase prompts aimed at children.

## Exceptions and context

- **Platform rules.** App stores and consoles set their own requirements for in-app purchases, odds disclosure and refunds, and often own the purchase dialog. Check the current rules for the platform; the interface around the platform dialog is still yours to judge.
- **Law varies by country** and is tightening: some jurisdictions restrict or ban paid randomized rewards, and European consumer authorities have set expectations that in-game prices be clear in real money. Flag likely problems and tell the owner to take legal advice. Do not rule on compliance.
- **Earned-only currencies** that cannot be bought with money need none of the real-money rules, as long as they cannot be converted to or from a paid currency.
- **Business credits** (API credits, cloud units, message bundles) are virtual currency too. The same clarity applies: the real price per unit, what a typical task consumes, expiry, and what happens at zero.
- **The evidence** (state it when asked):

| Claim | What the research supports |
|---|---|
| Spending on loot boxes is linked to problem gambling | A consistent small-to-moderate association across many surveys (around r = 0.26). Direction of cause is not established, and one recent study disputes that loot boxes add risk beyond overall game spending. |
| Paying with tokens or credits hurts less than paying money | Predicted by the standard theory of payment and consumption, and consistent with studies of card versus cash. Direct controlled tests on game currencies were not found. |
| Hiding the real cost increases spending | Supported for hidden fees by a large field experiment (see `patterns/pricing-and-persuasion`). Regulators treat obscured in-game pricing the same way. |
| These practices attract enforcement | Yes: settlements over single-press purchases, obscured loot-box costs and odds, and obstructed cancellation. |

## Implementation cautions

- Purchase, wallet, currency, entitlement, odds and refund logic are protected. Do not change what is charged, granted, drawn or refunded.
- Showing a real-money equivalent requires the exchange rate. Where the project already defines one fixed rate, displaying the equivalent is presentation; flag it for the owner to confirm. Where rates vary by pack, region or promotion, the figure is a derived claim: recommend it and give the owner the calculation.
- Odds must come from the system that performs the draw. Never write odds into the interface from documentation, an estimate or a guess.
- Separating a buy control from a preview control, adding a confirmation step, or changing which action is the default alters behavior. Restyling and relabeling existing controls so buy and preview look different is presentation; adding a step is functional. Report unconfirmed single-press purchases at P0 or P1 according to the amount at risk.
- Platform purchase sheets cannot be restyled. Work on what surrounds them.
- Removing a false "last chance" or a shaming decline message follows the rule on pressure the code proves false in `implementation-safety.md`.
- Never add a randomized reward, a currency, a streak, a timer or a spending prompt.

## Sources

- [BEH-31] Loot boxes and problem gambling survey; [BEH-32], [BEH-33] meta-analysis and systematic review
- [BEH-34] Payment and the pain of paying; [BEH-35] hidden fees field experiment
- [LAW-10] European consumer authorities on in-game virtual currencies; [LAW-12] consumer organisations' complaint on premium currencies
- [LAW-11] Settlement over unintended in-game purchases; [LAW-14] settlement over loot-box costs and odds; [LAW-13] settlement over enrollment and cancellation
- [LAW-09] Addictive design resolution; [LAW-07] manipulative interfaces; [FTC-01] dark patterns report
- [NNG-13] Deceptive patterns; [BEH-12] defaults

No usability study dedicated to virtual-goods purchase flows was found in open sources. The checks are derived from the enforcement record and consumer-authority principles above (Guidance) and from this skill's pricing and honesty rules (Judgment).
