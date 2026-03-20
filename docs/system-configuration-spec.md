# System Configuration Spec — Phase 1 (Core CRM & Pipeline)

## Purpose
Define the exact GoHighLevel (GHL) configuration required for Phase 1 setup: user roles, tags, custom fields, pipeline stages, forms, dashboard, and calendar settings.

---

## 1) Users & Permissions
**Roles**
- **Owner/Admin**: full access (settings, pipelines, automations, calendars)
- **VA (Intake Coordinator)**: contacts, pipeline, forms, calendar, notes
- **Care Manager**: contacts, pipeline, notes (no settings access)

**Minimum access needed**
- Create/edit contacts
- Move pipeline stages
- View forms submissions
- Book/modify appointments

---

## 2) Contact Tags
Create the following tags:
- `Lead`
- `Referral`
- `Family` (adult child)
- `Hospital`
- `VA`
- `Follow-Up Needed`
- `Tour Scheduled`
- `Tour Completed`
- `Accepted`
- `Rejected`
- `Waitlist`
- `Move-In Scheduled`
- `Moved In`

---

## 3) Custom Fields (Contacts)
Create these fields (type in parentheses):

**Client/Resident**
- `Resident Full Name` (single line)
- `Resident DOB` (date)
- `Resident Gender` (dropdown: Male, Female, Other)
- `Primary Diagnosis` (multi-line)
- `Care Level Needed` (dropdown: Independent, Assisted, Memory Care, Hospice)
- `Mobility Status` (dropdown: Ambulatory, Walker, Wheelchair, Bedbound)
- `Insurance Type` (dropdown: Private Pay, Long-Term Care, Medicaid, Other)
- `Estimated Move-In Date` (date)
- `Referral Source` (dropdown: Hospital, Family, VA, Professional, Website, Other)

**Decision Maker / POA**
- `Decision Maker Name` (single line)
- `Decision Maker Relationship` (single line)
- `Decision Maker Phone` (phone)
- `Decision Maker Email` (email)

**Financial / Bed Placement**
- `Monthly Budget` (number)
- `Preferred Property` (dropdown: Property A, Property B, No Preference)
- `Preferred Room Type` (dropdown: Private, Shared, No Preference)
- `Bed Assigned` (single line)
- `Room Number` (single line)

---

## 4) Pipeline: “Referral to Resident”
Create a pipeline with these **8 stages** (in order):
1. **New Inquiry**
2. **Contacted**
3. **Screening Complete**
4. **Tour Scheduled**
5. **Tour Completed**
6. **Accepted**
7. **Move-In Scheduled**
8. **Moved In**

**Required automations (Phase 1 baseline):**
- On **New Inquiry** → notify Owner + VA (email + SMS)
- On **Tour Scheduled** → send confirmation to decision maker
- On **Accepted** → internal notification + task to schedule move‑in
- On **Moved In** → tag contact as `Moved In`

---

## 5) Intake Forms
Create two forms and embed on website.

**Form A: Initial Inquiry**
Fields:
- Full Name
- Phone
- Email
- Relationship to resident
- Resident name
- Primary diagnosis
- Care level needed
- Preferred move‑in timeframe
- Budget range
- How did you hear about us?

**Form B: Screening / Pre‑Qualification**
Fields:
- Resident DOB
- Mobility status
- Insurance type
- Medication management needs (Yes/No)
- Behavioral concerns (Yes/No)
- Preferred property
- Preferred room type
- Additional notes

**Automation:** Form submissions → create contact → apply tag `Lead` → add to pipeline stage **New Inquiry**

---

## 6) Bed Management Dashboard (17 Beds)
Create a dashboard with:
- Total beds: 17
- Occupied
- Available
- Pending move‑ins
- Pending move‑outs

**Bed status field**
- `Bed Status` (dropdown: Available, Occupied, Hold, Maintenance)

**Bed record format**
- Bed ID (e.g., A‑01 … A‑09, B‑01 … B‑08)
- Status
- Resident name (if occupied)
- Expected move‑in date
- Expected move‑out date

---

## 7) Calendar Configuration
- Create appointment type: **“Care Tour / Intake Call”**
- Duration: 30–45 min
- Availability: Owner’s working hours
- Buffer: 15 min between tours
- Reminders: email + SMS 24 hrs & 2 hrs prior

---

## 8) Testing Checklist
- Form submission → contact created
- Tags applied correctly
- Pipeline stage assignment correct
- Stage notifications sent
- Calendar booking confirmation received
- Bed dashboard shows correct totals

---

## Sign‑Off Criteria
Owner confirms:
- All fields, tags, and pipeline stages exist
- Forms embedded and working
- Dashboard reflects 17 beds accurately
- Calendar integration stable

---

## Open Items (fill in once known)
- Property names (A/B actual names)
- Exact bed layout
- Owner availability hours
- Website pages for form embed