# Ecommerce

Surfaces where people find, evaluate and buy products through a cart and checkout.

**Load when:** there is a real catalog, cart and checkout (physical or digital goods).
**Skip when:** prices are shown but nothing can be bought online (pricing pages, catalogs with "enquire"), or the only transaction is a booking.
**Journey:** land → find → evaluate → choose variant → cart → checkout → confirmation → after the order.
**Pair with (when present):** `patterns/search-filter-sort`, `patterns/forms`, `patterns/responsive-mobile`, `patterns/loading-empty-error-states`; `profiles/fashion-apparel` for clothing; `profiles/high-stakes` on the payment step.

## Objectives

A shopper can find a suitable product, be confident it is the right one, know the full cost and delivery expectation before committing, and pay without being forced through steps that serve only the seller.

## Priority principles

1. **Findability decides everything downstream.** A product that cannot be found cannot be bought. Navigation, search, filtering and list design matter as much as the product page.
2. **Answer the buying questions on the product page:** what exactly is it, will it suit me, is my variant available, what does it cost in total, when will I get it, can I send it back.
3. **No surprises on cost.** Extra costs appearing late is the most cited reason shoppers give for abandoning a checkout.
4. **Remove obligations, not information.** Shorten checkout by dropping forced accounts and unneeded fields, never by hiding totals, policies or review.
5. **Never recommend a feature the store model does not support.** Check that wishlists, reviews, guest checkout, multiple fulfillment options and so on actually exist before judging their design.

## Checks

### Store navigation and categories
- Category names use shoppers' words and do not overlap. The current category and position in the hierarchy are shown.
- Each level offers a way to see everything in it ("View all").
- Breadcrumbs appear on category and product pages in multi-level catalogs.
- Category pages for broad categories guide users into subcategories before showing an undifferentiated list.
- Cart and search are reachable from every page in a consistent place; the cart shows its item count.

### Search (where present)
- The search field is visible, not hidden behind an icon, on stores where search is a main route.
- Search tolerates misspellings and common synonyms; the query stays in the field on the results page.
- Autocomplete suggestions, if offered, are keyboard-operable and clearly distinguish query suggestions from products.
- Zero-result pages keep the query editable and offer ways forward. Detail: `patterns/search-filter-sort`.

### Product lists
- Variations of one product (colors, patterns) are one list item with swatches, not separate items cluttering the list.
- Each list item shows enough to choose from the list: image, title, price (with any discount stated clearly), rating with the number of ratings where reviews exist, and available variations.
- Unit price is shown where pack sizes differ.
- Filters match the category (not one generic set for the whole store); applied filters are summarized above the list and individually removable.
- Sort options cover what shoppers compare on, typically price, rating, best-selling and newest, and the current sort is visible.
- Loading more products does not strand the footer or lose the user's place on return from a product page.

### Product page
- **Images:** several per product, large, zoomable; at least one showing scale or use in context; images match the selected variant.
- **Price:** current price prominent; any original price and saving shown honestly; currency and tax inclusion clear. Detail on reference prices, discounts, "free", urgency and defaults: `patterns/pricing-and-persuasion`.
- **Variants:** options exposed as visible buttons or swatches rather than buried in a dropdown, so availability is seen at a glance. Unavailable options remain visible and marked as unavailable, not removed. Color options have text names as well as swatches.
- **Stock and quantity:** availability for the selected variant is stated. Quantity uses a stepper with direct numeric entry.
- **Delivery and returns:** estimated delivery expressed as a date or date range where possible, shipping cost or the threshold for free shipping, and a link to the returns policy, all on the product page, not first revealed in checkout.
- **Add to cart:** the button is the clear primary action; pressing it gives unmistakable confirmation (announced to assistive technology) and updates the cart count, without forcing the user away unless that is the store's deliberate flow.
- **Descriptions:** scannable, with specifications in a structured list or table.
- **Reviews (where present):** a rating distribution summary, the ability to read negative reviews, and review photos browsable together.
- **Saving items (where present):** does not demand an account before the first save if the platform allows otherwise.

### Cart
- Each line shows image, name, chosen variant, unit price, quantity and line total. Quantity can be edited and items removed, with a chance to undo removal where the platform supports it.
- A cost summary shows subtotal, discounts, shipping (or an estimate) and tax as early as they can be known.
- The path to checkout is the primary action. Promo-code entry is available without dominating.
- Nothing is in the cart that the shopper did not add.
- The cart persists across sessions and devices where the platform supports it.

### Checkout
- **Guest checkout is offered and is at least as prominent as sign-in.** Account creation is optional and best offered after the order.
- Only necessary fields are asked. Each optional field is marked; the reason is given for sensitive ones such as phone number.
- Fields use correct `autocomplete`, input types and mobile keyboards; names are not split more than necessary; a second address line is available without looking required. Detail: `patterns/forms`.
- Billing address defaults to "same as shipping".
- Delivery options show cost and an arrival date, not just a speed or a number of business days.
- Validation messages say what is wrong and how to fix it, next to the field, and entered data is never lost.
- The order total is visible throughout, and the user reviews items, addresses, delivery and total before the final action.
- The final button states the action ("Place order", "Pay $84.00"), is pressed once, and shows a pending state.
- Card entry: one field per value, spaces tolerated, numeric keyboard, no custom widgets that break autofill, and a layout that looks deliberate and secure.
- Progress through steps is indicated, and going back keeps data.

### Confirmation and after
- The confirmation states that the order succeeded, the order number, what was bought, the total, the delivery estimate and what happens next, and says that an email is on its way.
- It is not gated behind account creation.
- Order status, tracking and the start of a return are easy to find later.

### Mobile commerce
- Product imagery, price, variant selection and the add-to-cart action are reachable without hunting. A sticky add-to-cart bar is useful where the page is long, provided it does not cover content, the focused element or the on-screen keyboard.
- Tap areas for cart, menu, swatches, quantity and filters are comfortably large and well separated.
- Filters open in a full-height panel with an apply action and a result count.
- Galleries swipe horizontally with a position indicator and do not trap vertical scroll.

## Anti-patterns

- Forcing account creation before purchase.
- Shipping cost, tax or fees first shown on the last step.
- Size or variant in a dropdown that hides which options are in stock.
- Out-of-stock variants silently removed, or selectable until an error at add-to-cart.
- Fake "Only 2 left!" or countdown timers; pre-added warranties or donations; pre-ticked marketing consent.
- A newsletter modal before the shopper has seen a product.
- One generic filter set for every category.
- Product variations listed as separate products.
- Promo-code field so prominent it sends shoppers away to hunt for codes.
- A homepage carousel carrying the only route to key categories.
- "Submit" as the pay button; no pending state; double charges invited.
- Confirmation page that is only "Thank you".

## Exceptions and context

- **Digital goods and licenses:** drop shipping, stock and delivery-date rules. Replace with delivery method (download, key by email), license terms, system requirements, activation and refund terms. Check that the delivery email is read back before payment, that the confirmation says where the key is going and what to do if it does not arrive, and that the key can be found again later.
- **Single-product or very small catalogs:** category navigation, filters and sort may be unnecessary. Do not recommend them.
- **B2B ordering:** quick order by SKU, bulk quantities, account-specific pricing and reorder matter more than visual discovery; forced sign-in can be legitimate. Combine with `saas-application` or `admin-backoffice` for the logged-in tools.
- **Food and restaurant ordering:** menu as catalog, modifiers as variants, pickup or delivery time as a booking choice; no returns or courier rules.
- **Subscriptions:** billing amount, cadence, renewal and cancellation route must be explicit before purchase.
- **Regulated products** may legitimately require accounts, age checks or extra fields.
- **Reviews, wishlists, multiple payment methods** are judged only if the store has them; their absence is a functional recommendation, not a UI finding.

## Implementation cautions

- Never touch price, discount, tax, shipping-rate, stock or promo logic. Changing how a price is *displayed* (order, emphasis, labels) is UI; changing what number appears is not.
- Payment fields are often hosted by the provider. Style them only through supported options; do not replace, wrap or re-implement them.
- Checkout step order, required fields and validation are usually tied to the backend and to fraud or address checks. Recommend changes; do not make them.
- Analytics and ad platforms depend on specific events, element ids and data-layer pushes in list, product, cart and checkout templates. Preserve them.
- Platform themes (Shopify, WooCommerce, Magento and others) reuse templates across many pages; check every page a template renders before editing it.
- Converting a variant dropdown to buttons is a presentation change only if the underlying inputs, names and values stay identical. Verify the add-to-cart request is unchanged.

## Sources

- [BAY-01] Reasons for cart abandonment
- [BAY-02] Checkout UX — guest checkout, field marking, delivery dates, error messages
- [BAY-03] Product page UX — variant buttons, in-scale images, shipping and returns information
- [BAY-04] Product list UX — combined variations, filters, sorting, applied-filter overview
- [BAY-05] Inline form validation
- [BAY-09] Mobile UX — view all, applied filters, swatches, error messages
- [BAY-10] Ecommerce search research
- [BAY-12] Ratings distribution summary
- [WEB-07] Payment and address form best practices
- [NNG-30] Infinite scrolling trade-offs
- [NNG-13] Deceptive patterns
- [W3C-05] Status messages — announcing add-to-cart
