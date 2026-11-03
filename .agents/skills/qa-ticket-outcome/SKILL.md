---
name: qa-ticket-outcome
description: Produce the final QA report for a BloomHr ticket and apply the permitted workflow transition when the executed results justify it. Use after test execution.
---

# BloomHr QA outcome and Jira transition

## Decide the outcome

- **At least one confirmed failure:** report failed scenarios with actual and expected results, prepare a defect report using `jira-defect-report`, and transition the ticket from Ready For QA to **QA Rejected**.
- **All required scenarios pass:** confirm applicable acceptance criteria were verified, provide a QA summary, and transition to **DONE** only when that is the available and appropriate workflow outcome.
- **Blocked or incomplete:** explain the blocker and list blocked/untested scenarios. Leave the ticket unchanged and request the missing clarification or access.

## Transition controls

1. Before transitioning, retrieve the ticket and verify it is still in Ready For QA.
2. Use only **QA Rejected** or **DONE**, and only when supported by the evidence and workflow. Never assume a transition is available.
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

Never imply generated tests were executed. Report blockers and unexpected behavior plainly, and do not expose credentials.
