# Custom Fields

Build these under Settings → Custom Fields, scoped to the object listed. The same list, in flat CSV form for quick reference/ticking off as you build, is in `imports/custom_fields_master.csv`.

## Contact fields

| Field Name | Type | Options | Required |
|---|---|---|---|
| Preferred Contact Method | Dropdown | Email, Phone, Text | No |
| Social Media Handle(s) | Text | — | No |
| Role/Title at Company | Text | — | No |

## Company fields

| Field Name | Type | Options | Required |
|---|---|---|---|
| Industry | Dropdown | Corporate, Nonprofit, E-commerce/Retail, Hospitality, Real Estate, Healthcare, Education, Personal/Individual, Music/Entertainment, Other | No |
| Website | URL | — | No |
| Brand Guidelines Link | URL | — | No |

## Deal fields

| Field Name | Type | Options | Required |
|---|---|---|---|
| Project Type | Dropdown | Commercial/Brand, Corporate/Training, Event Coverage, Wedding, Music Video, Documentary, Social Content Retainer, Other | Yes |
| Estimated Budget / Package Tier | Dropdown | Basic, Standard, Premium, Custom | Yes |
| Target Shoot Date(s) | Date | — | No |
| Lead Source | Dropdown | (mirrors Tags list, docs/04) | No |
| Lost Reason | Dropdown | Budget Mismatch, Chose Competitor, Timing/Not Ready, Went Silent, Scope Not a Fit | Only shown/required when Stage = Lost |

## Project fields

| Field Name | Type | Options | Required |
|---|---|---|---|
| Project Type | Dropdown | Same list as Deal → Project Type | Yes |
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

## Why these two Project Type fields exist twice

The Deal-level Project Type drives which Project Template gets applied automatically when the deal is won (docs/09, Workflow #1). The Project-level copy of the same field stays editable afterward in case scope changes mid-project.
