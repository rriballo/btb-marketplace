# Coworker Prompt: Aurora Recovery Email and Offers

Paste the prompt below into CX Coworker after refreshing the NORDVELL Brand and Content plugin.

```text
Use the NORDVELL Brand and Content plugin skills `nordvell-author-email` and `nordvell-author-offer-content`.

Create the complete creative-draft package for the recorded Aurora Parka recovery demo. Follow `aurora-recovery-content.md` as the canonical campaign reference and `bright-editorial-v1` as the fixed design system. Do not ask me to choose layout, colors, fonts, modules, offer position, CTA styling, footer design, or mobile behavior. Do not add a discount, promotion, urgency, exclusivity, or unsupported product claim.

Return these four complete artifacts in this response:

1. One complete responsive NORDVELL email package with:
   - three subject options and one recommendation;
   - preheader;
   - full Outlook-safe HTML document;
   - complete plain-text version;
   - NORDVELL header;
   - approved Aurora Parka narrative from the campaign reference;
   - Aurora Parka image using the approved creative-draft image placeholder when no real URL is available;
   - exactly one `<!-- offer -->` marker under the heading `While you wait`;
   - supplied support and fit copy, clearly recorded as requiring business/product approval before an AJO write;
   - fixed NORDVELL footer with the permitted creative-draft placeholders.

2. A preferred-size Fjell Parka HTML expression fragment:
   - stable name `nordvell-aurora-fjell-preferred-size-v1`;
   - internal role `TARGETED_BACK_IN_STOCK`;
   - Fjell Parka, SKU `NV-FJELL-PARKA`;
   - refers to the recipient's preferred size only when the preferred-size field and same-size stock evidence support it;
   - include the approved image placeholder and product destination placeholder if real values are unavailable;
   - include a concrete demo rendering for Tanya (`NV-0000252`, size M).

3. A higher-priority store-pickup Fjell Parka HTML expression fragment:
   - stable name `nordvell-aurora-fjell-store-pickup-v1`;
   - internal role `TARGETED_BACK_IN_STOCK`;
   - Fjell Parka, SKU `NV-FJELL-PARKA`;
   - requires preferred size, allow-listed postcode, verified same-size local stock, store name, and pickup capability;
   - state `Reserve it for in-store pickup`, not `collect today`;
   - never claim that an unavailable Aurora Parka size is available locally;
   - include a concrete demo rendering for Ivan (`NV-0000253`, size XL, postcode 0150) with explicit store/pickup placeholders where unresolved.

4. A notify-only fallback HTML expression fragment:
   - stable name `nordvell-aurora-size-notify-fallback-v1`;
   - internal role `FALLBACK_NOTIFY_ONLY`;
   - no Fjell availability, preferred-size, local-stock, store, or exclusivity claim;
   - suitable for Satish (`NV-0000254`) and Ricardo (`NV-0000255`);
   - include the size-preference CTA only if a real preference-center workflow and URL are supplied; otherwise provide the safe no-CTA version.

Use email-safe `role="presentation"` tables and inline critical styles for every fragment. Keep internal role names and audience logic out of customer-facing copy. Treat `{preferredSize}` and `{storeName}` as semantic requirements, not literal AJO syntax; do not hand-write an unverified personalization expression.

Return every artifact using the plugin's `NORDVELL_EMAIL_PACKAGE` and `NORDVELL_OFFER_FRAGMENT` output contracts. Include approved facts used, unresolved facts, placeholders, evidence, approvals required, and readiness flags. Set all assets to creative-draft and readiness false while activation placeholders or claim approvals remain.

Do not create, update, publish, attach, bind, activate, send, or otherwise mutate anything in Adobe Journey Optimizer. Stop after returning the complete reviewable email and three offer fragment packages.
```

## Follow-up After Review

Only after real URLs, assets, footer details, store facts, inventory evidence, preference-center behavior, and claim approvals have been supplied, use a separate Coworker message:

```text
Regenerate the reviewed Aurora recovery email and three offers in `ajo-ready` mode using the activation facts below. Require zero placeholders and re-run source, truthfulness, accessibility, and role-separation QA. Return the exact final payloads and diffs against the existing AJO resources, but do not mutate AJO until I provide the fresh exact approval phrase for each individual operation.

[PASTE ALL APPROVED ACTIVATION FACTS AND EXISTING AJO RESOURCE IDS HERE]
```
