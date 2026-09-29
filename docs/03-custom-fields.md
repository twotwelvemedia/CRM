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
| Industry | Dropdown | Corporate, Nonprofit, E-commerce/Retail, Hospitality, Real Estate, Healthcare, Education, Personal/Individual, Music/Entertainment, Other | No |
| Website | URL | — | No |
| Brand Guidelines Link | URL | — | No |

## Sales Pipeline card fields (scope: the "Video Production Sales" Task Board — docs/02)

| Field Name | Type | Options | Required |
|---|---|---|---|
| Project Type | Dropdown | Commercial, Brand Story, Conference, Podcast | Yes |
| Deliverable Medium | Dropdown | Video Only, Photo Only, Video + Photo | Yes |
| Estimated Budget / Package Tier | Dropdown | Basic, Standard, Premium, Custom | Yes |
| Target Shoot Date(s) | Date | — | No |
| Lead Source | Dropdown | Referral, Website, Instagram, Google Search, Google Ads, Past Client, Networking Event, Cold Outreach, Other | No |
| Lost Reason | Dropdown | Budget Mismatch, Chose Competitor, Timing/Not Ready, Went Silent, Scope Not a Fit | Only when Stage = Lost |

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
