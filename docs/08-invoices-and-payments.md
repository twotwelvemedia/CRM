# Invoices & Payments

## Payment structure (default — adjust to your actual pricing policy)

- **Deposit**: 50% due at contract signing, before a Project is created (Workflow #1 waits for this). Applies to Commercial, Brand Story, and Conference projects.
- **Final Balance**: remaining 50% due at final delivery, Net 7.
- **Podcast**: billed either per-episode (invoice on delivery) or as a monthly retainer covering an agreed number of episodes — decide per client and set up the matching invoice type below.
- **Add-ons / Change Orders**: extra revision rounds, rush fees, additional locations, additional photographers, etc. — invoiced separately as they come up, Net 7.

## Invoice line items to build

Exact wording in `templates/invoices/invoice-line-items.md`. Build each as a saved Invoice Item/Product so they're reusable across invoices:

1. Deposit Invoice — 50%
2. Final Invoice — Remaining Balance
3. Add-On / Change Order Invoice
4. Podcast Episode Invoice (per-episode billing)
5. Podcast Monthly Retainer Invoice (recurring)

## Late payment policy

| When | Action |
|---|---|
| Due date (Day 0) | Automatic reminder email (Workflow #4) |
| Day 7 | Second reminder, note that a late fee may apply |
| Day 14 | Late fee applied (set % in Settings → Invoicing) + Producer notified to pause next deliverable until paid |

## Setup steps in SuiteDash

1. Settings → Payments → connect Stripe and/or PayPal.
2. Settings → Invoicing → set default payment terms (Net 7), late fee percentage, and invoice numbering format.
3. Create each line item above as a saved Invoice Item so it's reusable without retyping.
4. For Podcast retainer clients: Invoices → Recurring → create a Subscription Plan per package tier (see tiers in docs/07).
