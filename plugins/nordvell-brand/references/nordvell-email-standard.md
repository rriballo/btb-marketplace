# NORDVELL Email Content Standard

## Output Contract

Every email-authoring response must return these labeled fields:

```json
{
  "contentType": "NORDVELL_EMAIL_PACKAGE",
  "locale": "approved locale",
  "audienceContext": "non-customer-facing summary",
  "subject": "customer-facing subject",
  "preheader": "customer-facing preheader",
  "html": "complete HTML document",
  "text": "complete plain-text alternative",
  "offerSlot": {
    "mode": "none | pending-policy | bound-policy",
    "marker": "<!-- offer --> or null",
    "referenceKey": "hero",
    "decisionPolicyId": null,
    "placementName": null
  },
  "assets": [],
  "links": [],
  "approvedFactsUsed": [],
  "unresolvedFacts": [],
  "approvalsRequired": [],
  "readyToWrite": false
}
```

`readyToWrite` is true only when all customer-facing facts, destinations, assets, required footer details, and the intended offer-slot mode are resolved and the complete source passes QA. It does not mean the user approved a mutation.

## Content Architecture

Create a complete focused email, not a generic newsletter:

1. Hidden preheader that complements rather than repeats the subject.
2. Text NORDVELL wordmark or supplied approved logo.
3. Focused editorial hero with one useful message.
4. The offer slot in the reviewed location.
5. One or two supporting blocks only when they add supplied facts.
6. One primary CTA per treatment and restrained secondary links.
7. Supplied postal address, privacy, unsubscribe, and required legal content.

Do not pad an email with unsupported product benefits, recommendations, testimonials, service promises, or lifestyle claims.

## Technical Source

- Return a complete HTML document with doctype, `html`, `head`, and `body`.
- Use a centered table/hybrid container no wider than 600px and `role="presentation"` on layout tables.
- Inline critical styles and use one conservative responsive media query.
- Use Arial, Helvetica, sans-serif and Outlook-safe markup.
- Add width and height to images where supplied and meaningful alt text; decorative images use empty alt text.
- Keep key information as live text and understandable with images or color disabled.
- Use descriptive links and touch targets around 44px where practical.
- Do not use JavaScript, forms, lazy loading, video-only information, fragile CSS, or unsupported personalization syntax.

Before a real policy exists, include the literal `<!-- offer -->` exactly once. Do not place `{{ }}` or `{% %}` expressions anywhere, including comments. When a real policy is available, pass the real `decisionPolicyId`, exact `placementName`, and `referenceKey` to the MCP template tool; the server generates the policy loop.

## QA

Check subject, preheader, HTML, plain text, hierarchy, mobile behavior, links, assets, alt text, color contrast, images-disabled behavior, offer marker/policy mode, unresolved placeholders, footer presence, and consistency with the approved content contract. Technical footer checks are not legal approval.
