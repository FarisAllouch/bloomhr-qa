---
name: qa-ticket-outcome
description: Produce the final QA report for a BloomHr ticket and apply the permitted workflow transition when the executed results justify it. Use after test execution.
---

# BloomHr QA outcome and Jira transition

## Decide the outcome

- **At least one confirmed failure:** report failed scenarios with actual and expected results, prepare a defect report using `jira-defect-report`, and transition the ticket from Ready For QA to **QA Rejected**.
- **All required scenarios pass:** confirm applicable acceptance criteria were verified, provide a QA summary, and transition to **DONE** only when that is the available and appropriate workflow outcome.
- **Blocked or incomplete:** explain the blocker and list blocked/untested scenarios. Leave the ticket unchanged by default. If the user explicitly directs a permitted transition after being told about the gap, perform only that transition and report the unverified coverage; never present incomplete coverage as fully passed.

## Transition controls

1. Before transitioning, retrieve the ticket and verify it is still in Ready For QA.
2. Use only **QA Rejected** or **DONE**. For an incomplete run, transition only when the user explicitly directs it after being informed of the gap. Never assume a transition is available.
3. If the required transition is unavailable, report that fact; do not try another status.
4. After a transition, retrieve the ticket again and confirm the resulting status. Do not claim success without confirmation.
5. Do not change unrelated Jira fields or create a bug issue without explicit user approval.

## Required QA report

- Jira key and summary
- Requirements analysis and acceptance criteria covered
- Generated test scenarios
- Executed test scenarios, separated into passed, failed, and blocked
- Confirmed defects and evidence, when available
- Final QA decision and rationale
- Previous Jira status and new status, if a transition was confirmed
- **Confidence:** a percentage from 0–100%, with a brief rationale grounded in the requirements reviewed, scenarios executed, evidence captured, and any gaps or blockers. Include this for every ticket outcome, including blocked or incomplete work.

Never imply generated tests were executed. Report blockers and unexpected behavior plainly, and do not expose credentials.

## Ticket ledger

After every ticket that was tested or attempted, update [the QA ticket ledger](../../qa-ticket-ledger.md) before selecting the next ticket. Include blocked and incomplete attempts, even when no Jira transition occurs. Record the Jira key, priority as read from Jira, outcome, confidence percentage and what that percentage measures, status before and confirmed status after (or "unchanged"), concise evidence or blocker, and the check date. Do not add tickets merely because they appear on the board or in account-wide Jira history.

Keep one current row per ticket key. On a later attempt, update that row with the latest result and retain the earlier attempt in its notes when it explains the decision; do not silently discard a prior failure or blocker. If priority or status could not be read, write "Unknown" rather than inferring it. A status transition is recorded only after the post-transition Jira check confirms it.

When asked for statistics or when the Ready For QA run ends, derive the ticket list and counts from this ledger, reconcile each reported decision with its row, and sort by Jira priority: Highest, High, Medium, Low, Lowest, then unset or unrecognized. Include the confidence percentage and state any gaps in the ledger instead of filling them from unrelated Jira changes.
