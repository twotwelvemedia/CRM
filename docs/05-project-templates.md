# Project Templates

**Built and live.** All 4 of these exist as SuiteDash Project Templates (Projects → Templates), each holding its full Task Group / task list below. Use "Start from Template" when creating a new real Project, matched by the card's **Project Type** field.

Four project types only: **Commercial**, **Brand Story**, **Conference**, and **Podcast**. Commercial, Brand Story, and Conference share the same 7-phase Base Template shape. Podcast is structured differently — an ongoing/episodic show, not a single shoot-to-delivery arc — see its own section.

## Phases are Task Groups, not a separate Milestones feature

Correction from earlier planning: Plutio's Projects don't have a dedicated "Milestones" tab or object (confirmed — a real project's tabs are Tasks, Calendar, Timesheet, Transactions, Proposals, Contracts, Conversations, Forms, Files, Wiki, nothing else). Each phase below is built as a **Task Group** inside the project's **Tasks** tab — the exact same mechanism used for the Sales Pipeline board's stages. Progress is whatever Plutio shows for task completion within a Task Group or project (percent of tasks checked off) — there's no separate per-phase deadline/budget tracking object the way SuiteDash-style "Milestones" work. If you want a very visible checkpoint, make the last task in each Task Group something like "Phase complete — notify client" so moving to the next phase is a deliberate, visible action.

## Deliverable Medium: Video, Photo, or Both

Every one of these four project types can involve video, photography, or both. Set the **Deliverable Medium** field (docs/03) on the card and Project, and whenever it includes Photo, fold the **Photo Add-On Tasks** below into the matching Task Groups of whichever template you're building.

### Photo Add-On Tasks (add when Deliverable Medium includes Photo)

- Pre-Production group: add "Photo shot list confirmed" and "Photographer(s) booked"
- Production group: add "Photos captured" and "Memory cards backed up on-site (2 copies minimum)"
- Post-Production group: add "Photo culling/selects complete," "Photo editing/retouching complete," and "Photo gallery prepared"
- Final Delivery group: add "Photo gallery delivered via Client Portal **(Client-Visible)**"

## Client visibility: no Private flag — use Assigned To

**Correction from earlier (Plutio-era) planning:** SuiteDash tasks have no "Private"/visibility toggle at all — confirmed by inspecting the Edit Task form field-by-field (Title, Est. Time, Description, Relative Due Date, Assigned To, Priority, Type, Status, Phase, Followers — nothing else). The opt-in-to-show vs. opt-out-to-hide question doesn't apply here; a different mechanism entirely controls client visibility.

**Confirmed live:** the **Assigned To** field on every task includes **Client** as a selectable option, alongside the internal roles (Project Leader, Coordinator, Salesperson) and named staff. Setting a task's Assigned To to **Client** is what surfaces it in the client's portal (the "Client Tasks" dashboard widget). When Assigned To is set to Client, a second toggle appears — **"Request Client Approval?"** — purpose-built for sign-off/approval-style tasks.

**What this means for the tasks flagged (Client-Visible) below:** each one needs **Assigned To** changed from the template default (Project Leader) to **Client**. For the sign-off/approval tasks specifically (e.g. "Client sign-off received," "Client approval received"), also enable **Request Client Approval?**.

**Built and live.** All 13 (Client-Visible)-flagged tasks across the 4 templates now have Assigned To set to **Client**, confirmed via fresh reload — the "(Client-Visible)" suffix is no longer just a label, it's backed by the actual mechanism. The 4 sign-off/approval-style tasks ("Client sign-off received" ×3, "Client approval received" on Podcast) also have **Request Client Approval?** enabled.

(Previously this was blocked — the quick-edit panel's real Save control turned out to be the "+ Add" button near Followers at the bottom of the form, which is actually `type="submit"` for the whole task-edit form, not just an add-a-follower button as its label implies. No visible "Save" text anywhere on the panel; that's the one that works.)

---

## Base Template: "Standard Video Project"

Used by **Commercial**, **Brand Story**, and **Conference** — build this once, then duplicate it and apply each type's differences below.

### Task Group 1 — Onboarding & Kickoff
- [ ] Welcome email sent + client portal link shared (auto via Automation #1)
- [ ] Internal kickoff: assign Producer/PM, Editor, Videographer(s)/Photographer(s)
- [ ] Confirm Creative Brief received (link to Sales Pipeline card)
- [ ] Confirm deposit invoice paid
- [ ] Kickoff call booked (client self-serves via the Kickoff Call Scheduler link, docs/13)
- [ ] Add key dates to shared calendar (shoot date, review date, delivery date)

### Task Group 2 — Pre-Production
- [ ] Finalize script / outline / interview questions
- [ ] Build shot list
- [ ] Location scouting & confirmation
- [ ] Location permits / access confirmed
- [ ] Talent/crew booked (on-camera talent, models, VO artist)
- [ ] Model/location releases prepared
- [ ] Equipment list finalized & gear reserved
- [ ] Shoot day schedule/call sheet sent to crew & client
- [ ] Weather/backup date contingency confirmed (if outdoor)

### Task Group 3 — Production
- [ ] Day-of equipment check
- [ ] Signed releases collected on-site
- [ ] Principal footage captured
- [ ] B-roll captured
- [ ] Audio recorded and checked
- [ ] Footage backed up on-site (2 copies minimum)
- [ ] Footage uploaded to project storage

### Task Group 4 — Post-Production
- [ ] Footage ingested & organized
- [ ] Selects/logging complete
- [ ] Rough cut complete
- [ ] Internal review of rough cut
- [ ] Music & SFX selected (licensing confirmed — Music Licensing field)
- [ ] Graphics/titles/lower thirds added
- [ ] Color grading complete
- [ ] Sound mix complete
- [ ] Final internal QC (audio levels, spelling, brand compliance, specs match Deliverable Specs field)

### Task Group 5 — Client Review & Revisions
- [ ] Review link sent via Client Portal **(Client-Visible)**
- [ ] Feedback deadline communicated
- [ ] Revision round 1 applied
- [ ] Revision round 2 applied (if included in package — check Number of Revisions Included field)
- [ ] Client sign-off received **(Client-Visible)**

### Task Group 6 — Final Delivery
- [ ] Final files exported in all required formats/specs
- [ ] Files delivered via Client Portal **(Client-Visible)**
- [ ] Usage rights/license terms confirmed in writing
- [ ] Raw footage archived per studio retention policy

### Task Group 7 — Wrap-up
- [ ] Final invoice sent (auto via Automation #5)
- [ ] Payment confirmed
- [ ] Testimonial/review request sent (auto via Automation #6)
- [ ] Project marked Complete/Archived
- [ ] Internal post-mortem (what worked / what didn't)

---

## Commercial — differences from Base

- Add to Group 1: "Brand guidelines received and confirmed"
- Add to Group 2: "Confirm usage/media buy rights (social, paid ads, broadcast) — sets Usage Rights field and licensing fee"
- Add to Group 4: "Legal/brand compliance review before delivery"

## Brand Story — differences from Base

- Add to Group 1: "Brand guidelines received and confirmed"
- Add to Group 2: "Identify story subjects/interviewees"
- Add to Group 2: "Pre-interview calls to shape narrative and confirm key messaging"
- Add to Group 2: "B-roll list for brand environment/product/team"
- Add to Group 4: "Story/narrative edit (paper cut) before video edit"
- Note: Brand Story projects often run longer revision cycles than a straight commercial — set Number of Revisions Included accordingly

## Conference — differences from Base

- Add to Group 1: "Confirm number of photographers/videographers needed for the event"
- Add to Group 2: "Confirm run-of-show/agenda from client"
- Add to Group 2: "Identify key moments not to miss (keynotes, panels, awards)"
- Add to Group 2: "Confirm number of cameras needed for simultaneous sessions"
- Add to Group 2: "Confirm credentialing/press access if required by the venue"
- Add to Group 3: "Confirm backup battery/storage plan — live, unrepeatable event, no reshoots possible"
- Optional add to Group 4: "Same-day highlight edit" (if sold as an add-on)
- This is the project type most likely to have Deliverable Medium = "Video + Photo" — build the Photo Add-On Tasks above into this template by default

---

## Podcast — separate structure (ongoing/episodic)

Podcast work isn't a single shoot-to-delivery arc — it's an ongoing show with recurring episodes. Build **one Project per show** (not per episode). Instead of 7 fixed Task Groups, give it a one-time Show Setup group, then **create a new Task Group for every episode** (e.g. "Episode 12"), so the current episode's status is always visible separately from past ones.

### Task Group: Show Setup (one-time, at onboarding)
- [ ] Confirm show format (interview, solo, panel) and typical episode length
- [ ] Confirm recording location/setup (in-studio vs. remote/guest via call)
- [ ] Confirm audio/video equipment and recording software
- [ ] Confirm Deliverable Medium — most podcast clients want Video + Photo (episode video, audio file, and thumbnail/cover photos)
- [ ] Build episode intro/outro template (graphics, music bed, licensing confirmed)
- [ ] Confirm distribution platforms (Distribution Platforms field, docs/03)
- [ ] Confirm publishing cadence and set Recording Cadence field (docs/03)

### Episode Task Group (create a new one for every episode, e.g. "Episode 12")
- [ ] Episode topic/guest confirmed
- [ ] Recording scheduled (date/time, location or call link)
- [ ] Pre-interview/questions prepared
- [ ] Recording day: video + audio captured
- [ ] Thumbnail/cover photos captured
- [ ] Raw footage/audio backed up (2 copies minimum)
- [ ] Episode edited (sync, cuts, filler-word removal)
- [ ] Show notes/episode description drafted
- [ ] Thumbnail/cover image designed
- [ ] Clips/audiograms cut for social (optional add-on)
- [ ] Episode sent for client review **(Client-Visible)**
- [ ] Client approval received **(Client-Visible)**
- [ ] Episode published to platforms **(Client-Visible)**
- [ ] Episode invoice processed (per-episode billing) or confirmed included in Subscription (docs/08)
