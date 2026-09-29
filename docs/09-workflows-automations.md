# Workflows / Automations

Build these under Settings → Workflows (trigger → condition → action builder). Recreate each row below as one workflow. Email bodies referenced are in `templates/emails/`.

| # | Trigger | Action(s) | Notes |
|---|---|---|---|
| 1 | Deal enters "Won — Contract Signed" **and** Deposit Invoice marked Paid | Create Project from the Project Template matching the Deal's Project Type field → invite the Contact to the Client Portal (if not already active) → send Welcome email (`welcome-email.md`) → create task "Kickoff call" assigned to Producer | Core handoff from sales to production — this is the single most important automation in the system. Confirm your plan can trigger the portal invite as a Workflow action; if not, it's a manual click (see docs/12) |
| 2 | Form 1 "New Inquiry" submitted | Create Contact → create Deal in "New Lead" stage → tag with Lead Source (from form answer) → notify Sales/Account Manager | |
| 3 | Project task "Review link sent" is checked (Phase 5) | Send "Review Ready" email (`review-request-email.md`) with Portal link → create follow-up task "Check for feedback" due in 3 days | |
| 4 | Invoice becomes overdue | Day 0 and Day 7: send reminder email (`invoice-reminder-email.md`); Day 14: apply late fee + notify Producer | See docs/08 for the late fee policy this implements |
| 5 | Project task "Final files delivered" is checked (Phase 6) | Send Final Invoice if not already sent → create task "Send testimonial request in 3 days" | |
| 6 | Task "Send testimonial request" comes due | Send testimonial email (`testimonial-request-email.md`) with link to Form 5 | |
| 7 | Deal marked "Lost" | Apply the Lost Reason tag → create task "90-day follow-up" assigned to Sales | Keeps lost leads in a nurture cycle instead of disappearing |
| 8 | 1st of each month, for active retainer clients | Generate the recurring invoice (docs/08) → create a new "Monthly Cycle" task list from the Social Retainer template | |
| 9 | All tasks in a Project phase's task list are marked complete | Mark the matching Milestone complete | Keeps the client's portal progress bar accurate — see docs/12 for the full client login/progress-tracking setup |
