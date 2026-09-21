# NORDVELL Brand and Content Plugin

This plugin gives CX Coworker one canonical NORDVELL brand system and focused skills for creating polished AJO email templates and modular Decisioning offer content.

Shared references define the exact email and offer output contracts plus reusable premium editorial composition patterns, so authoring returns complete source rather than a wireframe or generic marketing outline.

The Aurora Parka recorded-demo package is fixed in `references/aurora-recovery-content.md`. It aligns the shared no-discount email with preferred-size Fjell Parka, verified store-pickup, and notify-only fallback treatments, including the four named demo-profile outcomes.

Reviewable creative-draft source is under `examples/`: one complete responsive email and three modular offer fragments. These files intentionally contain non-sendable activation placeholders and must not be copied into AJO unchanged.

The default is `bright-editorial-v1`: Lichen header, Fjord hero, Cloud body context, colorful targeted/fallback offer, optional alternating support block, and Midnight footer. Coworker does not ask the user to design these sections.

Authoring starts in `creative-draft` mode. Coworker immediately returns complete HTML, plain text, and offer fragments using conspicuous non-sendable placeholders for missing URLs, assets, address, privacy, unsubscribe, or legal details. When the user asks to save, Coworker asks one consolidated activation question, regenerates in `ajo-ready` mode with zero placeholders, and only then begins separately approved Adobe operations.

## Skills

- `nordvell-brand-guidelines`: normalizes supplied facts into a brand-safe content contract or audits existing content.
- `nordvell-author-email`: writes a complete subject, preheader, plain text, and responsive email document with a controlled offer slot.
- `nordvell-author-offer-content`: writes targeted and fallback HTML expression-fragment packages from verified offer facts.
- `nordvell-build-email-experience`: coordinates content, fragments, Decisioning resources, policy binding, and template creation with separate approvals.
- `nordvell-audit-content`: performs a read-only brand, source, accessibility, and offer-truthfulness audit.

## Example Prompt

```text
Build NORDVELL email and offer content for the published Aurora Parka M/L
view-without-add audience. The approved alternative is Fjell Parka and it is
available in M and L. Use these approved product and footer URLs: [...].
Draft everything first and do not write to AJO until I approve each payload.
```

Coworker first identifies missing evidence. When sufficient facts exist, it returns a complete preview package before requesting any mutation approval.

## Fixed Environment

Adobe operations target only sandbox `aepenablementfy21`. A different sandbox is a stop condition.

The MCP connection is configured by `AJO_MCP_URL`, `ADOBE_IMS_TOKEN`, and `ADOBE_IMS_ORG_ID`. It points to the deployed `my-mcp-server`; this repository contains no Adobe credentials.

## Boundaries

- Stock, alternatives, prices, destinations, dates, product capabilities, assets, consent, and legal text must be supplied or evidenced. The current MCP does not provide inventory verification.
- A content draft is not an AJO mutation approval.
- Every create, update, publication, attachment, lifecycle change, policy creation, placement binding, and template save requires a fresh exact approval.
- The MCP does not create or activate Journeys or campaigns. Those remain explicit AJO UI steps.
- Source QA and preview do not prove audience qualification, proof delivery, activation, or business impact.
