# BloomHr QA workspace

## Application

- Product: BloomHr
- Environment: QA
- Base URL: https://hr.bloomteq.click
- Login URL: https://hr.bloomteq.click/login
- Work only with the BloomHr Jira project and board. Never retrieve unrelated Jira projects.

## QA boundaries

- Read the full BloomHr board for context, but test only tickets currently in **Ready For QA**. Verify the actual Jira status before work and again before any transition.
- When processing multiple Ready For QA tickets, group by Jira Priority and test from **Highest** to **Lowest**; put unset or unrecognized priorities last.
- Do not repeat QA on an unchanged ticket that has already been tested.
- Never invent requirements, test results, evidence, or missing information. Distinguish generated scenarios from executed tests.
- Do not modify real employee data, delete data, modify unrelated Jira fields, or expose credentials/confidential information.
- Do not create Jira bugs without explicit user approval. Prepare a report for confirmed defects instead.
- If requirements, browser access, credentials, or test data prevent completion, describe the blocker and leave the ticket unchanged.
- Use only the **QA Rejected** or **DONE** transitions when appropriate. Confirm the resulting status; if the required transition is unavailable, report that without choosing another status.

## Roles and QA accounts

BloomHr roles are Employee, Team Manager, HR, and System Manager. Check role access against each ticket’s requirements; do not assume permissions are shared. Use separate authorized QA accounts where needed.

Account emails are in the root `.env` file. Read it only when authentication is required, select the corresponding role variable, never include its values in output or Jira, and never modify `.env`:

- Employee: `BLOOMHR_EMPLOYEE_EMAIL`
- Team Manager: `BLOOMHR_TEAM_MANAGER_EMAIL`
- HR: `BLOOMHR_HR_EMAIL`
- System Manager: `BLOOMHR_SYS_MANAGER_EMAIL`

If an account needed for a role is unavailable, mark that role’s scenario as Blocked.

## Skills

Use the relevant workflow skill for QA work. Skills are in `.agents/skills/`:

- `jira-board-triage`: inspect the entire board and select eligible tickets.
- `jira-ticket-analysis`: analyze one ticket’s requirements, roles, dependencies, and ambiguity.
- `jira-task-creation`: create a BloomHr Task when QA or other work identifies a concrete follow-up need.
- `qa-test-design`: produce clear, comprehensive manual test scenarios.
- `qa-test-execution`: execute scenarios in the authorized QA browser and record evidence/results.
- `jira-defect-report`: prepare a structured report for a confirmed defect.
- `qa-ticket-outcome`: report results and apply a permitted Jira transition when warranted.

Communicate in English with clear, reproducible, technically precise reports. Ask for clarification when requirements are ambiguous.
