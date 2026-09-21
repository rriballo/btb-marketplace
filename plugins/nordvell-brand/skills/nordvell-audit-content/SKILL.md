---
name: nordvell-audit-content
description: Perform a read-only audit of NORDVELL email templates and offer fragments for brand, source quality, accessibility, evidence, and targeted/fallback truthfulness. Use before approval, publication, policy binding, or AJO UI application. Do not mutate resources or claim legal, qualification, activation, proof, or delivery status.
---

# Audit NORDVELL Content

Remain read-only. Follow `../../references/nordvell-brand-standard.md`, `../../references/nordvell-email-standard.md`, `../../references/nordvell-email-scaffold.md`, `../../references/nordvell-offer-contract.md`, and `../../references/campaign-facts-contract.md`.

## Workflow

1. Accept exact source or retrieve the exact template/fragment by ID. Never select by name alone.
2. Invoke `nordvell-brand-guidelines` in audit mode.
3. For an email, compare the source to the canonical scaffold and verify the `bright-editorial-v1` order and fixed treatment: hidden preheader, Lichen header, Fjord hero, Cloud context, Snow offer frame, optional support/closing, and Midnight footer. Inspect subject, preheader, HTML, plain text, hierarchy, marker or generated policy block, links, assets, footer, responsive source, images-disabled meaning, and accessibility indicators.
4. For each offer, verify the fixed Lichen targeted or Fjord fallback treatment, internal role, evidence, eligibility relationship, source/alternative SKUs, size claims, CTA destination, fragment format, and customer-visible copy.
5. Reject targeted claims not supported by the candidate's evidence. Reject fallback content that depends on a targeted fact or implies exclusivity, replenishment, an alternative, or local stock without universal evidence.
6. Search for hand-authored personalization, fake IDs, unresolved placeholders, internal labels, audience/algorithm language, unsupported claims, inaccessible image-only content, scripts/forms, and fragile email CSS. Placeholders are expected findings in `creative-draft`, permitted-but-blocking-production findings in `poc-draft-write`, and blockers in `ajo-ready`. A stored POC resource must carry `POC DRAFT - NOT FOR SEND` labeling and an unresolved manifest.
7. If comparing stored and live fragments, report each evidence source separately. A draft/live difference is a lifecycle finding, not proof of message behavior.

## Output

Return severity-ranked findings first. Each finding includes exact quoted source, violated rule, evidence, impact, and remediation direction. Then return pass evidence, unresolved facts, blind spots, and required human or AJO UI actions.

Do not rewrite one unsupported claim into another. Do not attest to legal approval, accessibility conformance, recipient qualification, policy selection, campaign activation, proofing, delivery, or impact.
