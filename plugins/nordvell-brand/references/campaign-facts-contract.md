# Campaign Facts Contract

Before creative authoring, normalize the request into four evidence classes. Missing activation facts do not block a creative preview.

## Supplied and Approved

Facts the user explicitly supplied and approved for customer-facing use, including locale, names, SKUs, size context, availability, alternative relationship, links, assets, dates, prices, footer, legal text, and CTA.

## Tool-Verified

Facts returned by a suitable read tool. Record tool, resource ID, retrieval time, and exact value. An audience definition proves logic, not current profile qualification. A campaign preview proves rendering, not delivery. The current AJO MCP has no inventory tool.

## Inferred for Drafting

Creative directions that do not assert external facts, such as hierarchy or a headline theme. Clearly label them and never convert them into product, availability, price, eligibility, legal, or performance claims.

## Unresolved

Missing, stale, contradictory, or unapproved facts.

In `creative-draft` mode, use only these conspicuous non-sendable placeholder forms when the value is necessary to show the complete design:

- `[APPROVED_PRODUCT_URL_REQUIRED]`
- `[APPROVED_IMAGE_URL_REQUIRED]`
- `[POSTAL_ADDRESS_REQUIRED]`
- `[PRIVACY_URL_REQUIRED]`
- `[UNSUBSCRIBE_URL_REQUIRED]`
- `[LEGAL_TEXT_REQUIRED]`
- `[APPROVED_PRICE_REQUIRED]`
- `[APPROVED_DATE_REQUIRED]`

Do not ask permission for each placeholder. Record all placeholders in `unresolvedFacts`, set readiness false, and label the package `creative-draft`. Never use a placeholder to fabricate stock, eligibility, a product relationship, product performance, or consent. If those facts are absent, choose a truthful generic or notify-only treatment instead.

Before any AJO mutation, switch to `ajo-ready` mode. Ask one consolidated activation question containing every unresolved fact, then regenerate and re-audit the complete source. No approved AJO payload may contain square-bracket placeholders, `href="#"`, fake UUIDs, fake asset URLs, or sample legal details.

Never call view-without-add behavior `abandonment` unless the data supports session sequencing. Use the approved audience name or `view-without-add audience` when that is the actual evidence.
