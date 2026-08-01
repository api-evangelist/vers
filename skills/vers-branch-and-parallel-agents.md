---
name: Branch a VM into parallel agent workers
description: >-
  Boot a golden VM, install/prepare it, then fork it into N isolated child VMs
  so multiple coding agents can work in parallel against identical live state
  (memory + filesystem inherited). Mirrors the Vers "agent swarms" tutorial.
api: openapi/vers-openapi-original.json
base_url: https://api.vers.sh
auth: bearer API key (Authorization: Bearer $VERS_API_KEY)
operations: [create_new_root_vm, exec_vm, commit_vm, branch_by_vm, branch_vm, delete_vm]
---

# Branch a VM into parallel agent workers

Use Vers to fork one prepared VM into many, so agents explore divergent paths
without rebuilding environment state each time. A branch copies the parent's
memory and filesystem in ~258µs; the parent auto-pauses on branch.

## Preconditions
- `VERS_API_KEY` is set. Every request sends `Authorization: Bearer $VERS_API_KEY`.
- Base URL is `https://api.vers.sh`, all paths under `/api/v1`.

## Steps
1. **Create the golden root VM** — `create_new_root_vm`
   (`POST /api/v1/vm/new_root`). Provide the boot image / VM config.
2. **Prepare it** — `exec_vm` (`POST /api/v1/vm/{vm_id}/exec`) to install
   dependencies, clone the repo, and warm caches. This is the state every
   worker will inherit.
3. **(Optional) freeze a reusable snapshot** — `commit_vm`
   (`POST /api/v1/vm/{vm_id}/commit`) to get an immutable, content-addressable
   commit you can re-branch later.
4. **Fan out workers** — for each parallel agent, `branch_by_vm`
   (`POST /api/v1/vm/branch/by_vm/{vm_id}`) from the live golden VM, or
   `branch_vm` (`POST /api/v1/vm/{vm_or_commit_id}/branch`). Each child is an
   isolated copy of the running state.
5. **Drive each worker** — `exec_vm` (or `exec_vm_stream` for streaming logs)
   per child VM to run the agent's commands.
6. **Clean up** — `delete_vm` (`DELETE /api/v1/vm/{vm_id}`) each worker when
   done (the CLI `kill` is an alias for delete).

## Conventions
- **Idempotency**: pass a per-request idempotency-key override (SDK request
  option) on create/branch/commit calls so retries don't double-provision.
- **Retries**: honor `Retry-After`; SDKs back off exponentially.
- **Errors**: responses are `{ "error": "...", "success": false }` with HTTP
  400/401/403/404/409/413/500/501 (see errors/vers-problem-types.yml).
