# Measuring whether a change worked

Read this when the user asks "did it work?", "how will I know?", or wants proof that a fix or a conversion pass paid off; and at Step 11 of `conversion-pass.md`. It tells you what to set up before a change, how to read the numbers after it, and what you may honestly say.

## Contents

- What you may and may not claim
- Before the change: record the baseline
- Pick the method the traffic allows
- Reading a before-and-after comparison
- Watching five people
- Which method answers which question
- What to report

## What you may and may not claim

- You may say which reasons to leave a change removed, and with what evidence class.
- You may report measured numbers with their period, their counts and the method.
- You may not predict an uplift, and you may not credit a change with a rise that the method cannot separate from chance, season or traffic.
- A surprisingly large effect from a small change is more often a measurement fault than a discovery. Check the counting before reporting it.

## Before the change: record the baseline

A result with no baseline cannot be read. Before editing, ask the owner for, or help them record:

1. **The outcome that matters** (enquiries, sign-ups, orders), as a count and as a share of visits.
2. **One or two steps on the way** (taps on the main action, forms started, forms sent). These happen more often than the outcome, so they show movement sooner.
3. **The period.** At least two full weeks, longer for small sites, so weekday swings even out.
4. **The split by device and by where visitors came from.**
5. **How it was counted.** Unique people or visits, and by which tool. The same method must be used afterwards.

If the page has no analytics, say so, recommend adding it as functional work, and suggest a manual count (enquiries logged per week by channel) meanwhile. Adding tracking scripts is the owner's decision: it changes what data is collected.

## Pick the method the traffic allows

| Situation | Method | What it can show |
|---|---|---|
| Thousands of outcomes a month | A controlled experiment: visitors split at random between old and new | Whether the change caused the difference |
| Tens to hundreds of outcomes a month | Before-and-after over matched periods, read with the cautions below, plus watching five people | A direction, not a proof |
| A handful of outcomes a month | Watching five people use the page, and a count by channel | Whether the reasons to leave are gone |

- Most small-business and early-stage pages are in the second or third row. Say so plainly; do not dress a before-and-after as a test.
- At low volume, large changes can show up where small wording changes never will. A conversion pass is a large change, which is the better case.
- In a controlled experiment, decide the size and length before starting and do not stop early because the numbers look good.

## Reading a before-and-after comparison

A rise after a change has other possible causes. Rule each one out, or name it:

| Other cause | Check |
|---|---|
| **Season and calendar** | Compare with the same weeks last year, or with a period of the same weekdays and no holiday or sale |
| **A change in who is arriving** | Compare the mix by source and device. A burst of unrelated visitors lowers the rate while the count stays flat |
| **Bounce-back from an unusual low** | If the change was made because of a bad week, some recovery would have happened anyway. Use a baseline of several weeks, not the worst one |
| **Something else changed** | Prices, advertising, stock, a competitor, a mention in the press, the form being repaired |
| **Too few to tell** | With counts in single or low double figures, a difference of a few is within ordinary variation |
| **Counting changed** | New tracking, a renamed event, a consent banner |

When a functional fault was repaired in the same pass (a form that sent nothing now sends), expect that repair to account for most of any rise, and report it that way.

## Watching five people

Numbers say where people leave; watching says why. Five people who match the customer, each asked to do the page's main job while thinking aloud, uncover most of the serious problems in a design. Fix what they hit and repeat with new people. This works at any traffic level and is the main check available to a small site.

Do not turn what five people did into a percentage or compare it with a conversion rate. One measures whether people can; the other whether they do.

## Which method answers which question

Reading code and screenshots answers some questions well and others not at all. Match the question to the method:

| Question | Can the skill answer it from the project? | Method that answers it |
|---|---|---|
| Is there a label, a focus style, enough contrast, a heading structure? | Yes | Inspection and measurement |
| Does the flow follow known good patterns? | Mostly | Heuristic review, cognitive walkthrough |
| Do people understand the pricing, the icon, the wording? | No | Watching five people try (qualitative usability test) |
| Can people find the right product or page? | No | Usability test; tree testing for navigation; search-log review |
| Where do people drop out, and how many? | No | Analytics and funnel data |
| Why do they drop out? | No | Usability test, interviews, session review |
| Is version B better than version A? | No | A controlled experiment where traffic allows; otherwise a before-and-after read with care |
| How satisfied are people, how does it compare over time? | No | Surveys, benchmark tests repeated over time |
| Does it work with screen readers and other assistive technology? | Partly | Testing with assistive technology, ideally with its users |

What people say and what they do differ; prefer watching behavior to asking for opinions. Most real questions need two methods: numbers to show where, people to show why.

## What to report

- The baseline, the period after, and the counts behind every rate.
- The method, and which row of the table above it is.
- Each other cause from the table: ruled out, or still possible.
- What five people did, if anyone watched.
- A plain conclusion in one of three forms: "the numbers moved and the other causes are ruled out", "the numbers moved but these causes cannot be separated", or "too few to tell; here is what to keep counting".

## Sources

- [NNG-88] Conversion rate: definition, consistent counting, small steps and outcomes, no universal benchmark
- [NNG-89] Qualitative and quantitative studies and their sample sizes; [NNG-90] five users; [NNG-91] what analytics can and cannot show
- [GOV-09] Completion rate and using data with research; [NNG-102] choosing a research method
- [BEH-50] Regression to the mean
- [BEH-45] Controlled experiments, surprising results and stopping rules; [BEH-13] published effects overstate

The three-row method table is this skill's own simplification (evidence class: Judgment).
