# Client Portal Access & Progress Tracking

## How clients actually get in — no traditional login

This is the biggest mechanical difference from the original SuiteDash version of this package: **Plutio clients don't create an account or set a password.** Each client gets a private, unique portal link by email, tied to their Contact record and their Project(s). They click it, and their branded portal opens — nothing to install, nothing to remember. This is arguably better for your "mobile app friendly" requirement: there's no signup friction on a phone, no forgotten-password support requests, just a link that opens straight into a mobile-optimized page.

If you ever need stricter security for a specific client (common for law-adjacent or highly sensitive work — not typical for video production), Plutio supports an optional password-protected portal mode. Default to the link-based model for every project type in this package unless a client specifically requires otherwise.

## Scope of what a client sees

A client only ever sees their own Project(s), files, invoices, and Milestone progress — never other clients' data. If a Company has more than one stakeholder who needs visibility (e.g. a marketing director plus a finance contact), add each person as their own Contact and share the project with both — each gets their own portal link.

## How progress tracking actually works

Plutio's client portal shows a **live, real-time progress bar** driven by Milestones (docs/05) — this is a native feature, not something built manually out of checklists:

- Each of the 7 phases in the Base Template (Commercial, Brand Story, Conference) is built as its own **Milestone**, each with a deadline.
- As tasks under a Milestone are completed, Plutio's progress calculation updates automatically.
- Mark the Milestone **reached** once its tasks are done — Automation #9 (docs/09) can do this for you automatically when every task under it is complete.
- The client's portal shows exactly which Milestone is current, without any of your internal task-level detail — unless a specific task is flagged **Client-Visible** (docs/05 flags which ones: review link sent, sign-off received, files delivered).

**Podcast is structured differently**: instead of one set of 7 Milestones for the whole engagement, each **episode is its own Milestone** (e.g. "Episode 12"), created fresh every cycle. The client's portal then always reflects the status of the current episode(s) rather than a single progress bar for an ongoing show that never "finishes." See the Podcast section of `docs/05-project-templates.md`.

## What the client actually experiences

1. Gets an email with their portal link when their card is won (Automation #1, docs/09) — no signup step.
2. Opens the link on their phone or desktop → lands on their branded portal.
3. Sees their Project's live Milestone progress bar (e.g. "Post-Production — in progress").
4. Sees any tasks flagged Client-Visible (e.g. "Review your rough cut").
5. Can view/download files, upload files back, view and pay invoices, and message you — all from the same link, every time.

## Setup checklist

- [ ] White-labeling configured (docs/01, Phase 0) so the portal carries your branding, not Plutio's
- [ ] Milestones built into every Project Template, matching the phases in docs/05
- [ ] Client-visible tasks flagged in each Project Template
- [ ] Automation #9 built (auto-mark Milestones reached) so progress stays accurate without manual updates
- [ ] Test: create a dummy Contact and Project, open the portal link yourself, confirm it shows only that project, the live Milestone bar, and the flagged client-visible tasks — nothing else
