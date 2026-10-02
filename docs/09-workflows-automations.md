# Automations

Build these under Plutio's Automations builder. Each automation is a **trigger** (an event in Plutio — a proposal signed, an invoice overdue, a task marked complete) paired with one or more **actions** (create an invoice, send a message, create a task, update a project, send a notification) — actions can chain from a single trigger. Email bodies referenced are in `templates/emails/`.

| # | Trigger | Action(s) | Notes |
|---|---|---|---|
| 1 | Sales Pipeline card enters "Won — Contract Signed" **and** Deposit Invoice marked Paid | Create Project from the Project Template matching the card's Project Type field → send Welcome email (`welcome-email.md`) with the client's portal link → create task "Kickoff call" assigned to Producer | Core handoff from sales to production — the single most important automation in the system |
| 2 | Form 1 "New Inquiry" submitted | Create Contact → create a card on the Sales Pipeline board in "New Lead" column → set Lead Source field from the form answer → send the Discovery Call Scheduler link (docs/13) → notify Sales/Account Manager | |
| 3 | Task "Review link sent" is marked complete (Task Group 5) | Send "Review Ready" email (`review-request-email.md`) with the client's portal link → create follow-up task "Check for feedback" due in 3 days | |
| 4 | Invoice becomes overdue | Day 0 and Day 7: send reminder email (`invoice-reminder-email.md`); Day 14: apply late fee + notify Producer | See docs/08 for the late fee policy this implements |
| 5 | Task "Final files delivered" is marked complete (Task Group 6) | Send Final Invoice if not already sent → create task "Send testimonial request in 3 days" | |
| 6 | Task "Send testimonial request" comes due | Send testimonial email (`testimonial-request-email.md`) with link to Form 5 | |
| 7 | Sales Pipeline card marked "Lost" | Set the Lost Reason field → create task "90-day follow-up" assigned to Sales | Keeps lost leads in a nurture cycle instead of disappearing |
| 8 | Podcast Subscription bills for the month | Create a new Episode Task Group from the Podcast template | Skip this for Podcast clients billed per-episode instead — they get a manual step each time an episode publishes |
| 9 | All tasks under a Task Group are marked complete | Add a final "Phase complete — notify client" task as the last item in each group, or trigger off group completion if the Automations builder supports it | Confirm whether "all tasks in a group complete" is an available trigger once you're actually in Automations — if not, the last-task-in-group convention is the fallback |
| 10 | Discovery Call booking confirmed via Scheduler | Create task "Prep for discovery call" assigned to Sales, due 1 hour before the meeting → notify Sales | Scheduler handles the client-facing confirmation/reminders automatically (docs/13) — this automation is just for your own prep |
