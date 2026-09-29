# Project Templates

Build these under Projects → Templates. Each one becomes a reusable task list/kanban that gets applied automatically when a deal is won (docs/09, Workflow #1), matched by the deal's **Project Type** field.

Four project types only: **Commercial**, **Brand Story**, **Conference**, and **Podcast**. Commercial, Brand Story, and Conference share the same 7-phase Base Template shape (just with different emphasis per type). Podcast is structured differently — it's an ongoing/episodic show, not a single shoot-to-delivery arc — see its own section below.

## Deliverable Medium: Video, Photo, or Both

Every one of these four project types can involve video, photography, or both. Set the **Deliverable Medium** field (docs/03: Video Only / Photo Only / Video + Photo) on the Deal and Project, and whenever it includes Photo, fold the **Photo Add-On Tasks** below into the matching phases of whichever template you're building — don't build separate all-photo templates from scratch.

### Photo Add-On Tasks (add when Deliverable Medium includes Photo)

- Phase 2 — Pre-Production: add "Photo shot list confirmed" and "Photographer(s) booked"
- Phase 3 — Production: add "Photos captured" and "Memory cards backed up on-site (2 copies minimum)"
- Phase 4 — Post-Production: add "Photo culling/selects complete" and "Photo editing/retouching complete" and "Photo gallery prepared"
- Phase 6 — Final Delivery: add "Photo gallery delivered via Client Portal **(Client-Visible)**"

## Client visibility: Milestones vs. Tasks

Each of the 7 phases in the Base Template is also a client-facing **Milestone** — the progress bar clients see in their portal. See `docs/12-client-logins-and-progress-tracking.md` for full setup. Tasks marked **(Client-Visible)** should be toggled visible in SuiteDash; everything else stays Team Only. Podcast uses a different milestone approach — see its section below.

---

## Base Template: "Standard Video Project"

Used by **Commercial**, **Brand Story**, and **Conference** — build this once, then duplicate it and apply each type's differences below.

### Phase 1 — Onboarding & Kickoff
- [ ] Welcome email + portal invite sent (auto via Workflow #1)
- [ ] Confirm client has portal login access (invite sent + accepted)
- [ ] Internal kickoff: assign Producer/PM, Editor, Videographer(s)/Photographer(s)
- [ ] Confirm Creative Brief received (link to Deal)
- [ ] Confirm deposit invoice paid
- [ ] Schedule kickoff call with client
- [ ] Add key dates to shared calendar (shoot date, review date, delivery date)
- [ ] Mark "Onboarding & Kickoff" milestone complete

### Phase 2 — Pre-Production
- [ ] Finalize script / outline / interview questions
- [ ] Build shot list
- [ ] Location scouting & confirmation
- [ ] Location permits / access confirmed
- [ ] Talent/crew booked (on-camera talent, models, VO artist)
- [ ] Model/location releases prepared
- [ ] Equipment list finalized & gear reserved
- [ ] Shoot day schedule/call sheet sent to crew & client
- [ ] Weather/backup date contingency confirmed (if outdoor)
- [ ] Mark "Pre-Production" milestone complete

### Phase 3 — Production
- [ ] Day-of equipment check
- [ ] Signed releases collected on-site
- [ ] Principal footage captured
- [ ] B-roll captured
- [ ] Audio recorded and checked
- [ ] Footage backed up on-site (2 copies minimum)
- [ ] Footage uploaded to project storage
- [ ] Mark "Production" milestone complete

### Phase 4 — Post-Production
- [ ] Footage ingested & organized
- [ ] Selects/logging complete
- [ ] Rough cut complete
- [ ] Internal review of rough cut
- [ ] Music & SFX selected (licensing confirmed — Music Licensing field)
- [ ] Graphics/titles/lower thirds added
- [ ] Color grading complete
- [ ] Sound mix complete
- [ ] Final internal QC (audio levels, spelling, brand compliance, specs match Deliverable Specs field)
- [ ] Mark "Post-Production" milestone complete

### Phase 5 — Client Review & Revisions
- [ ] Review link sent via Client Portal **(Client-Visible)**
- [ ] Feedback deadline communicated
- [ ] Revision round 1 applied
- [ ] Revision round 2 applied (if included in package — check Number of Revisions Included field)
- [ ] Client sign-off received **(Client-Visible)**
- [ ] Mark "Client Review & Revisions" milestone complete

### Phase 6 — Final Delivery
- [ ] Final files exported in all required formats/specs
- [ ] Files delivered via Client Portal **(Client-Visible)**
- [ ] Usage rights/license terms confirmed in writing
- [ ] Raw footage archived per studio retention policy
- [ ] Mark "Final Delivery" milestone complete

### Phase 7 — Wrap-up
- [ ] Final invoice sent (auto via Workflow #5)
- [ ] Payment confirmed
- [ ] Testimonial/review request sent (auto via Workflow #6)
- [ ] Project marked Complete/Archived
- [ ] Internal post-mortem (what worked / what didn't)
- [ ] Mark "Wrap-up / Complete" milestone complete

---

## Commercial — differences from Base

- Add to Phase 1: "Brand guidelines received and confirmed"
- Add to Phase 2: "Confirm usage/media buy rights (social, paid ads, broadcast) — sets Usage Rights field and licensing fee"
- Add to Phase 4: "Legal/brand compliance review before delivery"

## Brand Story — differences from Base

- Add to Phase 1: "Brand guidelines received and confirmed"
- Add to Phase 2: "Identify story subjects/interviewees"
- Add to Phase 2: "Pre-interview calls to shape narrative and confirm key messaging"
- Add to Phase 2: "B-roll list for brand environment/product/team"
- Add to Phase 4: "Story/narrative edit (paper cut) before video edit"
- Note: Brand Story projects often run longer revision cycles than a straight commercial — set Number of Revisions Included accordingly

## Conference — differences from Base

- Add to Phase 1: "Confirm number of photographers/videographers needed for the event"
- Add to Phase 2: "Confirm run-of-show/agenda from client"
- Add to Phase 2: "Identify key moments not to miss (keynotes, panels, awards)"
- Add to Phase 2: "Confirm number of cameras needed for simultaneous sessions"
- Add to Phase 2: "Confirm credentialing/press access if required by the venue"
- Add to Phase 3: "Confirm backup battery/storage plan — live, unrepeatable event, no reshoots possible"
- Optional add to Phase 4: "Same-day highlight edit" (if sold as an add-on)
- This is the project type most likely to have Deliverable Medium = "Video + Photo" — build the Photo Add-On Tasks above into this template by default

---

## Podcast — separate structure (ongoing/episodic)

Podcast work isn't a single shoot-to-delivery arc — it's an ongoing show with recurring episodes. Build **one Project per show** (not per episode), with a one-time Show Setup phase followed by a repeating Episode Cycle task list.

### Show Setup (one-time, at onboarding)
- [ ] Confirm show format (interview, solo, panel) and typical episode length
- [ ] Confirm recording location/setup (in-studio vs. remote/guest via call)
- [ ] Confirm audio/video equipment and recording software
- [ ] Confirm Deliverable Medium — most podcast clients want Video + Photo (episode video, audio file, and thumbnail/cover photos)
- [ ] Build episode intro/outro template (graphics, music bed, licensing confirmed)
- [ ] Confirm distribution platforms (Spotify, Apple Podcasts, YouTube, etc. — Distribution Platforms field, docs/03)
- [ ] Confirm publishing cadence and set Recording Cadence field (docs/03)
- [ ] Confirm client has portal login access (invite sent + accepted)
- [ ] Mark "Show Setup" milestone complete

### Episode Cycle (repeat for every episode)
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
- [ ] Episode invoice processed (per-episode billing) or confirmed included in retainer (docs/08)

### Podcast Milestones — different from the standard 7

Because a Podcast Project runs on and on rather than wrapping up once, don't use the standard 7-phase milestone bar. Instead, use a rolling milestone per episode, named clearly (e.g. "Episode 12 — Recorded," "Episode 12 — Published"), so the client's portal always shows the status of the current episode(s) rather than a single progress bar for the whole show. See `docs/12-client-logins-and-progress-tracking.md` for how this changes client login/progress setup for Podcast clients specifically.
