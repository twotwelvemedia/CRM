# Sales Pipeline (Task Board)

Plutio doesn't have a dedicated "Deals" object — the sales pipeline is built using a **Task Board** in Kanban view, with each card representing one prospective deal. This is a standard, fully-supported Plutio pattern (their own help docs cover it: "Using task boards as sales pipelines").

Keep this board separate from production work — sales and production are two different systems. A card here becomes a Project (docs/05) once it's won; don't run production work through this board.

## Build: "Video Production Sales" Task Board

Plutio's left sidebar has both a **Tasks** item and a **Projects** item — these are different things. **Tasks** is where standalone Kanban boards live (boards not tied to one client's work), which is where this pipeline board belongs. **Projects** is for the actual client work built in docs/05 — don't confuse the two.

1. Click **Tasks** in the sidebar, then create a new board (look for a "+ New Board" or similar create action).
2. Name it **Video Production Sales**.
3. Use **"Create Task Group"** to add one group per stage below — a Task Group is Plutio's name for a Kanban column. "Create Task" is a different button, for individual cards that go inside a group later; don't use it yet.
4. Switch to Kanban/Board view if there's a view switcher near the top — that's what displays Task Groups as side-by-side columns.

One Task Group per stage:

| # | Stage (Task Group) | Meaning | Exit criteria |
|---|-------|---------|----------------|
| 1 | New Lead | Inbound inquiry, not yet contacted | First response sent within 1 business day |
| 2 | Discovery Call Scheduled | Call booked | Call takes place |
| 3 | Discovery Call Completed | Needs/brief captured | Creative Brief form completed (docs/06, Form 2) |
| 4 | Proposal Sent | Proposal delivered | Client responds |
| 5 | Negotiation | Revising scope/price | Terms agreed |
| 6 | Contract Sent | Contract out for e-signature | Signed |
| 7 | Won — Contract Signed | Deposit invoice sent | Deposit paid → auto-creates Project (docs/09, Automation #1) |
| 8 | Lost | Did not close | Lost Reason field set (below) |

Keep **Lost** as a terminal Task Group rather than deleting cards — they're your remarketing list (Automation #7, docs/09).

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
