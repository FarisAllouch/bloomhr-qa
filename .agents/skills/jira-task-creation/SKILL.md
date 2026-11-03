---
name: jira-task-creation
description: Create a well-scoped Jira Task in the BloomHr project when QA or product work reveals a necessary follow-up. Use when a missing implementation, maintenance, or process task should be tracked; do not use this to file defects.
---

# BloomHr Jira task creation

## When to use

Use this workflow when the work reveals a concrete follow-up that should be tracked as a Jira **Task**, such as missing implementation or test coverage, documentation, or a product/process improvement. A confirmed product defect belongs in the defect reporting workflow; do not create a Bug through this skill.

## Workflow

1. Keep the work within the BloomHr Jira project. Check the current ticket, related issues, and existing project tickets for a duplicate or an already-tracked task.
2. Confirm the need is actionable and supported by observed behavior, an explicit requirement, or a clear gap. If the need or desired outcome is ambiguous, state the uncertainty and ask for clarification instead of creating a vague task.
3. Review nearby BloomHr tickets to follow their summary/title style and relevant Epic/parent conventions. Do not invent a naming convention or link an unrelated Epic.
4. Prepare the Task with a concise summary and a description that states:
   - Why the work is needed and its source/context
   - The desired outcome
   - Scope and relevant acceptance criteria, written so the result can be verified
   - Dependencies, affected roles, or risks when known
   - Evidence or source ticket links when available
   - Use this description format: a concise purpose paragraph followed by a `**Requirements:**` heading and actionable bullets. Use indented sub-bullets for role-specific navigation, sub-tabs, or related details. Preserve the product's visible labels and routes.
5. Set only fields supported by the project’s existing conventions and the available facts. Do not fabricate an assignee, priority, estimate, Epic, labels, or acceptance criteria. Avoid adding sensitive employee data or credentials.
6. Create the Task in the BloomHr Jira project using the available Atlassian tools. Do not create it in another project.
7. Read the created issue back and confirm its key, summary, project, issue type, and any links/fields actually set. If creation or verification fails, report that accurately and do not claim success.

## Report

Provide the Jira key and summary, a brief reason the task was needed, and the fields/links confirmed after creation. If a duplicate was found, report the existing issue instead of creating another. If requirements are too unclear to make an actionable task, describe the gap and request clarification.

## Boundaries

- This skill authorizes creation of BloomHr **Tasks** when the workflow identifies a concrete need. It does not authorize Bug creation; confirmed defects must be prepared as reports and require explicit user approval before a Bug is created.
- Do not change the status or unrelated fields of existing issues as part of creating a task.
- Do not modify unrelated Jira projects, expose credentials, or include confidential employee information.
