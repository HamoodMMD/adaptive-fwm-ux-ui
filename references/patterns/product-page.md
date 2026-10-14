# Product pages

The page where one thing is evaluated and bought: a physical product, a digital product, a service package or a plan. This module covers the page in depth; `profiles/ecommerce` covers the store around it.

**Load when:** a product, item or package detail page is in scope, or the user asks why a product page does not sell.
**Skip when:** the surface has no single-item page (a pricing table is `patterns/pricing-and-persuasion`; a landing page is `patterns/sales-journey`).
**Pair with (when present):** `profiles/ecommerce`, `profiles/fashion-apparel`, `patterns/pricing-and-persuasion`, `patterns/visual-scale`, `patterns/responsive-mobile`, `patterns/virtual-goods` for digital items.

## Objectives

A shopper who cannot touch the product gets every question answered that they would settle in a shop: what it is, what it looks like at true size and in use, whether it fits or works for them, what it costs in total, when it arrives, what happens if it is wrong, and what other buyers think. Choosing a variant and buying take a few obvious taps, on a phone, without hunting.

## Priority principles

1. **The page replaces handling the product.** Missing information ends in an abandoned purchase or a return.
2. **The buy section is the center.** Price, options, availability, delivery and the action sit together and are reachable at once.
3. **Show before telling.** Images and video carry most of the evaluation; text fills the gaps.
4. **The total and the terms are part of the product.** Delivery, returns and extra costs appear on this page, not in checkout.
5. **Honest evidence.** Real reviews with their criticism, real stock, real prices.
6. **Phone first.** Most product pages are met on a phone; the order of the single column is a design decision.

## Checks

### The first screen (phone)
- Product name, price and at least the start of the image gallery are visible on arrival. The buy action is on the first screen or within one short scroll.
- A rating summary sits near the title where reviews exist, and links to the reviews.
- Nothing covers the product on arrival (see `patterns/sales-journey`, Greet).

### Images and media
- Several images per product: the whole item, details, the item in use or in context, and one that shows scale (worn, held, or beside something familiar).
- Images are large, sharp, zoomable by pinch and tap, and swipeable with a visible position indicator; the next image peeks or thumbnails show that more exist.
- Images change to match the selected variant.
- Video is short, has controls, does not autoplay with sound, and is not the only place a fact appears.
- Customer photos, where they exist, are browsable together.
- Every image has a text alternative that says what it shows.

### Price and offers
- The current price is unmistakable and near the buy action. Its size may be modest; its position and contrast make it findable at once.
- Currency, tax treatment and what the price covers are clear. Unit price is shown where sizes or quantities differ.
- A reduced price shows the former price, marked as former, and the saving, next to each other, described once.
- Instalment or pay-later options state the number of payments and the total.
- An estimate of the order total (item, delivery, tax where known) is available before checkout.
- Detail: `patterns/pricing-and-persuasion`.

### Options and variants
- Sizes, colors and other options are visible buttons or swatches, not a dropdown, so availability is seen at a glance.
- The selected option is clearly marked by more than color. Colors have text names.
- Unavailable options stay visible, marked as unavailable, with a back-in-stock route where the store offers one.
- A size or fit guide is next to the size choice, in the units the audience uses.
- The buy action explains what is missing ("Select a size") instead of failing silently or being disabled without a reason.

### Availability, delivery and returns
- Stock for the selected variant is stated truthfully.
- Delivery is given as a date or range and a cost (or the threshold for free delivery), on this page, updating with location where the store supports it.
- The returns policy is summarized in a line near the buy action and linked in full.
- Warranty, guarantee and support terms that exist are stated.

### The buy action
- One clearly primary control, large enough for a thumb (about 44 to 48px high), labeled with the action.
- On long pages a slim sticky bar keeps the name, price and the action in reach, without covering content, the focused field or the keyboard, and without duplicating a button already on screen.
- Adding to the cart confirms unmistakably (visually and to assistive technology), updates the cart count, shows what was added, and offers both continuing and checkout.
- Quantity uses a stepper with direct entry.
- Express payment buttons, where present, do not push the main action off screen or outrank it.
- Saving an item does not demand an account first where the platform allows otherwise.

### Description and specifications
- The most important facts come first; the description is scannable, concrete and free of filler.
- Specifications are a structured list or table with units, complete enough to compare with another product.
- Technical terms are explained. Materials, dimensions, care, compatibility and what is in the box are stated.
- Long content is organized under clear headings. Collapsed sections are labeled so their contents are predictable, and nothing essential (price, delivery, returns) is only inside a collapsed section.

### Reviews
- A summary shows the average, the count and the distribution, and lets the reader filter by rating.
- Negative reviews are readable. Verified purchases are marked.
- Reviews can be searched or filtered by topic where there are many.
- The store's replies to complaints are visible where they exist.
- A product with no reviews says so plainly; it does not show empty stars as a rating.

### Related products
- Alternatives ("similar items") and complements ("goes with") are distinguished, relevant, and placed after the buyer has what they need to decide about this product.
- They do not interrupt the path from options to the buy action.

### Observed practice
Eighteen product pages from established online stores, loaded on a phone-sized screen in October 2026 (SURVEY-04 in the source index). Context, not targets.

| Element | What was found |
|---|---|
| Buy control within the first screen and a half | 16 of 18 (fully on the first screen on 10) |
| Price on the first screen | 12 of 18 |
| Price text size | 14 to 16px typical: small, but placed beside the title or the button |
| First image share of the first screen | 39% to 49% for the middle half |
| A buy bar that stays on screen while scrolling | 14 of 18 |
| Buy button height | 43 to 56px for the middle half |
| Rating summary near the top | 13 of 18 |
| Delivery or returns mentioned within two screens | 13 of 18 |
| Page length | 8 to 13 screens for the middle half |
| A crossed-out former price | 6 of 18 |
| Pay-later options named | 5 of 18 |
| Related or "you may also like" products | 11 of 18 |
| Dropdowns used for an option | 6 of 18 |
| Urgency or activity wording | 4 of 18 |
| A dialog over the page on arrival | 9 of 18 |

Half of these stores greeted the shopper with a dialog over the product, and a third still used a dropdown for options. Both are common and both are findings.

## Anti-patterns

- One small image, or images that do not match the chosen color.
- Size in a dropdown; out-of-stock sizes removed without trace.
- A disabled buy button with no explanation.
- Delivery cost and returns policy first revealed in checkout.
- "Add to cart" that gives no confirmation, or throws the shopper into the cart with no way back.
- The price only in a sticky bar, or only after choosing options.
- Specifications as a paragraph; "premium quality" with no facts.
- Reviews with no distribution, no negative reviews, or filtered to five stars.
- "Only 2 left" from a fixed string; "14 people are viewing this".
- A newsletter dialog over the product on arrival.
- Three sticky bars on a phone.
- Cross-sells between the options and the buy button.

## Exceptions and context

- **Simple, low-cost, repeat purchases** need little: image, price, quantity, buy. Do not pad them.
- **Complex or expensive products** need more: comparisons, specifications, documents, a way to ask a question.
- **Apparel and footwear**: fit, size guidance and on-model images lead. See `profiles/fashion-apparel`.
- **Configurable products**: see strategy 10 in `selling-strategies.md`.
- **Digital products and downloads**: show what is delivered, format, compatibility, license and refund terms; a preview or sample replaces handling.
- **Service packages**: what is included and excluded, who delivers it, how long it takes, what the buyer must provide, and what happens after purchase.
- **Luxury**: fewer elements and more space are deliberate; the questions still need answers within reach.
- **Marketplaces**: who sells and ships the item, and their rating, belong in the buy section.
- **The evidence.** Benchmark research finds most stores fail on several of these: size as a dropdown, no in-scale image, no return policy on the page, no unit price, no cost estimate near the buy section. Those and the product-page guidelines are Research. The ordering for phones and the two-bar limit are this skill's judgment.

## Implementation cautions

- Price, stock, variant, cart, delivery-estimate and review logic are protected. Change how they are shown, not what they compute.
- Replacing a dropdown with buttons changes markup that variant scripts, themes and analytics often depend on. It is frequently a theme or component change: check what reads the control, keep its name and values, and verify the same variant is submitted. If that cannot be verified, recommend it.
- A sticky buy bar that duplicates the main form's action must submit the same thing. Showing an existing bar is presentation; building one is functional.
- Never add or edit a rating, a review count, a stock message, a former price, a delivery promise or a badge. Remove pressure messages only under the rule on pressure the code proves false.
- Image alternatives describe what is visible. Do not invent product claims in them.
- Third-party review, payment and recommendation widgets are restyled only through their own options.
- After any change, repeat the purchase path on a phone: choose a variant, add to cart, confirm what was added.

## Sources

- [BAY-03] Product page benchmark; [NNG-64] product page guidelines
- [BAY-06], [BAY-07] Sizing and apparel; [BAY-16] unit price; [BAY-15] discounts on the product page
- [NNG-44] Taxes, fees and delivery charges; [NNG-43] communicating discounts
- [BAY-12] Ratings distribution; [BEH-37] reviews and sales; [LAW-03] rules on reviews
- [BAY-09] Mobile commerce; [NNG-32] sticky elements; [NNG-20] touch targets
- [BAY-20] Perceived security; [NNG-60] pop-ups
- [BEH-35] Hidden fees; [BAY-01] reasons for abandoning

The "Observed practice" table is this skill's own measurement (SURVEY-04).
