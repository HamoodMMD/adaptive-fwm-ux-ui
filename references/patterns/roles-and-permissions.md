# Roles, permissions, teams and workspaces

What people see and do when a product has more than one user per account: roles, invitations, permission-limited screens, access-denied pages, read-only views, sharing, switching between workspaces or organizations, and admins acting on behalf of others. The rules here are about the interface; who is actually allowed to do what is enforced on the server and is security policy.

**Load when:** the product has roles, team members, invitations, sharing, permission-dependent actions, an access-denied page, more than one workspace, organization, client or tenant per person, or an admin "view as" or impersonation feature.
**Skip when:** each account has exactly one user and nothing is shared.
**Pair with (when present):** `profiles/admin-backoffice`, `profiles/saas-application`, `profiles/high-stakes` (removing access, deleting a workspace), `patterns/account-security`, `patterns/loading-empty-error-states` (hidden versus disabled), `patterns/tables`.

## Objectives

People always know whose account and which workspace they are in, what their role lets them do, and how to get access when they lack it. Admins can give the right access quickly without giving too much. Nobody acts on the wrong organization by mistake, and nobody hits a dead end with no way forward.

## Priority principles

1. **Context first.** The current workspace, organization or client is visible on every screen; acting in the wrong one is the costliest mistake in multi-tenant products.
2. **Every "no" has a way forward.** A missing permission is explained in plain words with who can grant it, not a bare error.
3. **Least access by default, made easy to choose.** Invitations default to the smallest role that does the job, and the difference between roles is clear enough that admins do not over-grant out of confusion.
4. **Show what people need to understand the product; hide what they never need.** Main-workflow actions stay visible and disabled with a reason; functions a role never uses are hidden.
5. **Interface only.** Changing who is allowed to do what is security policy: report it, never change it in a fix pass.

## Checks

### Current context and switching
- The current workspace, organization, client or tenant is named in a consistent place on every screen, not only in the URL or a menu.
- The switcher lists each place by a recognizable name (and logo where available), marks the current one, and is searchable when the list is long.
- After switching, the user lands on a sensible page in the new context, and the change is visible at once; nothing from the previous context stays on screen.
- Actions with wide effect (delete, bulk change, invite, billing, export) name the workspace they will act on in the button or the confirmation.
- Links shared across workspaces open in the right context or say which one they belong to.

### Roles and what they mean
- Each role has a plain-language name and a one-line description of what it can do; a comparison of roles is one click away where roles are chosen.
- Custom permissions, where offered, are grouped by area and use the product's own nouns and verbs, not internal permission codes.
- People can see their own role and what it allows, for example on their profile or the members page.

### Invitations and members
- The role is chosen while inviting, with the least powerful suitable role as the default.
- Pending invitations are listed with who invited whom, when, the role, and when the invitation expires, with resend and revoke actions.
- An invitee who already has an account joins without creating a new one; a new invitee is guided through creating one.
- The members list shows each person's role, status (active, pending, suspended) and last activity where the product records it, and can be searched and filtered.
- Removing someone or lowering a role says what they will lose; removing or demoting yourself warns that you will lose access.
- The last owner or admin cannot be removed or demoted without naming a replacement.
- Bulk invitations report which succeeded and which failed, with the reason for each failure.

### When someone lacks permission
- **In the main workflow,** an action the user cannot take stays visible and disabled, with a short reason in place, in the form "Available to [role]" or "Ask an admin to [action]". Hiding it would make the product hard to understand and hard to ask about.
- **Functions a role will never use** (billing for a viewer, admin settings for a guest) are hidden rather than shown disabled.
- **Read-only** content that the user may view but not change is shown as read-only text or controls, not as a disabled form that looks broken.
- A submit button is not disabled to show missing permission or invalid input; follow the form validation pattern instead.
- **Access-denied pages** distinguish "you do not have access to this workspace or service" from "you do not have permission to do this", say which account is signed in, name who can grant access (or offer a "request access" action that notifies them), and give a way back. They do not reveal the title or contents of what is protected.
- A request for access tells the requester it was sent and to whom, and tells the approver exactly what was asked for.

### Acting on behalf of others
- When an admin or support agent views or acts as another user, client or tenant, a persistent, high-contrast banner names who they are acting as, with an "exit" action, on every screen until they leave.
- Actions taken while acting as someone else are recorded and visible to that someone where the product supports it.

### Sharing
- The sharing control states who can see the item now ("Only you", "Everyone in Acme", "Anyone with the link") before the user changes it.
- Making something public or available outside the organization is a separate, clearly labeled choice, never the default.
- People who can see an item are listed with their access level, and access can be removed from the same place.

## Anti-patterns

- A bare "403 Forbidden" or "Access denied" with no explanation, no account shown and no way to ask for access.
- Main navigation that silently changes from user to user, so colleagues cannot help each other.
- Role names like "Level 2" or "Editor+" with no explanation.
- An invitation form that defaults to Admin.
- The workspace name shown only in a dropdown, so bulk actions run in the wrong client account.
- Removing yourself from a workspace with one click and no warning.
- An impersonation mode that looks exactly like the normal product.
- "Anyone with the link" selected by default for confidential documents.

## Exceptions and context

- **Small teams with one or two roles** need only clear role names, a members list and a basic access-denied page.
- **Agencies, accountants and client portals** switch contexts constantly: the context indicator and wrong-tenant protection are the priority.
- **Regulated products** (health, finance, government) may require stricter access, audit logs and approval steps; check the interface explains them rather than calling them friction.
- **Single sign-on organizations** may manage roles in another system; the product should say where access is managed.

## Implementation cautions

- Safe UI work: role descriptions, disabled reasons, access-denied page wording and layout, showing the current workspace, banner styling, sharing labels, warnings when removing members.
- Functional work, recommend only: changing roles or permissions, default roles, what a role can see, request-access workflows, impersonation, audit logs, sharing defaults, last-admin protection.
- Hiding or disabling a control in the interface never replaces a server-side permission check; never treat a UI change as a security fix.

## Sources

- [NIST-02] Least privilege: only the access needed for assigned tasks
- [UXR-03] Permission handling in a design system: keep main-workflow actions visible and disabled with a reason, hide extra functions, full-page access-denied state, do not reveal protected data
- [UXR-04] Disabled versus read-only states and disabled reasons; do not disable form submission
- [GOV-14] Two access-denied cases: no access to the service, and no permission for an action; say who to contact
- [UXR-05] Inviting users: roles chosen at invite, personalized invitations, resending
- [WEB-16] Hidden versus disabled controls

Context indicators, wrong-tenant protection, impersonation banners and last-admin protection are this skill's judgment from error-prevention principles; little published research covers them.
