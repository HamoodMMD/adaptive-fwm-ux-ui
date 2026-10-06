# Fashion and apparel

An overlay for surfaces where people choose clothing, footwear or accessories. It adds what generic ecommerce rules miss: look, size, fit and color.

**Load when:** garments, footwear or wearable accessories are the product, on a store or on a brand site.
**Skip when:** the business is in fashion but the surface is not about choosing garments (a wholesale order form, an inventory tool, a careers page).
**Usually secondary to:** `profiles/ecommerce`. On a brand or lookbook site with no store, use only the imagery, collections and taxonomy sections.
**Pair with (when present):** `patterns/search-filter-sort`, `patterns/responsive-mobile`, `patterns/forms` for custom measurements.

## Objectives

A shopper can judge how a garment looks and fits without touching it, pick the right size with confidence, see exactly which size-and-color combinations are available, and know what happens if it does not fit.

## Priority principles

1. **The image is the product.** Discovery is visual; imagery quality, consistency and speed matter more here than in almost any other category.
2. **Size uncertainty is the main barrier.** Insufficient sizing information leads to hesitation, abandonment and returns. Treat size selection and size guidance as primary content, not a footnote.
3. **Availability is per variant.** "In stock" means nothing until size and color are chosen; show the combination.
4. **Fit confidence includes the way back.** Returns and exchange terms belong beside the size decision.
5. **Not every fashion surface needs every feature.** Judge what exists; recommend additions as functional work.

## Checks

### Visual-led discovery
- Product lists are image-dominant with consistent crops, backgrounds and aspect ratios so items can be compared.
- List items show available colors as swatches; choosing a swatch changes the thumbnail.
- A second image (alternate angle or on-model) is available from the list on hover or swipe where the platform supports it.
- Collections, campaigns and lookbooks link directly to the products shown; a shoppable image identifies which item is which.

### Taxonomy
- Categories follow how shoppers think about clothing: by person (women, men, children, age bands), by type (dresses, outerwear), and where relevant by occasion, season or collection.
- A product can be reached through more than one sensible route, but the breadcrumb shows one consistent path.
- Size-system differences between departments (children's ages, footwear, numeric versus alpha sizing) are handled per category, not by one global filter.

### Product imagery
- Multiple images per color: front, back, side, detail of fabric and construction.
- Shown on a human model as well as flat or on a mannequin, so drape, length and proportion are visible.
- The model's height and the size worn are stated.
- Selecting a color updates the whole gallery to that color.
- Zoom is sharp enough to see fabric texture; on touch devices pinch-zoom works and the gallery swipes with a position indicator.
- Video, where present, has controls and does not autoplay with sound.
- Accessories show scale: on a person, in a hand, or with dimensions.

### Color
- Each color has a text name as well as a swatch, and the selected color is named in text near the selector.
- Swatches are large enough to tap and distinguish, with a clear selected state that is not color alone.
- Similar shades are distinguishable by name.
- Unavailable colors remain visible and marked.

### Size selection
- Sizes are visible buttons, not a dropdown. Out-of-stock sizes stay in place, marked unavailable and not selectable (or leading to a back-in-stock request where that exists).
- The size system is labeled (EU, UK, US, alpha) and matches the size guide.
- A link to the size guide sits directly next to the size selector.
- If no size is chosen, add-to-cart explains what is missing and points to the selector instead of failing silently or staying disabled without reason.
- Stock is shown for the selected size-and-color combination.

### Size guide and fit guidance
- The guide is specific to the product type, not one generic chart for the whole store.
- Measurements are given in both centimeters and inches; international size conversions are provided where the audience is international.
- It explains how to take each measurement, ideally with a diagram.
- It distinguishes body measurements from garment measurements.
- It opens without losing the product page state, and closing it (including with the browser back button) returns to the same place.
- Fit is described in words: cut (slim, regular, relaxed, oversized), length, stretch, whether it runs small or large.
- Where reviews exist, an aggregate fit indicator (runs small / true to size / runs large) is shown.
- A route to ask for help with sizing is available from the guide.

### Ready sizes and custom sizes
Where a store offers both ready-to-wear sizes and made-to-measure or tailoring:

- The two routes are clearly separated and labeled at the point of choice, with the differences in price, lead time and return terms stated before the shopper commits.
- Custom measurement forms state the unit, show a diagram per measurement, give plausible ranges, and catch likely unit mistakes.
- Measurements can be reviewed before ordering and, where accounts exist, saved for reuse.
- The summary and confirmation repeat the measurements entered.
- Options such as length, sleeve or fabric are presented as explicit choices with their effect on price and delivery shown.

### Returns and fit confidence
- Return and exchange terms are summarized near the size selector or add-to-cart, with a link to the full policy.
- Different terms for sale, custom or hygiene-restricted items are stated on those products.

### Lists and filters
- Size filters are grouped and labeled by size system, in a logical order, not a jumble of numeric and alpha values.
- Color filters use swatches with names. Filters common to apparel (size, color, price, category, and where the catalog supports them, fit, length, material, occasion) are available per category.
- Filtering by size shows only products available in that size where the data supports it.

### Mobile browsing
- Two-column product grids keep images large enough to judge; one column for image-critical categories is acceptable.
- Swatches in list items scroll horizontally instead of wrapping into clutter.
- On the product page, gallery, price, color, size and add-to-cart are reachable in a short scroll; the size guide opens as a full-height sheet.

## Anti-patterns

- Size in a dropdown.
- One generic size chart for dresses, trousers and shoes alike.
- Size guide hidden in the footer, or opening a page that loses the selected variant.
- Sold-out sizes removed so the shopper cannot tell whether their size ever existed.
- Gallery that keeps showing black when beige is selected.
- Color conveyed by swatch only, with names such as "Color 3".
- Flat product shots only, with no model.
- Auto-rotating hero imagery that cannot be paused.
- Returns policy discoverable only in checkout.
- Custom-measurement and standard-size options mixed in one unlabeled form.
- Recommending wishlists, fit quizzes, virtual try-on or reviews as if their absence were a UI bug.

## Exceptions and context

- **One-size items and most accessories:** no size selector or size chart; show dimensions and scale instead.
- **Made-to-order only:** there is no stock per variant; show lead time prominently and treat measurement entry as the primary flow.
- **Brand or lookbook sites without a store:** apply imagery, collections and taxonomy checks; link to stockists or inquiry where that is the goal; do not introduce shopping affordances.
- **Luxury and editorial brands** may deliberately use sparse layouts and large imagery. Keep the feel; make sure price, size and the purchase action are still easy to find. See `core/brand-preservation.md`.
- **Modest wear, tailoring and cultural garments** often have their own measurements and length options; use the product's actual attributes, not a generic western size model.
- **Small catalogs** may not need filters or elaborate taxonomy.

## Implementation cautions

- Changing size dropdowns to buttons must leave the submitted option values, variant ids and add-to-cart request identical. Verify the request before and after.
- Variant availability comes from inventory data. Display it; never hard-code or infer it.
- Gallery-to-color linking depends on how images are associated with variants in the platform. If no association exists, recommend it; do not fake it by filename guessing.
- Size-guide content (measurements, conversions) is the merchant's data. Improve layout and access; do not invent numbers.
- Measurement validation ranges are business rules. Recommend them.
- Images are brand assets. Optimize delivery (sizes, formats, lazy loading below the fold); do not crop, recolor or replace them.

## Sources

- [BAY-06] Apparel sizing — ten practices for sizing information
- [BAY-07] Apparel UX — size buttons, human-model images, fit subscores, review images
- [BAY-03] Product page UX — variant selectors, in-scale images
- [BAY-04] Product list UX — combined variations, thumbnails, filters
- [BAY-09] Mobile UX — swatches in list items
- [W3C-01] WCAG 1.4.1 — color names in addition to swatches

Guidance on ready versus custom sizes is this skill's reasoning from general form and error-prevention principles (evidence class: Judgment); no dedicated published study was found for it.
