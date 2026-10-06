# UX/UI audit — <project or surface>

**Date:** <YYYY-MM-DD>
**Mode:** <audit only | scoped review | focus pass: … | design plan>
**Scope:** <what was audited>
**Access used:** <source code | running app | public URL | screenshots> — <what could not be inspected>
**Target:** WCAG 2.2 Level AA

## 1. Executive summary

<Four to eight sentences. The overall condition, the two or three issues that matter most, what is working well, and the recommended first step. Lead with the conclusion.>

| Priority | Count |
|---|---|
| P0 — blocking | |
| P1 — major | |
| P2 — friction | |
| P3 — polish | |

## 2. Classification

<Insert the completed classification, or a short version for scoped work: surface, profiles, pattern modules, users and goal, confidence and evidence.>

## 3. User workflows

For each key workflow:

### <Workflow name>

- **User and goal:**
- **Entry point:**
- **Information needed:**
- **Decisions and actions:**
- **Completion:**
- **Failure and recovery:**

| Question | Assessment |
|---|---|
| Can users recognize what to do? | |
| Can they find the right control? | |
| Can they predict what will happen? | |
| Do they get adequate feedback? | |
| Can they recover from mistakes? | |
| Can experienced users repeat it efficiently? | |

## 4. Strengths / preserve

<What works and should not be changed, with the reason. Be specific: a redesign that removes these would be a regression.>

- 

## 5. Findings

List by priority, highest first. One block per finding.

### <ID> — <short title>

| | |
|---|---|
| **Priority** | P0 / P1 / P2 / P3 |
| **Route or screen** | |
| **Component** | |
| **Workflow** | |
| **Issue** | <What is wrong, stated as an observation> |
| **Evidence** | <File and line, or what was observed> — *verified* / *inferred* |
| **Rule** | <module › section> — <Requirement (SC x.y.z, Level) / Principle / Research / Guidance / Judgment> |
| **User impact** | <Who is affected and how> |
| **Recommendation** | <The specific change> |
| **UI-only?** | Yes / No |
| **Functionality risk** | None / Low / Medium / High — <why> |
| **Status** | Reported / Implemented / Not implemented — functional |

## 6. Accessibility

**Summary:** <overall state against WCAG 2.2 AA; what was verified in the rendered UI and what was inferred from code>

| Area | Result | Findings |
|---|---|---|
| Keyboard and focus | | |
| Structure, names and labels | | |
| Forms and errors | | |
| Color and contrast | | |
| Targets and pointer input | | |
| Reflow, zoom and spacing | | |
| Motion, time and media | | |
| Status messages | | |

**Requirements failed or likely failed:** <list with success criterion numbers>
**Recommendations beyond AA:** <list, clearly separate from the above>

*This review identifies problems. It is not a statement of conformance.*

## 7. Responsive behavior

**Widths and conditions checked:** <list, and whether rendered or inferred>

| Area | Result | Findings |
|---|---|---|
| Content priority | | |
| Layout and overflow | | |
| Touch targets | | |
| Navigation | | |
| Forms | | |
| Tables and charts | | |
| Sticky elements, dialogs and sheets | | |
| Orientation and zoom | | |

## 8. Brand

**Inventory:** <logo, color tokens, typography, spacing, radius, elevation, motion, imagery, component library, modes — with source files>

**Coherence:** <where the system is consistent, where it has drifted>

**Preserve:** <identity elements that must stay>

**Usage problems:** <where a brand element is used in a way that harms usability, and the usage-level fix>

**Changes needing the owner's decision:** <derived variants or base-element changes, if any>

## 9. Recommendations

Safe UI changes, grouped by workflow or screen, in the order to do them.

| # | Change | Findings addressed | Effort | Risk |
|---|---|---|---|---|
| | | | | |

## 10. FUNCTIONAL UX RECOMMENDATIONS — NOT IMPLEMENTED

Improvements that need changes to behavior, data, logic or integrations. Not implemented; listed for a product and engineering decision.

| # | Recommendation | User benefit | What would have to change | Area affected |
|---|---|---|---|---|
| | | | | |

## 11. Suggested order of work

1. <P0 items>
2. <P1 items that are UI-only>
3. <Functional recommendations to schedule>
4. <P2, then P3>

## 12. Limits of this audit

<What was not inspected or could not be verified; assumptions made; anything that needs checking with real users, real devices or real data.>
