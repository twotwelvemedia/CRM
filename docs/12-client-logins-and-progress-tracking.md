# Client Portal Access & Progress Tracking

## How clients actually get in — password-based, invitation-triggered

**Correction from earlier (Plutio-era) planning:** this is the biggest mechanical difference from the original Plutio version of this package. Plutio clients got a no-password, repeat-use link. **SuiteDash clients set a password.** Confirmed via the live Add Contact form's own help text (quoted verbatim):

> "The Portal Access Invitation is an email that is sent to users, granting them immediate access to your Portal. It provides a uniquely coded link that will prompt the recipient to set their password and enter the Portal. When you add a new user, they will NOT be able to access the Portal until the Portal Access Invitation is sent."

In practice:
1. A Contact's **Role** is set to **Client** (or **Prospect**) — Leads don't get portal access.
2. At that point you choose whether to **Send Portal Access Invitation Immediately**, or hold off and trigger it later (manually, or via an Automation).
3. The invitation email contains a one-time coded link. Clicking it prompts the client to **set a password**.
4. From then on, it's a normal password-based login (via the Portal's login page) — not a repeat-use magic link like the old Plutio model.

This is a real (minor) onboarding step for the client — one password-set click the first time, then standard login after. Automation #2 (docs/09) handles the Contact-creation side of this when a new inquiry comes in; sending the actual invitation is still a manual or automation-triggered step, not automatic on Contact creation.

## Scope of what a client sees

A client only ever sees their own Project(s), files, invoices, and progress — never other clients' data. If a Company has more than one stakeholder who needs visibility (e.g. a marketing director plus a finance contact), add each person as their own Contact with their own Role/portal access.

## How progress tracking actually works

Progress is built from **Task Groups** inside each Project's Tasks area (docs/05) — same underlying mechanism as the Sales Pipeline board's stages.

**Correction from earlier (Plutio-era) planning:** there is no per-task "Private" flag in SuiteDash — see docs/05's "Client visibility" section for the full correction. The actual mechanism: a task's **Assigned To** field must be set to **Client** for it to surface in the client's portal (the "Client Tasks" dashboard widget); everything else (Assigned To any internal role or named staff) stays internal-only. A second toggle, **Request Client Approval?**, appears once Assigned To = Client — use it on sign-off/approval tasks specifically.

The **(Client-Visible)** flags in docs/05 mark which tasks need Assigned To switched to Client when a real Project is created from a template. **As of this writing, that switch hasn't been made yet in the 4 templates** (see docs/05's "Known gap" note) — it needs to be done by hand in the SuiteDash UI, either once in each template or per-project after Start from Template.

**Podcast is structured differently**: instead of 7 fixed Task Groups for the whole engagement, each **episode gets its own Task Group** (e.g. "Episode 12"), created fresh every cycle, so the current episode's status stays visually separate from past ones. See the Podcast section of `docs/05-project-templates.md`.

## What the client actually experiences

1. Gets a Portal Access Invitation email (sent manually by the team, or via an Automation) the first time they need portal access — sets a password on first click.
2. Logs into the Portal with that password going forward (desktop or phone).
3. Lands on the **Multi-Purpose Client Dashboard** — their branded landing page with a Dashboard Summary, Easy Navigation buttons (Send a Message / Book a Meeting / Your Agreements), a Client Tasks widget, a Projects widget, file upload/download, and the Client FAQs Knowledge Base (docs/10).
4. The Client Tasks widget shows only tasks where Assigned To = Client on their Project(s) — see the gap note above.
5. Can view/download files, upload files back, view and pay invoices, and message the team — all from the same portal login.

## Optional: a friendlier visual tracker

The native Client Tasks widget works, but it's a raw task list — not the clearest "where's my project" view for a client. `templates/client-portal/project-status-tracker.html` is a standalone, self-contained status page that shows the same journey (the 7 Base Template phases, or the 5-step episode flow for Podcast) as a simple step tracker with a "you are here" marker. It has no connection to SuiteDash's data — duplicate it per client/project, edit the `TRACKER_CONFIG` block at the bottom of the file to set the current stage, and either host it as an unlisted page / Showit embed or just send the client the .html file directly. See the usage notes in the file's header comment.

## Setup checklist

- [x] White-labeling configured (docs/01, Phase 0) so the portal carries your branding
- [x] Task Groups built into all 4 Project Templates, matching the phases in docs/05
- [ ] **Not yet done**: switch Assigned To → Client (+ Request Client Approval where noted) on the 13 (Client-Visible)-flagged tasks across the 4 templates — see docs/05's "Known gap" note for exactly which tasks and why this is still outstanding
- [ ] Test once real projects exist: create a test Project from a template, invite a test Client contact, confirm only the Assigned-to-Client tasks show in their portal's Client Tasks widget
