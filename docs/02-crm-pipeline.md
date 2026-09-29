# Sales Pipeline (Task Board)

Plutio doesn't have a dedicated "Deals" object — the sales pipeline is built using a **Task Board** in Kanban view, with each card representing one prospective deal. This is a standard, fully-supported Plutio pattern (their own help docs cover it: "Using task boards as sales pipelines").

Keep this board separate from production work — sales and production are two different systems. A card here becomes a Project (docs/05) once it's won; don't run production work through this board.

## Build: "Video Production Sales" Task Board

1. Create a new Task Board named **Video Production Sales**.
2. Switch it to Kanban view.
3. Create one column per stage:

| # | Stage (column) | Meaning | Exit criteria |
|---|-------|---------|----------------|
| 1 | New Lead | Inbound inquiry, not yet contacted | First response sent within 1 business day |
| 2 | Discovery Call Scheduled | Call booked | Call takes place |
| 3 | Discovery Call Completed | Needs/brief captured | Creative Brief form completed (docs/06, Form 2) |
| 4 | Proposal Sent | Proposal delivered | Client responds |
| 5 | Negotiation | Revising scope/price | Terms agreed |
| 6 | Contract Sent | Contract out for e-signature | Signed |
| 7 | Won — Contract Signed | Deposit invoice sent | Deposit paid → auto-creates Project (docs/09, Automation #1) |
| 8 | Lost | Did not close | Lost Reason field set (below) |

Keep **Lost** as a terminal column rather than deleting cards — they're your remarketing list (Automation #7, docs/09).

## Card conventions

- **Card title**: Client/Company name + short project descriptor (e.g. "Acme Corp — Brand Story")
- **Card description**: notes, next steps, context on the opportunity
- **Assignee**: whoever owns the deal (Sales/Account Manager)

## Card-level custom fields

Add these to the Task Board under Settings → Custom Fields (scope: this board) so every card carries them — full spec in `docs/03-custom-fields.md`:

- Project Type
- Deliverable Medium
- Estimated Budget / Package Tier
- Target Shoot Date(s)
- Lead Source
- Lost Reason

Fill these in before moving a card past Stage 3.

## Lost Reasons (set the Lost Reason field when a card is marked Lost)

- Budget Mismatch
- Chose Competitor
- Timing / Not Ready
- Went Silent (no response after 3 follow-ups)
- Scope Not a Fit

## Notes

- Podcast clients are ongoing/recurring by nature — still run the initial sale through this board once. Episode billing and renewals are handled inside the Podcast Project itself (docs/05, docs/08), not as repeat cards.
- Plutio doesn't support bulk CSV import for Task Board cards the way it does for Contacts/Companies — add your existing in-flight deals to this board by hand (docs/01, Phase 2).
