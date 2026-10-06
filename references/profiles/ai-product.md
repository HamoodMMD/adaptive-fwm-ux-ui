# AI product

Surfaces where people work with AI output: assistants, generators, copilots, AI-assisted features, and agents that act on a user's behalf.

**Load when:** AI involvement is assistive, generative or agentic on this surface.
**Skip when:** AI is only mentioned in marketing copy, or runs invisibly with no user-facing output to review.
**Journey:** understand what it can do → express intent → wait → review the output → correct, edit or retry → accept or apply → give feedback.
**Pair with (when present):** `profiles/saas-application` for the surrounding product; `profiles/high-stakes` when AI can take consequential actions; `patterns/forms`, `patterns/loading-empty-error-states`.

## Objectives

Users form an accurate picture of what the AI can and cannot do, can express what they want, can check and change what comes back, stay in control of anything it does on their behalf, and always have a way forward when it is wrong or unavailable.

## Priority principles

1. **Calibrated trust.** The aim is neither maximum confidence nor constant doubt, but confidence that matches how reliable the system is for this task.
2. **Output is a draft until the user accepts it.** Review, editing and rejection are first-class, not afterthoughts.
3. **The user stays in control,** most of all where stakes are high or the action is hard to undo.
4. **Design for being wrong.** Errors, refusals and poor results are normal operating conditions that need designed paths.
5. **Honest about what it is.** Do not imply a human, feelings, certainty or abilities the system does not have.

## Checks

### Mental model and capability boundaries
- Before first use the interface says what the feature does in terms of user benefit, and what it is not good at. The description is concrete: examples of good requests beat general claims.
- Limitations that matter are stated where they apply: knowledge cut-offs, no access to certain data, known weak areas, length limits, languages supported.
- It is clear what the AI can see and use: which documents, fields, history or account data are in its context, and what is not.
- Onboarding is staged and in context; users are encouraged to try low-risk requests instead of reading screens of instructions.
- AI-generated content is identifiable as such wherever it could be mistaken for human-written or verified content.

### No anthropomorphic deception
- The product does not claim or imply it is a person, has feelings, or "understands" in a human sense. Names and personality are acceptable as brand voice; false claims are not.
- Simulated typing delays, fake "thinking" pauses and other theatre that adds waiting without work are avoided.
- Agreement and praise from the assistant are not presented as evidence that the user is right.

### Input and prompt design
- The input area signals what to type: a purposeful label or placeholder with a persistent label for assistive technology, example prompts or starter actions that fill or run a request.
- Structured controls are used where the choices are known (tone, length, format, source), instead of expecting users to phrase everything.
- Attached context (files, selections, pages, records) is visible, removable and clearly scoped.
- Multi-line input is comfortable; the keyboard behavior of Enter versus new line is stated or conventional; the send control has an accessible name.
- Drafts survive navigation and errors. A failed request never loses what the user typed.
- Limits on length or file type are shown before they are hit.

### Generation, latency and streaming
- Submitting gives immediate acknowledgement. The request appears in place and the system shows it is working.
- For waits longer than a moment, progress is honest: streaming text, or a description of the actual stage ("Searching 3 documents"). No invented percentages.
- A visible stop control ends generation and keeps what was produced, marked as incomplete.
- Streaming does not move content the user is reading, steal focus, or force-scroll when the user has scrolled up.
- The interface remains usable while generating: the user can read earlier content, navigate away and come back.
- Long tasks continue in the background where the product supports it and notify on completion.

### Reviewing output
- Output is readable: structured with headings, lists, tables and code blocks as appropriate, at a comfortable measure.
- Verification is made easy: sources or references where the system has them, linked to the exact passage; changes to existing content shown as a comparison with the original.
- Where AI edits user content, what changed is visible before it is applied.
- Copying, exporting and inserting the output are one action each.
- Partial or truncated responses say so.
- Uncertainty is communicated when it matters to the decision, using coarse categories or plain wording in preference to precise-looking percentages. Blanket disclaimers that appear on everything become invisible and are not a substitute.

### Editing, regeneration and undo
- The user can edit the output directly, and can edit their request and try again without retyping.
- Regenerating does not destroy the previous result; earlier versions remain reachable where the product keeps them.
- Applying AI output to the user's own content is undoable, and the undo is easy to find immediately afterwards.
- Dismissing an unwanted suggestion takes one action and is remembered where sensible.
- It is easy to invoke the AI when wanted and easy to ignore it when not.

### Autonomous actions and approval boundaries
- Before the AI takes an action with consequences outside the conversation (sending, purchasing, deleting, publishing, changing settings or records, calling external services), it shows exactly what it will do and waits for explicit approval.
- The approval step states the scope: which items, which recipients, what amounts, which systems.
- Standing permissions ("always allow") are granular, visible and revocable in one obvious place.
- A record of actions taken by the AI is available: what, when, on whose instruction, with what result.
- Irreversible actions are never taken without confirmation, and the interface says they are irreversible.
- A running agent can be paused or stopped, and says what has already been done.
- See `profiles/high-stakes.md` when actions touch money, data loss, permissions or external communication.

### Errors, failure and fallback
- Different failures are distinguished and each says what to do: the service is unavailable or timed out (retry); a limit was reached (wait or upgrade, with the time); the request was declined by policy (rephrase, and why if it can be said); a tool or data source failed (which one); the result is low quality (refine).
- The original request is preserved after any failure and can be retried in one action.
- A non-AI path exists for the underlying task wherever possible, so that the user is not blocked when the AI fails.
- When the AI cannot do something, it says so plainly instead of producing a confident wrong answer; where that is model behavior, record it as a functional recommendation.

### Feedback
- Simple feedback (helpful or not) is offered on outputs, with an optional reason.
- The interface says what feedback is used for. It does not promise personalization or learning that does not happen.
- Reporting harmful or seriously wrong output has a clear route.

### Control, provenance and privacy
- Users can find, in one place, the controls for AI features: turning them off, adjusting how proactive they are, clearing history or memory where it exists.
- The model or system behind the output and the sources it used are disclosed where that affects trust or compliance.
- It is stated what data is sent for processing and whether it is stored or used for training, at the point where the user provides it.
- Changes in capability or behavior are announced to users.

### Accessibility specifics
- Streaming output is announced to screen-reader users in a controlled way (on completion or in sentence-sized chunks), not token by token.
- Generation start, completion and errors are status messages.
- Chat history is navigable by headings or landmarks; each message identifies its author.
- Mixed-direction output (for example Arabic with code or English terms) renders correctly. See `patterns/rtl-bilingual.md`.

## Anti-patterns

- "Ask me anything" with no indication of scope or limits.
- Presenting output as authoritative, with no sources and no way to check.
- An agent that sends, buys, deletes or publishes without showing what it will do.
- Losing the prompt on error.
- Regenerate that overwrites the only good answer.
- Output that cannot be edited or copied.
- A modal or full-screen lock while generating.
- Fake progress bars; artificial typing delays.
- "I feel…", "I'm happy to…" presented as real states; a human name and photo with no indication it is AI.
- The same disclaimer under every message.
- Numeric confidence scores with no basis.
- AI suggestions that pop up repeatedly after being dismissed.
- A thumbs-down that does nothing and says nothing.
- No way to complete the task without the AI.

## Exceptions and context

- **Low-stakes creative tools** tolerate imprecision; heavy verification UI would be friction. Keep editing and regeneration strong.
- **High-stakes domains** (health, finance, legal, safety) need stronger review, provenance and confirmation, and a clear statement that the output is not professional advice where that is true. Give no domain advice in the audit itself.
- **Invisible AI** (ranking, autocomplete, spam filtering) needs little of this beyond a way to correct or dismiss results and an explanation on request.
- **Expert users** may want less hand-holding and more control over parameters; offer depth without removing safeguards.
- **Showing confidence** helps only when it changes what users do and they can interpret it; if untested, prefer wording over numbers.

## Implementation cautions

- Do not change prompts, system instructions, model choice, parameters, tool definitions, tool permissions, safety filters, retrieval logic or memory behavior. They are the product's logic.
- How the model words uncertainty, refusals or its own nature is model behavior. Record it as a functional recommendation; do not edit prompts to change it.
- Approval gates, action logs, undo for applied changes, version history and stop controls are functionality. Improve their presentation where they exist; recommend them where they do not.
- Rendering of streamed content is UI, but touching the stream-handling code can break ordering, cancellation and error handling. Change styles and containers, and verify.
- Never add sources, citations, confidence indicators or "verified" labels that the backend does not supply.
- Never add a feedback control that sends nowhere.
- Do not expose system prompts, keys or internal identifiers in the interface or in the report.

## Sources

- [PAIR-01] Mental models — expectations, staged onboarding, human-like framing
- [PAIR-02] Explainability and trust — calibrated trust, when to show confidence
- [PAIR-03] Feedback and control — value of feedback, balancing automation and control
- [PAIR-04] Errors and graceful failure — paths forward, manual fallback, stakes
- [HAX-01] Guidelines for Human-AI Interaction (Amershi et al., CHI 2019)
- [HAX-02] The eighteen guidelines — notably G1–G2 (what it can do, how well), G7–G11 (invoke, dismiss, correct, scope, explain), G15–G18 (feedback, consequences, global controls, change notices)
- [NNG-36] AI hallucinations — communicating uncertainty, sources, avoiding false precision
- [NNG-37] Sycophancy in generative-AI chatbots
- [NNG-03] Response-time limits
- [APL-01] Platform guidance for generative AI features
- [W3C-05] Status messages

Guidance on approval boundaries for agentic actions combines the control and consequence guidelines above with error-prevention principles (evidence class: Judgment); the published guidance predates widely deployed agents.
