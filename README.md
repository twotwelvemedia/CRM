# Video Production CRM — Plutio Setup Package

A complete, ready-to-implement CRM & project-management configuration for a small video production studio/team, built to be set up inside **Plutio** (plutio.com).

Plutio is a hosted, all-in-one business platform — there's no code to deploy here, same as before. This package gives you everything to configure your Plutio workspace correctly the first time:

- The exact sales pipeline (built as a Task Board), custom fields, project/task templates with Milestones, forms, proposal/contract/invoice content, automation rules, client portal setup, and team roles for a video production business.
- CSV templates to bulk-import your existing contacts and companies.
- A step-by-step runbook (`docs/01-runbook.md`) that tells you the order to build everything in.

## Why Plutio (and what changed from the original SuiteDash version)

This package was originally built for SuiteDash, then rebuilt here after comparing alternatives against two hard requirements: a genuine native mobile app for the team, and white-labeling. Plutio confirmed both, plus CSV import for Contacts/Companies, and a trigger→action Automations engine that maps closely onto the workflow logic already designed for this business.

Two real differences from the SuiteDash version, reflected throughout this package:

1. **No "Deals" object.** Plutio's sales pipeline is built using a Task Board in Kanban view rather than a dedicated CRM pipeline object — see `docs/02-crm-pipeline.md`.
2. **Client portal access is link-based, not a traditional login.** Clients get a private, branded portal link by email — no account or password to set up (a password-protected option exists if you ever need it for a sensitive client). See `docs/12-client-logins-and-progress-tracking.md`.

## Who this is scoped for

A small studio/team: a producer/project manager, one or more editors, one or more videographers/photographers, and someone handling sales — running exactly four project types: **Commercial**, **Brand Story**, **Conference**, and **Podcast**. Each can involve video, photography, or both (set per project via the Deliverable Medium field).

## Where to start

1. Read **`docs/01-runbook.md`** — the master checklist, in build order. Everything else is referenced from it.
2. Work through each linked doc as the runbook calls for it.
3. Use the files in **`imports/`** when the runbook tells you to import data.
4. Use the files in **`templates/`** when the runbook tells you to build proposals, contracts, invoices, or emails.

## Folder structure

```
docs/       Reference docs for each part of the setup (pipeline, fields, forms, scheduling, automations, roles...)
templates/  Copy-paste-ready content for Proposals, Contracts, Invoices, and Emails
imports/    CSV templates for bulk-importing Contacts and Companies, plus the master custom-fields list
```

## Customizing this for your studio

Everything here is a strong, opinionated default — not a mandate. Pricing, revision counts, payment splits, and package tiers are placeholders you should replace with your actual numbers before you build proposals/contracts/invoices in Plutio.
