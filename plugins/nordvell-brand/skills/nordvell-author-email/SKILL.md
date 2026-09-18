---
name: nordvell-author-email
description: Write a polished, complete NORDVELL email package for Adobe Journey Optimizer, including subject, preheader, plain text, responsive HTML, and a controlled offer slot. Use when Coworker is asked to create or update NORDVELL email content. Do not use for isolated offer fragments, Journey activation, proofs, or invented campaign facts.
---

# Author a NORDVELL Email

Follow `../../references/nordvell-brand-standard.md`, `../../references/nordvell-email-standard.md`, `../../references/nordvell-creative-patterns.md`, `../../references/campaign-facts-contract.md`, `../../references/write-safety-and-recovery.md`, and `../../references/operation-receipt.md`.

## Creative Workflow

1. Invoke `nordvell-brand-guidelines` and obtain its normalized content contract.
2. Determine the email's one useful customer outcome. Use the actual evidence label, such as `view-without-add`, internally; do not tell the recipient they abandoned, were segmented, or were diagnosed.
3. Write three concise subject options and identify the recommended one. Avoid false availability, urgency, exclusivity, and implied surveillance.
4. Write a complementary preheader, not a duplicate subject.
5. Produce the exact `NORDVELL_EMAIL_PACKAGE` defined in the email standard. Include a complete plain-text version and complete HTML document, not a wireframe or prose description.
6. Compose a purposeful editorial hierarchy. Use supplied imagery and product facts when available. Do not fill empty space with invented benefits or generic marketing copy.
7. Use exactly one `<!-- offer -->` marker at the intended position when the policy is pending. When a real bound policy exists, omit the marker and record the complete real policy tuple; never hand-write its loop.
8. Validate source, mobile behavior, images-disabled behavior, contrast, alt text, links, CTA, footer, placeholders, and brand voice.
9. Present the rendered content summary, complete source package, approved facts used, unresolved facts, and `readyToWrite`. Content review does not authorize a write.

## Optional AJO Write

Only when the user explicitly asks to save the reviewed content:

1. Call `ajo_get_capabilities`; require sandbox `aepenablementfy21` and enabled Content writes.
2. List/read templates as needed and compare semantic content and exact IDs; never reuse by name alone.
3. For creation, show the exact template name, full HTML facts, offer-slot mode, risks, and required confirmation `create content-template <name>`. Obtain fresh approval, then call `ajo_content_create_email_template`.
4. For update, call `ajo_content_get_template` immediately before approval, show the full diff and ETag, obtain fresh approval with `update <templateId>`, then call `ajo_content_update_email_template`.
5. Re-read the template and audit the stored source. Record ID, ETag, source shape, marker/policy block, and unresolved external steps.

Do not claim that saving a template updates a Journey message. Applying a template creates a copy in AJO. Do not claim proof, activation, delivery, qualification, or legal approval.
