# Video plan for the docs

Written for whoever records these. Every clip has one job, sits on one page, and
can be re-recorded on its own when that part of the UI changes.

## Why short and separate, not one long walkthrough

A ten-minute product tour is watched once, by nobody, and dies with the next UI
change. Each clip below answers a single question a reader already has when they
are on that page. If a clip cannot be described in one sentence, it is two clips.

---

## The catalogue

| ID | Title | Length | Lives on | Priority |
| --- | --- | --- | --- | --- |
| **V1** | What the Autopilot actually does | 1:30 | Autopilot overview (+ marketing site) | **P1** |
| **V2** | Build your first Autopilot | 5:00 | Autopilot → Building one | **P1** |
| **V3** | Nothing was sent — how to find out why | 3:00 | Autopilot → Troubleshooting | **P1** |
| V4a | Connect HubSpot | 1:00 | `integrations/hubspot` | P2 |
| V4b | Connect LinkedIn | 1:15 | `integrations/linkedin` | P2 |
| V4c | Connect a mailbox | 2:00 | `integrations/email` | P2 |
| V4d | WhatsApp and Telegram | 1:30 | `integrations/whatsapp`, `/telegram` | P3 |
| V5 | Chrome extension and meeting battlecards | 2:00 | new extension page | P2 |
| V6 | Your first research (API) | 2:30 | `introduction/quickstart` | P3 |

**Record V1–V3 first.** They cover the part of the product with no documentation
at all, and V3 is the one that answers support tickets before they are written.

---

## Ground rules for every recording

**Account and data.** A demo account with realistic, boring data: two or three
Autopilots with names that read like a real team's (`Inbound signups`,
`Agencies — Poland`, `LinkedIn fallback`), a few hundred leads of history, one
connected LinkedIn seat, two mailboxes, HubSpot connected. Empty states make the
product look broken; fake names like `Test Test` make it look unfinished.

**Redactions — decide before recording, not in editing.** Real lead names,
addresses, phone numbers and portal IDs get replaced in the demo account itself,
so nothing has to be blurred afterwards. Blur reads as "something went wrong
here". Same rules as `SCREENSHOTS.md`.

**Picture.** 1440×900 recording area, light theme, no browser chrome, no
bookmarks bar, no other extensions in the toolbar. Cursor highlight on, click
effects on, no zoom-and-pan whiplash — one slow zoom per clip at most.

**Sound.** One take per segment, no music. Silence between sentences is fine and
makes editing possible.

**Language.** English, matching the docs and the UI. A Polish voice-over over the
same footage is a later, cheap addition — record the screen once, cleanly.

**Segments.** Record each numbered block below as its own file. When the builder
gets a new card, one segment is re-recorded instead of the whole video.

**Never say a number the product does not enforce.** "Twenty invites a day" is
fine — it is a hard cap. "Usually replies within a day" is not.

**Publishing.** Host unlisted on YouTube (or Loom) and embed on the page inside a
`<Frame>`. Keep the source files — a re-record is a segment swap, not a new
project.

```mdx
<Frame caption="Build your first Autopilot (5 min)">
  <iframe
    className="w-full aspect-video rounded-xl"
    src="https://www.youtube.com/embed/VIDEO_ID"
    title="Build your first Autopilot"
    allowFullScreen
  />
</Frame>
```

---

# V2 — Build your first Autopilot (full script)

**Length:** ~5:00 · **Goal:** the viewer can build and enable an Autopilot that
contacts the right people and says something true about them.

## Before you hit record

- [ ] HubSpot connected, product filled in under **Settings → Product**
- [ ] One LinkedIn seat *connected*, one mailbox *verified* and past warm-up
- [ ] Sender identity complete, so no "Emails are on hold" banner appears
- [ ] At least one existing Autopilot with real history, so the list is not empty
- [ ] A lead in the account with good research (a real LinkedIn post, a synergy)
      so **Show example** produces something worth reading
- [ ] Browser zoom 100%, sidebar expanded, notifications silenced

---

### Segment 1 — The starting point (0:00–0:25)

| Screen | Narration |
| --- | --- |
| **Dashboard → Autopilot**, list of existing Autopilots. Cursor rests, does not move. | "An Autopilot is three decisions: who gets contacted, what is said to them, and when it stops. Everything else — the research, the writing, the sending, the limits — happens on its own." |
| Slow scroll to the bottom of the list, stopping on **Start from a template** and **Build from scratch**. | "You can start from a template or from scratch. I will build one from scratch, because that is the version where you see every decision." |

### Segment 2 — Name and who it targets (0:25–1:30)

| Screen | Narration |
| --- | --- |
| Click **Build from scratch**. Type a name: `Agencies — Poland`. | "Name it after who it targets, not what it sends. In three months this list will have eight rows and you will be reading it in a hurry." |
| Scroll to the lead filter. Open the property picker, pick a real property, choose an operator, set a value. | "The filter is what makes this Autopilot different from every other one. It reads your HubSpot contact properties — the same ones your team already fills in." |
| Add a second rule. Point at the AND/OR control. | "Add a second rule and you decide whether both have to be true, or either." |
| Hover the empty-filter state briefly (or say it over the finished filter). | "One thing worth knowing: an Autopilot with no filter matches everyone. That is occasionally what you want — a catch-all at the bottom of the list — and never what you want by accident." |

### Segment 3 — Channels (1:30–2:05)

| Screen | Narration |
| --- | --- |
| Toggle **Email** and **LinkedIn** on. | "Channels are where this Autopilot may send from. It only offers what you have actually connected." |
| Point at the per-channel reach note under the channels. | "This line is worth reading before you commit to a channel — it tells you how many of this Autopilot's leads can even be reached that way. A LinkedIn step is useless to a lead with no LinkedIn profile, and this is where you find that out, rather than two weeks later." |

### Segment 4 — Voice and goal (2:05–2:50)

| Screen | Narration |
| --- | --- |
| Open the voice card. Pick a tone. | "Tone changes how the messages sound. It never changes what they ask for." |
| Switch the goal to something that needs input, so the requirement appears. | "The goal is what every message is working towards — a reply, a booked meeting, a link you want them to open. If a goal needs something from you, like a calendar link, the Autopilot will not turn on until you give it. A goal with nothing behind it is a message that asks for nothing." |
| Fill in the lead context field. | "And this line is how these people reached you. It becomes the first sentence of the first message — 'I saw you signed up for…' — which is the difference between a cold email and an obvious one." |

### Segment 5 — The sequence (2:50–4:05)

| Screen | Narration |
| --- | --- |
| Add the first touch: day 1, Email. Write a real angle in the body field. | "Each touch is a day, a channel, and an angle. The angle is your instruction, not the final text — the message itself is written per lead, from that lead's research." |
| Point at the **Uses research** chips, toggle one or two. | "These pick what the message is grounded in: their post, the company, the fit with your product. Leave them alone and it uses a sensible default." |
| Click **Show example**. Wait for the rendered email, scroll it, including the signature underneath. | "This is the same code path that sends. Not a mock-up — an actual message for an actual lead of yours, with your signature under it. If you would not send this one, change the angle and look again." |
| Add a LinkedIn invite touch on day 1, then a LinkedIn message touch a few days later. | "LinkedIn works in two steps: the connection request, and then a message once they accept. The message waits for the acceptance on its own — you do not have to guess the gap." |
| Add one more email a few days out. | "Three or four touches over two weeks is a sequence. Twelve is a campaign nobody finished reading." |

### Segment 6 — When it stops (4:05–4:35)

| Screen | Narration |
| --- | --- |
| Scroll to **When should it stop?**. Check the reply condition. | "This is the part people skip and then regret. A reply stops everything, on every channel — that one should always be on." |
| Check the call/meeting condition and point at the CRM property condition. | "A logged call that connected, or a booked meeting, means someone on your side already picked this person up. And you can nominate any CRM property — when a lifecycle stage changes, the sequence ends." |
| Hover the LinkedIn-accepted condition without checking it. | "This one is a choice, not a default: an accepted connection request is a connection, not an answer. Turn it on if connecting is the goal. Leave it off if you plan to say something afterwards." |

### Segment 7 — Enable and what happens next (4:35–5:00)

| Screen | Narration |
| --- | --- |
| Save from the sticky bar, then toggle the Autopilot on in the list. | "Save, then turn it on. From here, a new contact in HubSpot that matches this filter gets researched and enrolled within about a minute." |
| Point at the **Queue — N waiting** row, then at the row's counters. | "Leads that do not match anything yet wait here rather than being thrown away. And these counters — leads, active, responded — are how you find out whether any of this worked." |
| End on the list, no outro card. | "That is one Autopilot. If nothing seems to be sending, the next video is the one you want." |

---

# V1 — What the Autopilot actually does (outline)

**Length:** 1:30 · **Goal:** someone who has never opened the product understands
the loop and what it costs them.

1. **(0:00–0:20) One real lead, backwards.** Open Activity on a lead who replied.
   Show the timeline: invite sent, email, reply, sequence stopped. "Nobody typed
   any of that."
2. **(0:20–0:50) Where it starts.** Cut to HubSpot, a contact being created.
   "Everything begins here. The Autopilot checks whether anyone wants this lead —
   and only researches the ones that match, so the rest cost nothing."
3. **(0:50–1:15) What it writes from.** Flash the research on that lead — the
   post, the synergy — then the message that used it. "Written per person, from
   what we actually found. If there is nothing credible to say, it says nothing
   rather than sending filler."
4. **(1:15–1:30) Where it ends.** The reply, the sequence stopping by itself, the
   note landing back on the HubSpot contact. "It stops the moment a human takes
   over. That is the whole product."

**No feature list, no UI tour.** This clip exists to make the next one worth
watching.

---

# V3 — Nothing was sent, how to find out why (outline)

**Length:** 3:00 · **Goal:** cut the "it isn't working" support thread down to
one link.

1. **(0:00–0:20) The four places to look**, named up front: the Autopilot row,
   Activity, the Queue, Upcoming sends.
2. **(0:20–1:00) The row.** The delivery chip — leads waiting for a first
   contact, the reach per channel. "A chip that says nothing means nothing is
   stuck. It only speaks when leads are sitting uncontacted."
3. **(1:00–1:50) Activity, one lead expanded.** Walk the timeline, then land on a
   *skipped* touch and read the reason out loud. Show two or three different
   reasons — no phone number, already connected, no credible angle. "Nothing is
   skipped silently. Every one of these carries its reason."
4. **(1:50–2:25) The Queue.** *Waiting* versus *Abandoned*, and what abandoned
   costs (nothing). "If a lead you expected never appeared, this is where it is —
   and the fix is usually the filter, not the Autopilot."
5. **(2:25–2:50) Capacity and Upcoming sends.** The daily cap, the queue behind
   it, first-messages-first. "Not sent yet is not the same as not sending. This
   tells you which one you are looking at."
6. **(2:50–3:00) The escape hatch.** Close one lead by hand from Activity.

---

# V4a–V4d — Connect a channel (per-page clips)

Same shape each time, 60–120 seconds, no narration beyond what is on screen:

1. Where the page is.
2. The connect click, all the way through the real consent or QR screen.
3. The one setting that matters on that channel — the daily limit for LinkedIn,
   the reply address for email, warm-only for WhatsApp and Telegram, the property
   picker for phone and handle.
4. What "connected" looks like when it worked.

**Do not narrate the safety limits in the clip.** They belong in the page text,
where they can be corrected without a re-record.

**Redaction warning:** the WhatsApp and Telegram clips contain a **live QR login
code**. Replace it in post with a still, or record against a demo account you
then disconnect.

---

# V5 — Chrome extension and meeting battlecards (outline)

Only worth recording once the extension page exists. Two minutes:

1. Install and sign in.
2. Research a prospect from the extension.
3. Connect Google Calendar and switch on automatic research.
4. **The payoff shot:** the battlecard email arriving before a real meeting.
   That email is the reason anyone installs this — it should be half the clip.

---

# V6 — Your first research (API)

The quickstart, executed: create the key, one `curl`, poll, read the fields that
matter. Split screen, terminal on the left, dashboard research log on the right so
the credit and the run appear in real time. Optional — the written quickstart
already works; this is for the buyer who wants to see it before signing up.
