# Write Safety and Recovery

## Environment

The only permitted sandbox is `aepenablementfy21`. Call `ajo_get_capabilities`, verify the applicable write gate, and state the sandbox before proposing a mutation. Stop on any mismatch.

## Approval

Plan or draft approval is not mutation approval. Obtain fresh human approval for every exact payload. Before approval show the operation, resource type/name/ID, normalized payload or diff, references, lifecycle effect, risks, and exact confirmation phrase. A skill handoff invalidates prior mutation approval.

## POC Draft Content Exception

When the user explicitly requests `poc-draft-write`, draft Content Templates and draft HTML expression fragments may contain the placeholders allowed by `campaign-facts-contract.md`. The exact payload, placeholder manifest, assumptions, and `POC DRAFT - NOT FOR SEND` warning must be shown before the normal exact approval. This exception permits only create/update of draft content resources. It never permits publication, item approval, policy binding, message application, proofing, activation, or sending while placeholders or POC-only assumptions remain.

## Reuse, ETags, and Verification

Never reuse a resource by name alone. Compare IDs, lifecycle, normalized content/configuration, references, and differences. Immediately before update, publication, attachment, lifecycle change, archive, or delete, retrieve the resource and copy its ETag exactly. Never retry an ETag mismatch automatically. Re-read or relist after each mutation.

## Unknown Outcomes

A timeout does not prove failure. Mark an ambiguous operation `outcome-unknown`; do not repeat a create, publication, policy creation, or other non-idempotent operation until exact reads or AJO UI reconcile it. Poll asynchronous publication with bounded intervals rather than publishing twice.

Stop when facts or IDs are missing, reuse is ambiguous, write gates are disabled, an ETag changes, campaign scope is not DRAFT, an upstream result differs, or an outcome remains unknown.
