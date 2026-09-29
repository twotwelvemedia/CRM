# Setup Runbook

Build in this order. Each step names the SuiteDash area you'll work in and the doc/file to use. Don't skip ahead to Forms/Proposals/Workflows before the CRM foundation (Phase 2) is in place — later steps reference fields and tags created there.

## Phase 0 — Account basics

1. **Company profile & branding** — Settings → White Label. Upload your logo, set your brand color, and set your custom domain/subdomain if you have one (e.g. `portal.yourstudio.com`).
2. **Connect a payment processor** — Settings → Payments. Connect Stripe and/or PayPal so invoices can be paid online.

## Phase 1 — Team

3. **Create roles, then invite your team** — see `docs/11-team-roles-permissions.md`. Build the roles/permissions first so people never briefly have more access than they should.

## Phase 2 — CRM foundation

4. **Build the Deals pipeline** — see `docs/02-crm-pipeline.md`. Create the pipeline and its stages exactly as listed; you can rename labels later, but get the structure in first.
5. **Create Tags** — see `docs/04-tags.md`.
6. **Create Custom Fields for Contacts, Companies, and Deals** — see `docs/03-custom-fields.md`. Do this *before* importing data so the import step can map columns straight to real fields.
7. **Import existing Contacts / Companies / Deals** — fill in `imports/contacts_import_template.csv`, `imports/companies_import_template.csv`, `imports/deals_import_template.csv` with your real data, then import via each object's Import option.

## Phase 3 — Projects

8. **Create Project custom fields** — the remaining fields in `docs/03-custom-fields.md` (Project object).
9. **Build Project Templates**, one per project type — see `docs/05-project-templates.md`. Each becomes a reusable task list/kanban you apply the moment a deal closes.

## Phase 4 — Client-facing content

10. **Build intake & feedback Forms** — see `docs/06-forms.md`.
11. **Build Proposal templates** — see `docs/07-proposals-and-contracts.md` and `templates/proposals/`.
12. **Build Contract templates** — same doc, content in `templates/contracts/`.
13. **Set up Invoices** — see `docs/08-invoices-and-payments.md` and `templates/invoices/`. Build your deposit/final invoice line items and, if you offer retainers, your recurring invoice plan.

## Phase 5 — Automation

14. **Build Workflows** — see `docs/09-workflows-automations.md`. Recreate each trigger → action rule in SuiteDash's Workflow builder.
15. **Load Email templates** — `templates/emails/`, referenced by the workflows above.

## Phase 6 — Client Portal

16. **Configure the Client Portal** — see `docs/10-client-portal.md`: menu items, per-project folder structure, and starter Knowledge Base articles.

## Phase 7 — Go live

17. **Dry run** — create a test Contact → test Deal → move it through every pipeline stage → confirm a Project auto-creates on Won → confirm each Workflow fires → confirm the client-facing Portal looks right → then delete/void the test records.
18. **Go live** — point your real intake channel (website embed, ad landing page, etc.) at the SuiteDash form from step 10.
