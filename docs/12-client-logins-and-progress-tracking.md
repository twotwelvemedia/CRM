# Client Logins & Progress Tracking

## How client logins work in SuiteDash

- Every Contact can be granted **Portal Access** — this is what gives them a login. Turn it on under Contacts → [select Contact] → Portal Access → Invite to Portal. SuiteDash sends its own invite email with a link to set a password; this is separate from the custom Welcome email in `templates/emails/welcome-email.md`, which is a friendly follow-up, not the credential itself.
- **Scope**: a client only ever sees their own Company's/Contact's Projects, Files, Invoices, and Messages — never other clients' data.
- **Multiple stakeholders per client**: if a Company has more than one person who needs access (e.g. a marketing director plus a finance contact), invite each person individually rather than sharing one login, and use Portal Roles (below) to control what each sees.

## Portal Roles

Create at least two under Settings → Client Portal Roles:

| Role | Sees |
|---|---|
| Primary Contact | Projects, Files, Invoices, Messages (full visibility) |
| Stakeholder (view-only) | Projects and Files only — no Invoices |

Assign the role when you send the portal invite.

## Where "grant portal access" fits in the workflow

This isn't automatic — treat it as an explicit step:

- `docs/05-project-templates.md` Phase 1 (Onboarding & Kickoff) now includes: **"Confirm client has portal login access (invite sent + accepted)."**
- Check whether your SuiteDash plan can fire the portal invite automatically as a Workflow action (Settings → Workflows → Actions list). If it can, add it to Workflow #1. If not, it's a 10-second manual click each time a deal closes — don't skip it, since it's the entire point of this setup.

## How clients actually track progress

SuiteDash gives you two mechanisms. Use both, at different levels of detail — don't just hand clients your internal task list.

### 1. Milestones — the client's main progress view

Milestones are the high-level, client-facing progress bar for a Project. Build **one Milestone per phase**, matching the phases already defined in `docs/05-project-templates.md`, for every Project Template:

1. Onboarding & Kickoff
2. Pre-Production
3. Production
4. Post-Production
5. Client Review & Revisions
6. Final Delivery
7. Wrap-up / Complete

As the project moves through each phase, mark the matching Milestone complete. The client's portal dashboard then shows a clean progress bar ("Post-Production — in progress") with none of your internal task-level clutter.

### 2. Client-visible tasks — for the few things they need to act on

For the handful of tasks where the client genuinely needs to see or act on something (not just watch progress), toggle that specific task to **Visible to Client** instead of exposing your whole checklist. `docs/05-project-templates.md` flags these inline in the Base Template — mainly:

- "Review link sent" (Phase 5)
- "Client sign-off received" (Phase 5)
- "Final files delivered" (Phase 6)

Leave everything else — equipment checks, internal QC, crew scheduling, post-mortems — as Team Only. Clients don't need your internal punch list; it just makes their portal confusing.

## Keeping Milestones in sync (Workflow #9)

Added to `docs/09-workflows-automations.md`:

| # | Trigger | Action | Notes |
|---|---|---|---|
| 9 | All tasks in a phase's task list are marked complete | Mark the matching Milestone complete | Keeps the client's progress bar accurate without a PM updating two places |

If your plan doesn't support triggering off "all tasks in a list complete," make "mark [Phase] milestone complete" the literal last checklist item in each phase instead, so updating the client view is part of finishing the phase, not a separate step someone forgets.

## What the client actually experiences

1. Gets an invite email → sets a password → logs into your branded portal (`portal.yourstudio.com` once white-labeling is set up, per `docs/10-client-portal.md`).
2. Lands on their Dashboard → sees their Project(s) listed.
3. Opens a Project → sees the Milestone progress bar, plus any tasks flagged Visible to Client (e.g. "Review your rough cut").
4. Can view/download Files, view and pay Invoices, and message you — all from the same login.

## Setup checklist

- [ ] Client Portal Roles created (Primary Contact, Stakeholder)
- [ ] Milestones added to every Project Template (7 per project, matching phases)
- [ ] Client-visible tasks flagged in each Project Template
- [ ] Portal-invite step present in Phase 1 of every Project Template
- [ ] Test: create a dummy Contact, invite to portal, confirm they see only their own project, the milestone bar, and the flagged client-visible tasks — nothing else
