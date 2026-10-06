# Loading, empty and error states

Everything a view can be besides "loaded with data". These states are where most products leave users guessing.

**Load when:** the surface fetches data asynchronously, or behaves like an application.
**Skip when:** the surface is static content with no data-dependent regions.

## Objectives

At every moment the user can tell which situation they are in: still loading, nothing here yet, nothing matching, not set up, not allowed, cannot reach the server, failed, out of date, done, or partly done. Each tells them what, if anything, to do next.

## Priority principles

1. **One state, one meaning.** A single generic "No data" for every situation forces users to diagnose the system themselves.
2. **Never fake it.** No invented progress percentages, no fabricated sample data presented as real, no success shown before it is known.
3. **Keep what you have.** Do not throw away visible content or the user's input because something new is loading or failed.
4. **Scope the state to what is affected.** One failed widget is not a failed page.
5. **Every state has a next step,** or says plainly that there is none.

## Checks

### Tell the states apart
Each of these is a different situation and should look and read differently.

| State | What the user needs to know | Typical treatment |
|---|---|---|
| **Initial loading** | Something is coming; roughly what and where | Skeleton of the final layout, or a scoped spinner; nothing for very short waits |
| **Background refresh** | Content is being updated; what they see is still usable | Keep content; subtle progress cue; no layout shift |
| **Partial loading** | Some parts are ready, others pending | Show ready parts; per-region placeholders for the rest |
| **No data yet** (first use) | Nothing has been created; what belongs here; how to start | Explanation plus the primary action that fills it |
| **No results** (search or filters) | Nothing matches these criteria; data exists otherwise | Restate criteria; offer to clear or change them |
| **No configuration** | Setup is required before anything can appear | What to set up, why, and a link to do it |
| **No permission** | Content exists but this user cannot see or do it | Say so; say who can grant access or how to request it |
| **Disconnected / offline** | The app cannot reach the server; what still works | Persistent, non-blocking notice; automatic retry or a retry control |
| **Failed request** | Something went wrong; whether their work is safe; what to do | Specific message at the place of failure; retry; alternative |
| **Stale data** | What they see may be out of date; as of when | Last-updated time; warning when beyond the expected interval; refresh |
| **Success** | The action worked; what changed; what next | Specific confirmation near the action or as a status message |
| **Partial success** | Some of it worked and some did not; which | Counts, the failed items and reasons, retry for the failures only |

Also distinguish: **not found** (the item does not exist or was removed), **session expired** (sign in again without losing work), **rate limited or quota reached** (when it will work again), and **long-running** (it continues in the background; where to see it).

### Loading
- Under about 1 second: show no indicator. A flash of spinner or skeleton is more disruptive than a brief wait.
- About 1 to 10 seconds: a skeleton for a page or large region, because it shows the structure to come; a spinner for a single component or a button.
- Beyond about 10 seconds: a determinate progress indicator driven by real progress, or honest stage descriptions, with the option to cancel or to leave and return.
- Skeletons match the size and shape of the real content and reserve its space, so nothing jumps when data arrives. A skeleton that is only a header and footer around blank space looks broken.
- The indicator sits in the region that is loading. A full-page overlay for one panel blocks everything else needlessly.
- An action button that started the work shows a pending state in place and prevents repeated presses.
- If a wait exceeds expectations, say so and offer a way out, instead of spinning forever.
- Loading regions are marked busy for assistive technology, and completion is announced where the user is waiting on it.

### Background refresh
- Existing content stays visible and interactive.
- Refresh does not move scroll position, close open items, clear selections, or shift layout.
- Newly arrived items that would displace what the user is reading are announced ("12 new entries") and inserted on request.
- Automatic refresh can be paused where content changes while the user reads it.

### Empty states
- State what would be here and why it is empty, in one or two sentences.
- Offer the primary action that changes it: create, import, connect, clear filters.
- For first use, a brief explanation of the value and, where helpful, a link to learn more. This is a good moment for contextual teaching.
- "No results" names the active query and filters and offers one-click ways to relax them.
- Illustrations are optional, modest and in the brand's own style; the words and the action do the work.
- An empty container with no message at all is always a defect: the user cannot tell empty from loading from broken.
- Do not fill empty states with fabricated example data that could be mistaken for real records.

### Permission and configuration states
- A user without permission is told that access is restricted, not shown an empty list as if nothing existed.
- The message says what is needed (a role, a plan, an approval) and who or where to ask, without exposing details they should not see.
- A feature that needs setup shows what to configure and links straight to it; it does not look like a failure.
- Upgrade-gated features say so honestly and can be dismissed.

### Errors
- The message appears where the problem is: beside the field, inside the panel, on the row.
- It says in plain language what happened and what the user can do: try again, check something, use another route, contact support with a reference.
- It distinguishes "you can fix this" (invalid input, missing permission) from "we failed" (server, network), and never blames the user for the second kind.
- It says whether the user's data or action is safe: saved, not saved, unknown.
- The user's input is preserved.
- A retry control is offered for transient failures; repeated automatic retries are visible, not silent.
- Technical detail (codes, identifiers) is available for support but secondary to the explanation.
- Errors needing action stay until resolved. They are not shown only as a notification that disappears.
- A failed region leaves the rest of the page working.
- Errors use icon and text as well as color, and are announced to assistive technology.

### Connection and staleness
- Loss of connection is shown promptly and persistently without blocking reading of what is already loaded.
- Actions that cannot work offline are disabled with the reason, or queued visibly where the product supports that.
- Reconnection is confirmed, and content refreshes.
- Data that updates periodically shows when it was last updated; if an update is overdue, that is flagged so old values are not mistaken for current ones.

### Success
- Confirmation is specific: what was done, to what ("Invoice 1042 sent to accounts@example.com").
- It appears near the action or in the product's consistent notification area, and is announced as a status message without moving focus.
- For consequential actions the confirmation persists (a page, a banner, a record) and can be referred to later; for routine ones a brief message suffices.
- It offers the natural next step, or an undo where one exists.
- The view updates to reflect the change, so the user does not have to reload to see it.

### Partial success
- State exactly how many items succeeded and how many failed.
- List the failures with reasons.
- Offer to retry only the failures.
- Never report a partial failure as either a plain success or a total failure.

### Transitions between states
- Moving from loading to content, or content to error, does not jump the layout or steal focus.
- When focus was inside a region that is replaced, it moves to a sensible place.
- The same state looks the same everywhere in the product.

## Anti-patterns

- "No data" used for empty, filtered-to-nothing, unauthorized, misconfigured and failed alike.
- Blank regions with no message.
- A spinner that never ends.
- Full-page spinner or blocking overlay for a small update.
- Skeletons that flash for a fraction of a second, or look nothing like the content.
- Progress bars and percentages driven by a timer.
- Replacing a populated list with a spinner on every refresh.
- "Something went wrong" with no next step and no word on whether the action took effect.
- Errors in toasts that vanish before they are read.
- Clearing the form on error.
- Showing "Saved" before the save is confirmed, then failing silently.
- An empty list where the truth is "you do not have access".
- Stale values with no timestamp.
- Bulk operations reported as "Done" when some failed.
- Humorous error pages on a task the user needed.
- Demo data that looks real.

## Exceptions and context

- **Optimistic updates** (showing the result before the server confirms) are legitimate when failure is rare and the correction is clear. They are a deliberate product behavior, not something to add as a styling choice.
- **Static content sites** need little beyond a useful not-found page and form-submission states.
- **Real-time views** (monitoring, chat, feeds) make connection and staleness states primary.
- **Marketing surfaces** can afford warmer empty-state copy; operational tools want it terse.
- **Security-sensitive contexts** may deliberately not distinguish "not found" from "no permission"; follow the product's policy.
- **Very fast systems** need few loading indicators at all.

## Implementation cautions

- UI-safe: wording, layout, iconography and placement of states the code already distinguishes; skeleton shape and size; scoping an existing indicator to its region; adding `aria-busy`, `role="status"` or `role="alert"` to existing messages; preserving layout dimensions; showing an existing last-updated value.
- Functional, recommend: distinguishing states the code currently collapses (for example empty versus unauthorized versus failed); adding retry, cancel, offline detection, queueing, background jobs, real progress reporting, staleness detection, partial-success reporting, error boundaries or optimistic updates.
- You cannot honestly present a distinction the data layer does not make. If the API returns an empty array for both "none" and "forbidden", report it; do not guess.
- Do not swallow or reword errors in a way that hides information the user or support needs.
- Never display raw server errors, stack traces, tokens or internal identifiers to end users; never copy them into the audit report either.
- Loading and error components are often shared; a change affects every surface that uses them.

## Sources

- [NNG-05] Skeleton screens — no indicator under a second, skeleton or spinner up to about ten seconds, progress bar beyond, avoid frame-only skeletons
- [NNG-03] Response-time limits
- [NNG-08] Empty states in complex applications — communicate status, provide learning cues, offer a direct path
- [CARB-03] Empty-state types — no data, user action, error management
- [NNG-07] Error-message guidelines — visibility, plain and specific wording, constructive advice, preserve input
- [GOV-02] Writing error messages
- [NNG-18] No-results pages
- [W3C-05] Status messages
- [WEB-03] Layout stability — reserving space for late content
- [NNG-01] Visibility of system status; help users recognize, diagnose and recover from errors
- [W3C-01] WCAG 2.2 — 2.2.1, 2.2.2, 3.3.1, 3.3.3, 4.1.3

The state taxonomy and the partial-success and staleness guidance are this skill's synthesis of the sources above (evidence class: Judgment).
