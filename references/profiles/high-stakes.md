# High-stakes actions

An overlay for any surface where a mistake is costly or cannot be undone.

**Load when:** error consequence is high: moving money, deleting or overwriting important data, sending to many recipients, changing permissions or ownership, publishing, legal or contractual submissions, changes to live systems, records that others rely on.
**Skip when:** errors are cheap and easily undone.
**Usually secondary to:** whatever profile describes the surface.

This module is about interface risk only. It gives no legal, medical, financial or security advice, and it does not decide what a business must do to comply with any regulation.

## Objectives

Before acting, the user knows exactly what will be affected and what will happen. The interface makes the wrong action hard to take by accident. After acting, there is a record, and where possible a way back.

## Priority principles

1. **Make the object and the consequence explicit.** Most serious errors are the right action on the wrong thing.
2. **Prefer reversibility to warnings.** A grace period or undo protects better than any dialog.
3. **Friction in proportion to consequence.** Too little invites accidents; too much trains people to click through.
4. **Separate dangerous from routine** in space, appearance and interaction.
5. **Leave a trail.** What was done, by whom, when and on what.

## Checks

### Explicit state and context
- The user can always see which account, organization, tenant or person they are acting on, and as whom (their own identity, a role, on behalf of another).
- The environment is unmistakable where there is more than one: production versus test, live versus draft, real money versus sandbox.
- The current state of the object is shown before the action: balance, status, version, owner, number of items affected.
- Values that will be changed show both the current and the new value.

### Review before commitment
- Before a consequential submission the user sees a summary of everything they are about to commit, in plain words, and can go back to change any part without losing the rest.
- Amounts show currency and are formatted unambiguously; recipients, dates and quantities are written out in full.
- For legal, financial or data-changing submissions, at least one of these holds: the submission is reversible, the input is checked and the user can correct it, or the user reviews and confirms before finalizing. (WCAG 3.3.4, Level AA.)
- Calculated consequences are shown: fees, the resulting balance, what will be deleted along with the item, who will lose access.

### Confirmation
- Confirmation is used for serious, hard-to-reverse actions, and not for routine ones.
- The dialog names the specific object and count and states the consequence: "Delete 'Q3 report' and its 14 comments? This cannot be undone."
- Buttons are labeled with the action and its alternative ("Delete report" / "Keep report"), never Yes/No or OK/Cancel.
- The destructive option is not the default and is not triggered by Enter by default.
- Typed confirmation (entering the name or a word) is reserved for the gravest cases, such as deleting an account or a production resource.
- The confirmation cannot be dismissed into the destructive outcome by clicking outside it or pressing Escape.
- For unusually large or unusual actions, extra confirmation is appropriate even when the routine version has none.

### Reversibility
- Where the product supports undo, soft delete, a recycle bin, a cooling-off period, drafts or versioning, it is offered and its time limit is stated.
- Immediately after the action, the way to reverse it is visible.
- Where the action is irreversible, the interface says so before the user commits, in words, not just by color.
- Scheduled or delayed actions can be cancelled until they execute, and say when that is.

### Clarity of destructive and sensitive controls
- Destructive controls are labeled with a specific verb and object.
- They are placed apart from routine controls and are not the same size, style and position as "Save".
- Danger styling is consistent and used only for dangerous actions.
- Destructive actions are not hidden behind ambiguous icons, and are not the only item revealed by a swipe or long-press without confirmation or undo.
- Bulk versions state how many items are affected and whether that includes items not currently visible.

### Avoiding ambiguous shortcuts
- No single-key shortcut triggers a consequential action without confirmation.
- Enter in a form does not submit a destructive or financial action unintentionally.
- Double submission is discouraged by an immediate pending state on the button.
- Auto-advance, auto-submit on blur, and timers that complete an action for the user are avoided.
- Drag-and-drop that changes ownership, order of execution or amounts has a non-drag alternative and a way to undo.
- Defaults are the safe choice; nothing consequential is pre-selected.

### Provenance and audit
- Important values show where they came from: entered by whom, imported from what, calculated how, generated by AI.
- Timestamps are absolute, with time zone, and identify the actor.
- Where an audit trail exists, it is reachable from the object and readable: who did what, when, before and after values.
- System-initiated and AI-initiated changes are distinguishable from human ones.
- After a consequential action the user receives a durable confirmation: a reference, a receipt, a log entry.

### Permissions and approval
- Users who lack permission learn that before attempting the action, and learn who can do it or how to request it.
- Where approval by a second person exists, the state is clear: awaiting whom, since when, what was requested, and the requester cannot mistake "submitted for approval" for "done".
- Elevated modes (admin, impersonation, break-glass) are continuously and prominently indicated and easy to leave.

### Errors, interruptions and recovery
- If a consequential action fails or its outcome is unknown (timeout, lost connection), the interface says which, tells the user whether it is safe to retry, and shows how to check what happened.
- Partial completion is reported precisely.
- Session expiry and navigation away do not silently drop a half-completed submission, and do not silently submit it either.
- After a mistake, the route to help is immediate and specific.

### Input for high-consequence values
- Amounts, account numbers, identifiers and dates have clear formats, appropriate keyboards and validation that catches likely slips.
- Where a value is critical and error-prone, the interface reads it back in a second form (name of the recipient for an account number, amount in words, date with weekday).
- Paste is allowed; it reduces transcription errors.
- Units and currency are never implied.

## Anti-patterns

- "Are you sure?" with OK and Cancel.
- Delete next to Edit, identical in style.
- A red button that is sometimes "Delete" and sometimes "Sign up".
- Confirmation on everything, so nothing is read.
- Destructive default selected, or triggered by Enter.
- Production and test looking identical.
- Success and failure toasts for money movement that vanish before they can be read.
- "Something went wrong" after a payment attempt, with no word on whether money moved.
- Amounts with no currency; dates as "03/04".
- Bulk actions that include thousands of unseen records with no warning.
- Acting on behalf of another user with only a small label to show it.
- Swipe-to-delete with neither confirmation nor undo.
- Auto-submit when a countdown ends.
- Disabling paste on account or code fields.

## Exceptions and context

- **Expert, high-volume operators** (traders, dispatchers, support agents) may need fast paths with fewer confirmations. Compensate with strong undo, clear state, limits and audit, and treat the removal of safeguards as the owner's decision.
- **Emergency actions** must be quick: do not put a typed confirmation in front of "stop".
- **Regulatory or contractual requirements** may mandate specific wording, steps or delays. Keep them as they are.
- **Truly irreversible physical or external effects** (a sent message, a dispatched order, an executed transfer) cannot be undone by the interface; the weight shifts to review and confirmation.
- **Low-consequence actions inside a high-stakes product** should stay light, so that the serious confirmations keep their force.

## Implementation cautions

- Confirmation wording, button labels, placement, danger styling, summaries built from data already on the page, and read-backs of values are UI.
- Adding undo, soft delete, grace periods, approval steps, audit logging, idempotency, rate limits or server-side validation is functional work. Recommend it.
- Do not change which actions require confirmation if that is enforced or expected by backend, policy or tests; improve the confirmation itself.
- Do not alter handlers for consequential actions. If markup around them must change, verify the same request is sent exactly once.
- A pending or disabled state on submit is UI if the component already tracks submission; it is not a substitute for server-side protection against duplicates.
- Never display calculated consequences (fees, balances, counts) that are computed in new front-end code; show only what the system provides.
- Do not log, print or quote account numbers, personal data or secrets in the audit report.

## Sources

- [W3C-08] Understanding 3.3.4 Error Prevention (Legal, Financial, Data) — reversible, checked or confirmed
- [W3C-01] WCAG 2.2 — also 3.3.6 Error Prevention (All) at AAA, 2.2.1 Timing Adjustable, 2.5.2 Pointer Cancellation, 2.5.7 Dragging Movements, 3.3.8 Accessible Authentication
- [NNG-06] Confirmation dialogs — selective use, specific wording, action-labeled buttons, undo, thresholds for unusual actions
- [NNG-23] Preventing slips — constraints, defaults, forgiving formats
- [NNG-07] Error-message guidelines
- [GOV-04] Check answers before submitting
- [NNG-35] Modal dialogs — justified for preventing irreversible errors
- [HAX-02] G16 Convey the consequences of user actions; G11 Make clear why the system did what it did
- [PAIR-04] Assessing stakes when automation can fail
- [W3C-22] Time zones in displayed timestamps

Guidance on environment indication, provenance display and approval states is reasoned from visibility of system status and error prevention [NNG-01] (evidence class: Judgment).
