# Team Roles & Permissions

**Correction from earlier (Plutio-era) planning:** Plutio's model — four base roles plus a fully custom permission editor (Settings → User Roles, granular per-module rights, per-project overrides) — doesn't exist in SuiteDash. Confirmed live: the Add Staff Member form's **Staff Role** dropdown offers exactly six fixed options, with no customization screen anywhere in Settings:

> Admin, Project Manager, Office Manager, Teammate, Salesperson, Freelancer

(There's also a **Super Admin** tier above these six — the account owner — which isn't itself assignable from this dropdown; it's what the original account holder starts as.)

## Mapping the original 4 roles onto SuiteDash's fixed set

| Originally planned | Maps to | Why |
|---|---|---|
| Producer/PM | **Project Manager** | Closest named match; broad Projects/Sales access fits the Producer/PM job |
| Editor | **Teammate** | See note below — Freelancer looks like the better name fit but is more restrictive |
| Videographer/Photographer | **Teammate** | Same reasoning as Editor |
| Sales/Account Manager | **Salesperson** | Direct named match |

**Why Teammate over Freelancer for Editor/Videographer/Photographer:** despite "Freelancer" sounding like the natural fit for contract crew, a SuiteDash founder confirmed on a public support thread that Freelancer access is deliberately narrower than regular Staff — specifically, **Team Talk, Files, and Live Chat are closed to the Freelancer role**. Since editors and videographers need Files access (to pull footage, push drafts) as a baseline, Teammate is the better-fitting role for them even though the name is less on-the-nose. Reserve Freelancer only for a true one-off contractor who shouldn't see internal files or chat at all. *(Sourced from a SuiteDash founder reply on AppSumo's public Q&A for the product, not SuiteDash's own help docs directly — treat as reliable but not primary-source-verified.)*

## What's confirmed vs. not independently verified

Confirmed live, in this account:
- The six-role list above and the lack of any custom-permission UI.
- Staff get portal access the same way Clients do — a **Portal Access Invitation** email with a one-time link that prompts them to set a password (docs/12 covers the Client-side version of this in detail; it's the identical mechanism for Staff).
- **Teams** are a separate concept from Roles — a Team is just a named grouping of Staff Members you can bulk-assign to a Project at once, rather than adding each person individually. Team names are visible only to Super Admin, Admin, Project Manager, and Office Manager.

Reported by other SuiteDash users (not independently verified in this account — worth confirming before relying on it):
- Roles can reportedly only be changed **upward**, not downward, once assigned (e.g. you can promote Teammate → Project Manager, but not demote Project Manager → Teammate) — if true, be deliberate about initial role assignment rather than planning to adjust it later.
- All Staff may be able to see all CRM Contacts regardless of role, with no per-role "Limited vs. Full contact view" setting (unlike the old Plutio-based plan's assumption). If accurate, there's no way to restrict a Teammate/Freelancer editor from seeing your full client list the way the original Plutio design intended — worth testing once a second real staff member or contractor is added, by logging in as them and checking what they can see.

## Current live state

- **Marcus Williams** — Super Admin (account owner).
- **Eric Camacho** — added as **Project Manager**, matching the Producer/PM mapping above. Status shows **"Not Invited"** — his Portal Access Invitation hasn't been sent yet, so he can't log in until that happens (Manage Staff → his row → send invitation, whenever you're ready to onboard him).
- No other staff or contractors exist yet, so there's nothing live to configure for Editor, Videographer/Photographer, or Sales/Account Manager — when you hire or bring on a contractor for one of those functions, add them as Staff with the role from the mapping table above (Teammate or Salesperson).

## Notes

- There's no equivalent of Plutio's locked-down built-in "Client" role to separately configure — Client portal access and visibility are governed entirely by the mechanics in docs/10 and docs/12 (Assigned To = Client on tasks, Portal Access Invitation for login), not by a staff-side role setting.
- Revisit this doc once real Editor/Videographer/Sales hires exist — in particular, confirm the contact-visibility behavior empirically at that point, since it's currently sourced from other users' reports rather than a live test in this account.
