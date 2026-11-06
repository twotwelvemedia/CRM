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

The **(Client-Visible)** flags in docs/05 mark the tasks with Assigned To set to Client — **built and live across all 4 templates**, confirmed via fresh reload (docs/05).

**Podcast is structured differently**: instead of 7 fixed Task Groups for the whole engagement, each **episode gets its own Task Group** (e.g. "Episode 12"), created fresh every cycle, so the current episode's status stays visually separate from past ones. See the Podcast section of `docs/05-project-templates.md`.

## What the client actually experiences

1. Gets a Portal Access Invitation email (sent manually by the team, or via an Automation) the first time they need portal access — sets a password on first click.
2. Logs into the Portal with that password going forward (desktop or phone).
3. Lands on the **Multi-Purpose Client Dashboard** — their branded landing page with a Dashboard Summary, Easy Navigation buttons (Send a Message / Book a Meeting / Your Agreements), a Client Tasks widget, a Projects widget, file upload/download, and the Client FAQs Knowledge Base (docs/10).
4. The Client Tasks widget shows only tasks where Assigned To = Client on their Project(s) — see the gap note above.
5. Can view/download files, upload files back, view and pay invoices, and message the team — all from the same portal login.

## Progress tracking: what's native vs. what's a separate file

**Built and live, zero maintenance:** two native widgets on the Multi-Purpose Client Dashboard already give a baseline view of progress —
- **Client Tasks** widget — raw list of tasks flagged Assigned To = Client.
- **Projects** widget — a live **% COMPLETE** badge per project, calculated from real task completion. No setup beyond what's already built.

**Built and live — generic process explainer, embedded directly:** the Multi-Purpose Client Dashboard now has a "How a project moves through our studio" section (its own Row, above the Welcome banner), showing all 7 Base Template phases as a numbered journey, on-brand with the rest of the portal. It's the **same for every client** — not personalized to any one project's current stage, since the Dashboard is one shared page everyone sees. Confirmed live via fresh reload. See "How it's embedded" below for why this is an uploaded image rather than live HTML, and how to update it.

**Optional, friendlier *personalized* tracker:** for a client-specific "you are here" view (not just the generic explainer above), `templates/client-portal/project-status-tracker.html` is a standalone, self-contained status page showing the same 7-phase journey (or the 5-step episode flow for Podcast) with a current-stage marker set per client. It has no connection to SuiteDash's data — duplicate it per client/project, edit the `TRACKER_CONFIG` block at the bottom of the file to set the current stage, and either host it as an unlisted page / Showit embed or just send the client the .html file directly. See the usage notes in the file's header comment.

### How the generic explainer is embedded (and why it's an image, not live HTML)

SuiteDash's Text Block editor strips `<style>` and `<script>` tags from anything pasted into its HTML source view (confirmed by testing — a `<style>` block and a `<script>` tag both vanish on save; inline `style="..."` attributes survive fine). An `<iframe>` *does* survive — SuiteDash recognizes it as a native "embed" block — but claude.ai's own hosting (used to build/preview the explainer page) sends `Content-Security-Policy: frame-ancestors 'self' ...`, which refuses to render inside anyone else's iframe. So the practical path that actually worked: render the page as a static image and upload it through the Text Block's native image uploader (toolbar → image icon → Upload).

Source file: `templates/client-portal/our-process.html` (same brand styling as the tracker file, but static — all 7 phases shown, nothing marked "current"). To update the embedded image after editing that file:
1. Render it to a PNG (e.g. `npx playwright screenshot` or any headless-browser screenshot of the `.op-wrap` element, ~760px wide, 2x scale for crispness).
2. In the Multi-Purpose Client Dashboard editor, open the existing explainer Text Block → Upload → replace with the new image.
3. Save the Text Block, then **Save & Keep Editing** on the dashboard itself — these are two separate saves; the block-level Save alone does not persist to the live page.
4. Verify via a fresh reload (not just the in-session preview) that the new image is actually live.

**Note for future sessions:** uploading any file/image to SuiteDash goes through `s3.wasabisys.com` directly (SuiteDash's storage backend, not `app.suitedash.com` itself). A sandboxed session's network policy may block that host by default — add it to the environment's allowed hosts if uploads hang at "Uploading..." with no progress.

**Tried and reverted — native Portal Pages gated by CRM Circle:** the obvious SuiteDash-native alternative to a generic shared explainer was 5 Portal Pages (one per production stage), each visible only to clients in a matching CRM Circle (Pre-Production/Production/Post-Production/Delivered/New Client — these Circles already exist under CRM → Circles), which would have given each client a genuinely personalized in-portal tracker. Moving a client's Circle membership would auto-switch which stage page they see, no external hosting needed. **This doesn't work**: SuiteDash's own Portal Page editor has a confirmed bug where the "Assign Circle(s)" selection is silently dropped from the save request, verified by inspecting the raw network payload — the UI shows the circle selected and reports a successful save, but the field is never actually sent. A manually-constructed request with the field added was accepted by the server fine, confirming this is a bug in SuiteDash's client-side save logic, not a permissions/plan limitation. Revisit this only if SuiteDash fixes it.

## Setup checklist

- [x] White-labeling configured (docs/01, Phase 0) so the portal carries your branding
- [x] Task Groups built into all 4 Project Templates, matching the phases in docs/05
- [x] Assigned To → Client (+ Request Client Approval on the 4 sign-off tasks) set on all 13 (Client-Visible)-flagged tasks across the 4 templates, confirmed via fresh reload
- [ ] Test once real projects exist: create a test Project from a template, invite a test Client contact, confirm those tasks show in their portal's Client Tasks widget
