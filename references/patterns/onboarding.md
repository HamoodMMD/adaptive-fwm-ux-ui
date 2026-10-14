# Sign-up, onboarding and first use

Everything between "I want to try this" and "this is working for me": the sign-up form, verification, first-run setup, the first real task, and the help offered along the way.

**Load when:** the surface includes account creation, a trial start, a first-run experience, setup steps, product tours, checklists, or permission requests; or the user asks about onboarding, activation or drop-off after sign-up.
**Skip when:** the product has no accounts and nothing to set up.
**Pair with (when present):** `patterns/forms`, `patterns/ux-psychology`, `patterns/loading-empty-error-states`, `profiles/saas-application`, `patterns/conversion-and-retention`.

## Objectives

A new person reaches the first thing of real value with the fewest steps the product can honestly manage, understands what to do next without being lectured, and can leave and return without losing their place. Nothing is asked before it is needed, and nothing is taught before it is useful.

## Priority principles

1. **The best onboarding is a product that needs none.** Fix the interface before adding a tour to explain it.
2. **Value before identity.** Let people see or do something real before they must register, wherever the product allows.
3. **Ask late, ask little, say why.** Every field, permission and choice is requested at the moment it becomes necessary.
4. **Teach in context.** Help shown where and when it applies is used; instruction shown up front is skipped and forgotten.
5. **The first session has one job:** get this person to the first outcome that shows the product works for them.
6. **Honest terms from the start.** What is free, what will be charged, when, and how to stop.

## Checks

### Before sign-up
- The page that leads to sign-up shows what the product does with real screens or examples, and what the free or trial offer includes.
- Something can be tried or seen without an account where the product allows: a demo, a template, a sample result, a first step.
- The sign-up action says what happens ("Start free trial", "Create account"), whether it is free, and whether a card is needed.

### The sign-up form
- The first step asks for as little as possible, typically an email address or a sign-in provider. Name, company, role and password come later or not at all.
- Sign-in with an existing account (the providers the audience actually uses) is offered beside email, with equal clarity about what is shared.
- The page is free of distractions: no full site navigation, no competing offers.
- Password rules follow current guidance: length over complexity, no forced character mixes, paste and password managers allowed, a show-password control, rules stated before typing, and specific errors.
- Fields have visible labels, correct `type` and `autocomplete` values, and the right keyboard on phones.
- Consent boxes are unticked. Marketing consent is separate from terms.
- Bot checks do not block real people: no puzzle before the first field, and an accessible alternative.
- Errors keep everything typed. "Email already registered" offers sign-in and reset, not a dead end.

### Verification
- Email or phone verification does not block the first session unless security truly requires it. Let people in and verify in the background or before a sensitive action.
- A verification screen says where the message was sent, allows correcting the address, offers resend, and accepts a code as well as a link so a different device can be used.
- Returning from verification lands the person where they were going, signed in.

### First-run setup
- Setup questions are asked only when the answer changes what the person sees, and say why they are asked.
- Each is short, skippable where possible, has a sensible default, and can be changed later in settings.
- Preference and personalization questions come before appearance choices; cosmetic customization is not part of first run.
- Progress is shown as named steps when there are more than two, and reflects real progress.
- Inviting colleagues, connecting other tools and choosing a plan are offered, not required, unless the product cannot work without them.
- Setup can be abandoned and resumed; nothing entered is lost.

### The first real task
- After sign-up the person lands on the place where the first valuable action happens, with that action as the obvious primary control.
- Empty screens explain what will appear there and offer the action that fills them. Sample data or a template is offered where it helps, clearly labeled as sample, and easy to remove.
- The first task is completable in one sitting with what the person has to hand.
- Completion is acknowledged plainly and points to the next useful step.
- Imports, integrations and long-running setup show real status and let the person continue elsewhere.

### Guidance
- No multi-screen tutorial before the product is visible. If one exists, it can be skipped from the first screen and found again later.
- Hints appear where the feature is, when the person is likely to need it, one at a time, and can be dismissed for good.
- A checklist of a few real setup tasks is acceptable when it reflects what is truly done, can be dismissed, and does not nag.
- Only unfamiliar or novel features are explained. Standard controls are not.
- Help, documentation and a way to reach a person are findable from the first session.

### Permissions and notifications
- Each permission is requested when the person uses the feature that needs it, with a plain reason. Not all at once, and not on first launch unless the product cannot function otherwise.
- Declining leaves the product usable and can be reversed later.
- Notifications are opt-in, with choices by type.

### Trials, plans and payment in the first session
- Trial length, what happens at the end, and whether a card will be charged are stated before sign-up and visible during the trial.
- If a card is taken for a trial, the amount, the date of the first charge and how to cancel are on the same screen as the card field.
- Plan choice is not forced before the person has seen the product, unless the product genuinely differs by plan from the first screen.
- Upgrade prompts in the first session are few, relevant to what the person is doing, and dismissible.

### Coming back
- A person who leaves mid-setup returns to where they stopped.
- Reminder emails say what was left unfinished and link straight to it.
- New features are introduced to existing users in context, not by replaying onboarding.

### Observed practice
First step of the sign-up page on 22 established software products, measured on a desktop-sized screen in October 2026 (SURVEY-03 in the source index). Context, not a target.

| Element | What was found |
|---|---|
| Fields on the first step | 0 to 3; 18 of 22 asked for one field or none (an email address, or sign-in buttons only) |
| Password on the first step | 4 of 22 |
| Sign-in with an existing account | 20 of 22; Google on 18, then Microsoft and Apple |
| Site navigation on the page | Removed or reduced to a logo on 20 of 22 |
| "No credit card" stated | 5 of 22 |
| Pre-ticked consent boxes | None found |
| A bot check present | 11 of 22 |
| Words on the page | about 45 to 115 for the middle half |

## Anti-patterns

- A registration wall before any sight of the product.
- Ten fields to create an account; "confirm email" and "confirm password" fields.
- Password rules revealed only after a failed attempt; paste blocked.
- An email verification gate before the first screen, with no resend.
- A five-card tutorial before the interface, with no skip.
- A tour that points at buttons the person has no reason to press yet.
- Every permission requested on first launch.
- An empty dashboard with no explanation.
- Sample data that looks real and cannot be cleared.
- A checklist that counts "create an account" as an achievement and never goes away.
- A card required for a "free" trial with the charge date in small print.
- Asking for team size, role and use case to reach a product that looks the same for everyone.

## Exceptions and context

- **Regulated products** (banking, health, identity) must verify before access. Explain why, show progress, and let people save and return.
- **Products that cannot work without setup** (a data source, a team, a device) need that setup first. Make it the guided first task, not a form.
- **Business products bought by one person and used by another** need two onboarding paths: the buyer who configures and the invited user who just starts.
- **Novel interactions** (new input methods, unfamiliar concepts) justify a short interactive walkthrough.
- **Card-required trials** are the owner's commercial choice. They convert a larger share of fewer sign-ups; the net result differs by product. Check only that the terms are plain.
- **The evidence.** That tutorials do not improve task performance, that contextual help works better, that reasons raise permission acceptance, and that empty states should teach and offer an action come from usability research. In one controlled trial at a software company, a 7-day trial produced more subscribers than 14 or 30 days. Password rules follow a published standard. The first-session ordering and the "ask late" rule are this skill's synthesis.

## Implementation cautions

- Sign-up, authentication, verification, session and consent logic are protected. Field order, required fields and what is submitted are behavior: recommend changes, do not make them.
- Labels, hints, error wording, `autocomplete` and `type` attributes, show-password controls that already exist, spacing and removing page distractions are presentation.
- Password policy is a security decision. Report rules that conflict with current guidance; do not relax or tighten validation.
- Onboarding state (which steps are done, whether a tour was seen) is stored somewhere. Restyle its display; do not change what sets it.
- Sample data, templates and demo modes are features. If they do not exist, recommend them.
- Removing or deferring a verification gate, a card requirement or a setup step changes the product and its risk. Recommend, with the evidence.
- Never mark a step complete, pre-fill a consent or shorten a disclosure to make the flow look easier.

## Sources

- [NNG-79] Mobile-app onboarding: when it is needed and its components; [NNG-14] tutorials versus contextual help
- [NNG-56] Sign-up walls; [NNG-47] giving before asking
- [NNG-80] Password creation; [NIST-01] password requirements
- [NNG-81] Permission requests
- [NNG-08] Empty states
- [NNG-46] Trials without a card; [BEH-47] trial length field experiment
- [BEH-20] Endowed progress; [BEH-27], [BEH-28] progress indicators; [BEH-22] completing what one starts
- [GOV-03] One question at a time; [NNG-26] form recommendations; [BAY-21] form length

The "Observed practice" table is this skill's own measurement (SURVEY-03). The staging of the first session is this skill's judgment built on the sources above.
