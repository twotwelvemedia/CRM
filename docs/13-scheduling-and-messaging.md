# Scheduling & Messaging

**Correction from earlier (Plutio-era) planning — this whole file still needs a full rewrite pass, not done here.** The rest of this doc describes Plutio's Scheduler ("Settings → Scheduler," connecting Zoom/Meet/Teams directly, etc.), which doesn't exist in SuiteDash. The real mechanism, confirmed live:

- **Office → Scheduling → Generators** builds an **Appointment Generator** per meeting type (Discovery Call, Production Meeting, Pre-Production Strategy Session, etc.), each with its own duration, host/staff assignment, and availability.
- An Appointment Generator has **no shareable link of its own** — it only becomes bookable once attached to a **Booking Form** (Forms → Create Form → Booking), via that form's "Configure Appointment Generators" step. A Booking Form can hold one or several generators; if it holds more than one, the public page shows them as selectable cards (client picks which meeting type/staff member before picking a time).
- **Built and live:** two Booking Forms exist — "Schedule a Meeting with Marcus" and "Schedule a Meeting with Eric" — each wired to that staff member's generator(s). Each form's Link/Embed panel → Friendly URL gives a short alias under the account's custom domain:
  - Marcus: `https://clients.two-twelvemedia.com/bookmarcus`
  - Eric: `https://clients.two-twelvemedia.com/connecteric`
- The Client Portal's "Book a Meeting" button (docs/12) uses a third option — a native "Open Appointment Scheduling Pop-up" click-action that can attach Appointment Generators directly, no separate Form/link needed. See docs/12 for the fix made to that button (it shipped with no generators attached) and why it's wired to all 4 generators instead of just one.

## Scheduler (booking pages)

Build a separate booking page per meeting type under Settings → Scheduler — each gets its own duration, intake questions, and confirmation messaging:

| Booking page | Duration | Used for |
|---|---|---|
| Discovery Call | 30 min | New leads booking their first call — intake questions mirror Form 1 (project type, budget range, timeline) |
| Kickoff Call | 30 min | Won clients, right after Automation #1 creates their Project |
| Review/Feedback Call | 20 min | Optional — for clients who'd rather talk through revisions live instead of using Form 4 |
| Podcast Recording Session | Matches your typical episode length | Booking guest/host recording sessions (Podcast clients only) |

### Availability setup

1. Settings → Scheduler → set your working hours per day, buffer time between meetings, and any blocked vacation dates.
2. Connect Google Calendar or Outlook so existing commitments are automatically excluded from your available slots.
3. Connect Zoom, Google Meet, or Microsoft Teams — a video link is generated automatically and added to every booking confirmation and calendar invite.

Clients see your availability converted to their own timezone automatically — no manual back-and-forth needed. Every booking also triggers an automatic confirmation with calendar invite, a 24-hour reminder, and a day-of reminder — this is default Scheduler behavior, not something you need to build as an Automation.

### Where each booking link goes

- **Discovery Call** link → the confirmation/follow-up after Form 1 is submitted (Automation #2, docs/09) and in your own outreach.
- **Kickoff Call** link → added to the Welcome email (`templates/emails/welcome-email.md`) sent by Automation #1.
- Add a **"Book a Time"** link to the Client Portal (docs/10) so clients can self-serve a call anytime instead of messaging you to ask for one.

## Messaging (Conversations)

Plutio's native messaging is what powers the Client Portal's Messages section — clients message you directly, and you can reply in-app or straight from email (email replies post back into the conversation automatically).

- Any client message can be converted into a task in one click — use this whenever a message is actually an action item, instead of manually re-creating it as a task.
- Set your notification preferences under Settings → Notifications (30+ individual toggles across tasks, projects, communication, financial, and contacts). Turn on the "offline only" email option so you're not double-notified while you're actively working inside Plutio.

## Updates to earlier docs

- **Sales Pipeline (docs/02), Stage 2 "Discovery Call Scheduled"**: this is now driven by the client booking themselves through the Discovery Call Scheduler link, not manual back-and-forth.
- **Automation #2 (docs/09)**: update its action to also share the Discovery Call Scheduler link, not just notify Sales.
- **Client Portal (docs/10)**: the portal shows a message thread and a "Book a Time" link alongside progress, files, and invoices.
