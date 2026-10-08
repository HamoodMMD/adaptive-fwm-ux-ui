# Implementation safety

Read this before editing any file. It defines what a UX/UI change is allowed to touch and how to prove nothing else moved.

The principle: **a user who approved "UX improvements" did not approve a change to how their business works.** Anything that alters behavior, data or contracts needs its own explicit approval.

## Protected by default

Unless the user explicitly authorizes functional work, do not alter:

- API contracts, request and response schemas
- Database schema, migrations, persistence
- Backend behavior and business logic
- Routes and URL structure
- Authentication, sessions, RBAC and permission checks
- Billing, pricing calculations, discounts, taxes
- Inventory and stock logic
- Cart, checkout, shipping and payment behavior
- Booking and availability logic
- Monitoring logic, scan behavior, alert thresholds, severity mapping
- Analytics events and data-layer contracts
- Queues, cron jobs, workers, notification logic
- AI model selection, parameters, prompts, tool permissions, guardrails
- Third-party integrations and their configuration
- Environment and secret files

Visible labels may change without renaming the identifiers behind them. Renaming a button from "Submit" to "Request a quote" is UI; renaming its `name`, `id`, event name, route or translation key is not, unless you have confirmed nothing depends on it.

If a recommendation needs anything on the list, write it up under `FUNCTIONAL UX RECOMMENDATIONS — NOT IMPLEMENTED` with the benefit, the change required and who would need to make it. Then leave the code alone.

## Change boundary

| Safe: normal UX/UI work | Caution: verify behavior is unchanged | Off-limits without explicit approval |
|---|---|---|
| Styles, spacing, typography, color usage | Component state and props | API calls, endpoints, payloads |
| Token usage (not token values that define the brand) | Hooks, stores, context | Business rules and calculations |
| Responsive layout and overflow | Event handlers | Auth, sessions, permission checks |
| Semantic markup, headings, landmarks | Conditional rendering tied to data or roles | Routing and redirects |
| Labels, accessible names, ARIA | Form validation rules and schemas | Database, migrations |
| Focus order and focus styles | Element `id`, `name`, `data-*`, class names used by tests, analytics or third-party scripts | Payment, checkout, booking logic |
| Copy, microcopy, error wording | Translation keys | Dependencies, framework, build config |
| Grouping and ordering of existing content | Field order in forms that post to a backend | Feature flags, environment config |
| Presentation of loading, empty, error and success states that already exist | Debounce, timing, optimistic updates | Analytics events |

Some changes look visual and are not:

- **Adding a derived design token** (a darker step of a brand color) is allowed as a flagged change: add it beside the original, never replace the original, and report it for the owner.
- **Showing existing data under a new condition** (a low-stock note below some threshold) introduces a business rule. The owner chooses the threshold; without one, recommend it.

- **Removing or reordering form fields** can break backend validation, CRM mapping or autofill. Recommend it.
- **Changing an element type** (`div` to `button`, `a` to `button`) changes default behavior: form submission, navigation, keyboard activation. Add `type="button"` where needed and re-test the handler.
- **Hiding a control** for a role or state is permission logic if it changes who can do what. Changing how an already-unavailable control is presented is UI.
- **Changing validation timing** changes behavior. Changing how an existing error is displayed is UI.
- **Adding a new state** (a loading flag, an error boundary) adds logic. Styling a state the code already has is UI.
- **Payment and identity fields** are often hosted iframes or SDK components with compliance constraints. Style them only through the provider's supported options.
- **Markup around third-party embeds, consent banners and tag managers** often has selectors that outside scripts depend on.

## The harmful side-effect exception

Some of the worst usability defects live inside interface handlers: a failed submit that clears the form, a Back button that throws away later answers, an error path that resets a selection. The general rule would leave these untouched because they are in behavior-bearing code. That leaves the most damaging problem on the page as the one thing a fix pass will not fix.

So one narrow exception applies. You may remove or correct such a side effect when **every** condition holds:

1. **The harm is to the user's own input or place in the interface**: typed text, selections, scroll position, focus. It is not a business rule.
2. **The fix removes or narrows the side effect.** It adds no feature, state, request or dependency. Deleting a `form.reset()` call on the error path qualifies; adding autosave does not.
3. **Nothing that leaves the page changes for the same input.** Given the same values in the interface at the moment of the action, what is validated, submitted, saved, charged, routed or tracked is identical before and after, on both the success path and the failure path. Removing the side effect can still change what a user ends up submitting later in the session, because their input now survives (an opt-out box that a reset used to re-tick stays unticked). Report every such knock-on effect.
4. **You verify condition 3**, by running the same scenarios against the original and the changed code and comparing results. If you cannot run them, the exception does not apply.
5. **The line itself does nothing in a protected area.** It does not compute, validate, send or decide anything about payment, pricing, authentication, permissions, inventory, booking rules, alerting or AI prompts. Interface wiring inside a checkout or booking handler qualifies when it only touches what is on screen.

When you use the exception, say so in the implementation report under its own heading, "Behavior changed under the harmful side-effect exception": the line removed, the harm it caused, the scenarios compared, and how to revert it. It applies even when the user cannot be asked, because leaving the harm in place is not the conservative choice. If any condition is in doubt, report the defect as a functional recommendation instead.

## Existing content that cannot be verified

"Nothing fake" governs what you add. Projects also arrive containing claims you cannot check: statistics, testimonials, client names, awards, prices, phone numbers. Report them as findings under the trust rules and ask the owner to confirm or remove them. Do not delete, reword or replace them yourself unless the owner says they are placeholders. Content that is evidently placeholder (sample text, reserved or fictional phone numbers, example domains on a page about to go live) is at least P1, because it will be seen by real visitors.

## Nothing fake

Do not add search, filters, export, refresh, AI features, progress percentages, dashboard data, recommendations, metrics, controls, buttons, links, settings, integrations, charts or checkout steps that are not backed by working functionality and real data. If it does not exist, recommend it. Placeholder or sample content must never ship looking like real data.

## Nothing destructive

Do not delete project code, remove features, rewrite architecture, replace the design system or component library, add or swap dependencies, change the framework or migrate libraries unless the user asked for exactly that. Do not "clean up" unrelated code you happen to notice; mention it instead.

## Secrets and privacy

- Never print, quote or copy keys, tokens, passwords, connection strings or personal data into chat, reports or commits. Refer to them as `[redacted]` and name the file.
- Do not read more of a secret file than needed to know what it is. Do not modify `.env` files, secret stores or credentials.
- If you find a secret committed to the repository, tell the user plainly; do not attempt to rotate or remove it yourself.
- Do not send project code, screenshots or data to external services unless the user asked for that.

## Procedure

### Before the first edit

1. `git status` — record the branch, uncommitted changes and untracked files. If the tree is dirty, say so and confirm which changes are yours to build on. Never overwrite, revert or reformat someone else's uncommitted work.
2. Identify install, build, lint, type-check and test commands from the manifests, README and CI config.
3. Run a baseline where practical: build, lint, tests. Record what already fails so it is not attributed to you later. If you cannot run something, say why.
4. If you can run the app, capture the current behavior of each workflow you are about to touch.

### While editing

5. Work in small groups by workflow or screen, highest priority first. One concern per group. Stay inside the scope the user set: before editing a shared component, token or global stylesheet, check what else uses it, and ask first if that includes an area the user excluded.
6. Follow the project's own conventions: its components before new ones, its tokens before raw values, its naming, its file layout.
7. After each group, re-run the relevant checks and re-walk the affected workflow.
8. When a behavior-bearing file must be touched, keep the diff minimal, leave logic lines untouched where possible, and verify equivalence: same handlers fire, same requests are sent with the same payloads, same routes resolve, same validation outcomes, same analytics events.

### Before reporting

9. Read the complete diff. Every changed file must be explainable as a UX/UI change. Revert anything that is not.
10. Confirm no protected area changed: search the diff for API paths, schema files, auth, payment, env and config files.
11. Run the final build, lint, type-check and tests and compare with the baseline.
12. Complete the verification in SKILL.md Step 10 and write the implementation report.
13. Do not commit, push, merge, deploy or open a pull request unless the user asks. If they do, follow their conventions and keep UX changes separate from anything else.

## When you cannot verify

Say exactly what was not verified and why: no runnable environment, authentication required, a state that could not be triggered, tests absent. Mark the affected changes as *unverified* in the report and give the user the steps to check them. Do not describe an unverified change as working.

## If something breaks

Stop adding changes. Identify whether the failure predates your work (compare with the baseline). If your change caused it, fix or revert that group, re-run the checks, and record what happened in the report.
