# Custom Fields

Plutio lets you add custom fields to nearly any area — workspace, projects, tasks/task boards, contacts, companies, invoices, subscriptions, proposals, contracts, files, forms, conversations, schedulers, and transactions. Build each field under Settings → Custom Fields, choosing the correct scope.

**Build these before your Project Templates (docs/05)** — custom field values carry over automatically when a Project Template or Task Template is applied, so the values pre-fill correctly on every new project only if the fields already exist.

The same list, in flat CSV form for quick reference, is in `imports/custom_fields_master.csv`.

## Contact fields (scope: Contacts → People)

| Field Name | Type | Options | Required |
|---|---|---|---|
| Preferred Contact Method | Dropdown | Email, Phone, Text | No |
| Social Media Handle(s) | Text | — | No |
| Role/Title at Company | Text | — | No |

## Company fields (scope: Contacts → Companies)

| Field Name | Type | Options | Required |
|---|---|---|---|
| Client Type | Dropdown | Corporate, Small Business, Nonprofit, Agency, Conference/Event Organizer, Podcast Host/Network | Yes |
| Industry | Dropdown | Corporate, Nonprofit, E-commerce/Retail, Hospitality, Real Estate, Healthcare, Education, Personal/Individual, Music/Entertainment, Other | No |
| Website | URL | — | No |
| Brand Guidelines Link | URL | — | No |

**Client Type drives payment terms** (docs/08) — Corporate clients get a single Net 30 invoice, everyone else gets the standard 50/50 deposit split. Set this field before sending a proposal, not after.

## Sales Pipeline card fields — correction from earlier (Plutio-era) planning

**SuiteDash doesn't support custom fields scoped directly to Deals** — confirmed live, the Custom Fields "Usage" dropdown offers CRM > Target/Contacts/Company, Projects, Organization, Staff, Work Requests, Support, but no "Deals" option. The fields below were originally built scoped to **Projects** (an earlier, now-superseded attempt at modeling the pipeline — see docs/02), which doesn't make sense for pre-close data since a Project doesn't exist until a Deal is Won. They're effectively unused leftovers now, not cleaned up (see docs/02's "Known leftover" note):

- Pipeline Stage (Projects-scoped, orphaned)
- Lost Reason (Projects-scoped, orphaned — **superseded by the field below**)

**What's actually built and live for the pipeline now (docs/02):**

| Field Name | Scope | Type | Options | Required |
|---|---|---|---|---|
| Deal Lost Reason | CRM > Target (i.e. the Contact) | Dropdown | Budget Mismatch, Chose Competitor, Timing / Not Ready, Went Silent (no response after 3 follow-ups), Scope Not a Fit | No — filled in by hand when a Deal is marked Lost |

Project Type, Deliverable Medium, Estimated Budget Range, Target Shoot Date(s), and Lead Source are **not** duplicated at the Deal/pipeline level — they're captured once, directly on the Project, via the New Inquiry Kickoff Form (docs/06, docs/09 Automation #2), which writes straight to the Project-scoped fields below on submission. There's no separate pipeline-card copy of these fields to keep in sync.

## Project fields (scope: Projects)

| Field Name | Type | Options | Required |
|---|---|---|---|
| Project Type | Dropdown | Commercial, Brand Story, Conference, Podcast | Yes |
| Deliverable Medium | Dropdown | Video Only, Photo Only, Video + Photo | Yes |
| Shoot Date(s) | Date (or multi-line text if multiple sessions) | — | Yes |
| Shoot Location(s) | Text | — | No |
| Number of Shoot Days | Number | — | No |
| Crew Assigned | Text or multi-select of staff | — | No |
| Equipment Needed | Long Text | — | No |
| Deliverable Specs | Long Text | e.g. aspect ratio, length, resolution, format, number of cutdowns | Yes |
| Number of Revisions Included | Number | — | Yes |
| Usage Rights / License Terms | Dropdown | Social Only, Social + Paid Ads, Broadcast, Unlimited/Buyout, Personal Use Only | Yes |
| Music Licensing | Text/URL | Track name + license source | No |
| Raw Footage Storage Link | URL | — | No |
| Final Delivery Link | URL | — | No |

## Podcast-only fields (scope: Projects, used only when Project Type = Podcast)

| Field Name | Type | Options | Required |
|---|---|---|---|
| Recording Cadence | Dropdown | Weekly, Biweekly, Monthly, One-off | Yes |
| Distribution Platforms | Text or multi-select | e.g. Spotify, Apple Podcasts, YouTube | No |
| Current Episode Number | Number | — | No |

## Why Project Type and Deliverable Medium each exist twice

The Sales Pipeline card's copy of these fields determines which Project Template gets applied when you convert a won card into a Project (docs/05, docs/09 Automation #1). The Project-level copy stays independently editable afterward in case scope changes mid-project.
