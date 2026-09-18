# NORDVELL Bright Editorial Email Scaffold

Use this source structure for `bright-editorial-v1`. Tokens containing `APPROVED ... COPY`, `APPROVED EYEBROW`, `APPROVED HEADLINE`, or `APPROVED CTA LABEL` are authoring instructions and must be replaced with generated, evidence-safe copy even in creative-draft mode. The five `_REQUIRED` activation placeholders shown below are permitted only in creative-draft mode. Do not submit this reference verbatim or leave any placeholder in `ajo-ready` mode.

Optional approved image rows and one supporting block may be inserted according to `nordvell-email-standard.md`. Preserve the module IDs, top-level order, color pairings, offer position, table layout, and mobile behavior.

```html
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <meta name="x-apple-disable-message-reformatting">
  <title>NORDVELL</title>
  <style>
    @media only screen and (max-width: 620px) {
      .nv-container { width: 100% !important; }
      .nv-pad { padding-left: 24px !important; padding-right: 24px !important; }
      .nv-hero { padding-top: 36px !important; padding-bottom: 36px !important; }
      .nv-module { padding-top: 32px !important; padding-bottom: 32px !important; }
      .nv-headline { font-size: 30px !important; line-height: 34px !important; }
      .nv-stack { display: block !important; width: 100% !important; }
      .nv-fluid { width: 100% !important; height: auto !important; }
    }
  </style>
</head>
<body style="margin:0;padding:0;background:#F2F1EA;color:#101714;font-family:Arial,Helvetica,sans-serif;">
  <div id="preheader" style="display:none;max-height:0;overflow:hidden;opacity:0;color:transparent;">
    [APPROVED PREHEADER COPY]
  </div>
  <table role="presentation" width="100%" cellspacing="0" cellpadding="0" border="0" style="width:100%;background:#F2F1EA;">
    <tr>
      <td align="center">
        <table role="presentation" class="nv-container" width="600" cellspacing="0" cellpadding="0" border="0" style="width:600px;max-width:600px;">
          <tr id="brand-header">
            <td class="nv-pad" style="padding:24px 40px;background:#BFD76D;color:#101714;font-size:24px;line-height:30px;font-weight:700;letter-spacing:2px;">
              NORDVELL
            </td>
          </tr>
          <tr id="hero">
            <td class="nv-pad nv-hero" style="padding:48px 40px;background:#406A64;color:#FFFFFF;">
              <div style="font-size:12px;line-height:18px;font-weight:700;letter-spacing:1.5px;text-transform:uppercase;">[APPROVED EYEBROW]</div>
              <h1 class="nv-headline" style="margin:12px 0 16px;font-size:38px;line-height:42px;font-weight:700;color:#FFFFFF;">[APPROVED HEADLINE]</h1>
              <p style="margin:0;font-size:17px;line-height:26px;color:#FFFFFF;">[APPROVED HERO COPY]</p>
            </td>
          </tr>
          <tr id="context-intro">
            <td class="nv-pad nv-module" style="padding:40px;background:#F2F1EA;color:#101714;">
              <p style="margin:0;font-size:17px;line-height:26px;color:#101714;">[APPROVED CONTEXT COPY]</p>
            </td>
          </tr>
          <tr id="offer-slot">
            <td class="nv-pad nv-module" style="padding:40px;background:#FFFFFF;border-top:8px solid #BFD76D;color:#101714;">
              <!-- offer -->
            </td>
          </tr>
          <tr id="closing-band">
            <td class="nv-pad nv-module" style="padding:32px 40px;background:#F2F1EA;color:#101714;">
              <p style="margin:0;font-size:15px;line-height:23px;color:#626862;">[APPROVED CLOSING COPY]</p>
            </td>
          </tr>
          <tr id="brand-footer">
            <td class="nv-pad" style="padding:40px;background:#101714;border-top:4px solid #BFD76D;color:#FFFFFF;">
              <div style="font-size:20px;line-height:26px;font-weight:700;letter-spacing:2px;color:#FFFFFF;">NORDVELL</div>
              <p style="margin:20px 0 0;font-size:12px;line-height:19px;color:#D8DDD5;">[POSTAL_ADDRESS_REQUIRED]</p>
              <p style="margin:12px 0 0;font-size:12px;line-height:19px;color:#D8DDD5;">[LEGAL_TEXT_REQUIRED]</p>
              <div style="margin-top:24px;padding-top:16px;border-top:1px solid #626862;font-size:12px;line-height:20px;">
                <a href="[PRIVACY_URL_REQUIRED]" style="color:#FFFFFF;text-decoration:underline;">Privacy</a>
                <span style="color:#626862;"> &nbsp;|&nbsp; </span>
                <a href="[UNSUBSCRIBE_URL_REQUIRED]" style="color:#FFFFFF;text-decoration:underline;">Unsubscribe</a>
              </div>
            </td>
          </tr>
        </table>
      </td>
    </tr>
  </table>
</body>
</html>
```

When the hero has an approved destination, add one CTA after its paragraph using this treatment:

```html
<a href="[APPROVED_PRODUCT_URL_REQUIRED]" style="display:inline-block;margin-top:24px;padding:14px 24px;min-height:44px;box-sizing:border-box;background:#BFD76D;color:#101714;font-size:14px;line-height:18px;font-weight:700;text-decoration:none;border-radius:2px;">[APPROVED CTA LABEL]</a>
```

Omit the CTA when its destination is unresolved unless the complete layout specifically needs a creative-draft preview; in that case use the approved URL placeholder and keep `readyToWrite: false`.
