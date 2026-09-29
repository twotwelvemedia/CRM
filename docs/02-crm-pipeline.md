# CRM Pipeline (Deals)

Sales and production are two different systems in this setup: **Deals** track a lead through to a signed contract; **Projects** (docs/05) track the actual production work after a deal is won. Don't try to run production work through the Deal pipeline.

## Pipeline: "Video Production Sales"

| # | Stage | Meaning | Exit criteria |
|---|-------|---------|----------------|
| 1 | New Lead | Inbound inquiry, not yet contacted | First response sent within 1 business day |
| 2 | Discovery Call Scheduled | Call booked | Call takes place |
| 3 | Discovery Call Completed | Needs/brief captured | Creative Brief form completed (docs/06, Form 2) |
| 4 | Proposal Sent | Proposal delivered | Client responds |
| 5 | Negotiation | Revising scope/price | Terms agreed |
| 6 | Contract Sent | Contract out for e-signature | Signed |
| 7 | Won — Contract Signed | Deposit invoice sent | Deposit paid → auto-creates Project (see docs/09, Workflow #1) |
| 8 | Lost | Did not close | Lost Reason tag applied (below) |

Build stages 1–7 as your live pipeline columns. Keep **Lost** as a terminal stage rather than deleting lost deals — they're your remarketing list (see Workflow #7, docs/09).

## Lost Reasons (apply as a tag when marking a deal Lost)

- Budget Mismatch
- Chose Competitor
- Timing / Not Ready
- Went Silent (no response after 3 follow-ups)
- Scope Not a Fit

## Deal-level fields to fill in before moving a deal past Stage 3

- Project Type (custom field, docs/03)
- Estimated Budget / Package Tier (custom field, docs/03)
- Target Shoot Date(s) (custom field, docs/03)
- Expected Close Date (built-in Deal field)

## Notes

- If you run retainer/recurring clients (Social Content Package), still run the initial sale through this pipeline once. Renewals are handled as recurring invoices (docs/08), not repeat deals.
- Consider a second, lightweight "Referral / Past Client" pipeline later once volume justifies it — not needed at launch.
