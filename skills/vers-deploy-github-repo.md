---
name: Deploy a GitHub repo to a fresh VM
description: >-
  Clone, install, build, and run a GitHub repository on a new Vers VM, then
  make it reachable on a custom domain. Mirrors the Vers deploy flow.
api: openapi/vers-openapi-original.json
base_url: https://api.vers.sh
auth: bearer API key (Authorization: Bearer $VERS_API_KEY)
operations: [deploy_handler, list_vms, get_vm_metadata, vm_status, create_domain]
---

# Deploy a GitHub repo to a fresh VM

Turn a GitHub repository into a running service on Vers in one call, then
route a domain to it.

## Preconditions
- `VERS_API_KEY` is set; requests send `Authorization: Bearer $VERS_API_KEY`.
- Base URL `https://api.vers.sh`, paths under `/api/v1`.

## Steps
1. **Deploy** — `deploy_handler` (`POST /api/v1/deploy`) with the GitHub repo
   and deploy settings. Vers clones, installs, builds, and runs it on a new VM.
2. **Confirm the VM** — `list_vms` (`GET /api/v1/vm`) and `get_vm_metadata`
   (`GET /api/v1/vm/{vm_id}/metadata`) for IP, lineage, and SSH info.
3. **Wait for readiness** — poll `vm_status` (`GET /api/v1/vm/{vm_id}/status`)
   until the VM is running.
4. **Attach a domain** — `create_domain` (`POST /api/v1/domains`) to route a
   custom domain to the deployment (see docs.vers.sh/networking for routable
   ports and TLS).

## Conventions
- **Idempotency**: send a per-request idempotency-key override on `deploy_handler`
  and `create_domain` so retries don't create duplicates.
- **Errors**: `{ error, success:false }`; 409 = conflicting name, 413 = payload
  too large. See errors/vers-problem-types.yml.
- **Env vars**: use `set_env_vars` (`PUT /api/v1/env_vars`) to inject config
  into newly-created VMs before deploy.
