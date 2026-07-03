# Automation Designs — SunVault

Every automation is **a trigger, then actions**. These are designed for SunVault specifically:
they run on the pipeline from Part 1 and send the pretty emails from Part 4. Build 2–3 (the
4th is a stand-out stretch).

---

## A1 — Booking → Pipeline + Confirmation  *(the connector — build this one)*

**Why:** this is what turns a landing-page booking into a live lead on your board. Without it,
nothing connects.

- **Trigger:** Customer books an appointment on the **Solar Savings & Design Call** calendar.
- **Actions:**
  1. Create/Update opportunity → pipeline **SunVault — Residential Solar**, stage **Consult Booked**.
  2. Set **Lead Source** = the source (or "Website/Booking").
  3. Send email **01 — Booking Confirmation** (the pretty HTML from Part 4).
  4. *(optional)* Add tag `booked-call`.

## A2 — Pre-call nurture  *(build this one)*

**Why:** a booked lead who shows up warm closes far better than a cold one. This builds desire
before the call.

- **Trigger:** Appointment booked (same calendar) — OR contact tagged `booked-call`.
- **Actions:**
  1. **Wait** until ~1 day before the appointment (or Wait 1 hour for a fast first touch).
  2. Send email **02 — Pre-call Nurture** (savings proof + SunVault Live teaser).
  3. *(optional)* If appointment status = confirmed, stop; else send a gentle reminder.

## A3 — Aging follow-up on stalled proposals  *(build this one)*

**Why:** deals go cold in "Proposal Sent" when no one chases them. This keeps money from
slipping through the cracks — the same idea real firms use on unpaid invoices.

- **Trigger:** Opportunity enters stage **Proposal Sent**.
- **Actions:**
  1. **Wait 3 days.**
  2. **If/Else:** has the opportunity moved out of Proposal Sent?
     - **No →** send a friendly check-in email ("any questions on your SunVault design?") and
       create a task for the engineer to call. *(optional: notify internally)*
     - **Yes →** end (they're moving; leave them alone).

## A4 — Hot-lead router by monthly bill  *(STRETCH / stand-out)*

**Why:** a homeowner paying ₱18,000+/month is a high-value, high-intent lead — respond instantly.
Reuses the hot-lead pattern from your `D2/` Make work.

- **Trigger:** New contact created / new lead from the form.
- **Actions:**
  1. **If/Else** on **Monthly Electric Bill**:
     - **>= ₱18,000 (Hot) →** tag `hot-lead`, send instant speed-to-lead email, notify internally
       (email/Slack/WhatsApp), optionally push to a Google Sheet alert log (Make/n8n).
     - **< ₱18,000 (Standard) →** standard nurture path.
- Can be built in GHL, or in **Make/n8n** if you'd rather show that skill (you already have the
  pattern from Day 2/Day 3).

---

### Wiring checklist
- [ ] A1 sends email 01 and lands the lead in **Consult Booked**.
- [ ] A2 sends email 02 before the call.
- [ ] A3 branches on movement out of **Proposal Sent**.
- [ ] Each trigger is real (a booking or a pipeline move), not "on nothing".
- [ ] At least one automation sends a **pretty Part 4 email** (A1 and A2 both do).
