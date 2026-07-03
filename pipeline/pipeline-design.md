# Pipeline Design — SunVault

## Stages (the story a lead tells on the board)

| # | Stage | What it means | Moves forward when… |
|---|-------|---------------|---------------------|
| 1 | **New Lead** | Came from an ad/site, not yet talked to | They book a call |
| 2 | **Consult Booked** | Solar Savings & Design Call on the calendar | Call happens, site visit agreed |
| 3 | **Site Assessment** | Roof/energy assessment scheduled or done | Design finalized → proposal built |
| 4 | **Proposal Sent** | Priced proposal delivered | They sign |
| 5 | **Won** | Signed, install scheduled | — (celebrate) |
| — | **Lost** | Went elsewhere / not now | (kept for win-back) |

Keep it to these 5 + Lost — tight enough to read on camera, real enough to tell a story.

## Custom fields to add (Settings → Custom Fields, Contact)

- **Lead Source** (dropdown: Facebook Ad, Instagram, Referral, Website)
- **Monthly Electric Bill** (number, PHP) — powers the stretch "hot-lead router" automation
- **Roof Type** (dropdown: Concrete Deck, Metal, Clay Tile)
- **Roof Area** (number, sqm) — usable roof area for system sizing

## Deal values

Every card carries a value in **USD** ($3,750–$12,150 — premium PH solar + battery systems,
converted at ~₱56/$1). Once imported/added, the board header shows a real pipeline total
(~**$110k** across the active sample deals) — that's what makes it look like a live business.
The website displays these as **USD headline with ₱ underneath**; the GHL board runs in USD.

## Sample data

`sample-leads.csv` — 17 rows (16 active + 1 Lost) spread across all stages. All emails use the
`@fakemail-sunvault.com` domain and `+63-9xx-555-0xxx` phone numbers so nothing is a real person.

Distribution: New Lead ×4, Consult Booked ×4, Site Assessment ×3, Proposal Sent ×3, Won ×2, Lost ×1.

## Booking calendar

- Name: **Solar Savings & Design Call**
- Duration: 30 min · buffer 15 min · your availability set for the week
- This is the conversion point: a booking creates the contact + appointment automatically.
- After creating it, **copy the booking link into `brief.md`** (System links section).
