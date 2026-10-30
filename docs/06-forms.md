# Forms

Build these under Plutio's Forms builder (supports conditional logic, file uploads, date pickers, e-signature fields, and multi-page layouts). Where noted, a form submission triggers an Automation (docs/09) — build the form first, then wire the automation to it.

## Form 1 — New Inquiry (embedded on your website / linked from ads)

**Built in Tally (tally.so), not Plutio's Forms builder** — Plutio's own hosted form embeds as a slow-loading, hard-to-style iframe on an external website (confirmed first-hand). Tally is a free, lightweight form tool built for exactly this: fast embeds with a built-in transparent-background toggle, connected into Plutio via Zapier instead of living natively inside it. See docs/09, Automation #2, for the full Zapier wiring.

| Field | Type | Required |
|---|---|---|
| Full Name | Text | Yes |
| Email | Email | Yes |
| Phone | Phone | No |
| Company/Brand Name | Text | No |
| Project Type | Dropdown: Commercial, Brand Story, Conference, Podcast | Yes |
| Deliverable Medium | Dropdown: Video Only, Photo Only, Video + Photo | Yes |
| Estimated Budget | Dropdown: <$2.5k, $2.5k–$5k, $5k–$10k, $10k–$25k, $25k+ | Yes |
| Desired Timeline/Deadline | Date | No |
| Project Description | Long Text | Yes |
| How did you hear about us | Dropdown: Referral, Instagram, Google Search, Google Ads, Past Client, Networking Event, Cold Outreach, Other | No |
| Referred By | Text (conditional — show if "Referral" selected) | No |

### Embedding this form on your website

1. Build the form in Tally with the fields above.
2. In Tally's embed settings, turn on **Transparent Background**.
3. Copy Tally's embed code and place it on your website in place of any Plutio form embed.

On submit → Automation #2 (docs/09, via Zapier): creates a Contact + a card on the Sales Pipeline board in "New Lead" column, sets Lead Source field, notifies Sales/Account Manager.

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
