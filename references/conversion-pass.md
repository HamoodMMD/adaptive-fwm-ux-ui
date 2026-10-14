# The conversion pass

A procedure of eleven steps for turning an ordinary page into one that does its selling job well. Use it when the user asks to "make this page convert", "make it sell", "fix my landing page" or "why does nobody sign up". It ties together `patterns/sales-journey`, `selling-strategies.md`, `patterns/pricing-and-persuasion`, `patterns/ux-psychology` and `patterns/conversion-and-retention`; read those as each step calls for them.

## Contents

- What to read, and the checklist to copy
- What this can and cannot do
- The facts ledger
- Steps 1 to 11: diagnose, ask the owner, first screen, order, rewrite, proof, action, interruptions, check, content brief, report
- Rules that hold throughout

## What to read

A conversion pass is one page and one job, so read little:

- Always: this file, `patterns/sales-journey`, `core/content-and-trust`, and in `selling-strategies.md` only the rules, the identifying table and the one strategy the page uses.
- Then at most three pattern modules, chosen by what the page has: `pricing-and-persuasion` (a price or plans), `forms` (a form), `onboarding` (a sign-up), `product-page` (one product), `responsive-mobile` (most visitors on phones).
- Skim the always-on core modules (`universal-ux`, `accessibility`, `brand-preservation`) for their Checks sections only.
- `classification.md` only if the surface has not been classified yet.
- Read anything else only when a specific element calls for it.

**Starting from someone else's diagnosis.** If a diagnosis and the owner's answers already exist, trust the classification, ledger and findings, do not redo Steps 1 and 2, and begin at Step 3. Re-check only what the answers changed.

## The checklist

Copy this into your working notes and tick each line. Do not report until every line is ticked or marked "not applicable" with a reason.

```
[ ] 1  Ledger built; the main action and every contact link checked for whether they work
[ ] 2  Owner asked once (or noted as unreachable)
[ ] 3  First screen: what, who for, what they get, action, one proof line
[ ] 4  Sections ordered by the buyer's questions
[ ] 5  Copy concise, scannable, objective; no new claims
[ ] 6  Real proof beside the doubt; placeholders removed
[ ] 7  One action label; every answered channel offered; price visible
[ ] 8  Nothing interrupts on arrival
[ ] 9a Owner answers reconciled: every answer is on the page, in the brief, or listed as not used with a reason
[ ] 9b Every number, name, price and promise on the page traced to the ledger
[ ] 9c Walk-out test repeated on a phone, then a desktop; 320px checked
[ ] 9d Protected files unchanged; tests run
[ ] 10 Content brief written
[ ] 11 Report written from assets/implementation-report-template.md; baseline and what to watch stated; no predicted uplift
```

## What this can and cannot do

A page converts when a visitor **understands** the offer, **believes** it, and finds acting **easy**.

- **Understanding and ease** are properties of the page. You can fix them fully from what the project already contains.
- **Belief** depends on material only the owner has: real proof, real people, real prices, real promises. You can arrange it and ask for it. You cannot manufacture it.

So an honest conversion pass has two outputs: a page that is clear and easy, and a short, precise list of the real material the owner must supply to make it believed. A page rebuilt this way removes the reasons to leave that the page itself was causing. Whether sales rise also depends on the offer, the price and the traffic, so never promise a figure.

## The facts ledger

Everything you write must come from this ledger. Build it before changing a word.

| Fact | Source | Status |
|---|---|---|
| What is offered, to whom, where | code, page copy, owner | code-backed / copy only / confirmed / unverified |
| Prices, ranges, what is included | | |
| How it works, how long it takes | | |
| Proof: reviews, ratings, clients, numbers, qualifications | | |
| Promises: response time, guarantee, returns, cancellation | | |
| People and identity: names, address, registration | | |
| Contact channels that are really answered | | |

- **Code-backed**: the project's code enforces or computes it (a price constant, a validation rule, a plan list). **Copy only**: the page says it and nothing else supports or contradicts it. **Confirmed**: the owner told you. **Unverified**: it looks like placeholder or template content, the code contradicts it, or the owner has warned that content was made up.
- Template and placeholder content (sample testimonials, round invented statistics, reserved phone numbers and domains, stock names) is unverified until the owner confirms it. Pages built quickly are often full of it.
- If the owner says some of the page was invented, every copy-only claim becomes unverified until they confirm it.
- You may write from code-backed and confirmed facts. Copy-only facts may be kept and restated but not strengthened. Unverified facts are not relied on.
- A fact not in the ledger does not appear in your work.

## Step 1: Diagnose

- Classify the surface and name its selling strategy. A conversion pass is scoped to the selling surface, not a full audit: load the always-on core modules and `core/content-and-trust`, `patterns/sales-journey`, the matching strategy, and the pattern modules for what is on the page (pricing, forms, onboarding, product page, phone layout, sizes).
- Build the facts ledger.
- **Check that the action works at all.** Read the handler behind the main action and every contact channel: does the form send anywhere, do phone and email links point to real-looking destinations, do legal links lead to pages? A page whose form sends nothing cannot convert whatever else is fixed. On a local copy with no backend you may submit the form to see what happens; never submit to a live system.
- **Look for placeholders.** Signs include: telephone numbers in ranges reserved for fiction, domains ending in `.example`, `.test` or `.invalid`, `example.com`, links to `#`, sample names, round statistics with no source, identical star ratings, filler Latin text, and addresses that do not resolve to anything in the project. Treat these as unverified and ask.
- Run the walk-out test on the device most visitors use. List every moment a visitor could leave and its cause.
- Sort the causes into four piles:

| Pile | Walk-out causes that land here | Who fixes it |
|---|---|---|
| **Not understood** | did not understand, could not tell what would happen | You, from the ledger |
| **Not easy** | could not find, had to wait, was interrupted, had to work | You, where it is presentation; a recommendation where it needs functional work |
| **Not believed** | did not believe, was surprised, was steered | The owner's material and decisions; you arrange what exists |
| **Cannot be completed** | could not finish (a broken step, a form that sends nothing, a dead link) | Functional work: report at P0 or P1 |

- A confirmation that claims something the code does not do ("we have emailed you" when nothing is sent) belongs in the last pile. Ask the owner whether this is the live code before treating it as a live fault.

## Step 2: Ask the owner once

Ask after diagnosing, in one message, so the questions are about this page. These seven are the scaffold; adapt the wording, drop any the project already answers, and add what the diagnosis raised (facts to confirm, permissions for layout changes), to about ten at most. This replaces the usual limit of three to five questions for this mode only.

1. Who is your best customer, and what are they trying to get done when they find you?
2. What exactly do they get, and what does it cost (a price, a range, or what the price depends on)?
3. Why do customers pick you over the alternative? Facts you could prove, not adjectives.
4. What real proof can go on the page: reviews with names you have permission to use, a ratings page to link, photographs of real work or people, client names, qualifications, numbers?
5. What three doubts do people raise before buying, and what is the true answer to each?
6. What happens after someone gets in touch or signs up, and how fast, really?
7. Is anything on the current page placeholder, out of date or not true?

- If the owner asked to be consulted first, stop here: deliver the diagnosis, the plan and the questions, change nothing, and wait.
- If the owner cannot be reached, do the pass with code-backed and copy-only facts, rely on nothing unverified, and deliver the same questions as the content brief in Step 10.

**The stage-one deliverable** (when stopping to wait, or in audit-only mode): classification and selling strategy; the facts ledger; the walk-out table; the four piles with findings numbered F1, F2 in the usual short form; the planned changes numbered R1, R2 and functional recommendations FR1, FR2; and the questions.

## Step 3: Rebuild the first screen

From ledger facts only, the first screen says:

1. **What it is**, in the customer's words.
2. **Who it is for**, and where, if location matters.
3. **What they get or what changes for them**, stated as a fact.
4. **The main action**, labeled with what happens.
5. **One line of proof or reassurance**, if the ledger has one (a real rating with its count, a real response time, a real guarantee).

- If the existing headline is the brand's line, keep it and put the plain statement directly under it. Do not replace a brand line unasked.
- Nothing covers this screen on arrival, and the next section shows that the page continues.
- Read it as a stranger for five seconds, look away, and say what the business does and what you could do next. If you cannot, it is not done.

## Step 4: Order the page by the buyer's questions

Arrange existing sections so each answers the question the last one raised:

1. What is this and is it for me? (first screen)
2. What exactly do I get? (services, product, features, shown not only described)
3. What does it cost? (price, range, or what it depends on)
4. How does it work and how long does it take?
5. Why should I believe you? (proof)
6. What if it goes wrong? (guarantee, returns, cancellation, the doubts and their answers)
7. What do I do now, and what happens next? (the action)

Move sections; do not delete them. Company history and values go after proof, not before the offer. Unverified proof may travel with the section it sits in, but is not given more prominence.

## Step 5: Rewrite for scanning

In a measured study, the same content rewritten to be concise, scannable and objective more than doubled usability.

- **Concise:** cut filler, repetition and welcome text. Aim for about half the words where the meaning survives.
- **Scannable:** a heading for each section that carries the point by itself; short paragraphs; lists for parallel items; the most important fact first.
- **Objective:** plain statements of fact in place of boasting. Remove "best", "leading", "world-class" and similar words unless the ledger proves them; unsupported superlatives lower credibility.
- Front-load headings and links with the informative words. Use the customer's vocabulary, not internal names.
- Keep the brand's voice. Clearer is not the same as blander.

**What you may write:** the same facts in fewer or plainer words; headings and labels; the order; what happens next, when the ledger says so.
**What you may not write:** a new claim, number, superlative, testimonial, guarantee, deadline or price; a stronger version of an existing claim; anything not in the ledger.

## Step 6: Put proof where the doubt is

- Place each piece of real proof beside the claim it supports and near the action.
- Real photographs of the people, the place and the work are looked at; decorative and stock images are ignored. Where the project has real ones, use them where a visitor decides.
- Ratings show their count and source. Testimonials show who said them.
- Unverified proof is not moved, enlarged or relied on. It is listed for the owner to confirm or remove. Proof the owner has confirmed as placeholder is removed.

## Step 7: Make acting easy

- One primary action, with the same words wherever it appears, on the first screen and never more than about two phone screens away, with a lower-commitment alternative beside it. Buttons that choose between options (plans, services) name the option. Where a sticky header and the first section both show the action on a wide screen, the header's takes the quieter style.
- The channels the business really answers are offered: a tappable phone number, messaging, email, the form.
- The form is one column, asks only what is needed to respond, has visible labels and the right keyboards, says what happens after sending, and keeps what was typed when something fails. Removing fields is the owner's decision: recommend it.
- The price or how pricing works is visible before the visitor has to ask.

## Step 8: Remove what interrupts

- No dialog, banner or chat bubble over the offer on arrival.
- No carousel carrying the main message, no autoplaying sound, no text that waits to appear.
- A calm, consistent set of sizes and colors; nothing important styled like an advertisement.
- The page is light and the first screen appears fast.

## Step 9: Check on a phone, then a desktop

Three checks, in this order.

**Reconcile the owner's answers.** Go through the owner's message line by line. Each fact they gave is in exactly one place: on the page, in the content brief, or in a short "not used" list with the reason. A contact channel, price, proof or correction the owner supplied and the page does not show is a defect of the pass. Put the reconciliation table in the report:

| Owner's answer | Where it went |
|---|---|
| "WhatsApp on 07..." | First screen and contact list |
| "Photos next week" | Content brief |

**Trace the page back to the ledger.** Read the finished page once more and, for every number, name, price, time and promise, find its ledger line. Anything without one is removed.

**Repeat the walk-out test.** Every earlier cause is gone or is in the content brief. The main action is reachable throughout and never appears twice at once. Nothing overflows at 320 pixels wide. Protected files are unchanged and the project's tests pass.

## Step 10: The content brief

Give the owner an exact shopping list. For each item: what is needed, the form it should take, where it will go, and which doubt it answers.

| Needed | In what form | Where it goes | Doubt it answers |
|---|---|---|---|
| Three customer reviews | Full name or first name and area, what was done, permission to publish | Beside the services | "Are they any good?" |
| A starting price or range | "From X for Y" | In each service | "Can I afford it?" |
| Photographs | The team, real work, before and after | First screen and proof section | "Is this a real business?" |

Leave room in the layout only where an empty space will not look broken; otherwise leave the section out until the material arrives. Never fill it with sample content.

## Step 11: Say what changed and what to watch

Use `assets/implementation-report-template.md`, dropping rows that do not apply to the page, and add in this order: the owner-answer reconciliation table, the content brief, the functional recommendations, and the closing items below.

End the implementation report with:

- A table: each change, the reason to leave it removes, and its evidence class.
- The reasons to leave that remain and why (awaiting owner content, needs functional work).
- What to watch: the one or two behaviors that should move (enquiries per visit, sign-ups started and completed, drop-off at a named step), with a note to record the current figure first. How to record a baseline and read the result honestly: `measuring-results.md`.
- No predicted uplift.

## Rules that hold throughout

- Replacing content with what the owner has supplied (a real phone number, address, review, price) is part of the pass: the owner's answer is the authority. Change the visible text and its link target together, note each replacement in the report, and leave code and test fixtures that merely reuse an old placeholder as an example unless they are shown to visitors.
- When the owner says to leave some code alone, that wins over every rule here. A placeholder that lives in that code (an example number in an error message, wording in a script) is listed for whoever maintains it, not edited.
- A detail that looks like a placeholder but the owner has confirmed as real (a number in a range reserved for fiction, for instance) is used as given, and flagged once in the report so they can test it.
- Which option a form starts on (a checked radio, a selected plan) decides what gets sent when the visitor does nothing, so it is behavior: recommend the change, do not make it.
- On a phone, a sticky header does not repeat the main action while the first screen shows it. Give the header a different answered channel (a call button) or only the menu.
- Content that waits for script to appear is fixed in the stylesheet, by making it visible by default. Leave the script in place and note it.
- If the two limits on the main action cannot both be met without script, reach wins: repeat the action as a plain link at each decision point, and accept two in view for a moment while scrolling.
- "The same words" covers every link that leads to the action. The button that completes the form may say what it completes ("Create account"), and a button that starts a trial says so.
- A confirmation that is false in this copy but true once the owner's developer has wired it is left alone on the owner's word, with a plain "do not publish before this is wired" line in the report.
- A date for a figure ("as of October") is not a new claim when the owner gave the figure as current.
- Audience facts the owner gave (who the best customer is, what they use today) may shape the first screen. Leaving one unused is not a defect; list it under "not used".
- When a false "most popular" label is removed, the plan's existing visual emphasis stays unless the owner says otherwise; note it.
- New behavior is still functional work. A header action that hides while another is on screen, a form that posts somewhere, a new sticky bar: recommend these. Prefer a presentation-only way to meet a rule (repeating an existing link at a decision point) over new script.
- When the owner is available and asked to be consulted, hold every change until they answer; do not fix some things meanwhile.
- Functionality, data and behavior are protected exactly as in any fix pass (`implementation-safety.md`).
- The brand is preserved. A conversion pass changes order, words and emphasis inside the existing identity.
- The selling strategy is the owner's. Execute it better; recommend another only if it does not suit the offer.
- Pressure the code proves false may be removed under the rule in `implementation-safety.md`. No urgency, scarcity or social-proof device is added.
- If the page already converts for the reasons above, say so and change little.

## Sources

- [NNG-82] Concise, scannable and objective writing, measured; [NNG-84] most important first; [NNG-86] how unformatted text is skipped; [NNG-85] plain language for every audience; [NNG-87] headlines and short text
- [NNG-83] Real photographs versus decorative ones
- [NNG-49] The first seconds; [NNG-55] stating purpose and key tasks; [NNG-51] showing relevance on arrival
- [BAY-22] Single-column forms; [BAY-21] field count; [NNG-26] form recommendations
- [NNG-11], [STAN-01] credibility; [NNG-34] social proof; [NNG-60] pop-ups
- [BEH-45] How often changes work; [BEH-13] publication bias
- [AS-04] Checklists and verification loops for long procedures

The ledger, the owner questions, the step order and the three piles (not understood, not believed, not easy) are this skill's own procedure (evidence class: Judgment), built on the sources above.
