# Runbook 02 — Deploy the Landing Page + Wire Book-a-Call

**Goal:** the premium `landing-page/index.html` live on a public URL, with the book-a-call
button opening your GoHighLevel booking link. Screenshot into `D5/`.

> The page is a single self-contained `index.html` (all CSS/JS inline, fonts from Google).
> It works by double-clicking the file locally, and deploys anywhere static.

---

## A. Wire the booking link (do this before deploying)

The page has **4 book-a-call buttons**, all pointing to the placeholder `#BOOKING_LINK`.
Replace every one with your real GHL booking link from Runbook 01.

- Open `landing-page/index.html`, Find & Replace **`#BOOKING_LINK`** → your booking link
  (e.g. `https://api.leadconnectorhq.com/widget/booking/xxxxxxxx`). There are 4 occurrences.
- Save. (Tip: just ask me — "replace #BOOKING_LINK with <link>" — and I'll do it for you.)

📸 (optional) `D5/part2-booking-link-wired.png`

## B. Preview locally

Double-click `index.html` → it opens in your browser. Confirm:
- Brand navy/amber/green, the live monitor animates, the equalizer bars move.
- Every "Book a Solar Savings & Design Call" button opens your GHL calendar.
- 📸 **Screenshot →** `D5/part2-landing-hero.png` and `D5/part2-landing-full.png`
  (grab the hero, and a full-page scroll if your tool does it).

## C. Deploy (pick one — same as Week 1)

**Option 1 — Netlify Drop (fastest, no account math):**
1. Go to https://app.netlify.com/drop
2. Drag the **`landing-page/`** folder onto the page.
3. It gives you a live URL like `https://sunvault-xyz.netlify.app`. Done.

**Option 2 — GitHub Pages:**
1. New repo → upload `index.html` (and `assets/`).
2. Settings → Pages → deploy from `main` / root. Wait for the URL.

**Option 3 — Vercel:** `vercel` CLI or drag-drop import the folder.

> Stay in safe mode: do **not** connect a custom domain or take payments today. The free
> `*.netlify.app` / `*.github.io` URL is exactly what a draft ad should point to.

## D. Save the link + final check

1. Copy the deployed URL → paste into `brief.md` → *System links → Landing page link*.
2. Open the live URL on your phone too (it's responsive) and tap a book-a-call button.
3. 📸 **Screenshot →** `D5/part2-landing-live.png` (browser showing the live URL bar).

---

### ✅ Done when
- The page is live on a public URL, on-brand, with real copy (no placeholder text).
- Every book-a-call button opens your GHL booking calendar.
- The live URL is saved in `brief.md`.

*Stand out:* swap the hero's demo address/readings for numbers that match a "flagship" client,
or add a custom AI-generated hero image into `assets/` and reference it as a background.
