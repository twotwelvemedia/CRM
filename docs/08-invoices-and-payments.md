# Invoices & Subscriptions

## Payment structure — branches by Client Type

Which terms apply depends on the Company's **Client Type** field (docs/03). Set this before sending a proposal — it decides which Payment Terms block you leave in the proposal and contract.

**Corporate clients:**
- **Full invoice**: 100% of the project fee, invoiced at contract signing, Net 30.
- No deposit — production can begin on a signed contract, payment follows on the corporate client's AP cycle.

**Everyone else (Small Business, Nonprofit, Agency, Conference/Event Organizer):**
- **Deposit**: 50% due at contract signing, before a Project is created (Automation #1 waits for this). Applies to Commercial, Brand Story, and Conference projects.
- **Final Balance**: remaining 50% due at final delivery, Net 7.

**Podcast** (any Client Type): billed either per-episode (invoice on delivery) or as a monthly Subscription covering an agreed number of episodes — the Corporate/Small Business split above doesn't apply to recurring Podcast billing.

**Add-ons / Change Orders**: extra revision rounds, rush fees, additional locations, additional photographers, etc. — invoiced separately as they come up, Net 7 regardless of Client Type.

## Invoice line items to build

Exact wording in `templates/invoices/invoice-line-items.md`. Build each as a saved Invoice Item under Financials so they're reusable across invoices:

1. Deposit Invoice — 50% (Small Business, Nonprofit, Agency, Conference/Event Organizer)
2. Final Invoice — Remaining Balance (same client types as above)
3. Full Invoice — Net 30 (Corporate clients)
4. Add-On / Change Order Invoice
5. Podcast Episode Invoice (per-episode billing)
6. Podcast Monthly Subscription (recurring)

## Setting up the Podcast Subscription (Financials → Subscriptions)

Plutio calls recurring billing a **Subscription**, with two billing types:

- **Manual billing** — Plutio auto-sends the invoice on schedule; the client pays it on receipt.
- **Auto billing** — Plutio auto-charges the client's saved payment method on the billing date. Only Stripe and Square support auto-charge; PayPal and bank transfer don't, so those clients must be on manual billing.

Setup steps:
1. Financials → Subscriptions → Create subscription.
2. Select the subscriber (the Podcast client).
3. Attach it to the client's Podcast Project so generated invoices link to the right show.
4. Set the repeat interval (e.g. monthly) and start date.
5. Choose manual or auto billing based on the client's payment method.

## Late payment policy

| When | Action |
|---|---|
| Due date (Day 0) | Automatic reminder email (Automation #4) |
| Day 7 | Second reminder, note that a late fee may apply |
| Day 14 | Late fee applied (set % under Financials settings) + Producer notified to pause next deliverable until paid |

## Setup steps in Plutio

1. Settings → Financials/Payments → connect Stripe and/or Square (required for auto-billing) and/or PayPal (manual billing only).
2. Financials settings → set default payment terms (Net 7), late fee percentage, and invoice numbering format.
3. Create each line item above as a saved Invoice Item so it's reusable without retyping.
4. For Podcast retainer clients, set up the Subscription per the steps above.
