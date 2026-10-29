# X402 AI 自助门店

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

X402 AI 自助门店 ("X402 AI self-service store") is a single-operator agent-commerce storefront at easyfence.cn that sells only to other AI agents: a buyer agent reads the A2A agent card, lists seven generated services priced 0.30-2.00 USD per call in /api/catalog, optionally negotiates with the store clerk over A2A JSON-RPC at /a2a, and orders at /api/deliver, which answers HTTP 402 with an x402 payment requirement (USDC on Base or BSC, mainnet) until an EIP-3009 authorization is presented, then returns the deliverable. The store also acts as an ERC-8004 style identity issuer with a public trust registry and runs its own x402 facilitator for the BSC route. A FastAPI-generated OpenAPI 3.1.0 is served at /openapi.json; no SDKs, terms, support channel or operator identity are published, and payments are irreversible.

**Areas:** Agentic Commerce · AI Agents · A2A · x402 · Payments · Stablecoins · Agent Identity · Content Generation · Web3

## X402 AI 自助门店 on APIs.io

Everything profiled for X402 AI 自助门店 is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/easyfence-cn/](https://apis.io/providers/easyfence-cn/)** — or go straight to one of the APIs or properties below.

### APIs (11)

- [X402 AI 自助门店 A2A Agent](https://apis.io/apis/easyfence-cn/easyfence-cn-a2a-agent/) — The store's agent-to-agent surface: an anonymous A2A 0.3 JSON-RPC endpoint the agent card points at, where a buyer agent negotiates with the store clerk…
- [X402 AI 自助门店 x402 Facilitator API](https://apis.io/apis/easyfence-cn/easyfence-cn-x402-facilitator-api/) — A self-hosted x402 facilitator role on the same host - POST /facilitator/verify and POST /facilitator/settle with free-form JSON bodies, plus…
- [X402 AI 自助门店 A2a API](https://apis.io/apis/easyfence-cn/easyfence-cn-a2a-api/) — The A2a API from X402 AI 自助门店 — 1 operation(s) for a2a.
- [X402 AI 自助门店 Admin API](https://apis.io/apis/easyfence-cn/easyfence-cn-admin-api/) — The Admin API from X402 AI 自助门店 — 4 operation(s) for admin.
- [X402 AI 自助门店 Catalog API](https://apis.io/apis/easyfence-cn/easyfence-cn-catalog-api/) — The Catalog API from X402 AI 自助门店 — 1 operation(s) for catalog.
- [X402 AI 自助门店 Deliver API](https://apis.io/apis/easyfence-cn/easyfence-cn-deliver-api/) — The Deliver API from X402 AI 自助门店 — 1 operation(s) for deliver.
- [X402 AI 自助门店 Healthz API](https://apis.io/apis/easyfence-cn/easyfence-cn-healthz-api/) — The Healthz API from X402 AI 自助门店 — 1 operation(s) for healthz.
- [X402 AI 自助门店 Identity API](https://apis.io/apis/easyfence-cn/easyfence-cn-identity-api/) — The Identity API from X402 AI 自助门店 — 2 operation(s) for identity.
- [X402 AI 自助门店 Registry API](https://apis.io/apis/easyfence-cn/easyfence-cn-registry-api/) — The Registry API from X402 AI 自助门店 — 1 operation(s) for registry.
- [X402 AI 自助门店 .well Known API](https://apis.io/apis/easyfence-cn/easyfence-cn-well-known-api/) — The .well Known API from X402 AI 自助门店 — 1 operation(s) for .well known.
- [X402 AI 自助门店 X402 AI 自助门店 API](https://apis.io/apis/easyfence-cn/easyfence-cn-x402-ai-api/) — The X402 AI 自助门店 API from X402 AI 自助门店 — 1 operation(s) for x402 ai 自助门店.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [easyfence-cn-mcp.yml](https://apis.io/servers/easyfence-cn/easyfence-cn-mcp-yml/)

#### Overlays (1)

OpenAPI overlays, including conversational phrasing for each operation.

- [Easyfence Cn Store Api Overlay](https://apis.io/overlays/easyfence-cn/easyfence-cn-store-api-overlay/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Easyfence Cn Authentication](https://apis.io/security/easyfence-cn/easyfence-cn-authentication/)
- [Easyfence Cn Domain Security](https://apis.io/security/easyfence-cn/easyfence-cn-domain-security/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Easyfence Cn Plans Pricing](https://apis.io/plans/easyfence-cn/easyfence-cn-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Easyfence Cn Rate Limits](https://apis.io/rate-limits/easyfence-cn/easyfence-cn-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.easyfence.cn/)
- [Documentation](https://www.easyfence.cn/a2a)
- [API reference](https://www.easyfence.cn/docs)
- [Pricing](https://www.easyfence.cn/#services)

## API Evangelist rating

**Kin Score 29.3** — thin · rubric 0.24.0 · scored 2026-10-17

| Facet | Score |
|---|---|
| Discoverability | 62.5 |
| Contract quality | 35.0 |
| Contract governance | 18.2 |
| Operational transparency | 0.0 |
| Developer ergonomics | 30.4 |
| Access clarity | 36.8 |

**Agent readiness 30.4** — agent-ready

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | — |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | verified |
| OpenAPI Examples | — |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | — |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | conformant |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |

**Regulatory alignment 15.2** — Payments

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/easyfence-cn/](https://apis.io/providers/easyfence-cn/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for X402 AI 自助门店: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/easyfence-cn/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
