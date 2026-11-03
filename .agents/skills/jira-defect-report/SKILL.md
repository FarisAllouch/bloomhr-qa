---
name: jira-defect-report
description: Prepare a structured, evidence-based report for a confirmed BloomHr QA defect and match existing Jira title conventions. Use after a test scenario has failed against a clear requirement.
---

# BloomHr defect report

## Before drafting

1. Confirm the failure was observed during execution and conflicts with a clear requirement or acceptance criterion.
2. Review existing BloomHr project tickets to learn their title naming convention. Include the relevant Epic name or identifier in the title when the project convention does so. Do not invent a convention.
3. If the requirement is unclear or evidence is insufficient, report the uncertainty; do not label it a confirmed defect.

## Report format

### Title
Short, descriptive, and consistent with the existing project convention.

### Description
What is wrong and under which circumstances it occurs.

### Steps to reproduce
Numbered, specific steps.

### Actual result
Observed behavior, tied to the executed scenario.

### Expected result
Behavior required by the ticket or acceptance criterion.

### Severity
Blocker, Critical, Major, Minor, or Trivial.

### Priority
Highest, High, Medium, Low, or Lowest.

### Labels
Relevant labels, only when supported by project conventions/context.

Include evidence references when available. Never invent missing details or expose credentials/confidential data. Prepare the report only; do not create a Jira issue without explicit user approval.
