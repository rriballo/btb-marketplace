# Campaign Facts Contract

Before creative authoring, normalize the request into four evidence classes.

## Supplied and Approved

Facts the user explicitly supplied and approved for customer-facing use, including locale, names, SKUs, size context, availability, alternative relationship, links, assets, dates, prices, footer, legal text, and CTA.

## Tool-Verified

Facts returned by a suitable read tool. Record tool, resource ID, retrieval time, and exact value. An audience definition proves logic, not current profile qualification. A campaign preview proves rendering, not delivery. The current AJO MCP has no inventory tool.

## Inferred for Drafting

Creative directions that do not assert external facts, such as hierarchy or a headline theme. Clearly label them and never convert them into product, availability, price, eligibility, legal, or performance claims.

## Unresolved

Missing, stale, contradictory, or unapproved facts. Use a labeled placeholder only when the user explicitly authorizes it. Otherwise stop the affected content path. Report every unresolved fact before requesting a write.

Never call view-without-add behavior `abandonment` unless the data supports session sequencing. Use the approved audience name or `view-without-add audience` when that is the actual evidence.
