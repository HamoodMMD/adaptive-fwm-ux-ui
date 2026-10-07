# Booking and reservation

Flows where people reserve a time, a date range, a seat, a room, a table, a person or a resource.

**Load when:** availability, calendars, time slots or capacity decide what the user can choose.
**Skip when:** dates appear only as delivery estimates for an order. A pickup or delivery slot the customer chooses does count; use the availability, time-selection, conflict and confirmation sections for it.
**Journey:** choose what, where and with whom → see availability → pick date and time → give details → review → confirm → manage (reschedule, cancel).
**Pair with (when present):** `patterns/forms`, `patterns/responsive-mobile`, `patterns/search-filter-sort`, `patterns/loading-empty-error-states`; `profiles/marketplace-directory` when choosing among many providers; `profiles/high-stakes` for payment.

## Objectives

A user can see what is available without trial and error, choose a time they understand correctly, know the full price and the cancellation terms before committing, leave with proof of the booking, and change or cancel it later without having to phone someone.

## Priority principles

1. **Show availability; do not make people guess.** Every "sorry, not available" after a selection is a failure of the interface.
2. **A time is not understood until its date, zone and duration are.** Ambiguity here produces missed appointments.
3. **Total price and terms before commitment.**
4. **Keep the choices in view.** What, when, where, for whom and how much stay visible through the flow.
5. **Booking is half the task.** Rescheduling and cancelling are part of the product.

## Checks

### Entry and search
- Where booking is the main purpose, the booking controls are the most prominent thing on the entry page.
- The user can start from whichever they know first: a date, a service, a provider or a location.
- Required inputs for a search (dates, party size, location) are asked together, with sensible defaults, and remembered through the flow.

### Service, provider and location
- Each option carries what is needed to choose it: what it is, duration, price or price range, and for providers their role or specialty.
- "Any available" is offered when the user may not care who.
- Locations show address and distance or area; remote and in-person options are distinguished.
- Changing one choice updates availability without discarding the others.

### Availability
- Available and unavailable dates are distinguishable at a glance in the calendar; unavailable ones are visible but not selectable, with the reason where it helps (fully booked, closed, outside booking window).
- The earliest available date is easy to reach; the calendar does not open on a month with nothing free.
- When nothing is available for the chosen criteria, the nearest alternatives are offered: other times that day, adjacent days, other providers or locations.
- Scarcity is shown only when real and from live data.
- Price differences between dates or times are shown in the picker where they exist.

### Date selection
- A calendar picker is used for dates near the present, where day of week and relative position matter. Dates can also be typed.
- Months are named; the calendar's first day of week and date format follow the locale.
- Date ranges prevent an end before the start, show the selected span clearly, and keep the calendar still during selection so users do not mis-tap.
- Minimum and maximum stays, lead times and blackout periods are explained when they block a choice.
- The picker is fully operable by keyboard and screen reader, with dates announced in full.

### Time selection
- Times are offered as a list or grid of real slots, not a free time field that then fails validation.
- Each slot's duration or end time is evident.
- The time format follows the locale (12- or 24-hour), with AM and PM unambiguous.
- The time zone is stated in words, with a city or zone name, whenever the user and the provider may be in different zones or the service is remote. Offset-only notation is avoided. The user's own zone is detected and can be changed.
- Bookings across a daylight-saving change show the correct local time.

### Party size and capacity
- Guests, seats, rooms or participants are asked early, because they change availability and price.
- Limits are stated before they are hit; larger groups get a route (contact, group booking) instead of a dead end.
- Steppers with direct entry are used for small numbers.

### Price clarity
- The price shown in results and in the picker is the price paid, or it says clearly what will be added: taxes, service or cleaning fees, deposits.
- A full breakdown and total appear before the user enters payment details.
- Deposit versus full payment, when the remainder is due, and the currency are explicit.
- Cancellation, refund and no-show terms are shown before payment in plain words, with dates ("Free cancellation until 14 March, 18:00").

### Details and steps
- Only details needed for the booking are asked; guests can book without creating an account where the business allows.
- The steps and the user's position are shown; going back keeps every choice.
- A summary of the selection is visible throughout: service, provider, location, date, time with zone, duration, party size, price.
- If a slot is held for a limited time, the user is told how long, warned before it expires and offered more time where possible.

### Review, errors and conflicts
- A review step shows everything before the final action, with each item editable.
- If the slot is taken or the price changes during the flow, the message says so specifically, keeps the entered details, and offers the nearest alternatives.
- Payment failure keeps the booking details and says whether the slot is still held.
- The final button states the action and amount, and shows a pending state so it is pressed once.

### Confirmation
- The confirmation states clearly that the booking is made (or is pending approval, if so), with a reference number.
- It repeats what, when (with zone), where (address, map or joining link), for whom and the amount paid or due.
- It offers adding to a calendar, and says what the user will receive by email or message.
- It tells the user what to bring or do beforehand, and how to change or cancel.

### Managing a booking
- Reschedule and cancel are available online from the confirmation, the message and the account, without logging in where the business allows a secure link.
- Before confirming a change or cancellation the consequence is shown: fees, refund amount and timing, what is lost.
- Rescheduling reuses the availability picker and keeps the other details.
- After the change, a new confirmation is shown and sent.
- Past, upcoming and cancelled bookings are distinguishable.

### Mobile
- Date and time controls fit the viewport without sideways scrolling; slots are comfortably tappable.
- The selection summary and primary action stay reachable, typically as a compact sticky bar that does not cover the picker.
- Address opens in a maps app; phone numbers are tappable.

## Anti-patterns

- Choose a time, fill in the form, then learn it was not available.
- Calendar with every date enabled and errors after selection.
- Fees first shown on the payment step.
- Times with no time zone for remote services; "UTC+3" as the only clue.
- "10/11" for an international audience.
- A calendar that jumps months or re-renders while a range is being selected.
- "Only 1 left!" as decoration.
- Mandatory account creation before seeing availability.
- Countdown timers that pressure without a real hold.
- Confirmation that is only "Thanks!", with no reference or details.
- Cancellation by phone only when booking was online.
- Reschedule that makes the user start again from the first step.
- Dropdown lists of ninety time slots.

## Exceptions and context

- **Request-to-book and approval flows:** the confirmation must say the booking is pending, by when the user will hear, and what happens to any payment hold.
- **Recurring and multi-session bookings** need a view of all occurrences and rules for changing one versus all.
- **Walk-in or call-first businesses** may publish availability only as guidance; say so.
- **Complex travel** (multi-leg, multi-room) has its own comparison and itinerary needs beyond this module.
- **Regulated services** (medical, legal) may require intake forms or identity checks before confirmation.
- **Internal resource booking** (rooms, equipment) favors speed and overview: add `admin-backoffice` thinking.
- **Hijri or other calendars:** follow the locale and product decision; do not add a calendar system the product does not support.

## Implementation cautions

- Availability, capacity, slot generation, holds, pricing, fees, deposits, refunds and cancellation rules are business logic. Display them; never compute or alter them in the UI.
- Time-zone conversion and storage are functional. Displaying the zone name beside an already-correct time is UI; changing conversion is not.
- Never hard-code availability, disable dates by guess, or show scarcity not supplied by the backend.
- Date-picker libraries carry their own accessibility and locale behavior; configure them before replacing them, and replacing them is not a UI-only change.
- Confirmation emails, calendar files and reminders are functional outputs.
- Preserve tracking and booking-engine hooks; many booking flows are third-party embeds that can be styled only through their options.

## Sources

- [BAY-08] Travel site UX — prominent booking search, complete detail, fees and policies
- [BAY-13] Travel accommodations research — date pickers, availability and price by date
- [NNG-22] Date-input guidelines — picker versus typing, ranges, format ambiguity, limited options
- [GOV-05] Dates pattern — calendar pickers for looking dates up; typed dates for known dates
- [W3C-22] Working with time zones — explicit zone context, zone identifiers with exemplar cities, daylight-saving pitfalls
- [GOV-04] Check answers before submitting
- [NNG-23] Constraints that prevent slips
- [W3C-01] WCAG 2.2 — 2.2.1 Timing Adjustable, 3.3.4 Error Prevention, 1.3.5 Identify Input Purpose
- [NNG-13] Deceptive patterns — false scarcity, hidden costs
- [BAY-01] Extra costs as a stated abandonment reason
