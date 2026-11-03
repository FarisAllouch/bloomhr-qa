---
name: qa-test-execution
description: Execute approved manual BloomHr QA scenarios in the authorized browser environment and record observed results. Use only for verified Ready For QA tickets.
---

# BloomHr manual test execution

## Preconditions

- Confirm the ticket’s current Jira status is **Ready For QA**.
- When triaging multiple Ready For QA tickets, follow the `jira-board-triage` sequence: Highest, High, Medium, Low, Lowest, then unset or unrecognized priority. Recheck each ticket’s status immediately before testing.
- Use the QA environment at `https://hr.bloomteq.click` and its login page at `/login`.
- Select an installed browser that is currently accessible for QA (for example, Brave, Chrome, or Edge). Use the existing authenticated QA session when available. If no installed browser can be accessed, report the blocker and leave the ticket unchanged.
- Use only scenarios based on analyzed requirements. Resolve material requirement ambiguity before judging pass/fail.

## Execution

1. Follow each scenario’s steps and use the specified role. For authentication, read the root `.env` only as needed and use the matching `BLOOMHR_EMPLOYEE_EMAIL`, `BLOOMHR_TEAM_MANAGER_EMAIL`, `BLOOMHR_HR_EMAIL`, or `BLOOMHR_SYS_MANAGER_EMAIL` value. Never reveal credentials in reports or Jira, and do not edit `.env`.
2. Verify both allowed and disallowed role actions when required. If an account or access for a required role is missing, mark its scenarios **Blocked**.
3. Compare observed behavior with the stated expected result. Record each scenario as **Passed**, **Failed**, or **Blocked**, with actual result and evidence where available.
4. Capture screenshots or other evidence when available. Do not fabricate evidence or claim execution for a scenario that was only reviewed.
5. Stop before destructive actions or changes to real employee data. Report the limitation and leave the Jira ticket unchanged if safe execution is not possible.
6. After the QA run is complete, close the BloomHr QA browser session. If QA was performed in a pre-existing browser window with unrelated tabs, close only the BloomHr QA tab and leave unrelated tabs and windows open.

## Output

Clearly separate generated scenarios from executed scenarios. For each executed scenario, include its status, observed actual result, expected result, and evidence reference if available. Summarize untested or blocked coverage and why.

This skill does not authorize creating Jira bugs or changing ticket status; use the relevant reporting/outcome workflow after execution.
