# Universal Agent Workflow v1.1: English Examples

[Back to home](./README.en.md) | [LITE](./PROMPT.lite.en.md) | [GOVERNED](./PROMPT.governed.en.md) | [中文示例](./EXAMPLES.zh-CN.md)

Send these messages to an agent that has loaded the relevant workflow. The agent should normally infer duty and risk; users do not need to memorize the terminology.

## Example 1: LITE Bug Fix

```text
Fix an intermittent HTTP 500 response after user login.

Inputs: the current repository, error logs, and existing tests.
Constraints:
- do not change the login API;
- do not add an external dependency;
- do not touch production;
- preserve my other uncommitted changes.

After finding the root cause, implement the smallest fix and verify it. Ask me
only when a real decision would change scope or risk.
```

Expected: the agent briefly states objective, boundary, and verification, then proceeds without requesting duplicate approval.

## Example 2: Read-Only Public Research

```text
Compare three publicly available person-tracking approaches. Prefer current
official documentation and primary papers. State source dates, limitations,
and your inferences. Research only: do not install, purchase, or modify
anything. End with one recommendation.
```

Expected: the agent researches and cites sources directly without manufacturing a work order or approval step.

## Example 3: Spreadsheet Cleanup

```text
Clean customer_feedback.xlsx: normalize dates and category values, remove
exact duplicate rows, preserve the original sheet, and add cleaned and summary
sheets.

Do not upload the data to an external service or delete the original file.
Report row-count changes, applied rules, and uncertain records.
```

Expected: complexity may be M, but the action remains reversible. The agent uses a short plan without entering a high-risk workflow.

## Example 4: GOVERNED Public Release

```text
Prepare release v1.2.0: inspect the change, update release notes, and create
candidate release content.

You may complete all read-only checks and reversible preparation. Immediately
before creating a tag or Release, pushing, merging, or sending a public message,
show me the exact target, baseline, content, and recoverability and wait for
confirmation.
```

Expected: the agent separates preparation from publication and never bypasses EXTERNAL confirmation merely because the edit is small.

## Example 5: Sequential Multi-Agent Work

Planning session:

```text
Work in the PLAN duty. Inspect the real state and produce a PROPOSED WORK ORDER.
Do not modify implementation. Compare multiple approaches only when a real
tradeoff exists, and consolidate the decisions I must make.
```

Execution session:

```text
Work in the EXECUTE duty. Read the approved work order and bound baseline.
Implement only work traceable to that order, verify it, and preserve evidence.
If the baseline changes materially, mark authorization STALE_APPROVAL.
```

Independent review session:

```text
Work in the REVIEW duty. Read-only review the named diff, work order, and
evidence. Rank findings P0–P3. If none are found, write No findings within
reviewed scope and state what was not inspected.
```

Expected: these are three sequential duties, not a requirement that every task invoke three agents. Final `USER_ACCEPTED` status still comes from the user.

## Example 6: Explicit High-Risk Authorization

Preferred:

```text
Approve creation of a public v1.2.0 Release in Ray/example at main@abc123.
The audience is all GitHub visitors. This does not authorize production
deployment or additional public messages.
```

Avoid:

```text
Yes
```
