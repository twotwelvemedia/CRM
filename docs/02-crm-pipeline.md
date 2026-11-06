# Sales Pipeline

**Correction from earlier (Plutio-era) planning:** Plutio has no dedicated "Deals" object, so the original plan built the sales pipeline as a Task Board workaround (Kanban columns standing in for pipeline stages). **SuiteDash has a native Deals module** — a proper CRM pipeline object with its own Stages, Won/Lost status, probability weighting, and stage-level automations. Use that instead; there's no Task Board workaround needed.

## Built and live: "Video Production Sales" pipeline

Deals → Pipelines → **Video Production Sales** (renamed from SuiteDash's out-of-box "Default Pipeline," which shipped with generic stage names like "Qualified"/"Demo Scheduled" — those are gone now).

8 stages, confirmed live via fresh reload:

| # | Stage | Probability | Meaning |
|---|---|---|---|
| 1 | New Lead | 5% | Inbound inquiry, not yet contacted |
| 2 | Discovery Call Scheduled | 15% | Call booked |
| 3 | Discovery Call Completed | 30% | Needs/brief captured |
| 4 | Proposal Sent | 50% | Proposal delivered |
| 5 | Negotiation | 65% | Revising scope/price |
| 6 | Contract Sent | 85% | Contract out for e-signature |
| 7 | Won - Contract Signed | 100% | Deal marked Won. Project creation is a separate, manual "Start from Template" step the Producer does — see docs/09, Automation #1 detail |
| 8 | Lost | 0% | Did not close |

## Won vs. Lost: two different mechanisms — use the Stage, not the status buttons

This is the one easy-to-get-wrong part. Every Deal detail page has quick-action **Won**/**Lost** buttons at the top (green/red) that set the Deal's status directly — confirmed live, clicking them does **not** move the Deal through the Stage pipeline at all, and does **not** trigger any stage-based automation. SuiteDash's own automation system only fires on **Stage changes** ("Trigger Automations when a Deal is moved into/out of this Stage") — there's no separate "Deal marked Lost" trigger type, despite the module's own onboarding copy implying one exists.

**Practical rule: drag the card into the "Lost" stage instead of clicking the red Lost button.** That's what actually fires Automation #7 (the 90-day follow-up — see below). The quick-action buttons are fine for marking Won (reaching the "Won - Contract Signed" stage already represents Won), but don't use the red Lost button if you want the automation to fire.

**Confirmed end-to-end via a full dry run** (test Deal, real Won button click): clicking the green Won quick-action set Status Open → Won and Probability 5% → 100%, logged in the Deal's History, while the Stage pill stayed on whatever stage it was already on — exactly as documented above. No stray automation fired. Project creation afterward was a separate, manual "Start from Template" step (docs/09).

## Automation #7: 90-day follow-up on Lost

**Built and live.** On the "Lost" stage's "Into This Stage" automations (Pipeline → Video Production Sales → Stage View → the gear icon on the Lost column → Configure Automations):

- Action: **Apply Follow-Up Generator(s)** → "Lost Deal — 90-Day Follow-Up"

That Follow-Up Generator (Office → Follow-Ups → Generators) creates a single Follow-Up titled "90-Day Follow-Up: Re-engage Lost Lead," scheduled 90 days out, assigned to the Deal's Primary Salesperson, Private visibility, category "Follow Up." Confirmed via fresh reload.

**Lost Reason** isn't a field on the Deal itself — SuiteDash doesn't support custom fields scoped directly to Deals (confirmed: the Custom Fields "Usage" dropdown has no "Deals" option, only CRM > Target/Contacts/Company, Projects, Organization, Staff, Work Requests, Support). The closest working equivalent is a **Deal Lost Reason** custom field scoped to CRM > Target (i.e., it lives on the Contact record) — built and live, dropdown with the 5 options below. Not automatable (nobody can know *why* a deal was lost except the salesperson), so the Sales rep fills it in by hand on the Contact when they mark a deal Lost:

- Budget Mismatch
- Chose Competitor
- Timing / Not Ready
- Went Silent (no response after 3 follow-ups)
- Scope Not a Fit

This is a contact-level field, not a per-deal one — fine in practice since a given contact rarely has multiple simultaneous Lost deals needing different reasons recorded at once.

## Known leftover from earlier (Plutio-pattern) exploration — not cleaned up

Custom Fields admin currently also has an older **"Lost Reason"** and **"Pipeline Stage"** field, both scoped to **Projects** (not Deals/Contacts) — these were built earlier in this project's setup, before the native Deals module was discovered/used, as part of an abandoned attempt to model the pipeline on Project-level fields. They're not wired to anything pipeline-related now and are safe to ignore; cleaning them up is a separate, optional task not done here since they weren't confirmed unused elsewhere.

## Card conventions

- **Deal title**: Client/Company name + short project descriptor (e.g. "Acme Corp — Brand Story")
- **Target**: the CRM Contact this Deal is for
- **Category**: use the Project Type (Commercial/Brand Story/Conference/Podcast). **Built and live** — the 4 real categories replace SuiteDash's out-of-box defaults (Website Design, Photo Shoot, Logo Design, Supplier Contract), confirmed via fresh reload. Commercial is set as the default category (a category admin requirement — SuiteDash won't let the last default category be deleted, so swap the default to one of the real categories first if you ever need to remove another one)
- **Expected Value**: the deal's total project fee

## Notes

- Podcast clients are ongoing/recurring by nature — still run the initial sale through this same pipeline once. Episode billing and renewals are handled inside the Podcast Project itself (docs/05, docs/08), not as repeat Deals.
- No bulk import tested for Deals; add existing in-flight opportunities by hand (docs/01, Phase 2) if migrating from a prior system.
