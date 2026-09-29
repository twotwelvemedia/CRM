# Project Templates

Build these under Projects → Templates. Each becomes a reusable Project Template — carrying its custom field values and task lists — that gets applied when a Sales Pipeline card is won, matched by the card's **Project Type** field.

Four project types only: **Commercial**, **Brand Story**, **Conference**, and **Podcast**. Commercial, Brand Story, and Conference share the same 7-phase Base Template shape. Podcast is structured differently — an ongoing/episodic show, not a single shoot-to-delivery arc — see its own section.

## Milestones: how progress actually shows to the client

Each phase below is a native Plutio **Milestone**, not just a task label. Plutio's Milestones give each phase its own deadline (and optionally a budget allocation), and track progress at that level rather than only as a single project total. Build each phase as a Milestone, then group its tasks underneath it. As tasks complete, Plutio's real-time progress bar updates automatically; mark the Milestone itself **reached** once every task under it is done. This Milestone progress is what the client actually sees in their portal — see `docs/12-client-logins-and-progress-tracking.md`.

## Deliverable Medium: Video, Photo, or Both

Every one of these four project types can involve video, photography, or both. Set the **Deliverable Medium** field (docs/03) on the card and Project, and whenever it includes Photo, fold the **Photo Add-On Tasks** below into the matching Milestones of whichever template you're building.

### Photo Add-On Tasks (add when Deliverable Medium includes Photo)

- Pre-Production Milestone: add "Photo shot list confirmed" and "Photographer(s) booked"
- Production Milestone: add "Photos captured" and "Memory cards backed up on-site (2 copies minimum)"
- Post-Production Milestone: add "Photo culling/selects complete," "Photo editing/retouching complete," and "Photo gallery prepared"
- Final Delivery Milestone: add "Photo gallery delivered via Client Portal **(Client-Visible)**"

## Client visibility: Milestones vs. Tasks

Every Milestone is visible to the client by default in their portal's progress view — that's the point of using them. Individual tasks marked **(Client-Visible)** below should additionally be flagged visible on the task itself; everything else stays internal/team-only.

---

## Base Template: "Standard Video Project"

Used by **Commercial**, **Brand Story**, and **Conference** — build this once, then duplicate it and apply each type's differences below.

### Milestone 1 — Onboarding & Kickoff
- [ ] Welcome email sent + client portal link shared (auto via Automation #1)
- [ ] Internal kickoff: assign Producer/PM, Editor, Videographer(s)/Photographer(s)
- [ ] Confirm Creative Brief received (link to Sales Pipeline card)
- [ ] Confirm deposit invoice paid
- [ ] Kickoff call booked (client self-serves via the Kickoff Call Scheduler link, docs/13)
- [ ] Add key dates to shared calendar (shoot date, review date, delivery date)

### Milestone 2 — Pre-Production
- [ ] Finalize script / outline / interview questions
- [ ] Build shot list
- [ ] Location scouting & confirmation
- [ ] Location permits / access confirmed
- [ ] Talent/crew booked (on-camera talent, models, VO artist)
- [ ] Model/location releases prepared
- [ ] Equipment list finalized & gear reserved
- [ ] Shoot day schedule/call sheet sent to crew & client
- [ ] Weather/backup date contingency confirmed (if outdoor)

### Milestone 3 — Production
- [ ] Day-of equipment check
- [ ] Signed releases collected on-site
- [ ] Principal footage captured
- [ ] B-roll captured
- [ ] Audio recorded and checked
- [ ] Footage backed up on-site (2 copies minimum)
- [ ] Footage uploaded to project storage

### Milestone 4 — Post-Production
- [ ] Footage ingested & organized
- [ ] Selects/logging complete
- [ ] Rough cut complete
- [ ] Internal review of rough cut
- [ ] Music & SFX selected (licensing confirmed — Music Licensing field)
- [ ] Graphics/titles/lower thirds added
- [ ] Color grading complete
- [ ] Sound mix complete
- [ ] Final internal QC (audio levels, spelling, brand compliance, specs match Deliverable Specs field)

### Milestone 5 — Client Review & Revisions
- [ ] Review link sent via Client Portal **(Client-Visible)**
- [ ] Feedback deadline communicated
- [ ] Revision round 1 applied
- [ ] Revision round 2 applied (if included in package — check Number of Revisions Included field)
- [ ] Client sign-off received **(Client-Visible)**

### Milestone 6 — Final Delivery
- [ ] Final files exported in all required formats/specs
- [ ] Files delivered via Client Portal **(Client-Visible)**
- [ ] Usage rights/license terms confirmed in writing
- [ ] Raw footage archived per studio retention policy

### Milestone 7 — Wrap-up
- [ ] Final invoice sent (auto via Automation #5)
- [ ] Payment confirmed
- [ ] Testimonial/review request sent (auto via Automation #6)
- [ ] Project marked Complete/Archived
- [ ] Internal post-mortem (what worked / what didn't)

---

## Commercial — differences from Base

- Add to Milestone 1: "Brand guidelines received and confirmed"
- Add to Milestone 2: "Confirm usage/media buy rights (social, paid ads, broadcast) — sets Usage Rights field and licensing fee"
- Add to Milestone 4: "Legal/brand compliance review before delivery"

## Brand Story — differences from Base

- Add to Milestone 1: "Brand guidelines received and confirmed"
- Add to Milestone 2: "Identify story subjects/interviewees"
- Add to Milestone 2: "Pre-interview calls to shape narrative and confirm key messaging"
- Add to Milestone 2: "B-roll list for brand environment/product/team"
- Add to Milestone 4: "Story/narrative edit (paper cut) before video edit"
- Note: Brand Story projects often run longer revision cycles than a straight commercial — set Number of Revisions Included accordingly

## Conference — differences from Base

- Add to Milestone 1: "Confirm number of photographers/videographers needed for the event"
- Add to Milestone 2: "Confirm run-of-show/agenda from client"
- Add to Milestone 2: "Identify key moments not to miss (keynotes, panels, awards)"
- Add to Milestone 2: "Confirm number of cameras needed for simultaneous sessions"
- Add to Milestone 2: "Confirm credentialing/press access if required by the venue"
- Add to Milestone 3: "Confirm backup battery/storage plan — live, unrepeatable event, no reshoots possible"
- Optional add to Milestone 4: "Same-day highlight edit" (if sold as an add-on)
- This is the project type most likely to have Deliverable Medium = "Video + Photo" — build the Photo Add-On Tasks above into this template by default

---

## Podcast — separate structure (ongoing/episodic)

Podcast work isn't a single shoot-to-delivery arc — it's an ongoing show with recurring episodes. Build **one Project per show** (not per episode). Instead of one set of 7 Milestones for the whole project, give it a one-time Show Setup Milestone, then **create a new Milestone for every episode** (e.g. "Episode 12," each with its own deadline). This maps directly onto Plutio's native per-Milestone deadline/progress tracking, so the client's portal always shows exactly which episode is in progress.

### Milestone: Show Setup (one-time, at onboarding)
- [ ] Confirm show format (interview, solo, panel) and typical episode length
- [ ] Confirm recording location/setup (in-studio vs. remote/guest via call)
- [ ] Confirm audio/video equipment and recording software
- [ ] Confirm Deliverable Medium — most podcast clients want Video + Photo (episode video, audio file, and thumbnail/cover photos)
- [ ] Build episode intro/outro template (graphics, music bed, licensing confirmed)
- [ ] Confirm distribution platforms (Distribution Platforms field, docs/03)
- [ ] Confirm publishing cadence and set Recording Cadence field (docs/03)

### Episode Milestone (create a new one for every episode, e.g. "Episode 12")
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
