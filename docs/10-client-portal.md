# Client Portal

For how clients actually get portal access and see project progress (no traditional login required, Milestone progress), see `docs/12-client-logins-and-progress-tracking.md`. This doc covers the portal's structure and content once they're in.

## What the portal shows

Every client gets a private, branded page (your logo, colors, and domain if white-labeling is set up per docs/01) with:

- Live project progress (Milestones — docs/05)
- Task visibility for tasks flagged Client-Visible
- File access
- A payment button for any outstanding invoice
- The ability to upload files back to you (these land in the same shared project folder you see internally)
- A message thread to talk directly with your team (docs/13)
- A "Book a Time" link so they can self-serve a call without messaging you to ask for one (docs/13)

## File organization

Every Project has a main Files folder. Organize it with subfolders so both you and the client can find things:

```
[Client Name] - [Project Name]/
  01-Contracts/
  02-Brief-and-References/
  03-Raw-Footage-and-Photo-Links/
  04-Deliverables/
  05-Invoices/
```

Client uploads (brand assets, signed documents, reference material) land in this same shared folder — you'll see them alongside your own files, not in a separate inbox.

## Client-facing FAQs (Wiki)

Plutio's Wiki feature can host a public-facing help center for clients, separate from your internal documentation. Write these once:

1. How to request a revision
2. Understanding your usage rights & licensing
3. File formats & specs we deliver
4. How to download your final files
5. Our revision policy (how many rounds are included, what counts as a new request vs. an add-on)
6. Payment methods we accept & our late payment policy
7. What to expect on shoot day (for clients being filmed/interviewed)

## Branding

Logo, brand colors, and your custom portal domain are set under Settings → White Label — do this in Phase 0 of the runbook so everything client-facing you build afterward (forms, proposals, portal) already reflects your branding.
