---
name: Run a Testkube test workflow and collect the result
description: Execute a Testkube TestWorkflow against a connected environment, wait for it to finish, then pull logs and artifacts.
api: openapi/kubeshop-testkube-agent-openapi-original.yml
generated: '2026-07-19'
method: generated
operations:
  - listTestWorkflows
  - getTestWorkflow
  - executeTestWorkflow
  - getTestWorkflowExecution
  - getTestWorkflowExecutionArtifacts
  - downloadTestWorkflowArtifact
  - abortTestWorkflowExecution
---

# Run a test workflow and collect the result

Use this when you need to trigger a Testkube test run and report back what happened.

## Before you start

- Authenticate with a bearer token: `Authorization: Bearer <API_TOKEN>`. Tokens come from
  Organization Settings → API Tokens in the Testkube dashboard.
- Testkube is Kubernetes-native. A TestWorkflow is identified by its **name** within an
  environment, not by an opaque id.
- If a hosted MCP server is available, prefer it — `run_workflow`, `wait_for_executions`,
  `fetch_execution_logs` and `list_artifacts` cover this whole flow. See `mcp/kubeshop-mcp.yml`.

## Steps

1. **Find the workflow.** Call `listTestWorkflows` (`GET /test-workflows`). Narrow with the
   `selector`, `label` or `textSearch` query parameters — these use Kubernetes label-selector
   semantics. A malformed selector is the most common cause of `400`.
2. **Confirm the definition.** Call `getTestWorkflow` (`GET /test-workflows/{id}`) so you report
   against the definition you actually ran.
3. **Execute it.** Call `executeTestWorkflow` (`POST /test-workflows/{id}/executions`).
   **This is not idempotent.** Testkube publishes no `Idempotency-Key` contract, so every call
   starts a new execution. Never blindly retry on a timeout — reconcile with
   `listTestWorkflowExecutionsByTestWorkflow` first.
4. **Poll for completion.** Call `getTestWorkflowExecution`
   (`GET /test-workflow-executions/{executionID}`) until the status is terminal. Back off
   between polls.
5. **Collect artifacts.** Call `getTestWorkflowExecutionArtifacts`, then
   `downloadTestWorkflowArtifact` per file, or `downloadTestWorkflowArtifactArchive` for all of
   them. Artifact downloads answer with a `Location` redirect to a presigned URL.
6. **Abort if asked.** `abortTestWorkflowExecution`
   (`POST /test-workflow-executions/{executionID}/abort`).

## Rules

- **Errors are RFC 9457** `application/problem+json` with `type`, `title`, `status`, `detail`,
  `instance`, and sometimes `errorCode`. Read `detail`, do not guess from the status alone.
- **`402` means licensing, not failure.** 82 operations are gated behind a Pro subscription and
  answer `402 missing Pro subscription for a commercial feature`. Report it as a plan limitation
  and stop; retrying will never succeed.
- **`502` is the most common failure and is retryable.** It means the API could not reach the
  backing Kubernetes cluster (210 declared occurrences across the specs).
- **`410` on artifacts or logs means expired**, not missing — artifacts are retention-bound.
- Paginate with `pageSize` plus the `Link` header (RFC 8288, `rel="next"`); `Total-Count` carries
  the unpaginated total.
