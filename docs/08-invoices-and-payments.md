# Invoices & Payments

## Payment structure (default — adjust to your actual pricing policy)

- **Deposit**: 50% due at contract signing, before a Project is created (Workflow #1 waits for this).
- **Final Balance**: remaining 50% due at final delivery, Net 7.
- **Retainers** (Social Content Package): billed monthly in advance, auto-recurring.
- **Add-ons / Change Orders**: extra revision rounds, rush fees, additional locations, etc. — invoiced separately as they come up, Net 7.

## Invoice line items to build

Exact wording in `templates/invoices/invoice-line-items.md`. Build each as a saved Invoice Item/Product so they're reusable across invoices:

1. Deposit Invoice — 50%
2. Final Invoice — Remaining Balance
3. Add-On / Change Order Invoice
4. Monthly Retainer Invoice (recurring)

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
4. For retainers: Invoices → Recurring → create a Subscription Plan per retainer package tier (see tiers in docs/07).
