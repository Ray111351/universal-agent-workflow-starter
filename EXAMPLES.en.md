# Universal Agent Workflow Starter: English Examples

[Back to English home](./README.en.md) | [Complete English prompt](./PROMPT.en.md) | [中文示例](./EXAMPLES.zh-CN.md)

The following messages can be copied directly into an agent that has loaded the Universal Agent Workflow.

## Example 1: One Agent Fixes a Bug

```text
Follow the Universal Agent Workflow with the role set to SOLO.

Task: Fix an intermittent HTTP 500 response after user login.
Inputs: the current repository, error logs, and existing tests.
Constraints:
- do not change the login API;
- do not add an external dependency;
- do not touch production;
- preserve my other uncommitted changes.

Find the root cause and start with a concise Task Kickoff Card.
If this is an S task or an M task with no unresolved decision,
implement and verify it directly. Finish with a Task Completion Card.
```

## Example 2: A Planning Agent Produces a Work Order

```text
Follow the Universal Agent Workflow with the role set to PLANNER.

Objective: Add bulk export to the existing application.
Read the current requirements, API definitions, data model, and tests.
This task is limited to RESEARCH / DECISION / PLAN. Do not modify code.

Compare at least two genuinely viable approaches, including cost, risk,
compatibility, and rollback. Consolidate the decisions I need to make.
Once resolved, produce a USER_APPROVED or PROPOSED WORK ORDER without
adding any unapproved scope.
```

## Example 3: An Execution Agent Implements a Work Order

```text
Follow the Universal Agent Workflow with the role set to EXECUTOR.

Read the applicable AGENTS.md, authoritative requirements, and this
approved work order: [path or content]
Execution baseline: [branch or commit]
Authorization for this task: IMPLEMENT + VERIFY.

Stay strictly within the allowed paths. Run the narrowest relevant tests
first, followed by reasonable regression checks. If a conflict appears,
stop the affected work and continue unaffected work.
Finish by reporting actual changes, commands, results, deviations,
and remaining risks.
```

## Example 4: Independent Review

```text
Follow the Universal Agent Workflow with the role set to REVIEWER.

Perform a read-only review of: [commit, diff, report, or artifact]
Review basis: [approved work order, requirements, and acceptance criteria]

Inspect the complete change, relevant call paths, tests, artifacts,
and scope compliance. Rank concrete, locatable, actionable findings P0–P3.
If there are no findings, write No findings, but do not interpret that
as final ACCEPTED status.
```

## Common User Replies

```text
Approved
```

```text
Approved, with this change: describe the adjustment here
```

```text
Research only; do not implement
```

```text
Stop
```
