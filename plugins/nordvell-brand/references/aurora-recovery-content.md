# Aurora Parka Recovery Email and Offers

This is the canonical creative package for the recorded Aurora Parka recovery demo. Use it with the NORDVELL Bright Editorial email scaffold and offer contract. It fixes the narrative and treatment hierarchy so Coworker, the email shell, and AJO Decisioning do not introduce a discount or contradict one another.

## Non-Negotiable Story

- Source product: Aurora Parka, SKU `NV-AURORA-PARKA`.
- Approved alternative: Fjell Parka, SKU `NV-FJELL-PARKA`.
- The intervention addresses unavailable sizes and does not use a discount.
- Do not describe an unavailable Aurora size as available online or in a store without current store-level evidence.
- Do not replace the Fjell Parka with another product.
- Do not expose audience names, preferred-size logic, postcode logic, internal roles, or behavioral diagnosis in customer-facing content.
- Do not add savings, promotion, urgency, exclusivity, popularity, or scarcity language.

## Email Package

### Subject Options

1. `An update on the Aurora Parka`
2. `Your Aurora Parka size update`
3. `While the Aurora Parka returns`

Recommended subject: `An update on the Aurora Parka`

Preheader: `More stock is on its way, with another option for the wait.`

### Approved Module Copy

`brand-header`

```text
NORDVELL
```

`hero`

```text
PRODUCT UPDATE

The Aurora Parka sold out faster than expected.

Some sizes are currently unavailable. More stock is already on its way.

We will email you when your preferred size is available again.
```

Do not use `before it goes out to anyone else` unless an approved priority-access process supports that exclusivity claim.

Use an approved Aurora Parka image with alt text `Aurora Parka` when supplied. In creative-draft mode the image source is `[APPROVED_IMAGE_URL_REQUIRED]`. Omit the image rather than publishing the placeholder.

`context-intro`

```text
While you wait
```

Immediately follow this heading with the single AJO Decisioning offer slot. The selected treatment supplies the useful customer action.

`supporting-detail`

These statements were supplied for the demo but remain campaign claims requiring business approval before AJO-ready use:

```text
Free returns.
Two-year guarantee.
Built for Nordic winters.
```

`closing-band`

This fit guidance was supplied for the demo but remains a product claim requiring product-owner approval before AJO-ready use:

```text
Runs true to size. Between sizes? Size up for layering.
```

`brand-footer`

Use the fixed NORDVELL footer. Creative-draft mode may use only `[POSTAL_ADDRESS_REQUIRED]`, `[LEGAL_TEXT_REQUIRED]`, `[PRIVACY_URL_REQUIRED]`, and `[UNSUBSCRIBE_URL_REQUIRED]`. No placeholder may remain in an AJO-ready payload.

### Plain Text

```text
NORDVELL

PRODUCT UPDATE

The Aurora Parka sold out faster than expected.

Some sizes are currently unavailable. More stock is already on its way.

We will email you when your preferred size is available again.

WHILE YOU WAIT

[AJO DECISIONING OFFER]

Free returns. Two-year guarantee. Built for Nordic winters.

Runs true to size. Between sizes? Size up for layering.

[POSTAL_ADDRESS_REQUIRED]
[LEGAL_TEXT_REQUIRED]
Privacy: [PRIVACY_URL_REQUIRED]
Unsubscribe: [UNSUBSCRIBE_URL_REQUIRED]
```

The support and fit lines must be removed if they are not approved by the business and product owners.

## Decisioning Treatments

The three treatments are mutually exclusive at selection time. If a profile qualifies for pickup and preferred-size treatments, pickup has the higher priority because it contains the more specific verified option. Fallback applies only when neither targeted treatment returns an eligible item.

### 1. Preferred Size Alternative

- Stable name: `nordvell-aurora-fjell-preferred-size-v1`
- Internal role: `TARGETED_BACK_IN_STOCK`
- Eligibility: preferred size is `M` or `L`, plus current Fjell Parka stock in that exact size.
- Product: Fjell Parka, SKU `NV-FJELL-PARKA`.
- Demo profile: Tanya, `NV-0000252`, preferred size `M`.
- Image: approved Fjell Parka image when supplied; alt text `Fjell Parka`.

Customer-facing copy:

```text
AVAILABLE IN YOUR SIZE

The Fjell Parka is available in your preferred size, {preferredSize}.

Explore a similar outerwear option while the Aurora Parka returns.

View the Fjell Parka
```

Concrete Tanya demo render:

```text
AVAILABLE IN YOUR SIZE

The Fjell Parka is available in your preferred size, M.

Explore a similar outerwear option while the Aurora Parka returns.

View the Fjell Parka
```

`{preferredSize}` is a content-contract token, not literal AJO syntax. Resolve it through the AJO personalization picker using the real preferred-size profile field, or create separately approved static M and L items. Do not hand-write an unverified expression.

### 2. Preferred Size and Store Pickup

- Stable name: `nordvell-aurora-fjell-store-pickup-v1`
- Internal role: `TARGETED_BACK_IN_STOCK`.
- Priority: higher than preferred-size-only.
- Eligibility: allow-listed postcode, known preferred size, verified Fjell Parka stock in that size at the named store, and active reservation/pickup capability.
- Product: Fjell Parka, SKU `NV-FJELL-PARKA`.
- Demo profile: Ivan, `NV-0000253`, preferred size `XL`, postcode `0150`.
- Image: approved Fjell Parka image when supplied; alt text `Fjell Parka`.

Customer-facing copy:

```text
AVAILABLE FOR PICKUP

The Fjell Parka is available in your preferred size, {preferredSize}, at {storeName}.

Reserve it for in-store pickup.

Reserve for pickup
```

Concrete Ivan demo render after the store is supplied:

```text
AVAILABLE FOR PICKUP

The Fjell Parka is available in your preferred size, XL, at [APPROVED_STORE_NAME_REQUIRED].

Reserve it for in-store pickup.

Reserve for pickup
```

Do not use `collect today` unless pickup timing is current and approved. Do not claim Aurora Parka store availability for this treatment. `{preferredSize}` and `{storeName}` are content-contract tokens and must be resolved using real AJO data or approved static items before publication.

### 3. Notify-Only Fallback

- Stable name: `nordvell-aurora-size-notify-fallback-v1`
- Internal role: `FALLBACK_NOTIFY_ONLY`.
- Eligibility: universal fallback for recipients reaching this policy who receive neither targeted item.
- Alternative product: none.
- Demo profiles: Satish, `NV-0000254`; Ricardo, `NV-0000255`.

Customer-facing copy:

```text
SIZE UPDATE

Tell us your preferred size.

We will let you know when it is available again and can show you other options in that size.

Update your size
```

The CTA and final clause require a real preference-center workflow. If that workflow is unavailable, omit the CTA and use this universally truthful body instead:

```text
We will let you know when more Aurora Parka sizes are available.
```

## Bright Editorial Fragment Styling

Preferred-size and pickup treatments use the targeted styling:

- Lichen `#BFD76D` background.
- Midnight `#101714` text.
- Optional approved Fjell Parka image in its own row.
- Midnight CTA with Snow text.
- 12px uppercase eyebrow, 30px headline, 16px body.

Fallback uses:

- Fjord `#406A64` background.
- Snow `#FFFFFF` text.
- Lichen CTA with Midnight text only when the preference destination exists.

All fragments must be Outlook-safe `role="presentation"` tables, fit a 600px parent, use inline critical styles, and remain understandable when images are disabled.

## Activation Checklist

Resolve these together before any AJO content update or publication:

- Approved Aurora Parka image URL.
- Approved Fjell Parka image URL.
- Approved Fjell Parka product URL.
- Verified Fjell Parka inventory by treatment size.
- Ivan's approved store name, Fjell Parka XL local stock, reservation URL, and pickup terms.
- Preferred-size personalization field selected through AJO, or approved static size items.
- Approved preference-center URL and behavior for fallback.
- Approval for replenishment, free returns, guarantee, winter-performance, and fit claims.
- Postal address, legal text, privacy URL, and unsubscribe URL.
- Confirmed email consent and actual audience qualification for each test profile.

Creative review is not mutation approval. Updating an existing email, fragment, item, strategy, or policy requires its real resource ID, a fresh read and ETag where supported, an exact diff, and separate explicit approval.
