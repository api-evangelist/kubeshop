# Kubeshop

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Kubeshop is the company behind Testkube, an open-core, Kubernetes-native test orchestration platform. Testkube runs agents inside Kubernetes clusters under a central control plane, orchestrating tests written for existing frameworks — Cypress, Playwright, k6, JMeter, pytest and others — then aggregating executions, logs, artifacts, JUnit reports, flakiness metrics and cross-environment insights for engineering teams. It is configured declaratively through Kubernetes Custom Resource Definitions (TestWorkflow, Webhook, TestTrigger), installed via Helm, and driven by a first-party CLI. Kubeshop publishes three OpenAPI 3.0.1 documents — an open-source API, a standalone agent API and a commercial control-plane API — plus a gRPC service definition and a hosted Model Context Protocol server exposing 30 tools to AI assistants over OAuth 2.1. The company is backed by Insight Partners.

**Areas:** Company · Testing · Kubernetes · Continuous Integration · Developer Tools · Test Automation · Observability · DevOps · Cloud-Native · Quality Assurance · Open Source · MCP

## Kubeshop on APIs.io

Everything profiled for Kubeshop is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/kubeshop/](https://apis.io/providers/kubeshop/)** — or go straight to one of the APIs or properties below.

### APIs (26)

- [Kubeshop Artifacts API](https://apis.io/apis/kubeshop/kubeshop-artifacts-api/) — Artifact operations
- [Kubeshop Cluster Resources API](https://apis.io/apis/kubeshop/kubeshop-cluster-resources-api/) — The cluster-resources API from Kubeshop — 1 operation(s) for cluster-resources.
- [Kubeshop Executions API](https://apis.io/apis/kubeshop/kubeshop-executions-api/) — The Executions API from Kubeshop — 19 operation(s) for executions.
- [Kubeshop Executor API](https://apis.io/apis/kubeshop/kubeshop-executor-api/) — Executor operations
- [Kubeshop Keymap API](https://apis.io/apis/kubeshop/kubeshop-keymap-api/) — Keymap for fields in a form
- [Kubeshop Labels API](https://apis.io/apis/kubeshop/kubeshop-labels-api/) — Listing all available labels
- [Kubeshop Logs API](https://apis.io/apis/kubeshop/kubeshop-logs-api/) — Log operations
- [Kubeshop Organizations API](https://apis.io/apis/kubeshop/kubeshop-organizations-api/) — The Organizations API from Kubeshop — 104 operation(s) for organizations.
- [Kubeshop Repository API](https://apis.io/apis/kubeshop/kubeshop-repository-api/) — The repository API from Kubeshop — 1 operation(s) for repository.
- [Kubeshop Secrets API](https://apis.io/apis/kubeshop/kubeshop-secrets-api/) — The secrets API from Kubeshop — 2 operation(s) for secrets.
- [Kubeshop Status Pages API](https://apis.io/apis/kubeshop/kubeshop-status-pages-api/) — The Status Pages API from Kubeshop — 2 operation(s) for status pages.
- [Kubeshop Tags API](https://apis.io/apis/kubeshop/kubeshop-tags-api/) — The tags API from Kubeshop — 1 operation(s) for tags.
- [Kubeshop Template API](https://apis.io/apis/kubeshop/kubeshop-template-api/) — The template API from Kubeshop — 2 operation(s) for template.
- [Kubeshop Templates API](https://apis.io/apis/kubeshop/kubeshop-templates-api/) — The templates API from Kubeshop — 1 operation(s) for templates.
- [Kubeshop Test Sources API](https://apis.io/apis/kubeshop/kubeshop-test-sources-api/) — The test-sources API from Kubeshop — 2 operation(s) for test-sources.
- [Kubeshop Test Suites API](https://apis.io/apis/kubeshop/kubeshop-test-suites-api/) — Test suites orchestration operations
- [Kubeshop Test Triggers API](https://apis.io/apis/kubeshop/kubeshop-test-triggers-api/) — Test Triggers CRUD operations
- [Kubeshop Test Workflows API](https://apis.io/apis/kubeshop/kubeshop-test-workflows-api/) — The Test Workflows API from Kubeshop — 22 operation(s) for test workflows.
- [Kubeshop Tests API](https://apis.io/apis/kubeshop/kubeshop-tests-api/) — Tests operations
- [Kubeshop Users API](https://apis.io/apis/kubeshop/kubeshop-users-api/) — The Users API from Kubeshop — 2 operation(s) for users.
- [Kubeshop Webhook API](https://apis.io/apis/kubeshop/kubeshop-webhook-api/) — Webhook operations
- [Kubeshop Webhook Template API](https://apis.io/apis/kubeshop/kubeshop-webhook-template-api/) — The webhook-template API from Kubeshop — 2 operation(s) for webhook-template.
- [Kubeshop Config API](https://apis.io/apis/kubeshop/kubeshop-config-api/) — The Config API from Kubeshop — 1 operation(s) for config.
- [Kubeshop Debug API](https://apis.io/apis/kubeshop/kubeshop-debug-api/) — The Debug API from Kubeshop — 1 operation(s) for debug.
- [Kubeshop Export API](https://apis.io/apis/kubeshop/kubeshop-export-api/) — The Export API from Kubeshop — 1 operation(s) for export.
- [Kubeshop Pro API](https://apis.io/apis/kubeshop/kubeshop-pro-api/) — The pro API from Kubeshop — 18 operation(s) for pro.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Kubeshop Testkube Webhooks](https://apis.io/asyncapis/kubeshop/kubeshop-testkube-webhooks/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [testkube](https://apis.io/servers/kubeshop/testkube/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Kubeshop Agentic Access](https://apis.io/agentic-access/kubeshop/kubeshop-agentic-access/)

#### Collections (30)

Postman and Open Collection request collections.

- [Testkube Standalone Agent api API](https://apis.io/collections/kubeshop/open-kubeshop-api-api/)
- [Testkube Standalone Agent api artifacts API](https://apis.io/collections/kubeshop/open-kubeshop-artifacts-api/)
- [Testkube Standalone Agent api cluster-resources API](https://apis.io/collections/kubeshop/open-kubeshop-cluster-resources-api/)
- [Testkube Standalone Agent api Executions API](https://apis.io/collections/kubeshop/open-kubeshop-executions-api/)
- [Testkube Standalone Agent api executor API](https://apis.io/collections/kubeshop/open-kubeshop-executor-api/)
- [Testkube Standalone Agent api keymap API](https://apis.io/collections/kubeshop/open-kubeshop-keymap-api/)
- [Testkube Standalone Agent api labels API](https://apis.io/collections/kubeshop/open-kubeshop-labels-api/)
- [Testkube Standalone Agent api logs API](https://apis.io/collections/kubeshop/open-kubeshop-logs-api/)
- [Testkube Standalone Agent api Organizations API](https://apis.io/collections/kubeshop/open-kubeshop-organizations-api/)
- [Testkube Standalone Agent api pro API](https://apis.io/collections/kubeshop/open-kubeshop-pro-api/)
- [Testkube Standalone Agent api repository API](https://apis.io/collections/kubeshop/open-kubeshop-repository-api/)
- [Testkube Standalone Agent api secrets API](https://apis.io/collections/kubeshop/open-kubeshop-secrets-api/)
- [Testkube Standalone Agent api Status Pages API](https://apis.io/collections/kubeshop/open-kubeshop-status-pages-api/)
- [Testkube Standalone Agent api tags API](https://apis.io/collections/kubeshop/open-kubeshop-tags-api/)
- [Testkube Standalone Agent api template API](https://apis.io/collections/kubeshop/open-kubeshop-template-api/)
- [Testkube Standalone Agent api templates API](https://apis.io/collections/kubeshop/open-kubeshop-templates-api/)
- [Testkube Standalone Agent api test-sources API](https://apis.io/collections/kubeshop/open-kubeshop-test-sources-api/)
- [Testkube Standalone Agent api test-suites API](https://apis.io/collections/kubeshop/open-kubeshop-test-suites-api/)
- [Testkube Standalone Agent api test-triggers API](https://apis.io/collections/kubeshop/open-kubeshop-test-triggers-api/)
- [Testkube Standalone Agent api Test Workflow Executions API](https://apis.io/collections/kubeshop/open-kubeshop-test-workflow-executions-api/)
- [Testkube Standalone Agent api Test Workflow Templates API](https://apis.io/collections/kubeshop/open-kubeshop-test-workflow-templates-api/)
- [Testkube Standalone Agent api Test Workflow With Executions API](https://apis.io/collections/kubeshop/open-kubeshop-test-workflow-with-executions-api/)
- [Testkube Standalone Agent api Test Workflows API](https://apis.io/collections/kubeshop/open-kubeshop-test-workflows-api/)
- [Testkube Standalone Agent api tests API](https://apis.io/collections/kubeshop/open-kubeshop-tests-api/)
- [Testkube Standalone Agent api Triggers API](https://apis.io/collections/kubeshop/open-kubeshop-triggers-api/)
- …and 5 more published on APIs.io

#### Overlays (3)

OpenAPI overlays, including conversational phrasing for each operation.

- [Kubeshop Testkube Agent Overlay](https://apis.io/overlays/kubeshop/kubeshop-testkube-agent-overlay/)
- [Kubeshop Testkube Control Plane Overlay](https://apis.io/overlays/kubeshop/kubeshop-testkube-control-plane-overlay/)
- [Kubeshop Testkube Overlay](https://apis.io/overlays/kubeshop/kubeshop-testkube-overlay/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Kubeshop Authentication](https://apis.io/security/kubeshop/kubeshop-authentication/)
- [Kubeshop Domain Security](https://apis.io/security/kubeshop/kubeshop-domain-security/)

#### OAuth scopes (1)

The permissions the API asks for.

- [Kubeshop Scopes](https://apis.io/scopes/kubeshop/kubeshop-scopes/)

#### Rate limits (1)

Published request limits.

- [Kubeshop Rate Limits](https://apis.io/rate-limits/kubeshop/kubeshop-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://testkube.io/)
- [Documentation](https://docs.testkube.io/)
- [Getting started](https://docs.testkube.io/articles/tutorial/quickstart)
- [API reference](https://docs.testkube.io/openapi/overview)
- [Pricing](https://testkube.io/pricing)
- [Sign up](https://testkube.io/get-started)
- [Support](https://testkube.io/contact)
- [Changelog](https://docs.testkube.io/changelog)
- [Blog](https://testkube.io/blog)
- [Compliance](https://testkube.io/pricing)
- [Terms of service](https://testkube.io/terms-and-conditions/202602)
- [Privacy policy](https://testkube.io/privacy-policy)
- [GitHub](https://github.com/kubeshop)

## API Evangelist rating

**Kin Score 52.9** — developing · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 73.3 |
| Contract quality | 54.3 |
| Contract governance | 4.5 |
| Operational transparency | 26.3 |
| Developer ergonomics | 73.2 |
| Access clarity | 52.6 |

**Agent readiness 45.1** — agent-ready (gated down from agent-native)

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | — |
| MCP Server | templated |
| Auth Clarity | served (partial credit) |
| Idempotency | — |
| Error Semantics | derived (partial credit) |
| OpenAPI Examples | partial |
| Rate Limit Signal | derived (partial credit) |
| Event Surface Described | yes |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | served (partial credit) |
| Protected Resource Metadata | verified |
| Dynamic Client Registration | yes |
| Agentic Commerce | — |
| Pagination Ratio | — |
| Operation Distinctiveness | — |

**Regulatory alignment 39.2** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/kubeshop/](https://apis.io/providers/kubeshop/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Kubeshop: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/kubeshop/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
