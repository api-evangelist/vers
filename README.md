# Vers

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

Vers is "git for running compute" — a branchable microVM platform from HD Research (hdresearch) that lets you fork a live virtual machine (memory, processes, sockets and all) in roughly 258 microseconds, commit its state as an immutable content-addressable snapshot, and restore or branch that snapshot anywhere. Built for AI agent swarms, parallel scenario and database-state testing, CI preview environments, and time-travel debugging, Vers exposes a 63-operation Orchestrator Control Plane API (OpenAPI 3.1) behind a bearer API key, plus a git-style CLI, official SDKs for nine languages, and two Model Context Protocol servers so coding agents can drive compute directly.

**Areas:** Company · Compute · Virtualization · MicroVM · Orchestration · Infrastructure · AI Agents · Developer Tools · Sandbox · CI/CD

## Vers on APIs.io

Everything profiled for Vers is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/vers/](https://apis.io/providers/vers/)** — or go straight to one of the APIs or properties below.

### APIs (12)

- [Vers Commit Tags API](https://apis.io/apis/vers/vers-commit-tags-api/) — The commit_tags API from Vers — 2 operation(s) for commit_tags.
- [Vers Commits API](https://apis.io/apis/vers/vers-commits-api/) — The commits API from Vers — 4 operation(s) for commits.
- [Vers Deploy API](https://apis.io/apis/vers/vers-deploy-api/) — The deploy API from Vers — 1 operation(s) for deploy.
- [Vers Domains API](https://apis.io/apis/vers/vers-domains-api/) — The domains API from Vers — 2 operation(s) for domains.
- [Vers Env Vars API](https://apis.io/apis/vers/vers-env-vars-api/) — The env_vars API from Vers — 2 operation(s) for env_vars.
- [Vers Images API](https://apis.io/apis/vers/vers-images-api/) — The images API from Vers — 5 operation(s) for images.
- [Vers Keys API](https://apis.io/apis/vers/vers-keys-api/) — The keys API from Vers — 1 operation(s) for keys.
- [Vers Public Repositories API](https://apis.io/apis/vers/vers-public-repositories-api/) — The public_repositories API from Vers — 4 operation(s) for public_repositories.
- [Vers Repositories API](https://apis.io/apis/vers/vers-repositories-api/) — The repositories API from Vers — 6 operation(s) for repositories.
- [Vers System API](https://apis.io/apis/vers/vers-system-api/) — The System API from Vers — 1 operation(s) for system.
- [Vers Vm API](https://apis.io/apis/vers/vers-vm-api/) — The vm API from Vers — 20 operation(s) for vm.
- [Vers Vms API](https://apis.io/apis/vers/vers-vms-api/) — The vms API from Vers — 2 operation(s) for vms.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [vers-mcp.yml](https://apis.io/servers/vers/vers-mcp-yml/)

#### Collections (12)

Postman and Open Collection request collections.

- [Orchestrator Control Plane commit_tags API](https://apis.io/collections/vers/open-vers-commit-tags-api/)
- [Orchestrator Control Plane commit_tags commits API](https://apis.io/collections/vers/open-vers-commits-api/)
- [Orchestrator Control Plane commit_tags deploy API](https://apis.io/collections/vers/open-vers-deploy-api/)
- [Orchestrator Control Plane commit_tags domains API](https://apis.io/collections/vers/open-vers-domains-api/)
- [Orchestrator Control Plane commit_tags env_vars API](https://apis.io/collections/vers/open-vers-env-vars-api/)
- [Orchestrator Control Plane commit_tags images API](https://apis.io/collections/vers/open-vers-images-api/)
- [Orchestrator Control Plane commit_tags keys API](https://apis.io/collections/vers/open-vers-keys-api/)
- [Orchestrator Control Plane commit_tags public_repositories API](https://apis.io/collections/vers/open-vers-public-repositories-api/)
- [Orchestrator Control Plane commit_tags repositories API](https://apis.io/collections/vers/open-vers-repositories-api/)
- [Orchestrator Control Plane commit_tags System API](https://apis.io/collections/vers/open-vers-system-api/)
- [Orchestrator Control Plane commit_tags vm API](https://apis.io/collections/vers/open-vers-vm-api/)
- [Orchestrator Control Plane commit_tags vms API](https://apis.io/collections/vers/open-vers-vms-api/)

#### Overlays (1)

OpenAPI overlays, including conversational phrasing for each operation.

- [Vers Orchestrator Overlay](https://apis.io/overlays/vers/vers-orchestrator-overlay/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Vers Authentication](https://apis.io/security/vers/vers-authentication/)
- [Vers Domain Security](https://apis.io/security/vers/vers-domain-security/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://vers.sh/)
- [Documentation](https://docs.vers.sh/overview)
- [Getting started](https://docs.vers.sh/quickstart)
- [API reference](https://docs.vers.sh/api-reference/introduction)
- [Sign up](https://vers.sh/auth/signin)
- [Support](https://discord.gg/MFvKgPe3sT)
- [Blog](https://vers.sh/blog)
- [Terms of service](https://vers.sh/terms-of-service)
- [Privacy policy](https://vers.sh/privacy-policy)
- [GitHub](https://github.com/hdresearch)

## API Evangelist rating

**Kin Score 39.6** — developing · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 75.0 |
| Contract quality | 41.8 |
| Contract governance | 4.5 |
| Operational transparency | 2.6 |
| Developer ergonomics | 66.1 |
| Access clarity | 34.2 |

**Agent readiness 29.9** — agent-ready

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | — |
| Reversibility Documented | documented (partial credit) |
| MCP Server | documented (partial credit) |
| Auth Clarity | bearer (partial credit) |
| Idempotency | documented (partial credit) |
| Error Semantics | verified |
| OpenAPI Examples | — |
| Rate Limit Signal | — |
| Event Surface Described | — |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | — |
| Operation Distinctiveness | mostly (partial credit) |

**Regulatory alignment 24.5** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/vers/](https://apis.io/providers/vers/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Vers: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/vers/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
