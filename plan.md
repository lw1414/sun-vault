# plan.md — SunVault System Build Plan

The map of the whole system, planned before touching any platform. Pulls from `brief.md`.
A lead moves left → right: **Ad → Landing page → Booking → Pipeline → Automations/Emails.**

---

## The funnel (how a lead moves)

| Stage | Tool | What happens |
|-------|------|--------------|
| The ad | Instagram carousel + Facebook ad (draft) | Stranger sees the smart-solar hook, clicks through |
| The landing page | Claude-built HTML, deployed | Reads the promise, clicks **Book a Solar Savings & Design Call** |
| The booking | GoHighLevel calendar | Picks a time → becomes a contact + appointment |
| The pipeline | GoHighLevel | Lands in **Consult Booked**, moves toward Won |
| The engine | GoHighLevel automations + pretty emails | Confirmation, nurture, follow-up run automatically |

---

## Pipeline stages (Part 1)

`New Lead` → `Consult Booked` → `Site Assessment` → `Proposal Sent` → `Won`  (+ `Lost`)

- **Deal value** on every card in USD (installs run $3,750–$12,150 ≈ ₱180k–₱680k).
- **Custom fields:** Lead Source, Monthly Electric Bill (PHP), Roof Type.
- 12–16 sample leads spread across the stages (fake data) — see `pipeline/sample-leads.csv`.
- Booking calendar: "Solar Savings & Design Call", 30 min, availability set, link saved to brief.

## Page promise (Part 2)

Headline: **"See exactly what you save — down to the watt — from day one."**
Sub: Premium solar + battery, installed by one dedicated engineer, with the SunVault Live app
for life. One main action on the page: **Book a Solar Savings & Design Call** (→ GHL calendar).

## Carousel + ad (Part 3)

6-slide carousel: hook → the blind-spot problem → the SunVault Live difference → savings proof
→ how it works (3 steps) → CTA. Facebook ad = carousel as creative, destination = landing link,
**stays a draft** (no spend, no card).

## Emails (Part 4)

1. **Booking confirmation** — "Your Solar Savings & Design Call is booked" (what to expect, prep).
2. **Pre-call nurture** — savings proof + SunVault Live app teaser, builds desire before the call.
Both email-safe HTML (inline CSS, table layout, 600px, first-name merge field).

## Automations (Part 5) — designed for SunVault

1. **Booking → Pipeline + Confirmation** (the connector): booking triggers add-to-pipeline
   (`Consult Booked`) + send booking-confirmation email.
2. **Pre-call nurture:** on booking, send the nurture email ~a day before the call.
3. **Aging follow-up:** lead in `Proposal Sent` with no movement for 3 days → friendly check-in.
4. *(Stretch)* **Hot-lead router:** high Monthly Bill → tag Hot + instant internal alert.

---

## Build order

1. brief.md ✔ → 2. plan.md ✔ → 3. Pipeline → 4. Landing page → 5. Carousel + ad →
6. Emails → 7. Automations → 8. Record Loom (client) + Raven (instructor).

## Safe mode (non-negotiable)

FB ad stays a **draft**. No real domain, no payments, no real contact data. Sample leads are
clearly fake. This is a showcase build.
