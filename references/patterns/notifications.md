# Notifications, alerts and interruptions

How an interface tells people something: badges, inline messages, toasts, banners, dialogs, notification centers, email and push. The rule underneath is that interruption is a cost, so how loudly something is said should match how much it matters and whether the person must act.

**Load when:** the surface shows toasts, banners, badges, alerts, confirmation dialogs or a notification center; sends email or push notifications; or is a monitoring, admin or collaborative product where events arrive while people work.
**Skip when:** the surface has no messages beyond form errors (those are in `patterns/forms`).
**Pair with (when present):** `patterns/loading-empty-error-states`, `profiles/monitoring-observability`, `profiles/high-stakes`, `core/accessibility` (4.1.3 status messages).

## Objectives

People notice what they need to notice, when they need to, and are not interrupted for anything else. Each message is at the right level of loudness, stays as long as it is needed, says what to do, and can be reached again later. Urgent messages keep their power because they are rare.

## Priority principles

1. **Match loudness to importance and to whether action is needed.** Overstated urgency trains people to ignore every message.
2. **Put the message where the problem is.** Contextual beats global; inline beats toast for anything about the current task.
3. **Nothing important disappears on a timer.** If the person must read it or act on it, it stays until they do.
4. **Interrupt rarely.** A dialog stops work; use one only when stopping is the point.
5. **Undo beats asking.** For reversible actions, act and offer undo; keep confirmation for the irreversible and the rare.

## Checks

### Choosing the level

| What happened | Default form |
|---|---|
| Something changed that may interest the user, no action needed | Indicator: a badge, a count, a highlight |
| A problem with the user's own input | Inline validation at the field (`patterns/forms`) |
| A light action succeeded | Toast or inline confirmation, polite, auto-dismissing |
| A problem affects the current task | Inline message in that area, persistent until resolved |
| A system-wide condition (maintenance, degraded service, billing problem) | One banner at a time, persistent until dismissed or resolved |
| An event needs action soon and the user may be elsewhere | Notification center entry, plus email or push if the user chose it |
| The next step is irreversible, costly or affects others | Confirmation dialog with outcome-named buttons |
| Safety, security or money at immediate risk | The loudest channel the product has, used for nothing else |

- Each message's level can be justified from the table. Anything louder than its row is a finding.
- Severity colors (information, success, warning, error) are used consistently and never alone: an icon and a word go with the color.

### Toasts
- A toast carries one short message (about three lines at most) and at most one action.
- A toast that has an action, or that the user must read, does not auto-dismiss.
- Toasts are announced politely (`role="status"`) and do not take focus.
- A toast is not the only record: anything important can be found again (in the item itself, a history or a notification center).
- Toasts do not cover the controls the user is using, or each other.

### Banners
- One banner at a time; several stacked banners are a finding.
- A dismissed banner stays dismissed for that condition.
- Banners do not push content around after the page loads.

### Dialogs and confirmations
- A confirmation is used before irreversible, costly or wide-reaching actions, and not before routine ones; frequent confirmations are clicked through without being read.
- Buttons name the outcome ("Delete 12 invoices", "Keep them"), not "Yes" and "No".
- The text says exactly what will happen and to what.
- Initial focus goes to the least destructive choice when the action cannot be undone.
- Typing a word to confirm is kept for the most serious, rare actions.
- Where the action can be undone, prefer doing it and offering undo over asking first.

### Notifications outside the page (email, push, in-app center)
- Each type of notification can be turned on or off by the user, by type and by channel.
- Permission to send push notifications is asked when the value is clear (after the user does something that a notification would help with), not on arrival.
- The notification says what happened and links straight to it.
- Repeated events are grouped rather than sent one by one.
- Nothing is marked urgent that is not; the urgent level is kept for safety, security and time-critical events.

### Monitoring and alerting products
- Alert states use words as well as colors, and the most severe items lead.
- Acknowledging, silencing and resolving are distinct and visible.
- A flood of alerts is grouped and counted, not shown as an endless stream.

## Anti-patterns

- An error shown only in a toast that vanishes after four seconds.
- A success toast for every small action, so the important ones are lost.
- "Are you sure?" with Yes and No on every delete, including ones that could be undone.
- A push-permission prompt on first visit.
- Every notification marked as high priority.
- Three banners stacked above the page.
- A red badge count that never goes to zero because it counts things that need no action.

## Exceptions and context

- **Monitoring and incident tools** need persistent, high-contrast alerting; quietness is wrong there for real incidents. The rule is still to reserve that level for real incidents.
- **Consumer apps** depend on users keeping notifications on; overuse leads to them being switched off entirely.
- **Assistive technology users** hear every live-region announcement; chatty status updates are costlier for them.

## Implementation cautions

- Safe UI work: wording, severity styling, which ARIA live role a message uses, making a toast persistent when it carries an action, button labels in confirmations, initial focus in a dialog.
- Functional work, recommend only: adding a notification center or preferences, changing what triggers a notification, email or push delivery, grouping logic, adding undo.
- Removing a confirmation dialog before an irreversible action is never a UI fix; replacing a confirmation with undo needs undo to exist first.

## Sources

- [NNG-100] Indicators, validations and notifications; [NNG-06] confirmation dialogs and habituation; [NNG-07] error messages and severity
- [CARB-04] Notification types, persistence, severity, and not timing out critical messages
- [W3C-05] Status messages; [W3C-15] dialog focus, including the least destructive choice for irreversible actions
- [W3C-29] Limit interruptions (cognitive accessibility)

The loudness table is this skill's synthesis of these sources (evidence class: Guidance).
