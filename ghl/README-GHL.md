# CFS booking page: how to put it into GoHighLevel

This folder is the new booking page (the "V3 Blue Interactive" design), ready to paste into the existing GHL funnel
page at https://taxscholarshipsecrets.com/. To see what it should look like, open `../v3/index.html` in a browser.
That preview and these files hold the same content.

All the page's styles are scoped under one class, `cfs-lp`, so they can't change the rest of your GHL page, and GHL's
styles can't change this page. That was tested against a deliberately hostile stylesheet (see `test-harness.html`).

## Pick ONE option

### Option A (recommended): one block, the whole page
Use this unless you need to edit sections separately inside GHL. It is the most faithful to the preview.

1. In the funnel page editor, add ONE new section. Set it to **Full Width**, with section, row and column
   **padding 0**, margins 0, and **no background** (no color, no image).
2. Add ONE **Custom Code** element to that column and paste in all of `ALL-IN-ONE.html`.
3. Do NOT also add `00-head.html` or `99-footer-scripts.html`. ALL-IN-ONE already has the fonts, styles and scripts.

### Option B: one GHL section per page section
Use this if the team wants to move, hide or edit sections one at a time in GHL.

1. **Page Settings > Tracking Code > Header:** paste `00-head.html` (fonts + styles).
   *Or* paste `00-custom.css` into the page's **Custom CSS** box instead. Use one, not both.
2. Create 12 GHL sections in this order. In each one, set it to **Full Width**, with section, row and column
   **padding 0**, margins 0, and **no background**. Add one **Custom Code** element and paste in the matching file:
   `01-header`, `02-hero` (includes the Reduce / Offset / Fund steps), `03-book` (includes the live calendar),
   `04-reviews`, `05-videos`, `06-fit`, `07-numbers`, `08-lance`, `09-faq`, `10-press`, `11-closer`, `12-footer`.
3. **Page Settings > Tracking Code > Footer:** paste `99-footer-scripts.html`. This runs the rotating steps and the
   click-to-play videos.
4. The white booking card (03) is designed to overlap the bottom of the blue hero (02). If the top of the card looks
   cut off, the GHL section holding 03 is hiding its overflow. Switch that section's overflow to visible if the editor
   allows it, or use Option A.

## Both options
- **Header and footer.** This page brings its own Legetty header (01) and footer with the compliance text (12).
  Remove GHL's own header and footer from this page, or keep them and delete 01 / 12. Don't show both.
- **Remove the old page's sections.** Remove the old hero, the "Scholarship House" subhead, the old calendar
  section, the three old featured cards, the old media grid and the "Don't wait until it's too late" closer.
  The page must end up with one H1 and one calendar.
- **Rename the calendar.** In **Calendars > Settings**, rename "Tax Scholarships 1 on 1 mtg" to
  **Tax & College Opportunity Review Call**. The calendar widget shows that name as its own header.
- **The calendar embed is the live one** (calendar `jz4PWYKlNfHjOEj0p1p5`, same as today). It sits inside `03-book`
  (and ALL-IN-ONE) with GHL's `form_embed.js`, which resizes it. Today's page embed also has `allow="payment"` on the
  iframe. The call is free, so it isn't needed, but it's harmless to add.
- **Keep the tracking.** Leave the page's existing tracking codes (Meta pixel, Hyros and anything else) in place.
  When you paste `00-head` / `99-footer-scripts`, add them next to the existing codes. Don't replace the codes.
- **SEO.** Set the title and description in the GHL page's SEO settings:
  - Title: `Tax Scholarships: 3 Steps to Pay for College Differently`
  - Description: `Book a Tax & College Opportunity Review and see how the Reduce, Offset, Fund framework could apply to your family's income, tax bill, college timeline, and retirement.`

  These files contain no noindex tag.
- **Logos.** The Legetty logos are embedded in 01 and 12, so nothing has to be uploaded. If you'd rather host them,
  upload `../v3/assets/legetty-white.png` / `legetty-navy.png` to Media and swap the `src`.

## Test before publishing (on a real phone, and on a desktop)
1. Tap every green button ("Pick a Time for My Review Call", "Book My Free Call"). Each one must scroll down to
   the calendar card. On a phone, the button in the hero should land on the calendar itself.
2. **Book a real test appointment** on the calendar, then confirm it shows up in GHL (and that the pixel/Hyros
   booking events fire as they do today). Cancel the test booking afterwards.
3. The Reduce / Offset / Fund box should change step every 5 seconds. It should pause while the mouse is over it and
   stop for good once a step is tapped.
4. Tap a testimonial video. It should start playing in place.
5. On a phone, check that the page doesn't scroll sideways.

## Still TODO (client)
- **Lance's photo.** In `08-lance`, replace the dashed "Lance photo (client to supply)" box (`.cfs-photo`) with
  his real headshot. No AI or stock faces.
- **Privacy Policy / Terms of Service links.** In `12-footer` they are `href="#"` placeholders. Point them to the
  canonical URLs.
- **Official rating widgets.** The Trustpilot and BBB ratings in `02-hero` and `04-reviews` are styled text stand-ins.
  Production must use the official Trustpilot TrustBox widget and BBB's dynamic Accredited Business seal.
- **Calendar rename** (see above).
- **Calendar logo.** The calendar widget still shows the old College Funding Secrets graduation-cap logo at its
  top. Swap it for the Legetty logo in the calendar's settings so the widget matches the page.
- **Booking window (FYI).** On 2026-10-03 the calendar offered one bookable day (Mon Oct 5), because it is set to
  book a few days out. That caps how many people can book from this page; widen it in the calendar's availability
  settings if that is not intended.

## For whoever edits the page later
Don't hand-edit these files. Edit `../v3/index.html`, then run `python3 ../tools/build_ghl.py` to regenerate this
folder. It rebuilds every file, including `test-harness.html`.
