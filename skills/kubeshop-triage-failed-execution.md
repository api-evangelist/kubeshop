---
name: Triage a failed Testkube execution
description: Given a failing test workflow, gather logs, JUnit reports, events and metrics to explain why it failed and whether it is flaky.
api: openapi/kubeshop-testkube-control-plane-openapi-original.yml
generated: '2026-07-19'
method: generated
operations:
  - listTestWorkflowExecutions
  - getTestWorkflowExecution
  - getExecutionLogsV2
  - getExecutionJUnitReports
  - getExecutionEvents
  - getTestWorkflowMetrics
  - rerunTestWorkflowExecution
---

# Triage a failed execution

Use this to turn a red test run into an explanation.

## Steps

1. **Locate the run.** `listTestWorkflowExecutions` (`GET /test-workflow-executions`), filtering
   by `status` and `workflowName`. Sort to the most recent failure.
2. **Read the execution record.** `getTestWorkflowExecution` gives you the status, result and
   step breakdown — start here before pulling any bulk data.
3. **Pull the logs.** `getExecutionLogsV2` (`GET /executions/{id}/logs/v2`) is the current log
   endpoint; `getExecutionLogs` is the older one.
4. **Pull structured results.** `getExecutionJUnitReports`
   (`GET /organizations/{id}/environments/{environmentID}/executions/{executionID}/junit`).
   Testkube processes JUnit, JMeter, k6 and Artillery reports automatically as of v2.10.0, so
   prefer the structured report over scraping log text.
5. **Check cluster-side events.** `getExecutionEvents` distinguishes a genuine test failure from
   an infrastructure problem (scheduling, image pull, OOM kill).
6. **Check whether it is flaky.** `getTestWorkflowMetrics`
   (`GET /test-workflows/{id}/metrics`) gives pass/fail history and resource consumption.
   A test that alternates pass/fail across runs on an unchanged definition is flaky — say so
   rather than reporting a hard failure.
7. **Re-run only when justified.** `rerunTestWorkflowExecution`
   (`POST /test-workflow-executions/{executionID}/rerun`) starts a **new** execution. Do not
   re-run to "check" a failure you have not read the logs for.

## Rules

- Distinguish the four failure classes before reporting: **test assertion failure** (read the
  JUnit report), **infrastructure failure** (`502`, or cluster events), **licensing** (`402`),
  and **expiry** (`410` — the logs or artifacts aged out of storage).
- Errors are RFC 9457 `application/problem+json`; the `detail` field carries the specific cause.
- `429` on AI-assisted endpoints carries `limit`, `used` and `resetsAt` in the body rather than
  in headers. Wait until `resetsAt` — there is no `Retry-After` header.
