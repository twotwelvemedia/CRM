# Scheduling & Messaging

Plutio has native features for both of these — you don't need a third-party scheduler or chat tool.

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
