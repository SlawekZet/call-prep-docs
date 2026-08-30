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
