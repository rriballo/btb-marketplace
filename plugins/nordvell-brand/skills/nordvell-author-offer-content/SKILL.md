---
name: nordvell-author-offer-content
description: Write truthful NORDVELL targeted and fallback offer content as AJO-ready HTML expression-fragment packages. Use for back-in-stock, same-size alternative, verified local-stock, and notify-only treatments. Do not use for complete emails, unsupported stock claims, or automatic Adobe writes.
---

# Author NORDVELL Offer Content

Follow `../../references/nordvell-brand-standard.md`, `../../references/nordvell-offer-contract.md`, `../../references/nordvell-creative-patterns.md`, `../../references/campaign-facts-contract.md`, `../../references/write-safety-and-recovery.md`, and `../../references/operation-receipt.md`.

## Authoring

1. Invoke `nordvell-brand-guidelines` and classify every treatment as `TARGETED_BACK_IN_STOCK` or `FALLBACK_NOTIFY_ONLY`.
2. Default to `creative-draft` and the fixed Bright Editorial targeted/fallback treatments. Do not ask design questions before drafting.
3. Build an evidence table while writing. Availability, same-size alternatives, replenishment, pickup, prices, dates, URLs, assets, and product capabilities require supplied or suitable tool-verified evidence. The current MCP cannot verify inventory.
4. For targeted content, use only the exact option supported by eligibility and evidence. If that evidence is missing, do not ask repeatedly or insert an availability placeholder; draft only the truthful fallback. Never infer a customer's size from an aggregate report or reveal the targeting mechanism.
5. For fallback, remove every dependency on targeted eligibility. Promise only acknowledgement or notification when no recovery option is verified.
6. Write concise headline, body, and CTA options. Select and explain the strongest brand-aligned option without fabricating a benefit.
7. Return one complete `NORDVELL_OFFER_FRAGMENT` package per viable treatment exactly as defined in the offer contract. The `expression` must be usable colorful HTML fragment source, not an entire email.
8. Use approved non-sendable placeholders for missing destination, image, price, or date details; list them without interrupting the creative preview. Validate accessibility, mobile width, role separation, unsupported claims, and unresolved facts. Set `readyToCreate` independently.

## Optional Fragment Operations

Only after the exact package is reviewed and the user explicitly requests the operation:

1. Ask one consolidated activation question for unresolved facts across all treatments, regenerate them in `ajo-ready` mode, and require zero placeholders.
2. Call `ajo_get_capabilities`; require sandbox `aepenablementfy21` and enabled Content writes.
3. List and read potential fragment matches. Compare exact ID, subtype, lifecycle, draft/live expression, and differences; never reuse by name alone.
4. Create only an expression fragment with `subType: HTML`. Show the exact payload and obtain fresh approval with `create expression-fragment <name>` before calling `ajo_content_create_expression_fragment`.
5. For updates, fresh-get the fragment and ETag, show the full replacement expression and diff, obtain approval with `update <fragmentId>`, update, and re-read.
6. Publication is a separate lifecycle mutation. Fresh-get, show exact ID/ETag/content and impact, obtain approval with `publish <fragmentId>`, publish once, and poll bounded status until complete, failed, or pending.
7. Verify the live fragment after successful publication. Attaching it to an item is another separately approved operation through the coordinated build skill or the relevant MCP tools.

Never carry approval from creation to publication or attachment. Never claim that a published fragment is selected, bound, rendered, sent, or delivered.
