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
