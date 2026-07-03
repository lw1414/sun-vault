# Runbook 05 — Build the Automations (GoHighLevel)

**Goal:** 2–3 automations, all designed by you for SunVault, each wired to a real trigger from
your pipeline/booking, at least one sending a pretty Part 4 email. Screenshot into `D5/`.

Designs live in `automations/automation-designs.md`. Build A1 + A2 + A3 (A4 is a stretch).

> Every automation = **a trigger, then actions.** Build in **Automations → Workflows → + Create**.

---

## A1 — Booking → Pipeline + Confirmation

1. New workflow → name **"A1 · Booking → Pipeline + Confirmation"**.
2. **Trigger:** *Appointment / Customer Booked Appointment* → filter to the **Solar Savings &
   Design Call** calendar.
3. **Action 1:** *Create/Update Opportunity* → pipeline **SunVault — Residential Solar**,
   stage **Consult Booked**.
4. **Action 2:** *Send Email* → select **01 — Booking Confirmation** (from Runbook 04).
5. *(optional)* *Add Tag* → `booked-call`. Save & **Publish**.
6. 📸 **Screenshot →** `D5/part5-a1-booking-connector.png`

## A2 — Pre-call nurture

1. New workflow → **"A2 · Pre-call Nurture"**.
2. **Trigger:** Appointment booked (same calendar) **or** Tag added `booked-call`.
3. **Action 1:** *Wait* → "1 day before appointment" (or Wait 1 hour for a first touch).
4. **Action 2:** *Send Email* → **02 — Pre-call Nurture**. Save & Publish.
5. 📸 **Screenshot →** `D5/part5-a2-nurture.png`

## A3 — Aging follow-up on stalled proposals

1. New workflow → **"A3 · Proposal Follow-up"**.
2. **Trigger:** *Opportunity Stage Changed* → stage = **Proposal Sent**.
3. **Action 1:** *Wait* **3 days**.
4. **Action 2:** *If/Else* → condition: opportunity stage **is still** Proposal Sent.
   - **Yes branch:** *Send Email* (friendly check-in) + *Create Task* "Call about SunVault design".
   - **No branch:** end.
5. Save & Publish. 📸 **Screenshot →** `D5/part5-a3-followup.png`

## (Stretch) A4 — Hot-lead router
Build in GHL (If/Else on **Monthly Electric Bill**) or in Make/n8n reusing your Day 2/3 pattern.
Tag `hot-lead`, instant email, internal alert. 📸 `D5/part5-a4-hotlead.png` (optional).

---

## Test it end-to-end (the money moment for your Loom)

1. Open your **booking calendar link** and book a test slot as a fake contact with a first name.
2. Watch: the contact appears on the pipeline in **Consult Booked**, and the **booking
   confirmation email** sends (check the contact's Conversations/Activity or your test inbox).
3. 📸 **Screenshot →** `D5/part5-test-run.png` (the automation history / contact timeline showing
   it fired).

---

### ✅ Done when
- 2–3 automations built, all your own, each on a real trigger from the pipeline/booking.
- At least one sends a pretty Part 4 email (A1 and A2 do).
- A test booking flows through: lead lands on the board + confirmation email sends.

*Stand out:* add A4's hot-lead routing (email + SMS/WhatsApp + Sheet log via Make/n8n) so the
system visibly "does all that" on camera.
