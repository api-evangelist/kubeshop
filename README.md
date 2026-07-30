# Kubeshop

Kubeshop is the company behind **Testkube**, an open-core, Kubernetes-native test orchestration
platform. Testkube runs agents inside Kubernetes clusters under a central control plane,
orchestrating tests written for existing frameworks (Cypress, Playwright, k6, JMeter, pytest and
others), then aggregating executions, logs, artifacts, JUnit reports and flakiness metrics across
environments and CI/CD systems.

Backed by: insight-partners — https://testkube.io/

## APIs

| API | Paths | Notes |
|---|---|---|
| Testkube Control Plane API | 108 | Commercial control plane; bearer auth; proxies to connected agents |
| Testkube Standalone Agent API | 34 | Agent running in standalone mode |
| Testkube API (open source) | 74 | MIT-licensed surface from `kubeshop/testkube` |

Base URL: `https://api.testkube.io` · Docs: https://docs.testkube.io ·
OpenAPI index: https://docs.testkube.io/openapi/overview

## Highlights

- **Hosted MCP server** at `api.testkube.io/organizations/{org}/environments/{env}/mcp` with
  **30 documented tools**, OAuth 2.1 (PKCE S256, dynamic client registration, scope `mcp:full`),
  RFC 8414 + RFC 9728 discovery metadata. Also runnable locally via `testkube mcp serve`.
- **RFC 9457 problem+json errors** across 619 responses, with a real problem-type namespace
  (`https://kubeshop.io/testkube/problems/`).
- **RFC 8288 pagination** via `Link` + `Total-Count` headers.
- **gRPC**: a 1,045-line `TestKubeCloudAPI` service definition with streaming RPCs.
- **11 documented webhook events** configured through the `executor.testkube.io/v1` Webhook CRD.
- **HTTP 402** is used as an explicit plan-gating signal on 82 operations.

## Notable absences (verified, not assumed)

- No `Idempotency-Key` contract — execution-creating operations are **not** idempotent.
- No AsyncAPI document (webhooks are documented instead).
- No `/.well-known/security.txt`, no SECURITY.md, no bug bounty or disclosure page.
- No status page (`testkube.statuspage.io` is an unclaimed redirect).
- No written deprecation policy and no RFC 8594 Sunset/Deprecation header support.
- No per-language client SDKs on npm, PyPI, RubyGems, Maven Central, NuGet or crates.io —
  distribution is a Go client package, a Homebrew CLI, Helm charts and container images.

## Artifacts

`openapi/` `overlays/` `grpc/` `mcp/` `skills/` `asyncapi/` `conventions/` `errors/`
`authentication/` `scopes/` `lifecycle/` `changelog/` `cli/` `packages/` `conformance/`
`data-model/` `rate-limits/` `well-known/` `llms/` `security/` `agentic-access/`
