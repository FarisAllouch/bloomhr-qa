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
- Every ticket report must include a confidence percentage (0–100%) and a brief evidence-based rationale. This is mandatory for all tickets, including blocked or incomplete QA; confidence describes certainty in the reported conclusion and does not replace test evidence.
- Never modify real employee data or use real personal data as test data. Get the user's explicit approval before any data-changing action in BloomHr or Jira, including creating, editing, deleting, commenting, or transitioning issues. Get the user's explicit approval before creating or modifying any file inside this project. Read-only inspection and preparing an unsent report do not require approval. Do not expose credentials or confidential information.
- Do not create Jira bugs without explicit user approval. Prepare a report for confirmed defects instead.
- If requirements, browser access, credentials, or test data prevent completion, describe the blocker. Leave the ticket unchanged by default; if the user explicitly directs a permitted transition after being told about the gap, make only that transition and report the remaining unverified coverage.
- Use only the **QA Rejected** or **DONE** transitions. Confirm the resulting status; if the directed transition is unavailable, report that without choosing another status.

## Roles and QA accounts

BloomHr roles are Employee, Team Manager, HR, and System Manager. Check role access against each ticket’s requirements; do not assume permissions are shared. Use separate authorized QA accounts where needed.

Role account emails are in the root `.env` file. Read it only when authentication is required, select the corresponding role variable, never include its values in output or Jira, and never modify `.env`. The `.env` currently contains the four role email variables below; it does not contain role passwords or other `BLOOMHR` authentication secrets. Use an already authorized session or the supported sign-in flow; do not assume that an email alone completes authentication:

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
