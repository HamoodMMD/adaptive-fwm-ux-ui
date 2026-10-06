# Marketplace and directory

Surfaces where people discover and compare listings supplied by many independent sellers, providers or places.

**Load when:** listings come from multiple parties and the user must choose among them.
**Skip when:** every listing belongs to one seller (use `ecommerce` or `service-business`).
**Journey:** search or browse → narrow → compare → check the listing and who is behind it → contact, book or buy.
**Pair with (when present):** `patterns/search-filter-sort`, `patterns/responsive-mobile`, `patterns/loading-empty-error-states`; `profiles/booking-reservation` or `profiles/ecommerce` for the transaction itself.

A marketplace is always more than one surface. The buyer's discovery pages follow this module. The seller's or provider's tools are a work application: classify them as `saas-application` or `admin-backoffice`.

## Objectives

A visitor can narrow a large, uneven supply to a shortlist that fits, compare candidates on the same terms, judge whether the party behind each listing can be trusted, and understand exactly what happens when they make contact or pay.

## Priority principles

1. **Supply is uneven and written by others.** The interface must make inconsistent listings comparable and survive missing data gracefully.
2. **Trust is about the counterparty.** Users are judging a stranger; give them the evidence.
3. **Discovery is the product.** Search, filtering, sorting and location do most of the work.
4. **Ranking is a claim.** Say what the default order means and label paid placement.
5. **Never fabricate trust signals.** Badges, counts and ratings come from real data or do not appear.

## Checks

### Discovery
- Entry points suit how people start: a search with the key criteria (what, where, when), and browsable categories.
- Categories are in users' terms and show what they contain; counts are shown where the data supports them.
- Location is a first-class input where services or items are local: detect with permission, allow manual entry, show what area is being searched.
- Recently viewed and saved items are offered where the product has them.

### Search, filters and sort
- Filters fit the category: the attributes that distinguish listings in that category, not a single global set.
- Filters for trust and logistics are available where data exists: rating, verified status, availability, distance, price.
- The applied criteria and the number of results are always visible.
- Sort options are named clearly. The default order is explained ("Recommended: based on rating, distance and availability"), and sponsored or promoted listings are labeled as such in the list.
- Results from outside the requested area or criteria are separated and labeled, not blended in.
- Detail: `patterns/search-filter-sort`.

### Listing cards
- Every card shows the same key facts in the same positions so cards can be compared: title, primary image, price or price range with its unit, location or distance, rating with the number of reviews, and two or three category-specific attributes.
- Badges (verified, top-rated, new) are few, defined somewhere the user can find, and backed by data.
- Missing data is handled deliberately: a neutral image placeholder that does not look broken, "No reviews yet" instead of an empty star row, omitted fields instead of "null" or "N/A" clutter.
- The whole card or its title is one clear link; secondary actions (save, share) do not hijack it.

### Listing detail
- Structured facts first: what is offered, price and what it includes, location, availability, key attributes, policies.
- Free-text description follows, formatted to be read.
- Photos are large, browsable and belong to this listing.
- The party behind the listing is introduced on the page with a link to their profile.
- Similar or nearby listings are offered for comparison.
- The page states when the listing was last updated where staleness matters.

### Seller and provider credibility
- A profile shows who they are, how long they have been on the platform, what they offer, their response time or rate where measured, and their reviews.
- Verification is specific about what was verified (identity, license, address) and is shown only when it happened.
- Credentials and policies supplied by the provider are distinguished from what the platform has checked.
- Contact and location are disclosed according to the platform's rules, and the user is told when contact details are withheld until booking.

### Reviews
- The overall rating always appears with the number of reviews behind it.
- A distribution of ratings is shown once there are enough reviews to be meaningful, and can be used to filter.
- Negative reviews are as easy to read as positive ones; reviews can be sorted by recency.
- Each review shows its date and, where true, that it comes from a verified transaction.
- Provider responses are shown with the review they answer.
- Review photos are browsable together where they exist.
- How reviews are collected and moderated is explained somewhere reachable.

### Location and maps
- List and map views show the same results and stay in sync where both exist; selecting one highlights the other.
- Distance uses the locale's unit and states its basis (from you, from the searched place).
- The map is not the only way to get the information: addresses and areas are in text, and the list is fully usable without the map.
- Exact locations are shown or approximated according to the platform's privacy rules, and approximations are labeled.

### Comparison and shortlisting
- Attributes appear in a consistent order across listings so that side-by-side reading works even without a compare feature.
- Saving a listing, where supported, is one action, is reflected immediately, and the saved list is easy to find.
- A dedicated comparison view, where present, aligns the same attributes in rows and highlights differences.
- Returning from a listing to the results restores position, filters and sort.

### Contact and transaction
- The primary action says what will happen: "Message seller", "Request to book", "Buy now", "Call". The user knows whether they are committing, inquiring or leaving the platform.
- Platform fees, deposits and protections are stated before the user commits.
- Messaging shows expected response time and keeps the conversation attached to the listing.
- When the transaction completes off-platform, the user is told what protection does and does not apply.

### Trust and safety
- Reporting a listing, review or user is available from the item itself and confirms that the report was received.
- Blocking and safety guidance are reachable where the platform has them.
- Guidance on safe transactions is offered at the moment of contact, briefly.

### Thin and empty supply
- Few or no results in an area lead to useful alternatives: widen the area, relax a filter, nearby categories, notify me.
- New listings with no reviews are not penalized visually as broken; they are labeled as new.

## Anti-patterns

- Sponsored listings mixed into organic results with no label.
- A star rating with no review count.
- "Verified" badges with no definition, or shown for everyone.
- Invented review counts, "5 people are looking at this", or activity notices not driven by data.
- Cards with different fields in different places, making comparison impossible.
- Broken-image icons and "undefined" where providers left fields blank.
- A map as the only interface, with no list.
- Default sort that nobody can explain.
- Results silently padded with listings that do not match the filters.
- Hiding negative reviews or burying them behind extra steps.
- Contact button that turns out to be a paid lead form for third parties.
- Back from a listing resets the search.
- Fees revealed only at payment.

## Exceptions and context

- **Curated directories** with editorial selection may have no reviews and no ranking; say what the selection is based on.
- **Free listing directories** with no transaction need contact clarity and data freshness more than payment trust.
- **High-value or regulated categories** (property, vehicles, healthcare, finance) need stronger provenance; add `high-stakes` and give no domain advice.
- **Single-category marketplaces** can use a richer, fixed card design; multi-category ones need category-specific attributes.
- **New marketplaces** with little supply should favor honesty about coverage over the appearance of abundance.
- **Location may be irrelevant** (digital services, remote work); drop map and distance checks.

## Implementation cautions

- Ranking, relevance, sponsored placement, review eligibility, verification and moderation are platform logic. Label and explain them; do not change them.
- Never add badges, counts, ratings, activity notices or "verified" marks that the data does not supply.
- Client-side sorting or filtering of a paginated server result gives wrong answers; restyle what the server returns.
- Listing content belongs to providers. Improve how it is laid out and how gaps are handled; do not rewrite or fill it.
- Map providers and geolocation need consent and have usage terms; configure through their options.
- Messaging, booking and payment hand-offs are functional flows.
- Preserve structured data and tracking attributes on cards and detail pages.

## Sources

- [BAY-04] Product list UX — list item information, filters, sorting, applied-filter overview (applied here to listings)
- [BAY-12] Ratings distribution summary — the most used part of a reviews section; rating with count
- [BAY-08] Travel site UX — category-specific filters, maps, linking to independent reviews
- [NNG-11] Credibility — connection to independent sources, upfront disclosure
- [STAN-01] Web credibility — real organization, verifiable claims
- [NNG-34] Social proof — when numbers help and when low numbers backfire
- [NNG-19] Filter design and user intent
- [NNG-13] Deceptive patterns; [FTC-01] dark patterns report — disguised ads, fabricated activity
- [W3C-01] WCAG 2.2 — 1.4.1 Use of Color (map and badge states), 1.1.1 Non-text Content

Dedicated, openly published usability research on two-sided marketplaces is thin. Much of this module applies ecommerce list research, credibility research and reviews research to multi-provider listings (evidence class: Judgment where no source is cited).
