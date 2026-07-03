# Runbook 04 — Pretty Emails into GoHighLevel

**Goal:** 1–2 branded, email-safe HTML emails living in GHL, tested, with the first-name merge
field filling in. Screenshot into `D5/`.

Files: `emails/01-booking-confirmation.html`, `emails/02-precall-nurture.html`.
Both are email-safe (table layout, inline CSS, 600px, no JS) and use the merge field
`{{contact.first_name}}`.

---

## A. Preview locally first

Double-click each `.html` → confirm it renders styled and on-brand (navy card, amber button,
live-readout block). This is what should land in the inbox.
📸 **Screenshot →** `D5/part4-email-design.png`

## B. Paste into GHL's email code builder

Recommended: build inside an **automation email step** so you can watch it render.

1. **Automations → create/open a workflow → add an Email action** (you'll wire triggers in
   Runbook 05; for now you just need the email to exist).
2. In the email step, open the **Builder** and choose the **Code / Custom HTML** option
   (sometimes "Import HTML" or a `</>` block). Screens change — if you can't find it, tell your
   AI "I need to paste custom HTML email code in GHL's email builder, where is it now?"
3. Paste the full contents of `01-booking-confirmation.html`. Watch it render in the preview.
4. Set the **subject**: `You're booked, {{contact.first_name}} — your SunVault call`
5. Repeat for `02-precall-nurture.html` in a second email step/template.
   Subject: `Before your call — solar you can actually watch`
6. 📸 **Screenshot →** `D5/part4-email-in-ghl.png` (builder showing the rendered email).

> **Merge field note:** GHL uses `{{contact.first_name}}`. It's already in the HTML (subject +
> body). If your sub-account uses a different token, swap it — ask me and I'll update the files.

> **Booking button:** both emails link to `#BOOKING_LINK`. Find & replace with your real GHL
> booking link (or ask me to do it) so the buttons work.

## C. Send yourself a test

1. Use **Send Test Email** to your own address.
2. Normal things to expect: a first send from a shared address may land in **spam** and take a
   few minutes — that's normal. Check it renders **styled, not plain text**, and that the
   first name fills in (send as a test contact that has a first name).
3. 📸 **Screenshot →** `D5/part4-email-test-inbox.png` (the styled email in your inbox).

---

### ✅ Done when
- At least one email is in GHL as styled HTML (both, ideally).
- A test send arrives looking designed and on-brand, not plain text.
- `{{contact.first_name}}` fills in correctly.

*Stand out:* keep the header/button/footer identical across both emails so every message is
unmistakably SunVault — a branded email *system*, not one-off emails.
