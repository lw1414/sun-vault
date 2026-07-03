# Runbook 01 — Pipeline + Calendar (GoHighLevel)

**Goal:** a pipeline with 5 stages + Lost, 16 leads across it, and a booking calendar whose
link you save into `brief.md`. Screenshot each ✅ step into `D5/`.

> New screen? Tell your AI what you're trying to do and ask it to walk you through the exact
> screen you're on, then bring any error back. Screens change; the intent below does not.

---

## A. Create the custom fields (do this first, so import can map them)

1. **Settings → Custom Fields → Add Field** (Contact).
2. Create three fields:
   - `Lead Source` — Dropdown (Single) — options: Facebook Ad, Instagram, Referral, Website
   - `Monthly Electric Bill` — Number
   - `Roof Type` — Dropdown (Single) — options: Asphalt Shingle, Tile, Metal
3. 📸 **Screenshot →** `D5/part1-custom-fields.png`

## B. Build the pipeline

1. **Opportunities → Pipelines → + Add Pipeline** (or Settings → Pipelines).
2. Name it **SunVault — Residential Solar**.
3. Add stages in this order, then Save:
   `New Lead` · `Consult Booked` · `Site Assessment` · `Proposal Sent` · `Won` · `Lost`
4. 📸 **Screenshot →** `D5/part1-pipeline-stages.png`

## C. Import the sample leads

1. **Contacts → ⋯ / Import Contacts → Upload** `pipeline/sample-leads.csv`.
2. Map columns: First Name, Last Name, Email, Phone → standard fields;
   Lead Source, Monthly Electric Bill, Roof Type → the custom fields from step A.
   (GHL contact import may not set the opportunity/stage or deal value directly — that's fine;
   see D to place them on the board.)
3. Finish the import. 📸 **Screenshot →** `D5/part1-contacts-imported.png`

## D. Place leads on the board (with deal values)

For each contact, create an opportunity on **SunVault — Residential Solar** in the stage and
with the deal value from the `Pipeline Stage` / `Deal Value` columns in the CSV. Two ways:

- **Fast:** Opportunities view → **+ Add Opportunity** → pick contact, pipeline, stage, and type
  the deal value + a lead-source note. Repeat for all 16 (Lost row optional).
- **Or** if your import flow offered opportunity mapping, use it and just spot-check.

Aim for the spread: New Lead ×4, Consult Booked ×4, Site Assessment ×3, Proposal Sent ×3,
Won ×2, (Lost ×1). The board header should now show a pipeline total near **$110k** (USD).

📸 **Screenshot →** `D5/part1-pipeline-populated.png`  (this is the money shot for the Loom)

## E. Build the booking calendar

1. **Calendars → Calendar Settings → + Create Calendar** (a simple/round-robin calendar).
2. Name: **Solar Savings & Design Call** · Duration **30 min** · buffer 15 min.
3. Set your **availability** for the week (a few slots is enough for the demo).
4. Save, then open the calendar and **Copy scheduling/booking link**.
5. Paste that link into `brief.md` → *System links → Booking calendar link*.
6. 📸 **Screenshot →** `D5/part1-booking-calendar.png`

---

### ✅ Done when
- Pipeline shows 16 leads across all stages with deal values (a real total in the header).
- A **Solar Savings & Design Call** calendar exists and its link is saved in `brief.md`.

*Stand out:* add a believable objection/next-step note on 2–3 cards, and set deal values so the
header total reads like a real month's pipeline.
