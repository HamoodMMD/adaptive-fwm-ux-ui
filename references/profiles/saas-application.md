# SaaS application

Authenticated products people return to in order to get work done, including the account and settings areas of any logged-in experience.

**Load when:** there is sign-in, persistent user data and repeated use: workspaces, projects, settings, teams.
**Skip when:** the surface is public marketing, or a staff-only record-management tool (use `admin-backoffice`).
**Journey:** sign up → first use → reach first value → return → build habits → manage account, team and plan.
**Pair with (when present):** `patterns/navigation`, `patterns/forms`, `patterns/tables`, `patterns/loading-empty-error-states`; `profiles/dashboard-analytics`, `profiles/monitoring-observability`, `profiles/ai-product` for what the app does.

**For customer portals and account areas** (order history, profile, addresses, preferences): use only the sections marked *(also for customer portals)*.

## Objectives

A new user reaches something useful quickly without being taught. A returning user finds things where they left them and does repeated work with little effort. Everyone always knows which account or workspace they are in, what state their work is in, and what they are allowed to do.

## Priority principles

1. **Let people start.** Users learn by doing; they skip tours. Teach in context, when the need arises.
2. **Design for the hundredth visit as much as the first.** Repeat efficiency is the product.
3. **Context is always visible:** which organization, workspace, project, environment and role.
4. **State is never ambiguous:** saved or unsaved, synced or pending, active or archived.
5. **Add power without adding clutter:** defaults for novices, depth on request, accelerators for experts.

## Checks

### Sign-up and first run
- Sign-up asks only what is needed to create the account; anything else waits until it is useful.
- After sign-up the user lands somewhere they can act, not on an empty shell.
- Guidance is contextual and dismissible: a hint beside the control it explains, a checklist of first steps the user can ignore and return to. Forced multi-step tours before any use are avoided.
- Sample content or templates, where the product has them, are clearly labeled as samples and easy to remove.
- Password and authentication fields allow paste and password managers; requirements are shown before the user types.

### Activation
- The first valuable action (create the first project, connect the first source, invite the first colleague) is the obvious primary action on first run.
- Setup that must precede value (connect, verify, configure) shows what remains and why each step is needed.
- Blocking steps that could be deferred are flagged for the product team as functional recommendations.

### Empty states *(also for customer portals)*
- Every list, table and dashboard has a designed empty state that says what will appear here and offers the action that fills it.
- "No results for these filters" is distinct from "nothing created yet". Detail: `patterns/loading-empty-error-states`.

### Application navigation *(also for customer portals)*
- Primary navigation is persistent, stable and labeled; the current location is marked.
- Navigation is organized by the user's objects and tasks, not by internal modules.
- The number of top-level items is small enough to scan; rarely used areas are grouped.
- Deep links work: a URL returns to the same object and view, and browser back behaves predictably.
- Global actions (search, create, notifications, help, account) are in consistent places.
- Detail: `patterns/navigation`.

### Workspace and tenant context
- The current organization, workspace or project is always visible, and switching it is easy to find.
- Switching says what will change; unsaved work is protected.
- Content from different workspaces or environments cannot be mistaken for one another; production versus test is unmistakable where that distinction exists.

### Settings *(also for customer portals)*
- Settings are separated by scope: personal, workspace or organization, billing, and labeled so.
- Related settings are grouped under descriptive headings; large settings areas have their own navigation and, where it exists, search.
- The save model is consistent: either explicit save (with a clear unsaved-changes indicator and protection on leaving) or automatic save (with a visible "saved" confirmation). Mixed models within one area are flagged.
- Each setting says what it does and what it affects; risky ones say so.
- Destructive account actions (delete workspace, leave organization, close account) are set apart and confirmed. See `profiles/high-stakes.md`.

### Account, profile and security *(also for customer portals)*
- Users can see and edit their own details, change email and password, manage two-factor authentication and sessions where the product supports them.
- Changes to sign-in details confirm what happened and what to do if it was not them.
- Notification preferences are granular enough to be useful and easy to find from a notification.

### Teams and invitations
- Inviting people is straightforward, shows the role being granted, and allows several invitations at once.
- Pending, accepted and expired invitations are distinguishable; invitations can be resent or revoked.
- The member list shows role and status and can be searched when long.
- Removing a member or changing a role states the consequences.

### Roles and permissions as presented
- Role names are explained in plain words: what each can see and do.
- A user who cannot perform an action understands why. Prefer hiding actions that are never available to their role, and showing-but-disabling, with a stated reason, actions that are temporarily unavailable or need an upgrade or an approval.
- An action never appears available and then fails with a permission error.
- Who has access to an object is visible to those allowed to know.

### Subscription and plan states
- The current plan, usage against limits, renewal date and next charge are easy to find.
- Trial status and what happens when it ends are stated plainly, before and during the trial.
- Limit, past-due and suspended states explain what is affected and how to resolve it, and do not hide the user's data.
- Upgrade prompts are relevant to what the user is doing and can be dismissed. Downgrade and cancellation are as easy to find as upgrade and do not use obstruction or guilt.

### Repeat workflows and efficiency
- Frequent tasks start from where users already are, with sensible defaults and remembered choices.
- Recent items, favorites, saved views or filters exist where work repeats; lists remember sort, filter and scroll position on return.
- Bulk actions exist for operations done many times. Duplicate and template options exist for repeated creation.
- Keyboard: logical tab order, Enter submits, Escape closes. Shortcuts for frequent actions are shown in menus and tooltips and never override browser or assistive-technology keys. A command palette, where present, lists commands with their shortcuts and is operable by screen-reader users.

### Progressive complexity
- The default view serves the common case. Advanced options sit behind a labeled disclosure, one level down.
- Complex objects are created with few required fields and refined afterwards.
- Expert features do not disappear when simplified views are added.

### Feedback, saving and interruption
- Saving, syncing and background work show status; failure is reported next to the work it affects.
- Navigating away with unsaved changes warns the user.
- Toasts confirm; they do not carry errors the user must act on, and they are announced to assistive technology.
- Session expiry warns in advance and preserves work across re-authentication.
- Long operations continue in the background with progress visible, and report completion.

## Anti-patterns

- A five-screen tour before the user can touch anything.
- A blank screen for a new account.
- Users unsure which workspace they are in after following a link.
- Settings as one long undifferentiated page.
- Some settings auto-save while neighbors need a save button, with nothing to tell them apart.
- Buttons that fail with "403" instead of explaining a permission limit.
- Upgrade modals blocking core work; cancellation hidden or routed to a phone call.
- Notification settings that are all-or-nothing.
- Lists that reset filters and scroll position on every return.
- Shortcuts that hijack browser keys.
- Critical errors in auto-dismissing toasts.
- Session timeout that discards a half-written form.

## Exceptions and context

- **Simple tools** with one main task may need no navigation, workspaces or onboarding at all.
- **Genuinely novel interactions** can justify a brief introduction; conventional controls never need one.
- **Expert products** may reasonably expect training; in-context cues and discoverable shortcuts still help.
- **Single-user products** skip teams, roles and invitations.
- **Enterprise deployments** may manage sign-in, roles and billing outside the product; show the state and where it is managed.
- **Customer portals** are infrequent-use: favor clarity over accelerators.

## Implementation cautions

- Permission checks, role definitions, plan limits, billing logic, feature flags and onboarding progress flags are functional. Only their presentation is in scope.
- Showing, hiding or disabling a control according to role changes who can attempt what. Restyle an existing conditional; do not add or alter the condition.
- Changing a save model, adding autosave, undo, unsaved-changes guards or session-expiry handling adds behavior: recommend.
- Routes, deep links and state persistence (URL parameters, local storage keys) are contracts with bookmarks and other code.
- Authentication screens are often provided by an identity service; style through supported options.
- Do not alter emails, notification triggers or invitation logic.

## Sources

- [NNG-14] Onboarding tutorials versus contextual help
- [NNG-08] Empty states in complex applications
- [NNG-04] Design guidelines for complex applications
- [NNG-02] Progressive disclosure
- [NNG-31] Accelerators
- [NNG-06] Confirmation and undo
- [NNG-13] Deceptive patterns — obstruction in cancellation
- [CARB-03] Empty-state types
- [W3C-10] Accessible authentication — paste, password managers
- [W3C-01] WCAG 2.2 — 2.1.4 Character Key Shortcuts, 2.2.1 Timing Adjustable, 3.2.6 Consistent Help

Guidance on workspace context, save models, permission presentation and plan states is reasoned from the universal heuristics [NNG-01] (evidence class: Judgment).
