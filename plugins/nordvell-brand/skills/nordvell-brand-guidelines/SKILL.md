---
name: nordvell-brand-guidelines
description: Apply or audit the canonical NORDVELL identity, voice, truthful-offer, accessibility, and email rules. Use before creating or reviewing any NORDVELL email or offer content. Do not use as legal, inventory, offer, mutation, activation, or delivery approval.
---

# Apply NORDVELL Brand Guidelines

Follow `../../references/nordvell-brand-standard.md`, `../../references/campaign-facts-contract.md`, and the applicable email or offer standard. The brand system constrains creative work; it never supplies missing campaign facts.

## Required Inputs

- Authoring or read-only audit mode.
- Objective, audience context, market, locale, and channel.
- Supplied product names/SKUs, size context, proposition, links, assets, dates, prices, footer, legal text, and evidence provenance.
- Internal role for each offer: `TARGETED_BACK_IN_STOCK` or `FALLBACK_NOTIFY_ONLY`.

Do not require the user to understand the complete contract before helping. Extract available facts from their request and relevant read tools, then ask only for facts that block the requested output or a safe write.

## Workflow

1. Separate supplied/approved, tool-verified, drafting-only, and unresolved facts according to the campaign facts contract.
2. Verify that customer-facing statements are supported. The current MCP has no inventory tool; never imply that an AJO read verified stock.
3. Classify each treatment. A targeted treatment requires evidence for its exact recovery option. A fallback must be valid for every possible fallback recipient.
4. Apply the visual and voice standard. Remove internal audience, algorithm, diagnosis, Decisioning, and offer-role language from customer copy.
5. Return a normalized content contract with the following keys: `brand`, `mode`, `channel`, `locale`, `objective`, `audienceContext`, `approvedFacts`, `toolVerifiedFacts`, `draftingDirections`, `offerRoles`, `visualRules`, `voiceRules`, `accessibilityRules`, `forbiddenClaims`, `unresolvedFacts`, `requiredApprovals`, and `readyForAuthoring`.
6. Set `readyForAuthoring` false when missing facts would force an unsupported claim. Draft unaffected sections only when doing so cannot disguise the gap.
7. For authoring, pass the contract to `nordvell-author-email` or `nordvell-author-offer-content`. For audit, quote the exact issue and applicable rule.

This skill performs no AJO mutation and grants no approval to another skill. State what is aligned, what is unverified, and what exact evidence or human approval remains.
