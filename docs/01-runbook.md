# Setup Runbook (Plutio)

Build in this order. Each step names the Plutio area you'll work in and the doc/file to use.

## Phase 0 — Workspace basics

1. **Create your Plutio workspace** if you haven't already, on a plan that includes white-labeling: Core ($19/mo) or Pro ($49/mo) plus the $9/mo white-label add-on, or Max ($199/mo) which includes it.
2. **Branding & white-label** — Settings → White Label. Upload your logo, set your brand colors, and connect your custom domain (e.g. `portal.yourstudio.com`). Once set, outgoing client emails and the client portal itself run under your domain and branding, not Plutio's.
3. **Connect a payment processor** — Settings → Financials/Payments. Connect Stripe and/or Square if you want auto-billing on retainer clients (required for Podcast Subscriptions with auto-charge, see docs/08). PayPal and bank transfer work for manual invoices but can't auto-charge.

## Phase 1 — Team

4. **Create custom roles, then invite your team** — see `docs/11-team-roles-permissions.md`. Build roles under Settings → User Roles before inviting people, so nobody briefly has more access than they should.

## Phase 2 — CRM foundation

5. **Build the Sales Pipeline Task Board** — see `docs/02-crm-pipeline.md`. This replaces a dedicated "Deals" object — you're building it as a Kanban Task Board.
6. **Create Custom Fields** for Contacts, Companies, and the Sales Pipeline board — see `docs/03-custom-fields.md`. Build these before importing data or building Project Templates, since field values carry over into templates.
7. **Import existing Contacts / Companies** — fill in `imports/contacts_import_template.csv` and `imports/companies_import_template.csv` with your real data, then import via Contacts → Import and Companies → Import. Plutio doesn't support bulk CSV import for Task Board cards, so add your handful of active in-flight deals to the Sales Pipeline board by hand — use `imports/deals_import_template.csv` as a field reference while you do, not as an upload.

## Phase 3 — Projects

8. **Create Project custom fields** — the remaining fields in `docs/03-custom-fields.md` (Project object, plus Podcast-only fields).
9. **Build Project Templates with Milestones**, one per project type — see `docs/05-project-templates.md`. Each phase becomes a native Plutio Milestone with its own task list.

## Phase 4 — Client-facing content

10. **Build intake & feedback Forms** — see `docs/06-forms.md`.
11. **Build Proposal templates** — see `docs/07-proposals-and-contracts.md` and `templates/proposals/`.
12. **Build Contract templates** — same doc, content in `templates/contracts/`.
13. **Set up Invoices & Subscriptions** — see `docs/08-invoices-and-payments.md` and `templates/invoices/`.

## Phase 5 — Automation

14. **Build Automations** — see `docs/09-workflows-automations.md`. Recreate each trigger → action rule under Plutio's Automations builder.
15. **Load Email templates** — `templates/emails/`, referenced by the automations above.

## Phase 6 — Client Portal

16. **Configure the Client Portal** — see `docs/10-client-portal.md`: file organization and a client-facing Wiki for FAQs.
17. **Confirm client portal access & progress tracking** — see `docs/12-client-logins-and-progress-tracking.md`. Read this before your first real client — Plutio's access model (secure link, no password) is different from a traditional login and is worth understanding up front.

## Phase 7 — Go live

18. **Dry run** — create a test Contact → test Sales Pipeline card → move it through every stage → confirm a Project auto-creates on Won → confirm each Automation fires, including Milestone progress → open the client portal link as if you were the client and confirm it shows only that project, the live progress bar, and the flagged client-visible tasks → then delete/void the test records.
19. **Go live** — point your real intake channel (website embed, ad landing page, etc.) at the Plutio form from step 10.
