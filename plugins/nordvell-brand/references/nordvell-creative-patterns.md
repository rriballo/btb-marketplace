# NORDVELL Bright Editorial Patterns

`bright-editorial-v1` is the default design. Do not ask the user to choose a visual direction unless they explicitly request a deviation. Bracketed values are creative placeholders governed by `campaign-facts-contract.md`; they may be stored only in an explicitly requested `poc-draft-write` resource labeled `POC DRAFT - NOT FOR SEND`.

## Color Rhythm

Use color in this fixed sequence:

```text
Lichen header
Fjord hero
Cloud context
Snow offer frame
Lichen targeted offer OR Fjord fallback offer
Optional alternating Fjord/Lichen support
Cloud closing band
Midnight footer
```

This creates a colorful email without gradients, decorative colors, or contrast failures. Never use Alert except for a real unavailable/error state.

## Product Recovery Composition

1. Open with a useful outcome, not behavior tracking.
2. Use one hero thought and one optional hero CTA.
3. Bridge into the dynamic treatment with one short Cloud panel.
4. Make the colorful offer fragment the visual focal point.
5. Add no more than one supporting block, and only from approved facts.
6. End with a quiet closing band when it adds a distinct action.
7. Use the fixed Midnight footer.

The email must look complete with no image. Approved photography enhances the hero or offer but never carries critical information.

## Copy Directions

Subject directions, when supported:

- `Another option in your size`
- `An update on the [approved product name]`
- `We’ll keep watch for [approved size or product]`

Avoid `You left this behind`, `Your exclusive pick`, `Last chance`, or any phrasing that exposes surveillance or unsupported urgency.

Targeted alternative hierarchy:

```text
AVAILABLE IN YOUR SIZE
Another way through the weather
The [alternative product] is available in [size], the size you viewed.
Explore [alternative product]
```

This is structure, not approved campaign copy. Do not assert matching fit, features, materials, performance, delivery, or price without evidence.

Notify-only fallback hierarchy:

```text
SIZE UPDATE
We’ll keep watch
There is no confirmed update for [product] in [size] yet. Choose notification and we’ll let you know when that changes.
Keep me notified
```

Use the CTA only when notification behavior and its destination are approved.

## Responsive Rules

- Outer canvas: Cloud, 100% width. Main presentation table: 600px maximum.
- Desktop gutters: 40px; hero vertical padding: 48px; normal module vertical padding: 40px.
- Mobile breakpoint: 620px. Mobile gutters: 24px; module vertical padding: 32-36px.
- Stack split cells at 100% width on mobile. Images become fluid with explicit source dimensions where known.
- Headline: 38/42px desktop and 30/34px mobile. Offer headline: 30/34px desktop and 26/30px mobile.
- Body: 16-17px with 24-26px line height. Footer: 12-13px with 18-20px line height.
- CTAs: at least 44px high, direct verb-first labels, 16px 24px padding, 0-4px radius.
- Do not create dense card grids, centered walls of text, or repeated CTA buttons.

## Draft-First Rule

Generate the entire visual draft on the first pass. Do not ask about logo treatment, colors, typography, layout, module order, CTA styling, image crop, or footer styling. Use the fixed defaults.

If activation facts are missing, use only approved placeholders, list them once, and continue the creative preview. Before a production AJO write, ask one consolidated activation question and regenerate without placeholders. For explicit `poc-draft-write`, retain the manifest and allow only draft content creation/update.
