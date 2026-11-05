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

**Correction from earlier planning:** a Project's Files aren't one flat folder — SuiteDash splits every Project's file area into two native root folders with built-in, system-enforced client visibility, not a convention you have to maintain by hand:

- **Private Files** — "Client cannot see Project Files in this folder." Internal-only.
- **Public Files** — "Files visible to the Client" / "Files uploaded by the Client." This is also where the client's own uploads land.

**Built and live.** A reusable **Folder Generator** (Files → Folder Generators → "Standard Project File Structure," Generator Type = Project) pre-builds the subfolder structure inside each root, confirmed via fresh reload:

```
Private Files/
  01-Contracts/
  02-Brief-and-References/
  03-Raw-Footage-and-Photo-Links/
  05-Invoices/
Public Files/
  04-Deliverables/
```

`04-Deliverables` lives under Public Files specifically because that's the client-downloadable tier — final files land where the client can actually get to them; everything else (contracts, briefs, raw footage, invoices) stays internal.

Apply this Folder Generator to a Project's Files area to get the structure above instead of building folders by hand each time. **Not yet wired to Automation #1** (docs/09) — attaching an "Apply Folder Generator" action to the Project-creation trigger so every new Project gets this structure automatically is a natural next step, not yet attempted.

Client uploads (brand assets, signed documents, reference material) land in the Public Files folder — you'll see them alongside your own files there, not in a separate inbox.

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
