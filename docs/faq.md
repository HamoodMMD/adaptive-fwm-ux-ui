# Questions and limitations

## Questions

<details>
<summary><strong>Will it change my code if I just ask it to "check" my site?</strong></summary>

No. *Audit, review* and *check* are read-only. It does not leave helper files in your project either.
</details>

<details>
<summary><strong>Is this a set of guidelines, or does it do the fixing?</strong></summary>

Both. By default it audits and reports. When you ask it to fix, it makes the changes itself, within [its safety limits](how-it-works.md#what-it-will-never-do), and gives you a report of exactly what changed.
</details>

<details>
<summary><strong>How do I try it without risk?</strong></summary>

Ask for an audit only. Or ask for fixes on a new git branch and review the diff before merging. It never commits or pushes on its own.
</details>

<details>
<summary><strong>Will it interfere when I say "audit" about something else, like security or SEO?</strong></summary>

It is meant for UX, UI, usability and accessibility requests. A security audit or an SEO audit is a different job, and the skill does not claim it.
</details>

<details>
<summary><strong>Can I use it with a design skill that builds new pages?</strong></summary>

Yes. They do different jobs: a design skill creates a new look, and this one checks and repairs an existing interface without restyling it. A common flow is to build with one and audit with the other.
</details>

<details>
<summary><strong>Does it work for Arabic and other right-to-left sites?</strong></summary>

Yes. There is a dedicated module for RTL and bilingual layouts. It checks structure and rendering; it does not judge the quality of wording in languages the agent cannot verify.
</details>

<details>
<summary><strong>Can it make my page sell more?</strong></summary>

It can make your real offer clearer and easier to act on, which is usually what a sales page is missing. It will not invent offers, and it will not promise a conversion increase, because no honest tool can.
</details>

## Limitations

- **No sales effect has been measured.** The skill removes reasons to leave and tells you how to measure the result; nobody has yet measured it on a live site with real visitors.
- **It predicts; it does not watch real users.** Findings rest on published research and standards, not on testing with your customers.
- **What it can verify depends on what it can see.** From code alone it cannot confirm real colors, layouts or keyboard order, and it marks those findings as *inferred*. A running app or screenshots give better results.
- **It is not a compliance certificate or legal advice.** It finds accessibility and consumer-protection problems; it cannot prove there are none.
- **It is not a redesign or rebrand tool,** and not a performance-engineering tool.
- **Some guidance is judgment.** Where strong research is thin, the modules say so. See "Known gaps" in [`references/research-sources.md`](../references/research-sources.md).
- **The measured site figures will date.** They were taken in October 2026, by script, one visit per page.
- **The thirteen selling strategies are an interpretation.** They group what real sites were observed doing, supported by research on each technique. No study validates the grouping itself, the sites walked were large brands, and naming a site's strategy is a judgment the skill labels as one.
- **Testing so far** is blind AI-agent runs on routing scenarios and demo pages, on two model sizes. It has not been tested with real users, on physical devices or with screen readers.

---

[← Back to the main page](../README.md)
