# Forms

Any place users type or choose values and submit them: contact, checkout, sign-up, settings, data entry, multi-step applications.

**Load when:** the surface has a form beyond a single search box.
**Skip when:** the only input is search (use `search-filter-sort`).

## Objectives

Users know what each field wants before they type, can enter it in the way that is natural to them, learn about a problem at a useful moment and in a useful way, never lose what they entered, and know that submission worked.

## Priority principles

1. **Ask less.** Every field removed is the most reliable improvement to a form. (Removing fields is a functional change: recommend it.)
2. **Labels stay visible.** A user must be able to see what a field is for while it is empty, while typing and after filling it.
3. **Let the browser and the device help.** Correct types, `autocomplete` and input modes save more effort than any custom widget.
4. **Validate at the moment it helps,** never before the user has had a chance to answer.
5. **An error message is an instruction,** not a verdict.

## Checks

### Labels, hints and placeholders
- Every control has a visible, persistent label that is programmatically associated with it (`label` with `for`/`id`, or wrapping).
- Placeholder text is never the only label. It disappears on input, strains memory, is often too faint to read, and can be mistaken for a filled value. Use it sparingly, for an example of format at most.
- Labels sit above or directly beside their field, close enough that the pairing is unmistakable.
- Hint text that the user needs before answering is placed between label and field, stays visible, and is associated with the control (`aria-describedby`).
- Labels are short nouns or questions in the user's words; they are not replaced by icons alone.
- Formatting rules and constraints (password rules, accepted file types, character limits) are stated before input, not revealed by an error.

### Required and optional
- It is explicit which fields are required and which are optional, using words. Either mark only the optional ones "(optional)" when most fields are required, or mark both; be consistent across the product.
- An asterisk alone needs an explanation and must not be the only indicator; color alone is never the indicator.
- Optional fields are few. A field that is rarely needed is a candidate for removal or for a later step.

### Grouping and order
- Related fields are grouped under a heading; groups of radio buttons or checkboxes use `fieldset` and `legend`.
- Order follows the user's logic and convention (name before address, card number before expiry before security code).
- Forms use a single column. Side-by-side fields are reserved for short, closely related pairs (city and postcode, expiry and security code).
- Field width hints at the expected length: a postcode field is short, an address line is long.
- Long forms are split into steps or sections with clear headings.

### Choosing the control
- A few mutually exclusive options are radio buttons; several of many are checkboxes; long lists are a select or a searchable list.
- A binary setting that takes effect immediately is a switch; a binary answer in a submitted form is a checkbox or radios.
- Small numeric quantities use a stepper that also allows typing.
- Native controls are preferred. Custom selects, date pickers and comboboxes are justified only when the native one cannot do the job, and then they implement the full keyboard and screen-reader pattern.

### Input types, keyboards and autofill
- `type` matches the data: `email`, `tel`, `url`, `password`, `search`. Card numbers, postcodes and codes that are digits but not quantities use `inputmode="numeric"` with a text type, not `type="number"`.
- `autocomplete` tokens are set on fields about the user: `name`, `email`, `tel`, `street-address`, `postal-code`, `country`, `cc-number`, `cc-exp`, `cc-csc`, `new-password`, `current-password`, `one-time-code`, and so on. For personal data fields this is a WCAG Level AA requirement.
- Autocorrect and autocapitalize are turned off for emails, usernames, codes and identifiers.
- Paste is never blocked.
- One input per value: do not split card numbers, phone numbers or codes across boxes in ways that break autofill and paste.

### Validation timing
- Do not show an error while the user is still typing a first attempt, or the moment a field receives focus.
- Validate a field when the user leaves it, or when the entry is plainly complete, where the project uses inline validation; always validate on submit.
- Remove the error as soon as the input becomes valid, while the user is still in the field.
- Positive confirmation (a check mark) is useful for fields where users doubt themselves, such as a complex password or a card number; not needed everywhere.
- Guidance differs on inline validation versus submit-only validation. Both camps agree on the points above. Keep the project's existing approach unless it is premature or absent.

### Error messages
- Each error is shown in text next to its field, says what is wrong and how to put it right, and uses the same words as the label: "Enter a phone number, like 050 123 4567", not "Invalid input".
- Errors are identified by more than color: text plus an icon or border change.
- The field is marked invalid for assistive technology (`aria-invalid`), and the message is associated with it.
- On a failed submit of a longer form, a summary at the top lists the errors, links to each field, and receives focus; the page title can be prefixed to signal the error.
- No blame, no jokes, no "please" that implies it is optional, no bare codes.
- The same problem always gets the same message.

### Preserving data
- Nothing the user typed is cleared when validation fails, when they go back a step, or when the session is renewed.
- A reset or clear button is not offered beside submit.
- Long or interruptible forms save progress where the product supports it, and say so.
- Information already given in the same process is not asked for again; it is pre-filled or selectable. (WCAG 3.3.7, Level A.)

### Multi-step forms
- The user knows how many steps there are and where they are. A simple "Step 2 of 4" is often enough.
- Each step has one purpose; going back keeps all answers.
- A review step before the final submission shows every answer with a way to change it and return directly to the review.
- The final action is clearly different from "Continue".

### Specific fields
- **Names:** one full-name field, or flexible fields that do not assume a Western first-and-last structure. Do not reject hyphens, apostrophes, spaces, non-Latin scripts or single names.
- **Addresses:** fields suit the country served; postcode and state are not forced where they do not exist; a second address line is available without appearing required; country is chosen early if the format depends on it. Address lookup, where present, allows manual entry.
- **Phone numbers:** accept spaces, dashes, brackets and a leading plus; state whether a country code is expected; say why the number is needed.
- **Email:** `type="email"`, no confirmation field retyping unless the product has evidence it helps; catch obvious typos by suggestion, not by blocking.
- **Passwords:** requirements shown upfront and checked as the user types; a show/hide control; paste and password managers allowed; no arbitrary composition rules presented only on failure.
- **Dates:** a calendar picker for nearby dates the user is choosing; typed day, month and year fields for dates the user already knows (birth date, document dates); never three long dropdowns. Month names prevent format confusion.
- **One-time codes:** a single field with `autocomplete="one-time-code"`, numeric keyboard, paste allowed.
- **File upload:** accepted types and size stated first; progress shown; the chosen file named and removable.

### Submission and success
- The submit button says what it does ("Create account", "Send message", "Pay now").
- Pressing it shows a pending state so users do not press twice.
- Avoid disabling the submit button as the only signal that something is missing: a disabled button gives no reason and is skipped by keyboard. Prefer an enabled button that reports what is needed.
- Success is confirmed specifically, with what happens next. The form does not simply clear itself.
- Failure of the submission itself (network, server) keeps the data and says whether to retry.

### Accessibility summary
- Label and name every control; group related controls; announce errors and success as status messages; keep focus visible and in a logical order; ensure targets meet the minimum size; do not rely on color; do not time out without warning. See `core/accessibility.md` for the criteria.

## Anti-patterns

- Placeholder as label.
- Red border with no message.
- "Invalid" as the whole error.
- Errors on every field the moment the page loads or a field is focused.
- Clearing the form after a failed submit.
- A disabled submit button with no explanation.
- `type="number"` for card numbers, postcodes and phone numbers.
- Four boxes for a card number; six boxes for a code that cannot be pasted.
- Blocking paste in password or email-confirmation fields.
- Mandatory phone number with no reason.
- Rejecting valid names and addresses with over-strict patterns.
- Month, day and year as three dropdowns.
- Asking for the same address twice.
- Multi-column layouts that scramble reading and tab order.
- A "Reset" button next to "Submit".
- CAPTCHA puzzles with no alternative.

## Exceptions and context

- **Expert data-entry forms** in admin tools can be denser, use multiple columns where field relationships are well known, and favor keyboard speed. Tab order must still follow the visual order.
- **Short, familiar forms** (sign-in, single-field newsletter) need no progress indicator or review step.
- **Government-style one-question-per-page flows** suit infrequent, high-consequence forms for the general public; they would slow down daily operational use.
- **Inline editing** follows the same labeling and error rules without a submit button; state when a change is saved.
- **Regulatory fields and wording** are kept as required.
- **Marking required versus optional** follows the project's convention if it is explicit and consistent.

## Implementation cautions

- UI-safe: adding or fixing labels, `for`/`id` association, hint text, `autocomplete`, `inputmode`, `type` (where it does not change submitted values), grouping markup, error text wording, error placement, `aria-invalid`, `aria-describedby`, live-region announcement of existing messages, focus management on existing error states.
- Functional, recommend: removing, adding or reordering fields; changing which are required; changing validation rules or timing; adding steps, review pages, autosave or address lookup; changing what is submitted.
- Changing an input `type` can change the value format the backend receives (`type="number"` strips characters; `type="date"` submits ISO format). Verify the submitted payload is identical.
- Field `name` and `id` values are contracts with the backend, tests, autofill and analytics; do not rename them.
- Form libraries and schema validators own error state; restyle their output instead of adding a parallel mechanism.
- Hosted payment and identity fields are styled only through the provider's options.
- Error and label text may live in translation files; change it at the source in every language you can verify.

## Sources

- [NNG-25] Placeholders in form fields are harmful
- [NNG-26] Website forms usability — fewer fields, single column, field size, marking optional and required, visible errors
- [BAY-05] Inline form validation — when to fire, removing errors when fixed, positive validation
- [GOV-01] Recover from validation errors — validate on submit, error summary, page title
- [GOV-02] Writing error messages
- [GOV-03] Question pages — one thing per page, marking optional, hint text, progress
- [GOV-04] Check answers
- [GOV-05] Dates pattern; [NNG-22] date-input guidelines
- [WEB-07] Payment and address form best practices — autocomplete, input types, single fields
- [BAY-02] Checkout field marking and error messages; [BAY-11] mobile touch keyboards
- [W3C-17] WAI forms tutorial
- [W3C-01] WCAG 2.2 — 1.3.5, 3.3.1, 3.3.2, 3.3.3, 3.3.4, 3.3.7, 3.3.8, 4.1.3
- [W3C-10] Accessible authentication
- [NNG-07] Error-message guidelines
