# Team Roles & Permissions

Plutio ships four built-in roles — **Owner**, **Co-owner**, **Team**, and **Client** (Client is locked; you can't rename it and many permissions are locked off for it by design). Beyond those, create custom roles under Settings → User Roles with granular permissions across every area. Permissions are set per role, not per person — everyone assigned a role sees and does the same things, and changing the role's permissions updates everyone in it at once. You can also override permissions on specific Projects or Task Boards without changing the role itself, which is how you scope a freelancer to only their assigned work.

Create these roles **before** inviting staff:

| Custom Role | Modeled on | Scope |
|---|---|---|
| Producer/PM | Co-owner-level access to Projects/Sales Pipeline, limited Financials | Full CRM + Projects, view-only Invoices, edit Client Portal content |
| Editor | Team, scoped to assigned Projects | Edit tasks on assigned Projects only, no CRM/Financials access |
| Videographer/Photographer | Team, scoped to assigned Projects | Edit tasks on assigned Projects only, no CRM/Financials access |
| Sales/Account Manager | Team, full Sales Pipeline board | Full CRM + Proposals/Contracts, view-only Invoices, view-only Projects |

## Permission matrix

| Module | Owner | Producer/PM | Editor | Videographer/Photographer | Sales/Account Mgr |
|---|---|---|---|---|---|
| Sales Pipeline / Contacts / Companies | Full | Full | View | None | Full |
| Projects & Tasks | Full | Full | Edit (assigned only, via per-project override) | Edit (assigned only, via per-project override) | View |
| Proposals & Contracts | Full | Full | None | None | Full |
| Invoices & Subscriptions | Full | View | None | None | View |
| Client Portal content (Files, Wiki) | Full | Edit | None | None | None |
| Automations | Full | View | None | None | None |
| Settings/White Label | Full | None | None | None | None |

## Contact visibility

Under each role, Contacts (People and Companies) can be set to **Limited view** (only contacts on shared projects/channels) or **Full view** (all contacts). Set Editor and Videographer/Photographer to Limited view so freelancers and contractors only see the clients they're actually working with, not your full client list.

## Notes

- The built-in Client role governs what clients themselves see when they access their portal link — most of its permissions are locked by Plutio, so there's little to configure beyond what's covered in docs/10 and docs/12.
- Revisit this table once your team grows past these five roles; it's deliberately minimal for a small studio.
