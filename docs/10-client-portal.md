# Client Portal

For how clients actually get portal access (password-based, via an emailed invitation) and how task progress visibility actually works, see `docs/12-client-logins-and-progress-tracking.md`. This doc covers the portal's structure and content once they're in.

## What the portal shows

Every client gets a private, branded page (your logo, colors, and domain if white-labeling is set up per docs/01) with:

- Live project progress (Task Groups — docs/05)
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

## Client-facing FAQs (Knowledge Base)

**Built and live.** SuiteDash's Knowledge Base module (not a "Wiki" — that's Plutio's term) hosts the public-facing help center for clients, separate from internal documentation. A Knowledge Base called **"Client FAQs"** exists under Knowledge Base Pages, with one Category ("Working With Us") and all 7 planned articles published:

1. How to Request a Revision
2. Understanding Your Usage Rights & Licensing
3. File Formats & Specs We Deliver
4. How to Download Your Final Files
5. Our Revision Policy
6. Payment Methods We Accept & Late Payment Policy
7. What to Expect on Shoot Day

Each article was built using the Knowledge Base's rich-text article editor. **Placement:** a Knowledge Base isn't visible anywhere by default — it has to be explicitly placed on a page or dashboard via the module's Placements tab. The "Client FAQs" Knowledge Base is placed as a block on the **Multi-Purpose Client Dashboard** (the main landing page clients see when they log into the portal), titled "Client FAQs," showing up to 5 results. Confirm via `Knowledge Base Pages → Client FAQs → Placements` — it should list "Multi-Purpose Client Dashboard."

If you want the FAQs reachable from elsewhere too (e.g. the standalone "How to Prepare for a Video Production" Portal Page), add another Knowledge Base block there the same way — Placements will list every page/dashboard it's been added to.

## Branding

Logo, brand colors, and your custom portal domain are set under Settings → White Label — do this in Phase 0 of the runbook so everything client-facing you build afterward (forms, proposals, portal) already reflects your branding.
