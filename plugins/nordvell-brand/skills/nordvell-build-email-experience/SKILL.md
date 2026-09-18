---
name: nordvell-build-email-experience
description: Coordinate a complete NORDVELL AJO email and Decisioning offer build from approved facts through fragments, items, strategy, fallback, placement, policy binding, and Content Template. Use when the user asks Coworker to build the complete email experience. Do not use for campaign or Journey creation, activation, proofing, or one isolated content edit.
---

# Build a NORDVELL Email Experience

Follow all references in this plugin, especially `../../references/write-safety-and-recovery.md` and `../../references/operation-receipt.md`. The sandbox is fixed to `aepenablementfy21`.

## Required Outcome

Turn a concise request into a reviewed creative and technical package without forcing the user to specify every AJO resource. Ask focused questions only when missing facts block truthful content, eligibility, a destination, required footer/legal content, or a safe operation.

## Preflight

1. Call `ajo_get_capabilities`; record available reads and write gates. A disabled write gate does not prevent drafting.
2. Invoke `nordvell-brand-guidelines` and normalize campaign facts and evidence.
3. If an audience is supplied, list and exact-get its system record. Audience definition or publication does not prove nonzero qualification or eligibility for a specific profile.
4. Invoke `nordvell-author-offer-content` for at least one targeted package and one universally truthful fallback package when Decisioning is requested.
5. Invoke `nordvell-author-email` for the static shell. Use `<!-- offer -->` while the Decision Policy is pending.
6. Return a combined preview and operation manifest before any mutation. Plan or content approval does not authorize writes.

## Build Sequence

For every mutation, present its exact payload and obtain a fresh approval.

1. Create and separately publish the reviewed targeted and fallback HTML expression fragments. Verify their live content.
2. Resolve the Decisioning catalog and inventory existing resources. Reuse only after semantic comparison.
3. Create or verify the eligibility rule from supported Profile fields or an exact audience system ID. Never use an audience display name as a system identifier or copy generated PQL blindly.
4. Create draft targeted and fallback items with truthful dates, priority, eligibility, and metadata. Attach each published fragment under the same stable `referenceKey`. Fresh-get items and ETags immediately before every attachment or lifecycle change.
5. Validate item readiness. Approve each item through a separate reviewed lifecycle operation. The fallback must be approved and universally truthful.
6. Create or reuse exact collections and a selection strategy. Create ranking only when the business requirement needs it.
7. Create or reuse the exact email placement.
8. Resolve one exact DRAFT Action campaign message scope. Campaign and Journey creation remain AJO UI work.
9. Present final policy preflight: scope, strategy IDs, optional manual IDs, approved fallback IDs, placement, and output count. Stop on unresolved dependencies.
10. Separately approve and create the Decision Policy. Its unknown outcome requires UI reconciliation; never retry blindly.
11. Separately approve and bind the exact placement to that policy and scope.
12. Backfill or create the email template using the real policy UUID, exact placement name, and fragment reference key so the MCP generates the only permitted policy loop.
13. Re-read every mutated resource and return the operation receipt plus external AJO UI steps.

Do not automatically follow a diagnosis tool's recommended mutations. Diagnosis is evidence input, not write authorization. Never create or activate a Journey/campaign, send a proof, or claim delivery when unsupported.
