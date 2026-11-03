---
name: jira-board-triage
description: Inspect the BloomHr Jira board, map columns to statuses, and identify tickets eligible for QA. Use before selecting tickets for QA or when asked to review board readiness.
---

# BloomHr Jira board triage

## Objective

Build a complete, project-scoped picture of the BloomHr board and identify tickets that may be processed by QA.

## Instructions

1. Use the available Atlassian MCP tools to inspect only the BloomHr project and board.
2. Read all board columns and their tickets. Record the visible column names and corresponding Jira statuses; inspect workflow transitions when available.
3. Review enough ticket context (summary, status, description, comments, attachments, links) to understand board state and avoid duplicate QA.
4. Select only tickets displayed in **Ready For QA**, then verify each candidate’s actual Jira status directly.
5. Do not test tickets outside Ready For QA. Do not reprocess a ticket already tested unless its implementation or requirements have changed.
6. Read each eligible ticket’s Jira Priority field and group candidates from highest to lowest: Highest, High, Medium, Low, Lowest. Put unset or unrecognized priorities last; do not infer or change priority.
7. Within each priority group, preserve the board order. Present the ordered groups as the QA sequence. If a priority cannot be retrieved, place that ticket last and report the gap.
8. If the board, statuses, or history needed to determine eligibility cannot be read, report the limitation rather than infer eligibility.

## Output

Report the board columns and statuses, eligible ticket keys and summaries grouped from highest to lowest priority in test order, verified current status, and any context or access gaps. This skill is read-only: do not edit issues, comment, transition, or create bugs.
