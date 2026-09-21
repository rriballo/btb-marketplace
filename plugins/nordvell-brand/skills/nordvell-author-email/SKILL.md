---
name: nordvell-author-email
description: Write a polished, complete NORDVELL email package for Adobe Journey Optimizer, including subject, preheader, plain text, responsive HTML, and a controlled offer slot. Use when Coworker is asked to create or update NORDVELL email content. Do not use for isolated offer fragments, Journey activation, proofs, or invented campaign facts.
---

# Author a NORDVELL Email

Follow `../../references/nordvell-brand-standard.md`, `../../references/nordvell-email-standard.md`, `../../references/nordvell-email-scaffold.md`, `../../references/nordvell-creative-patterns.md`, `../../references/campaign-facts-contract.md`, `../../references/write-safety-and-recovery.md`, and `../../references/operation-receipt.md`.

## Creative Workflow

1. Invoke `nordvell-brand-guidelines` and obtain its normalized content contract.
2. Default to `creative-draft` and `bright-editorial-v1`. Do not ask the user to choose logo treatment, colors, fonts, header, hero, body sections, offer location, CTA styling, footer design, or responsive behavior.
3. Determine the email's one useful customer outcome. Use the actual evidence label, such as `view-without-add`, internally; do not tell the recipient they abandoned, were segmented, or were diagnosed.
4. Write three concise subject options and identify the recommended one. Avoid false availability, urgency, exclusivity, and implied surveillance.
5. Write a complementary preheader, not a duplicate subject.
6. Produce the exact `NORDVELL_EMAIL_PACKAGE` defined in the email standard on the first response. Include a complete plain-text version and complete HTML document, not a wireframe, partial snippet, or prose description.
7. Start from the canonical email scaffold and use its fixed Bright Editorial header, hero, context, offer slot, optional support, closing, and footer modules. Preserve its module IDs and ordering. Use approved placeholders for missing activation URLs/assets/footer details and omit unsupported optional claims. Do not block the visual draft for those details.
8. Use exactly one `<!-- offer -->` marker at the intended position when the policy is pending. When a real bound policy exists, omit the marker and record the complete real policy tuple; never hand-write its loop.
9. Validate source, mobile behavior, images-disabled behavior, contrast, alt text, links, CTA, footer, placeholders, and brand voice.
10. Present the rendered content summary, complete source package, approved facts used, unresolved facts, one consolidated activation checklist, and `readyToWrite`. Content review does not authorize a write.

## Optional AJO Write

Only when the user explicitly asks to save the reviewed content:

1. If unresolved facts remain, ask one consolidated activation question. Do not start a multi-question interview. Regenerate the complete package in `ajo-ready` mode after the answer and fail closed if any non-sendable placeholder remains.
2. Call `ajo_get_capabilities`; require sandbox `aepenablementfy21` and enabled Content writes.
3. List/read templates as needed and compare semantic content and exact IDs; never reuse by name alone.
4. For creation, show the exact template name, full HTML facts, offer-slot mode, risks, and required confirmation `create content-template <name>`. Obtain fresh approval, then call `ajo_content_create_email_template`.
5. For update, call `ajo_content_get_template` immediately before approval, show the full diff and ETag, obtain fresh approval with `update <templateId>`, then call `ajo_content_update_email_template`.
6. Re-read the template and audit the stored source. Record ID, ETag, source shape, marker/policy block, and unresolved external steps.

Do not claim that saving a template updates a Journey message. Applying a template creates a copy in AJO. Do not claim proof, activation, delivery, qualification, or legal approval.
