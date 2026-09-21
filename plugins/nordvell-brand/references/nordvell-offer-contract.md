# NORDVELL Offer Content Contract

## Required Input

For each treatment require:

- Internal role: `TARGETED_BACK_IN_STOCK` or `FALLBACK_NOTIFY_ONLY`.
- Audience or eligibility basis and the evidence source.
- Source product display name, canonical SKU, and relevant size context.
- Exact verified proposition: source replenishment, same-size alternative, local stock, or notification only.
- Alternative product name/SKU and same-size availability evidence when applicable.
- Approved price or terms only if shown.
- Approved CTA label and reachable destination URL.
- Approved image URL and alt-text facts when imagery is used.
- Market, locale, date/timezone, provenance, approver, and any required legal qualification.

The current AJO MCP does not verify inventory. A diagnosis, catalog, inventory owner, or explicit user approval must supply availability evidence. Mark stale, ambiguous, or missing evidence as unresolved.

## Output Contract

Return one package per treatment:

```json
{
  "contentType": "NORDVELL_OFFER_FRAGMENT",
  "mode": "creative-draft | poc-draft-write | ajo-ready",
  "designSystem": "bright-editorial-v1",
  "internalRole": "TARGETED_BACK_IN_STOCK",
  "name": "stable AJO fragment name",
  "subType": "HTML",
  "referenceKey": "hero",
  "sourceProduct": { "name": "", "sku": "" },
  "alternativeProduct": { "name": "", "sku": "" },
  "eligibleSizes": [],
  "headline": "",
  "body": "",
  "cta": { "label": "", "destination": "" },
  "expression": "email-safe HTML fragment",
  "evidence": [],
  "unresolvedFacts": [],
  "approvalsRequired": [],
  "pocDraft": false,
  "productionReady": false,
  "readyToCreateDraft": false,
  "readyToCreate": false
}
```

Use `alternativeProduct: null` for notify-only fallback. `readyToCreate` means production-capable and requires a valid destination when the fragment contains a CTA, complete customer-facing facts, and source QA. `readyToCreateDraft` may be true for a placeholder-bearing `poc-draft-write` fragment while `readyToCreate` and `productionReady` remain false. Neither is mutation approval.

Creative-draft packages may use approved URL, image, price, date, store-name, pickup, or preference-center placeholders from the campaign facts contract and must set `readyToCreate: false`. In explicitly requested `poc-draft-write`, those packages may be written to AJO as draft expression fragments after exact approval. Name and describe each resource as `POC DRAFT - NOT FOR SEND`, set `pocDraft: true`, and preserve the unresolved manifest. Stock, eligibility, product relationships, size, pickup, performance, or consent may be used only when supplied as explicit POC scenario assumptions or verified evidence; otherwise omit the assertion. Publication remains blocked until regeneration in `ajo-ready` with zero placeholders.

## Fragment Format

The expression is a modular, email-safe table block, not a complete document. It must fit a 600px parent, use inline critical styles, remain understandable without its image, and avoid scripts, forms, external CSS, internal role names, and hand-authored AJO personalization.

Targeted content may state only the option supported by its eligibility and evidence. Fallback content must be truthful for every recipient who can receive it and cannot depend on targeted eligibility. Never silently convert one role into the other.

## Fixed Bright Editorial Treatments

Targeted same-size/replenishment fragment:

- Lichen outer background with Midnight copy and 32px desktop/24px mobile padding.
- Optional approved image in a separate full-width or 40/60 table row; omit cleanly when absent.
- 12px uppercase eyebrow, 30px headline, 16px body, approved product line, and Midnight CTA with Snow text.
- Use `AVAILABLE IN YOUR SIZE` only when current same-size evidence exists.

Notify-only fallback fragment:

- Fjord outer background with Snow copy and 32px desktop/24px mobile padding.
- 12px uppercase `SIZE UPDATE` eyebrow, 30px headline, 16px body.
- Lichen CTA with Midnight text only when notification behavior and destination are approved; otherwise omit the CTA in the draft and record the gap.

Both treatments use `role="presentation"` tables, inline styles, no external CSS, no shadow, no gradient, no internal role label, and the same typography and CTA geometry as the email shell.
