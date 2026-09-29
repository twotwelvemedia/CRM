# Video Production CRM — SuiteDash Setup Package

A complete, ready-to-implement CRM & project-management configuration for a small video production studio/team, built to be set up inside **SuiteDash** (suitedash.com).

SuiteDash is a hosted SaaS platform — there's no code to deploy here. Instead, this package gives you everything you need to configure your SuiteDash account correctly the first time:

- The exact sales pipeline stages, custom fields, tags, project templates, forms, proposal/contract/invoice content, automation rules, client portal structure, and team roles for a video production business.
- A client login system: each client gets their own portal account showing a real-time progress bar for their project (docs/12), without exposing your internal task list.
- CSV templates to bulk-import your existing contacts, companies, and deals.
- A step-by-step runbook that tells you the *order* to build everything in, so you're not guessing or rebuilding things twice.

## Who this is scoped for

A small studio/team: a producer/project manager, one or more editors, one or more videographers/shooters, and someone handling sales — running a mix of project types (commercial/brand, corporate, event coverage, weddings, music videos, documentary, and social content retainers).

## Where to start

1. Read **`docs/01-runbook.md`** — this is the master checklist, in build order. Everything else is referenced from it.
2. Work through each linked doc as the runbook calls for it.
3. Use the files in **`imports/`** when the runbook tells you to import data.
4. Use the files in **`templates/`** when the runbook tells you to build proposals, contracts, invoices, or emails — copy/paste the content straight into SuiteDash's builders.

## Folder structure

```
docs/       Reference docs for each part of the setup (pipeline, fields, forms, workflows, roles...)
templates/  Copy-paste-ready content for Proposals, Contracts, Invoices, and Emails
imports/    CSV templates for bulk-importing Contacts, Companies, Deals, plus the master custom-fields list
```

## Customizing this for your studio

Everything here is a strong, opinionated default — not a mandate. Pricing, revision counts, payment splits, and package tiers are placeholders you should replace with your actual numbers before you build proposals/contracts/invoices in SuiteDash. Anywhere that matters, it's flagged inline.
