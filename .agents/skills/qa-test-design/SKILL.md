---
name: qa-test-design
description: Generate reproducible manual test scenarios from BloomHr ticket requirements and acceptance criteria. Use after ticket analysis and before executing QA.
---

# BloomHr manual test design

## Objective

Translate verified ticket requirements into practical scenarios with clear expected results.

## Instructions

1. Use the ticket analysis and full-ticket context as the source of requirements. Cover each applicable acceptance criterion.
2. Cover relevant positive and negative paths, boundaries, input validation, error handling, UI/UX behavior, regression risks, and role permissions.
3. Identify which of Employee, Team Manager, HR, and System Manager are affected. Derive permitted and restricted actions from requirements; do not assume all roles share access.
4. If behavior is unclear or contradictory, identify the ambiguity and do not invent an expected result. Mark dependent scenarios as needing clarification rather than making them executable.
5. Keep scenarios specific, repeatable, and safe for the QA environment. Avoid destructive actions and changes to real employee data.

## Required fields per scenario

- Test case title
- Requirement or acceptance criterion covered
- Preconditions, including role and data state
- Numbered test steps
- Expected result
- Priority

Label the output as **Generated test scenarios**. Do not imply that scenarios have been executed.
