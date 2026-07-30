---
name: Wire Testkube webhook notifications
description: Subscribe an external endpoint to Testkube test workflow lifecycle and state-change events, with a custom payload template.
api: openapi/kubeshop-testkube-agent-openapi-original.yml
generated: '2026-07-19'
method: generated
operations:
  - listWebhooks
  - createWebhook
  - getWebhook
  - updateWebhook
  - deleteWebhook
  - listWebhookTemplates
  - createWebhookTemplate
---

# Wire webhook notifications

Use this to push Testkube test results into Slack, an incident tool, or any HTTP endpoint.

## Steps

1. **Check what already exists.** `listWebhooks` (`GET /webhooks`) — avoid creating a duplicate
   subscription for an endpoint that is already wired.
2. **Pick the events.** Testkube publishes two families:
   - *lifecycle*: `queue-testworkflow`, `start-testworkflow`, `end-testworkflow-success`,
     `end-testworkflow-failed`, `end-testworkflow-aborted`, `end-testworkflow-canceled`,
     `end-testworkflow-not-passed`
   - *state change*: `become-testworkflow-up`, `become-testworkflow-down`,
     `become-testworkflow-failed`, `become-testworkflow-aborted`

   For alerting, prefer the `become-*` family — it fires only on transitions, so it will not
   page on every run of an already-failing test.
3. **Create it.** `createWebhook` (`POST /webhooks`). The body mirrors the
   `executor.testkube.io/v1` `Webhook` CRD: `uri`, `events`, optional `selector`,
   `payloadTemplate`, `headers`, `disabled`.
4. **Scope it.** Use `selector` (a Kubernetes label selector) so the webhook only fires for the
   workflows you care about rather than everything in the environment.
5. **Authenticate to the receiver.** Testkube does **not** sign webhook payloads. Put a shared
   secret in `headers` — documented examples use `Authorization`, `X-Token` or `x-api-key`.
   The receiver must verify it; do not treat an unauthenticated Testkube webhook as trusted.
6. **Shape the payload.** `payloadTemplate` is a Go template. Available variables include
   `{{ .Id }}`, `{{ .Type_ }}`, `{{ .ClusterName }}`,
   `{{ .TestWorkflowExecution.TestName }}`, `{{ .TestWorkflowExecution.Number }}`,
   `{{ .TestWorkflowExecution.ExecutionResult.Status }}`, plus
   `{{ index .Envs "VAR" }}` and `{{ index .Config "key" }}`.
7. **Reuse shapes.** For more than one destination, define a `createWebhookTemplate` and
   reference it rather than copying the template body.
8. **Disable rather than delete** while debugging — set `disabled: true` via `updateWebhook`.

## Default payload

```json
{
  "id": "...",
  "type": "end-testworkflow-failed",
  "resource": "testworkflowexecution",
  "resourceId": "...",
  "testWorkflowExecution": { },
  "clusterName": "..."
}
```

## Rules

- Webhooks can equally be managed as Kubernetes manifests (`executor.testkube.io/v1`, kind
  `Webhook`). If the environment is GitOps-managed, write the CRD instead of calling the API, or
  the next reconcile will revert your change.
- Testkube publishes **no AsyncAPI document** — this webhook catalog is the event contract.
- Alternative event surfaces exist: Kubernetes Events and CDEvents. See
  `asyncapi/kubeshop-testkube-webhooks.yml`.
