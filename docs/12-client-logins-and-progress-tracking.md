# Client Portal Access & Progress Tracking

## How clients actually get in — no traditional login

This is the biggest mechanical difference from the original SuiteDash version of this package: **Plutio clients don't create an account or set a password.** Each client gets a private, unique portal link by email, tied to their Contact record and their Project(s). They click it, and their branded portal opens — nothing to install, nothing to remember. This is arguably better for your "mobile app friendly" requirement: there's no signup friction on a phone, no forgotten-password support requests, just a link that opens straight into a mobile-optimized page.

If you ever need stricter security for a specific client (common for law-adjacent or highly sensitive work — not typical for video production), Plutio supports an optional password-protected portal mode. Default to the link-based model for every project type in this package unless a client specifically requires otherwise.

## Scope of what a client sees

A client only ever sees their own Project(s), files, invoices, and progress — never other clients' data. If a Company has more than one stakeholder who needs visibility (e.g. a marketing director plus a finance contact), add each person as their own Contact and share the project with both — each gets their own portal link.

## How progress tracking actually works

Correction from earlier planning: Plutio's Projects don't have a separate "Milestones" feature with its own deadline/progress tracking — confirmed by checking a real project's tabs (Tasks, Calendar, Timesheet, Transactions, Proposals, Contracts, Conversations, Forms, Files, Wiki, nothing else). Progress is built from **Task Groups** inside the Tasks tab instead (docs/05) — the same mechanism as the Sales Pipeline board's stages.

What this means in practice:
- Each of the 7 phases in the Base Template is a Task Group, with its tasks underneath.
- Whatever percent-complete or progress indicator Plutio shows is calculated from tasks checked off, not from a dedicated milestone object.
- **Still to confirm once you're in the Client Portal setup (docs/10)**: exactly what a client sees — whether it's an overall percent-complete, a breakdown by Task Group, or just the individual tasks flagged Client-Visible. Note the answer here once confirmed live, since it affects how much detail to put in front of clients.
- In the meantime, the **(Client-Visible)** flags in docs/05 mark the specific tasks worth exposing directly (review link sent, sign-off received, files delivered) — treat those as the minimum a client should see regardless of how the overall progress indicator ends up looking.

**Podcast is structured differently**: instead of 7 fixed Task Groups for the whole engagement, each **episode gets its own Task Group** (e.g. "Episode 12"), created fresh every cycle, so the current episode's status stays visually separate from past ones. See the Podcast section of `docs/05-project-templates.md`.

## What the client actually experiences

1. Gets an email with their portal link when their card is won (Automation #1, docs/09) — no signup step.
2. Opens the link on their phone or desktop → lands on their branded portal.
3. Sees their Project's progress (exact presentation TBD — see above).
4. Sees any tasks flagged Client-Visible (e.g. "Review your rough cut").
5. Can view/download files, upload files back, view and pay invoices, and message you — all from the same link, every time.

## Setup checklist

- [ ] White-labeling configured (docs/01, Phase 0) so the portal carries your branding, not Plutio's
- [ ] Task Groups built into every Project Template, matching the phases in docs/05
- [ ] Client-visible tasks flagged in each Project Template
- [ ] Confirm exactly what progress indicator the client portal shows, and update this doc with the real answer
- [ ] Test: create a dummy Contact and Project, open the portal link yourself, confirm it shows only that project, its progress, and the flagged client-visible tasks — nothing else
