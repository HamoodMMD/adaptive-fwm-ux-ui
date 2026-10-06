# UX/UI implementation report — <project or surface>

**Date:** <YYYY-MM-DD>
**Scope:** <what was changed>
**Based on audit:** <reference to the audit and the findings addressed>

## 1. Summary

<Three to six sentences: what was changed, what was deliberately left, whether everything was verified, and anything the reader must do next.>

## 2. Baseline

| Item | Before any change |
|---|---|
| Branch | |
| Working tree | <clean / existing uncommitted changes: list them> |
| Build | <command> — <pass / fail / not run: why> |
| Lint and type check | <command> — <result> |
| Tests | <command> — <passed / failed / skipped counts> |
| Pre-existing failures | <list, or none> |

## 3. Files changed

| File | Kind of change | Findings addressed |
|---|---|---|
| | <styles / markup / copy / ARIA / layout / tokens usage> | |

**Files touched that contain behavior** (state, handlers, API calls, routing): <list each with why it was necessary and how equivalence was checked, or "none">

## 4. Changes by workflow or screen

### <Workflow or screen>

- **Before:** <the problem>
- **After:** <what changed>
- **Findings addressed:** <IDs>
- **Verified:** <how>

## 5. Accessibility

| Check | Result | Notes |
|---|---|---|
| Keyboard reachability and order | | |
| Focus visible and not obscured | | |
| Names, labels and roles | | |
| Contrast of changed elements | | |
| Status messages announced | | |
| Target size | | |
| Reduced motion | | |

**Requirements now met:** <success criteria fixed>
**Still outstanding:** <success criteria not fixed and why>

## 6. Responsive

| Width or condition | Result | Notes |
|---|---|---|
| 320 CSS px | | |
| Phone (360–390) | | |
| Tablet (about 768) | | |
| Desktop (1280 and wider) | | |
| 200% zoom | | |
| On-screen keyboard open (forms) | | |
| RTL (if applicable) | | |

<State which were checked in a rendered environment and which were inferred.>

## 7. Functionality preservation

| Protected area | Touched? | Evidence |
|---|---|---|
| API contracts and payloads | No | |
| Data, schema, persistence | No | |
| Routes and URLs | No | |
| Authentication and permissions | No | |
| Pricing, tax, inventory, checkout, payment, booking | No | |
| Monitoring logic, thresholds, alerts | No | |
| AI prompts, model settings, tools | No | |
| Analytics events and tracking hooks | No | |
| Integrations, jobs, notifications | No | |
| Dependencies, build and environment configuration | No | |

<Change "No" only with an explanation and the user's authorization. Describe how each workflow was re-checked after the changes.>

## 8. Brand preservation

- **Preserved:** <identity elements left untouched>
- **Aligned to the existing system:** <off-system values corrected>
- **Derived variants added:** <tokens added, where, and flagged for the owner — or none>
- **Not changed, recommended for the owner's decision:** <or none>

## 9. Tests after the changes

| Check | Command | Result | Compared with baseline |
|---|---|---|---|
| Build | | | |
| Lint and type check | | | |
| Tests | | | |

**Failures that existed before this work:** <list, or none>
**Failures introduced and fixed during this work:** <list, or none>
**Failures remaining:** <list with explanation, or none>

## 10. Not verified

<Each change that could not be verified, why, and the exact steps for someone to verify it. Write "Nothing — all changes verified" only if that is true.>

## 11. Remaining issues

<Findings from the audit that were not addressed in this pass, with priority.>

## 12. FUNCTIONAL UX RECOMMENDATIONS — NOT IMPLEMENTED

| # | Recommendation | User benefit | What would have to change |
|---|---|---|---|
| | | | |

## 13. Version control

<State whether anything was committed or pushed. By default nothing is; changes are left in the working tree for review.>
