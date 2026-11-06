# Forms

Build these under Plutio's Forms builder (supports conditional logic, file uploads, date pickers, e-signature fields, and multi-page layouts). Where noted, a form submission triggers an Automation (docs/09) — build the form first, then wire the automation to it.

## Form 1 — New Inquiry (embedded on your website / linked from ads)

**Built natively in SuiteDash as a Kickoff Form — no Zapier, no third-party form tool, no custom HTML.** SuiteDash's Kickoff Form type is purpose-built for exactly this case: it's designed to onboard Unknown Targets (people with no existing CRM record), can be embedded on an external website or linked to standalone, and lets you configure the CRM/email automation that fires on submission directly in the form builder. This replaced the original Plutio-era plan (custom HTML + Zapier webhook), which existed only to work around Plutio's poor hosted-form embedding — SuiteDash doesn't have that problem.

Built and live: **"New Inquiry"** (Forms → New Inquiry). Two different URLs, confirmed by testing both anonymously: `https://app.suitedash.com/frm/u/24Xey5xetrdCwVGur` (with `/u/`) is the internal builder/edit link — it redirects an anonymous visitor to the staff login page, so don't share it. The real public submission form is `https://app.suitedash.com/frm/24Xey5xetrdCwVGur` (no `/u/`) — see the embed section below.

| Field | Type | Maps to |
|---|---|---|
| Primary Email | Email | CRM Contact: Primary Email |
| First Name | Text | CRM Contact: First Name |
| Last Name | Text | CRM Contact: Last Name |
| Company Name | Text (open-ended, creates Company if no match) | CRM Company: Company Name |
| Primary Phone | Text | CRM Contact: Primary Phone |
| Project Type | Dropdown: Commercial, Brand Story, Conference, Podcast | Project Custom Field: Project Type |
| Deliverable Medium | Dropdown: Video Only, Photo Only, Video + Photo | Project Custom Field: Deliverable Medium |
| Estimated Budget Range | Dropdown: <$2.5k, $2.5k–$5k, $5k–$10k, $10k–$25k, $25k+ | Project Custom Field: Estimated Budget Range |
| Target Shoot Date(s) | Date | Project Custom Field: Target Shoot Date(s) — stands in for "Desired Timeline/Deadline" |
| Lead Source | Dropdown: Referral, Instagram, Google Search, Google Ads, Past Client, Networking Event, Cold Outreach, Other | Project Custom Field: Lead Source — stands in for "How did you hear about us" |
| Message | Long Text, writes a Target Custom Field | Project Description / general inquiry notes |

Not built: a conditional "Referred By" field (would need a Choice Block for the conditional logic) — minor gap, skip unless it matters to you; Sales can always just ask who referred them.

### How it's wired (already done — nothing to connect)

- **Form Type:** Kickoff, title "New Inquiry"
- **Unknown Target Role:** Lead (so a first-time visitor becomes a CRM Lead, not a Client — they can't log into the Portal at this stage, which is correct; see docs/02)
- **Coordinator:** Marcus Williams (required by SuiteDash once Role = Lead; reassign per-lead once Sales claims it)
- **Email Notification:** fires on every submission to Marcus Williams (`info@two-twelvemedia.com`), subject "New Website Inquiry: {{clientFullName}}", body dumps the full submission via SuiteDash's `{{allSubmittedFormData}}` merge token
- **Portal invitation:** not sent (Leads can't be invited anyway — see the Role note above)

### Embedding it on your website

Use the embed script, not an iframe — it's SuiteDash's own JS embed, loads fast, and inherits the form's styling:

```html
<script src="https://app.suitedash.com/frm/24Xey5xetrdCwVGur.js"></script>
```

Paste that into a Code Embed block in Showit wherever the inquiry form should appear. The direct standalone link (for a "Get a Quote" button linked from ads, etc.) is `https://app.suitedash.com/frm/24Xey5xetrdCwVGur`.

Default styling (white background, dark gray text/buttons) is functional but generic — restyle it to match your brand under the form's Link/Embed panel → Styling Options (title/label/background/button colors) whenever you get to it; it's cosmetic, not blocking.

`templates/forms/new-inquiry-embed.html` is no longer the primary path — it's kept only as a reference/fallback if you ever need a fully custom embed outside SuiteDash.

On submit → creates/updates the CRM Contact (and Company, if given) as a Lead, writes the submitted project details to the new Project custom fields, writes the message to a Target Custom Field on the Contact (visible on the Contact's Home panel under "Target Custom Fields" → MESSAGE — not a separate CRM Note object), and emails Marcus Williams the full submission. **Confirmed via two live test submissions as part of a full dry run**: no Project or Deal is auto-created on submit (Leads only), so Sales reviews the email, then manually creates the Sales Pipeline card in "New Lead" (docs/02) and claims the lead — same manual handoff as before, just without Zapier in the middle.

## Form 2 — Creative Brief / Discovery Intake (send after the discovery call)

| Field | Type | Required |
|---|---|---|
| Project Goals | Long Text | Yes |
| Target Audience | Text | Yes |
| Key Message / Call to Action | Long Text | Yes |
| Brand Guidelines Link | URL | No |
| Reference Videos / Inspiration | Long Text or URL | No |
| Deliverables Needed | Checkbox list: 16:9 main video, 9:16 vertical cutdowns, 1:1 square, GIFs, Raw footage, Photo gallery, Podcast audio file | Yes |
| Number of Locations | Number | No |
| Talent Needed | Text | No |
| On-Camera Talent Provided By | Dropdown: Client, Studio, N/A | No |
| Hard Deadline | Date | Yes |
| Special Requirements/Notes | Long Text | No |

Completing this form is the exit criteria for Sales Pipeline Stage 3 ("Discovery Call Completed") — see docs/02.

## Form 3 — Shoot Day Logistics (internal, shared with crew and client)

| Field | Type | Required |
|---|---|---|
| Shoot Date(s) | Date | Yes |
| Call Time | Time | Yes |
| Location Address | Text | Yes |
| Parking/Access Notes | Long Text | No |
| Point of Contact On-Site | Text (name + phone) | Yes |
| Talent Call Times | Text | No |
| Equipment Checklist | Checkbox list | No |
| Weather Backup Plan | Long Text | No (Yes if outdoor shoot) |

## Form 4 — Client Feedback / Revision Request (attached to the review link)

| Field | Type | Required |
|---|---|---|
| Timestamp of Note | Text (e.g. "0:45") | No |
| Feedback / Change Requested | Long Text | Yes |
| Priority | Dropdown: Must-fix, Nice-to-have | Yes |
| Overall Approval | Radio: Approved as-is / Approved with notes above / Needs another round | Yes |

## Form 5 — Testimonial / Review Request

| Field | Type | Required |
|---|---|---|
| Star Rating | 1–5 | Yes |
| Testimonial Text | Long Text | Yes |
| Permission to use publicly | Checkbox | Yes |
| Permission to use name/company | Checkbox | No |
| Google/Social Review Link | Link-out to your actual review page | — |
