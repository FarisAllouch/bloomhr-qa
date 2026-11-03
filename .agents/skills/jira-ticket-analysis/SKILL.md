
---
name: jira-ticket-analysis
description: Analyze BloomHr Jira tickets, understand requirements and acceptance criteria, identify affected roles, dependencies, risks, and ambiguities. Use when reviewing a Jira ticket before QA testing.
---

# Jira ticket analysis

## Objective

Analyze a Jira ticket to determine what functionality needs to be tested and what the expected behavior should be.

## Instructions

1. Retrieve the complete Jira issue using the available Atlassian MCP tools.
2. Review its summary, description, acceptance criteria, comments, attachments, and linked issues when accessible.
3. Verify its current Jira status.
4. Identify the affected BloomHr functionality.
5. Identify relevant user roles:
   - Employee
   - Team Manager
   - HR
   - System Manager
6. Identify dependencies and potential regression risks.
7. Identify missing, unclear, or contradictory requirements.
8. Do not invent requirements or expected behavior.

## Output

Provide:

- Jira issue key and summary
- Current status
- Functionality being tested
- Requirements and acceptance criteria
- Affected user roles
- Dependencies
- Potential risks
- Unclear requirements
- Recommended testing scope

## Restrictions

- Do not modify Jira issues.
- Do not add comments.
- Do not change issue statuses.
- Do not create bugs.
- Do not execute application tests during analysis.