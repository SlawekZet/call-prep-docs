# Screenshots needed for the Integrations docs

Each `.mdx` page carries a marker at the exact spot a screenshot belongs, e.g.

```mdx
{/* SCREENSHOT hs-1 — spec in SCREENSHOTS.md */}
```

Take the shot, save it as `images/integrations/<filename>`, then replace the
marker with:

```mdx
<Frame caption="Short caption">
  <img src="/images/integrations/<filename>" alt="Descriptive alt text" />
</Frame>
```

## House rules for every shot

- **Browser:** light theme, no browser chrome (no URL bar, no bookmarks, no
  extensions), 1440 px wide viewport. Crop to the card or section named below —
  never the full page with empty space around it.
- **Format:** PNG, 2× device pixel ratio (a 900 px-wide card becomes an 1800 px
  file). Keep each file under ~400 KB.
- **Redact before saving:** real customer names, real lead email addresses, phone
  numbers, HubSpot portal IDs, the `li_at` cookie field, and anything under
  "Technical details". Replace with plausible fake data rather than black boxes —
  a blurred screenshot teaches nothing. Company name in the demo account can stay.
- **State:** use a demo account with realistic-looking data. Empty states and
  zeroed counters make the product look broken.
- **Consistency:** the same account, the same product name and the same theme
  across all shots.

---

## HubSpot — `integrations/hubspot.mdx`

### hs-1 · Connected HubSpot card
- **File:** `hubspot-connected.png`
- **Where:** Dashboard → Integrations → HubSpot
- **State:** HubSpot connected to a product
- **Must show:** the green *Connected* badge, Product, HubSpot user, HubSpot
  account, Connected date, and the grey line below the card that says new
  contacts reach the Autopilots through this connection
- **Redact:** portal ID → `12345678`, HubSpot user → a demo address
- **Crop:** the HubSpot card plus the explanatory line beneath it

### hs-2 · What CallPrep writes onto the contact
- **File:** `hubspot-timeline.png`
- **Where:** HubSpot itself → a contact record → Activity timeline
- **State:** a contact that received at least one email and one LinkedIn touch
  from an Autopilot, so both shapes are visible
- **Must show:** one *Email* activity with a real subject line, and one *Note*
  from a non-email channel — enough of each that the reader recognises the format
- **Redact:** contact name and email → demo values (keep them consistent with the
  rest of the shots)
- **Crop:** two or three timeline entries, no HubSpot left/right sidebars

### hs-3 · The waiting queue
- **File:** `autopilot-queue.png`
- **Where:** Dashboard → Autopilot → the *Queue — N waiting* row → open it
- **State:** at least three leads in *Waiting* with a visible "~Xh left before
  abandoned", and the *Abandoned* tab reachable in the shot
- **Must show:** both tabs, the per-lead countdown
- **Redact:** lead emails → demo values

---

## LinkedIn — `integrations/linkedin.mdx`

### li-1 · The three ways to connect
- **File:** `linkedin-connect.png`
- **Where:** Dashboard → Integrations → LinkedIn, with **no seat connected**
- **Must show:** the *Connect account* button, the Chrome-extension block, and
  the collapsed "Sign in to LinkedIn with Google? Connect without a password"
  link — all three options in one frame
- **Note:** if a seat is already connected on your account, take this on a fresh
  demo account; the empty state is the point of this shot

### li-2 · Seat limits and schedule
- **File:** `linkedin-schedule.png`
- **Where:** Dashboard → Integrations → LinkedIn, a **connected** seat expanded
- **Must show:** account name with the *connected* status, Timezone, Send
  from/until, Daily limit set to 20, the *Send on weekends* toggle, and the
  Pause / Disconnect controls
- **Redact:** the LinkedIn account name → a demo name

### li-3 (optional) · The risk confirmation
- **File:** `linkedin-risk-modal.png`
- **How to trigger:** set *Send until* to 23:00 (or switch weekends on) and click
  Save — the blocking confirmation appears
- **Must show:** the full modal text and both buttons
- **Where it would go:** next to the "Sending limits" warning in the page. Add it
  only if the section reads as if the confirmation might be a soft warning.

---

## Email — `integrations/email.mdx`

### em-1 · The mailbox list
- **File:** `email-mailboxes.png`
- **Where:** Dashboard → Integrations → Email
- **State:** **two** mailboxes connected — one Gmail marked *✉ Replies here*, one
  other provider — both collapsed
- **Must show:** the "N of M mailboxes" counter, both rows with provider and
  `N/day`, the accent border on the primary, and the *Add another mailbox* button
- **Redact:** both addresses → demo addresses on a demo domain

### em-2 · Sender identity and signature
- **File:** `email-signature.png`
- **Where:** Settings → Outreach → Email signature
- **State:** identity **complete** (name, company, postal address filled in), so
  the card shows a finished preview rather than the hold warning
- **Must show:** the source choice (from profile / pasted HTML / none), the
  layout options, and the live preview on the right with the signature and the
  identity line under it
- **Redact:** postal address → a plausible fake address; keep the demo company

### em-3 · One mailbox's settings
- **File:** `email-mailbox-settings.png`
- **Where:** Dashboard → Integrations → Email → one row expanded
- **Must show:** Daily limit, *Of which imported*, *This mailbox sends*, *Collect
  replies here*, *Pause this mailbox*, and the working-hours block
- **Bonus:** if you have a mailbox connected less than a week ago, take it on that
  one so the `5/day · warming up` state and the warm-up note are visible; otherwise
  a second shot `email-warmup.png` of just that row is worth having

---

## WhatsApp — `integrations/whatsapp.mdx`

### wa-1 · Connecting the number
- **File:** `whatsapp-connect.png`
- **Where:** Dashboard → Integrations → WhatsApp with no number connected, then
  click *Connect WhatsApp* — the shot is the **QR page that opens**
- **Must show:** the QR code and the instruction text around it
- **Redact:** blur or replace the QR code itself — a live code is a live login.
  Swap in a dummy QR image if in doubt.

### wa-2 · Phone number source
- **File:** `whatsapp-phone-source.png`
- **Where:** Dashboard → Integrations → WhatsApp, number connected
- **State:** two properties listed in order (e.g. *Mobile phone number*, then
  *Phone number*)
- **Must show:** the ordered rows with the up/down/remove buttons, and the
  explanatory line above them

### wa-3 · Warm-only policy
- **File:** `whatsapp-warm-only.png`
- **Where:** the *Who can be messaged* card on the same page
- **State:** warm-only **on** (the default), so the shot documents the safe state
- **Must show:** the toggle labelled "Warm leads only (recommended)" and the full
  explanatory paragraph under it
- **Optional second shot** `whatsapp-cold-modal.png`: the blocking confirmation
  that appears when switching warm-only off, with its full text

---

## Telegram — `integrations/telegram.mdx`

### tg-1 · Connecting the account
- **File:** `telegram-connect.png`
- Same as wa-1, on the Telegram page. **Blur or replace the QR code.**

### tg-2 · Handle source
- **File:** `telegram-handle-source.png`
- **Where:** Dashboard → Integrations → Telegram, account connected
- **State:** a custom HubSpot property (e.g. *Telegram username*) selected
- **Must show:** the ordered list and the line explaining that a phone number
  will not work here
- **Bonus:** a second shot of the HubSpot property itself
  (`telegram-hubspot-property.png`, HubSpot → Settings → Properties → the custom
  single-line text field) would make step 2 self-explanatory

### tg-3 · Warm-only policy
- **File:** `telegram-warm-only.png`
- Same as wa-3, on the Telegram page.

---

## Nice to have, not required

- **`autopilot-list.png`** — Dashboard → Autopilot with two or three Autopilots,
  their counters and the *Queue — N waiting* row. Would give
  `integrations/overview.mdx` a picture of where all this comes together.
- **`autopilot-capacity.png`** — the email capacity bar with the organic vs
  imported split visible, for the "First emails come first" section of the Email
  page.

---

## Autopilot — `autopilot/*.mdx`

### ap-1 · The builder, open on a new Autopilot
- **File:** `autopilot-builder.png`
- **Where:** Dashboard → Autopilot → **Build from scratch**
- **State:** name filled in (`Agencies — Poland`), one filter rule set, Email and
  LinkedIn on, two or three touches in the sequence — a builder that looks used,
  not blank
- **Must show:** the four cards in order (Name · Who should it contact? · Where can
  it reach out? · the sequence), and the save bar at the bottom of the frame
- **Crop:** the form column only, no sidebar

### ap-2 · Show example
- **File:** `autopilot-show-example.png`
- **Where:** the same builder → **Show example** on the first email touch
- **Must show:** the rendered email — greeting, body, and the signature block
  underneath — next to (or under) the angle that produced it
- **Why it matters:** this is the shot that sells the product. Use a lead whose
  research is genuinely good, so the example reads like something a person wrote
- **Redact:** the example lead's name and company → demo values

### ap-3 · A lead's timeline in Activity
- **File:** `autopilot-activity-lead.png`
- **Where:** Dashboard → Autopilot → **Activity** → expand one lead
- **State:** a lead with a **mixed** history — at least one sent message, one
  skipped touch **with a visible reason**, and one still scheduled
- **Must show:** the reason text on the skipped touch (this is the whole point of
  the shot), and the sent message body
- **Redact:** lead name, email, company → demo values

### ap-4 · The queue
- **File:** `autopilot-queue.png`
- **Where:** Dashboard → Autopilot → the **Queue — N waiting** row
- **Must show:** both tabs (Waiting / Abandoned) and the per-lead countdown
- *(Same shot as hs-3 above — take it once and reference it from both pages.)*

### ap-5 · Autopilot settings
- **File:** `autopilot-settings.png`
- **Where:** Dashboard → Autopilot → the gear icon
- **Must show:** all three blocks in one frame — Queue wait time with an option
  selected, the lateness options with **Off** selected, and both *Addresses to
  skip* checkboxes

### ap-6 · A template, expanded
- **File:** `autopilot-template.png`
- **Where:** Dashboard → Autopilot → **📚 Templates** → expand one
- **Must show:** the sequence timeline across the top, a few steps with their
  angles beneath it, and the **Use this template** button

### ap-7 · Analytics
- **File:** `autopilot-analytics.png`
- **Where:** Dashboard → Autopilot → **📈 Analytics**
- **State:** an account with at least a few weeks of history and a non-zero
  responded rate — zeros teach nothing
- **Must show:** the outcome tiles, the responded rate, and the weekly chart with
  bars and the rate line

---

## Chrome extension — `extension/*.mdx`

### ext-1 · The side panel
- **File:** `extension-panel.png`
- **Where:** the extension open beside a normal page (a LinkedIn profile or a CRM
  record — something that makes the context obvious)
- **State:** signed in, a couple of upcoming meetings listed, at least one already
  researched
- **Must show:** the panel in place next to the page, so the reader understands it
  sits beside their work rather than replacing it
- **Redact:** meeting titles and attendee names → demo values. **Check the host
  page for customer data too** — this is the one shot where the background is part
  of the image

### ext-2 · Meetings with automatic research on
- **File:** `extension-meetings.png`
- **Where:** the extension's meeting list, or Settings → auto research
- **Must show:** either the meeting cards with research attached, or the
  auto-research toggle **on** with the line about one credit per research
- **Optional companion** `extension-battlecard.png`: the battlecard email itself,
  opened on a phone or in a mail client. Worth more than either of the above —
  it is the thing people actually keep
