# New booking page: GoHighLevel setup guide

**For:** Daniel · **From:** Phil Glutting (Unicorn Marketers) · **Updated:** October 3, 2026

This is the new booking page for **https://taxscholarshipsecrets.com/**, ready to paste into the existing GHL funnel
page. It replaces what is on that page today.

- **See the finished page:** https://gostrategicmarketing-deployment.github.io/cfs-booking-concepts/full-v3/
- **All files (view with a Copy button, or download):** https://gostrategicmarketing-deployment.github.io/cfs-booking-concepts/ghl/

All of the page's styles are contained inside one wrapper (class `cfs-lp`), so they won't change anything else in your
GHL page, and GHL's own styles won't change this page. We tested that against a stylesheet built to break it.

## What's on the page, top to bottom

1. **Header:** Legetty logo.
2. **Hero:** "Book a free 30-minute call" label, the headline *Your Tax Bill Is Your Biggest Untapped Source of
   College Funding*, the line *Let us show you the 3 steps to pay for college without sacrificing your financial
   future*, the "Pick a Time for My Review Call" button, the income line, BBB A+ and Trustpilot 4.4 badges, the
   "As featured in" outlets, and the Reduce / Offset / Fund steps, which rotate every 5 seconds.
3. **Booking card:** the live calendar (the same one on the page today) plus what we cover on the call.
4. **What Families Say:** 4 written reviews (2 Trustpilot, 2 BBB) under the Trustpilot and BBB rating cards.
5. **Hear It From Families:** 7 testimonial videos from Lance's YouTube and Vimeo. They load only when tapped, so the
   page stays fast.
6. **Who the review is for / not a fit.**
7. **Numbers to have ready for the call.**
8. **Meet the Founder:** Lance's bio.
9. **Common questions.**
10. **In the News:** 32 press features, each linked to its article.
11. **Closing call to action.**
12. **Footer:** Legetty logo, compliance text, copyright, Privacy and Terms links.

## Pick ONE way to install it

### Option A (recommended): the whole page in one block
Use this unless you need to edit sections one at a time inside GHL. It matches the preview most closely.

1. In the funnel page editor, add ONE new section. Set it to **Full Width**, with section, row and column
   **padding 0**, margins 0, and **no background** (no color, no image).
2. Add ONE **Custom Code** element to that column and paste in all of **`ALL-IN-ONE.html`**.
3. Don't also add `00-head.html` or `99-footer-scripts.html`. ALL-IN-ONE already includes the fonts, styles and
   scripts.

### Option B: one GHL section per page section
Use this if you want to move, hide or edit sections separately in GHL.

1. **Page Settings > Tracking Code > Header:** paste **`00-head.html`** (fonts and styles).
   *Or* paste **`00-custom.css`** into the page's **Custom CSS** box instead. Use one, not both.
2. Create 12 GHL sections in this order. Set each one to **Full Width**, with section, row and column
   **padding 0**, margins 0, and **no background**. Add one **Custom Code** element to each and paste in the matching
   file: `01-header`, `02-hero`, `03-book`, `04-reviews`, `05-videos`, `06-fit`, `07-numbers`, `08-lance`, `09-faq`,
   `10-press`, `11-closer`, `12-footer`.
3. **Page Settings > Tracking Code > Footer:** paste **`99-footer-scripts.html`**. It runs the rotating steps and
   the click-to-play videos.
4. The white booking card (03) is designed to overlap the bottom of the blue hero (02). If the top of the card looks
   cut off, the GHL section holding 03 is hiding its overflow. Set that section's overflow to visible if the editor
   allows it, or use Option A.

## For both options

- **Header and footer.** This page brings its own Legetty header (01) and footer with the compliance text (12).
  Either remove GHL's own header and footer from this page, or keep them and leave out 01 / 12. Don't show both.
- **Remove the old page's content:** the old hero, the "Scholarship House" subhead, the old calendar section, the
  three old featured cards, the old media grid, the old testimonials and the "Don't wait until it's too late" closer.
  The page should end up with one headline and one calendar.
- **Keep the tracking.** Leave the page's existing tracking codes (Meta pixel, Hyros, anything else) in place. If you
  use Option B, add `00-head` / `99-footer-scripts` next to the existing codes. Don't replace them.
- **SEO settings** (GHL page settings):
  - Title: `Tax Scholarships: 3 Steps to Pay for College Differently`
  - Description: `Book a Tax & College Opportunity Review and see how the Reduce, Offset, Fund framework could apply to your family's income, tax bill, college timeline, and retirement.`
- **Logos** are built into the code (01 and 12), so there's nothing to upload.

## Calendar settings (in GHL Calendars)

- **Rename the calendar** from "Tax Scholarships 1 on 1 mtg" to **Tax & College Opportunity Review Call**. The widget
  shows that name as its heading, and the page and the ads call it that.
- **Swap the calendar's logo.** The widget still shows the old College Funding Secrets graduation-cap logo. Change it
  to the Legetty logo.
- **Booking window (FYI).** On October 3 the calendar offered only one bookable day (Mon, Oct 5), because it's set to
  book a few days out. That limits how many people can book from this page. Widen it if that isn't intended.
- The embed itself is the live calendar already on the page (`jz4PWYKlNfHjOEj0p1p5`), so nothing changes there.

## Test before publishing (on a real phone and on a desktop)

1. Tap every green button ("Pick a Time for My Review Call", "Book My Free Call"). Each must scroll down to the
   calendar. On a phone, the hero button should land on the calendar itself.
2. **Book a real test appointment**, confirm it shows up in GHL and that the pixel and Hyros booking events fire as
   they do today, then cancel it.
3. The Reduce / Offset / Fund box should change step every 5 seconds, pause while the mouse is over it, and stop once
   a step is tapped.
4. Tap a testimonial video. It should play in place.
5. On a phone, check that the page doesn't scroll sideways.

## Still needed from your side

- **Lance's headshot.** In `08-lance` (and ALL-IN-ONE), replace the dashed "Lance photo (client to supply)" box with
  his real photo. Or send it to Phil and we'll build it in.
- **Privacy Policy and Terms of Service links.** In the footer they are placeholders (`href="#"`). Point them to the
  real pages.
- **Official rating widgets.** The Trustpilot and BBB badges are styled text for now. On the live page, please use
  Trustpilot's official TrustBox widget (your Trustpilot plan includes it) and BBB's official Accredited Business
  seal. Both keep themselves up to date.
- **Footer legal name.** The copyright line says "College Funding Education, LLC". Tell us if it should name a
  different company (for example Legetty Educational Services, Inc., the name on your Trustpilot profile).
- **Kevin Harrington video.** If Kevin was paid or compensated for his endorsement, the FTC expects that to be
  disclosed next to his video. Let us know and we'll add the line.
- **Micaela Karlson video.** It shows with her name only. The caption on today's page says the program "paid for
  itself" with one year of tax savings, which your own funnel brief rules out for testimonials.

## Changes later

Please don't hand-edit the code files. Send changes to Phil. We update the page and regenerate every file so
they stay in sync with the preview.
