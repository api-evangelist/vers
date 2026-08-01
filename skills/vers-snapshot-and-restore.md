---
name: Snapshot and restore VM state
description: >-
  Commit a live VM to an immutable, content-addressable snapshot and restore it
  to a fresh VM later — the basis for time-travel debugging and reproducible
  environments. Mirrors the Vers commits/restore model.
api: openapi/vers-openapi-original.json
base_url: https://api.vers.sh
auth: bearer API key (Authorization: Bearer $VERS_API_KEY)
operations: [create_new_root_vm, exec_vm, commit_vm, restore_from_commit, list_parent_commits, delete_vm]
---

# Snapshot and restore VM state

A Vers commit freezes a VM's full state (memory + disk) as an immutable,
content-addressable snapshot. Restoring re-creates a running VM from that
commit anywhere — the same idea git applies to code, applied to running compute.

## Preconditions
- `VERS_API_KEY` is set; requests send `Authorization: Bearer $VERS_API_KEY`.
- Base URL `https://api.vers.sh`, paths under `/api/v1`.

## Steps
1. **Boot a VM** — `create_new_root_vm` (`POST /api/v1/vm/new_root`).
2. **Do work / reach the interesting state** — `exec_vm`
   (`POST /api/v1/vm/{vm_id}/exec`).
3. **Snapshot** — `commit_vm` (`POST /api/v1/vm/{vm_id}/commit`). Returns a
   `commit_id`. Commits are immutable; tag them if you want a mutable name.
4. **Inspect lineage** — `list_parent_commits`
   (`GET /api/v1/vm/commits/{commit_id}/parents`) to walk the ancestry tree.
5. **Restore later** — `restore_from_commit` (`POST /api/v1/vm/from_commit`)
   to boot a fresh VM at exactly that captured state (time-travel debugging).
6. **Tear down** — `delete_vm` (`DELETE /api/v1/vm/{vm_id}`).

## Conventions
- **Idempotency**: use the per-request idempotency-key override on `commit_vm`
  and `restore_from_commit` so a retry reuses the same result.
- **Errors**: `{ error, success:false }` JSON envelope; see
  errors/vers-problem-types.yml. 409 signals a state conflict.
