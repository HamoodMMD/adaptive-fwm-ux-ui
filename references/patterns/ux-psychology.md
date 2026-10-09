# Psychology in interface decisions

How people decide, remember, persist and value things, and what that means for an interface. Also how to check a psychology claim before building on it, because popular accounts of these effects are often half right.

**Load when:** onboarding, sign-up, multi-step flows, defaults, progress indicators, upgrade prompts, engagement or retention features are in scope; or the user, a brief or a reference cites a psychological principle ("use loss aversion", "apply the goal gradient effect").
**Skip when:** the work is purely structural (tables, navigation, accessibility fixes) and no motivational or decision design is involved.
**Pair with (when present):** `patterns/pricing-and-persuasion` for prices, anchoring, framing and urgency; `patterns/sales-journey`; `patterns/forms`; `core/content-and-trust`.

## Objectives

The interface asks for as little thinking, remembering and deciding as the task allows, shows people honestly how far they have come, gives before it asks, and states real consequences plainly. Psychological effects are used to help people finish what they came to do. They are never used to make people do what they would not choose if they saw how the interface worked.

## Priority principles

1. **Psychology explains; it does not license.** An effect being real does not make every use of it acceptable.
2. **The honest version always uses true facts.** Real progress, real availability, real consequences, real comparisons in the same units. Every one of these effects has a counterfeit that looks the same on screen.
3. **The disclosure test.** If the visitor could see exactly how the element works and why it is there, would they feel helped or tricked? Tricked means do not build it.
4. **Check the claim before using it.** Which study, did it measure this, has it held up, and does the situation match?
5. **Effects shrink outside the laboratory.** Never promise a result. Say which obstacle a change removes.
6. **Serve the person's goal, not time-on-app.** Designing for compulsion is out of scope and is flagged when found.

## Checks

### Vetting a psychology claim
When a brief, an article, a video or the user cites a principle, run this before acting on it:

1. **Name the study.** Who, when, measuring what? An anecdote from a book is not a study.
2. **Is it the right effect?** Popular sources often attach a famous study to a different principle.
3. **Has it held up?** Use the table under "Exceptions and context". Several famous effects are weaker than reported, and a few have largely failed replication.
4. **Does the situation match?** A loyalty card over nine months is not a two-minute sign-up.
5. **Is the example itself honest?** Check its numbers, units and wording against the disclosure test.

Report the result plainly: what is supported, what is overstated, and what the honest application would be.

### Fewer decisions: defaults and pre-filled values
A sensible starting value turns filling in a form into checking one. Defaults are among the best-supported effects in this field, which is exactly why they need rules.
- A default is what most people would choose or what the system already knows: today's date, the last value used, the detected country.
- It is visibly a choice and changing it takes one step.
- It favors the user. Nothing that costs money, extends a commitment or shares data is pre-selected.
- Any claim shown alongside it ("12 tables available") is real and current.
- Pre-filled values the user did not enter are easy to notice, so they are confirmed, not missed.
- Where no good guess exists, the field starts empty.

### Progress and momentum
People work harder as a goal gets closer, and are more likely to finish something that already looks started.
- Progress shown is progress made. A step counts as done only if the person did it or the system truly completed it for them.
- The steps are named and their number is known from the start.
- The first steps are the easy ones, so early movement is quick. Slow early movement on a progress display raises abandonment.
- The indicator moves at an honest, even pace. It does not race and then stall, or sit at 99%.
- Completion is acknowledged, and what the person has already done is kept if they leave and return.

### Give before asking
People return favors, and they cannot value what they have not seen.
- The visitor gets something real before being asked for an account, an email or a card: a result, a preview, a working example.
- What is withheld for sign-up is clearly more of the same, not the answer they were promised.
- Results are not blurred, truncated or faked to force registration.
- The ask comes at a moment when the benefit of saying yes is obvious ("save this report").

### Ownership and effort
People value what they have made and what feels like theirs.
- Where it suits the product, the visitor can make or customize something before signing up, and signing up is how they keep it.
- What they made is preserved exactly through sign-up, errors and reloads.
- The making is easy to finish. The effect depends on successful completion; a task people fail or abandon lowers their opinion.
- Their work is never held hostage: no deleting, locking or exporting only on payment unless that was stated before they started.

### Loss and consequences
Losses weigh more than equal gains, on average.
- A warning describes something that will really happen, with the real amount, date and items.
- Destructive actions, expiring data and unsaved work get a clear statement of what will be lost and a way to avoid it.
- Declining is a plain choice ("Not now"). It is never worded to shame or frighten ("I'll risk it").
- Upgrade prompts state what the paid plan adds. They do not invent a threat to what the person already has.

### Honest comparison
A figure is judged against whatever is next to it.
- Compared amounts use the same unit and period. A monthly charge is not shown as a percentage of a one-time price.
- The comparison is one the buyer would choose to make: the alternatives they are really deciding between.
- Detail: `patterns/pricing-and-persuasion`.

### Memory and attention
- **Recognition over recall.** Show options, recent items and examples so people choose instead of remembering.
- **Working memory holds about four things.** Do not ask people to carry information from one screen to another; show it again where it is needed. This is a limit on what must be remembered, not on how many items a visible menu may hold.
- **More options take longer to choose from,** though not in proportion. Group, order and label them; a well-organized long list beats a short vague one.
- **Things placed together are read as belonging together.** Spacing groups related controls and separates unrelated ones.
- **Experiences are remembered by their most intense moment and their end.** Fix the worst moment and finish well.

### Waiting
People judge a wait partly by what they believe is being done for them.
- When a real operation takes time, say what is happening in specific terms.
- Never add an artificial delay or a staged "working" animation to make an instant result look laborious.
- Detail on loading states: `patterns/loading-empty-error-states`.

### Engagement and habit
- Features that return people to the product do so because the product was useful: reminders the person set, saved work, a real update.
- Flag designs built to produce compulsion: endless scrolling and autoplay as unchangeable defaults, streaks that punish a missed day, rewards on an unpredictable schedule, notifications sent to recapture attention, guilt at the exit.
- Notifications are opt-in, specific and easy to turn off.

## Anti-patterns

- A progress bar that starts at an invented figure or counts steps nobody took.
- "12 available" from a fixed string.
- A default that spends the user's money or shares their data.
- A result blurred behind a sign-up after the page promised it free.
- Customization that is discarded at sign-up.
- A fabricated threat ("your files will be deleted") used to sell an upgrade.
- "No thanks, I don't like saving money."
- A monthly price shown as a small percentage of a one-time purchase.
- A fake "analyzing…" delay.
- Quoting a study for a principle it did not test.
- Capping a visible menu at seven items "because of Miller's law".
- A report that says a change "leverages" an effect and will raise conversion.

## Exceptions and context

- **Experts and frequent users** are less swayed by framing and more hurt by anything that slows them. Defaults and shortcuts help them; progress celebrations do not.
- **High-stakes decisions** (money, health, legal) call for slowing people down at the commitment, the opposite of momentum.
- **Children and vulnerable users** warrant stricter limits on all motivational design.
- **Genuine protective warnings** (data loss, security, deadlines set by others) should be loud. The rule is truth, not quietness.
- **Regulation** increasingly treats manipulative and addictive design as a consumer-protection matter. Flag likely problems; do not rule on compliance.
- **How well the evidence holds** (state this when asked whether a technique "works"):

| Effect | What the research supports |
|---|---|
| Defaults | Strong, consistent, larger in consumer settings. |
| Endowed progress (a head start raises completion) | Supported by a field experiment and related work; one context, modest sample. |
| Goal gradient (effort rises near the goal) | Supported in loyalty programs. |
| Progress indicators in forms | Mixed: a steady indicator does not reliably reduce drop-off; slow early progress increases it. |
| Giving first | Supported by usability research on sign-up walls and gated content. |
| Valuing what one made (IKEA effect) | Supported and replicated, only when the task is completed. |
| Endowment (owning raises value) | Real in experiments; smaller with experience; mechanism disputed. |
| Loss aversion | Real on average; weaker for small stakes and informed people. |
| Choice overload (the jam study) | The original result has not replicated reliably; the average effect across studies is near zero. |
| Decision fatigue as a depleting resource | Large preregistered replications found little or no effect. Fewer decisions is still good design, for reasons of effort, not depletion. |
| Remembering unfinished tasks better (Zeigarnik) | Not supported in a recent meta-analysis; a tendency to resume interrupted tasks is. |
| "Seven plus or minus two" | A loose estimate for recall, since revised to about four; not a rule for visible menus. |
| Showing the work during a wait | Supported in experiments for real, explained effort. |

Isolation and serial-position effects, sunk cost, commitment and variable rewards are often cited in design writing. They were not checked for this index; treat claims built on them as unverified until checked.

## Implementation cautions

- A default changes what is submitted when the user does nothing. Pre-filling a value the system already holds, in a field the user will see, is presentation. Choosing a default plan, quantity, add-on or consent is the owner's decision: recommend it.
- A progress indicator needs state and a true count of steps. Restyling one that exists is presentation; adding one, or changing what it counts, is functional. Never adjust its figures to look further along.
- Removing or moving a sign-up wall, adding a preview, or letting people build before registering changes the product's flow and data. Recommend it with what would have to change.
- Warnings must be driven by real system state. If the code cannot know that files are at risk, the warning cannot say so.
- Rewording a decline option to neutral language is presentation and may be done in a fix pass. Removing a manufactured threat changes marketing content: report it at P1 or higher and recommend removal.
- Do not add delays, streaks, counters, notifications or reward mechanics.
- When citing an effect in a report, give its evidence status from the table and name the obstacle the change removes. Do not predict an outcome.

## Sources

- [BEH-12] Defaults meta-analysis; [NNG-38] defaults as anchors
- [BEH-20] Endowed progress; [BEH-21] goal gradient; [BEH-27], [BEH-28] progress indicators and completion
- [NNG-47] Reciprocity; [NNG-56] sign-up walls; [NNG-27] gated content
- [BEH-22], [BEH-23] The IKEA effect and its replication; [BEH-24] the endowment effect
- [BEH-08], [BEH-09] Loss aversion; [NNG-39] prospect theory; [NNG-13] deceptive patterns; [FTC-01] dark patterns report
- [BEH-19] The jam study; [BEH-06], [BEH-07] choice-overload meta-analyses; [BEH-25] ego depletion replication
- [BEH-29] Zeigarnik and resumption meta-analysis; [BEH-30] working memory capacity; [NNG-73] short-term memory and menus
- [NNG-72] Recognition and recall; [NNG-75] choice and decision time; [NNG-74] proximity; [NNG-59] peak-end rule; [NNG-52] cognitive load
- [BEH-26] Operational transparency during waits
- [BEH-13] Publication bias in nudge research; [LAW-09] addictive design; [LAW-07] manipulative interfaces

The disclosure test, the claim-vetting steps and the split between presentation and owner decisions are this skill's own rules (evidence class: Judgment).
