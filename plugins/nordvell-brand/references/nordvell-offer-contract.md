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
  "readyToCreate": false
}
```

Use `alternativeProduct: null` for notify-only fallback. `readyToCreate` requires a valid destination when the fragment contains a CTA, complete customer-facing facts, and source QA. It is not mutation approval.

## Fragment Format

The expression is a modular, email-safe table block, not a complete document. It must fit a 600px parent, use inline critical styles, remain understandable without its image, and avoid scripts, forms, external CSS, internal role names, and hand-authored AJO personalization.

Targeted content may state only the option supported by its eligibility and evidence. Fallback content must be truthful for every recipient who can receive it and cannot depend on targeted eligibility. Never silently convert one role into the other.
