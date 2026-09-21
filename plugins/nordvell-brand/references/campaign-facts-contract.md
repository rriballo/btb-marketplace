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

In `creative-draft` or explicitly requested `poc-draft-write` mode, use only these conspicuous placeholder forms when the value is necessary to show or store the complete design:

- `[APPROVED_PRODUCT_URL_REQUIRED]`
- `[APPROVED_IMAGE_URL_REQUIRED]`
- `[POSTAL_ADDRESS_REQUIRED]`
- `[PRIVACY_URL_REQUIRED]`
- `[UNSUBSCRIBE_URL_REQUIRED]`
- `[LEGAL_TEXT_REQUIRED]`
- `[APPROVED_PRICE_REQUIRED]`
- `[APPROVED_DATE_REQUIRED]`
- `[APPROVED_STORE_NAME_REQUIRED]`
- `[APPROVED_PICKUP_URL_REQUIRED]`
- `[APPROVED_PREFERENCE_URL_REQUIRED]`

Do not ask permission for each placeholder. Record all placeholders in `unresolvedFacts`. In `creative-draft`, set readiness false. In `poc-draft-write`, set `pocDraft: true`, `productionReady: false`, and `readyToCreateDraft: true` only after source QA. Never represent a placeholder as verified fact.

## POC Draft-Write Exception

`poc-draft-write` is permitted only when the user explicitly requests creation or update of placeholder-bearing content for a controlled proof of concept. It permits placeholders in draft AJO Content Templates and draft HTML expression fragments. It does not make the content sendable or production-ready.

In this mode:

- Prefix or suffix deterministic resource names with `POC` or `poc-draft`.
- Show the exact placeholder-bearing payload and unresolved-fact manifest before the write.
- Obtain the normal fresh exact approval for each create or update.
- Keep the resource in draft. Do not publish a fragment, approve an item, bind a policy, apply the template to a live message, activate a campaign or Journey, send a proof, or send a message.
- Do not use fake UUIDs or claim that placeholders are real URLs, assets, legal terms, consent, stock, eligibility, or delivery evidence.
- The user may explicitly approve scenario assumptions such as Fjell Parka demo availability for this POC. Record them as `pocScenarioAssumptions`, not tool-verified or production facts.
- Missing stock, eligibility, relationship, product-performance, pickup, or consent facts may be represented only as clearly labeled POC scenario assumptions or omitted from the copy. Do not silently infer them.
- Every operation receipt must state `POC DRAFT - NOT FOR SEND` and list all placeholders and assumptions.

For production-capable writes, switch to `ajo-ready`, ask one consolidated activation question, regenerate, and re-audit. An `ajo-ready` payload may not contain square-bracket placeholders, `href="#"`, fake UUIDs, fake asset URLs, or sample legal details.

Never call view-without-add behavior `abandonment` unless the data supports session sequencing. Use the approved audience name or `view-without-add audience` when that is the actual evidence.
