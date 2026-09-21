# Coworker Prompt: Aurora Recovery Email and Offers

Paste the prompt below into CX Coworker after refreshing the NORDVELL Brand and Content plugin.

```text
Use the NORDVELL Brand and Content plugin skills `nordvell-author-email` and `nordvell-author-offer-content`.

Author the actual content for the recorded Aurora Parka recovery demo in explicit `poc-draft-write` mode. Do not return a plan, wireframe, content outline, implementation instructions, or references to example files instead of the content. Follow `aurora-recovery-content.md` as the canonical campaign reference and `bright-editorial-v1` as the fixed design system. Do not ask me to choose layout, colors, fonts, modules, offer position, CTA styling, footer design, or mobile behavior. Do not add a discount, promotion, urgency, exclusivity, or unsupported product claim.

The required deliverables are one complete email HTML document and three complete modular HTML expression fragments for AJO offers. Print every HTML source in full inside a labeled `html` fenced code block. Do not abbreviate source, use ellipses, describe what HTML should contain, or defer authoring to a later response.

Return these four complete artifacts in this response:

1. One complete responsive NORDVELL email package whose `html` field contains the full email document with:
   - three subject options and one recommendation;
   - preheader;
   - full Outlook-safe HTML document;
   - complete plain-text version;
   - NORDVELL header;
   - approved Aurora Parka narrative from the campaign reference;
   - Aurora Parka image using the approved creative-draft image placeholder when no real URL is available;
   - exactly one `<!-- offer -->` marker under the heading `While you wait`;
   - supplied support and fit copy, recorded as a POC scenario assumption where production approval is absent;
   - fixed NORDVELL footer with the permitted POC placeholders.

2. A preferred-size Fjell Parka offer package whose `expression` field contains the complete HTML expression fragment:
   - stable name `nordvell-aurora-fjell-preferred-size-v1`;
   - internal role `TARGETED_BACK_IN_STOCK`;
   - Fjell Parka, SKU `NV-FJELL-PARKA`;
   - refers to the recipient's preferred size only when the preferred-size field and same-size stock evidence support it;
   - include the approved image placeholder and product destination placeholder if real values are unavailable;
   - include a concrete demo rendering for Tanya (`NV-0000252`, size M).

3. A higher-priority store-pickup Fjell Parka offer package whose `expression` field contains the complete HTML expression fragment:
   - stable name `nordvell-aurora-fjell-store-pickup-v1`;
   - internal role `TARGETED_BACK_IN_STOCK`;
   - Fjell Parka, SKU `NV-FJELL-PARKA`;
   - requires preferred size, allow-listed postcode, verified same-size local stock, store name, and pickup capability;
   - state `Reserve it for in-store pickup`, not `collect today`;
   - never claim that an unavailable Aurora Parka size is available locally;
   - include a concrete demo rendering for Ivan (`NV-0000253`, size XL, postcode 0150) with explicit store/pickup placeholders where unresolved.

4. A notify-only fallback offer package whose `expression` field contains the complete HTML expression fragment:
   - stable name `nordvell-aurora-size-notify-fallback-v1`;
   - internal role `FALLBACK_NOTIFY_ONLY`;
   - no Fjell availability, preferred-size, local-stock, store, or exclusivity claim;
   - suitable for Satish (`NV-0000254`) and Ricardo (`NV-0000255`);
   - include the size-preference CTA only if a real preference-center workflow and URL are supplied; otherwise provide the safe no-CTA version.

Use email-safe `role="presentation"` tables and inline critical styles for every fragment. Keep internal role names and audience logic out of customer-facing copy. Treat `{preferredSize}` and `{storeName}` as semantic requirements, not literal AJO syntax; do not hand-write an unverified personalization expression.

Return every artifact using the plugin's `NORDVELL_EMAIL_PACKAGE` and `NORDVELL_OFFER_FRAGMENT` output contracts. The email package must contain authored HTML, and every offer package must contain authored fragment HTML in `expression`; neither a summary nor an AJO resource configuration is a substitute. Include approved facts used, unresolved facts, placeholders, evidence, approvals required, and readiness flags. Set `mode: poc-draft-write`, `pocDraft: true`, `productionReady: false`, `readyToCreateDraft: true`, and production readiness fields false.

After authoring and source QA, prepare four deterministic draft AJO content operations: one Content Template and three HTML expression fragments. Prefix their names and descriptions with `POC DRAFT - NOT FOR SEND`. Show each exact payload, placeholder manifest, POC scenario assumptions, target sandbox, and exact approval phrase in one consolidated approval request. Do not refuse draft creation because placeholders remain. After I provide the exact approvals, create or update only those four draft content resources, re-read them, and return IDs, ETags, lifecycle state, placeholders, assumptions, and production remediation.

Do not publish fragments, create or approve Decisioning items, create or bind a policy, apply the template to a message, send a proof, activate a campaign or Journey, or send a message. Stop after the four verified draft content resources exist.
```

## Follow-up Approval

After Coworker displays the four exact operations, reply with the exact approval phrases it provides. Approval must identify all four payloads; it does not authorize publication, binding, activation, proofing, or sending.

## Production Follow-up

Only after real URLs, assets, footer details, store facts, inventory evidence, preference-center behavior, and claim approvals have been supplied, use:

```text
Regenerate the reviewed Aurora recovery email and three offers in `ajo-ready` mode using the activation facts below. Require zero placeholders and re-run source, truthfulness, accessibility, and role-separation QA. Return the exact final payloads and diffs against the existing AJO resources, but do not mutate AJO until I provide the fresh exact approval phrase for each individual operation.

[PASTE ALL APPROVED ACTIVATION FACTS AND EXISTING AJO RESOURCE IDS HERE]
```
