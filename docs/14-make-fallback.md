# Fallback: Make.com instead of Zapier (New Inquiry automation) — OBSOLETE

**No longer applicable.** Automation #2 (New Inquiry) now runs as a native SuiteDash Kickoff Form with its own built-in CRM-creation and email-notification automation — see docs/06 (Form 1) and docs/09. There is no Zapier webhook, no Plutio "Create Person" step, and nothing to fall back to Make.com from. Kept only for historical reference from the Plutio-era build.

---

Use this only if Zapier support can't resolve the intermittent "required field missing" error on the Plutio "Create Person" step (see docs/09, Automation #2). Make.com (make.com) has its own Plutio integration and tends to handle incoming webhook data more explicitly, which may avoid the bug entirely. Same logical flow, different platform — no changes needed to the form's fields.

## 1. Create a Make.com account and scenario

1. Sign up at make.com (free tier covers this volume easily).
2. Click **Create a new scenario**.

## 2. Trigger: Custom Webhook

1. Add a module → search **Webhooks** → choose **Custom webhook**.
2. Click **Add** to create a new webhook, give it a name (e.g. "New Inquiry"), and click Save. Make gives you a webhook URL — copy it.
3. In `templates/forms/new-inquiry-embed.html`, replace the value of `WEBHOOK_URL` with this new Make.com URL (same spot as the Zapier URL is now).
4. Click **"Re-determine data structure"** (Make's version of Zapier's trigger test) — it'll wait for a real request. Go submit the live form once to send sample data, then Make will auto-detect the field structure (firstName, lastName, email, phone, company, projectType, deliverableMedium, estimatedBudgetRange, desiredTimeline, projectDescription, leadSource, referredBy).

## 3. Action: Plutio → Create a Person

1. Add a module → search **Plutio** → choose **Create a Person** (exact label may vary slightly).
2. Connect your Plutio account — Make will ask for the same API key/credentials used for Zapier (Plutio Settings → Integrations/API).
3. Map fields:
   - First Name → `firstName`
   - Last Name → `lastName`
   - Email → `email`
   - Phone → `phone`
   - Role → type the literal value `client` (lowercase — confirmed this is the value Plutio's API expects, not "Client")
   - Invite to Plutio → set to `false`/No
4. If Make's Plutio module exposes a Company field here (worth checking — Zapier's didn't), map Company → `company`. If not, same fallback as the Zapier build: leave it off here and include it in the notification email instead.
5. Run this module once to test (Make calls this "Run once") and confirm a real Person is created with the correct fields — no error.

## 4. Action: Email notification

1. Add a module → search **Email** → choose **Send an email** (Make's built-in email module, no separate account needed — similar to Zapier's "Email by Zapier").
2. To: `info@two-twelvemedia.com`
3. Subject: `New Inquiry — {{firstName}} {{lastName}} ({{projectType}})`
4. Body: same content as the Zapier version (docs/09) — dump in Company, Email, Phone, Deliverable Medium, Estimated Budget Range, Desired Timeline, Lead Source, Referred By, Project Description — plus the reminder line to add the lead to the Sales Pipeline board's "New Lead" column by hand (Make's Plutio integration has the same limitation as Zapier's: it can create tasks inside a Project, not on a standalone Task Board).
5. Run once to test, confirm the email arrives with real data.

## 5. Turn it on

1. Toggle the scenario to **ON** (Make's equivalent of Zapier's Publish).
2. Submit one final live test from the actual website, confirm the Person is created and the email arrives.
3. Delete the test Person record(s) and any test Sales Pipeline cards afterward.

## Notes

- No dedupe/duplicate-check step here either, same reasoning as the Zapier build (docs/09): not worth the added complexity for how rarely it'd matter. If this ever becomes worth revisiting, Make's Plutio integration does expose a **Search People** action (which Zapier's doesn't) — a real fix would look like: Search People by email → router/filter on found vs. not found → Create Person only on the "not found" branch, both branches continuing to the notification email.
- Everything else in the system (Plutio itself, the Sales Pipeline board, Project Templates, docs/02–13) is unaffected by this swap — only the webhook destination and the automation platform change.
