# Personas, Pain Points & Proof-of-Concept PRD

> Companion to [README.md](./README.md) (market & GTM plan).
> Status: **Draft v0.2 for review. Nothing built yet.** v0.2 brings **hospital OPD consultations** and the **medication loop (prescription → pharmacy → patient)** into scope; see §A.5. Pain-point scores are hypotheses to confirm in discovery (Phase 0 shadowing).
> Context: India first, private hospitals with 100–500 beds, inpatient (IPD) wards.

---

## Part A — Personas and pain points

### A.1 Persona map

| # | Persona | Type | Role in the product | Role in the sale |
|---|---|---|---|---|
| P1 | **Ward staff nurse** | Primary user | Captures most entries every shift | Adoption decides renewal |
| P2 | **Nursing in-charge / charge nurse** | Primary user | Runs shift handover; checks ward charts | Local champion |
| P3 | **Resident / junior doctor (RMO, DNB/MD resident)** | Primary user | Progress notes, discharge summaries | Adoption |
| P4 | **Consultant** | Secondary user | Ward rounds; signs off summaries | Influencer (can block) |
| P5 | **Patient** | Beneficiary | Gives consent; receives summary; owns record (ABHA) | Reputation / NPS |
| P6 | **Attendant / family caregiver** | Beneficiary | Often the actual consent-giver and instruction-follower in India | Reputation |
| P7 | **Nursing superintendent / CNO** | Buyer-champion | Configures wards, views dashboards | **Champion** |
| P8 | **Medical director / quality & NABH coordinator** | Buyer | Audit, completeness, incidents | Approver |
| P9 | **CIO / IT head** | Gatekeeper | Integration, security, devices | Can veto |
| P10 | **CEO / CFO / owner** | Economic buyer | ROI dashboard | Signs |
| P11 | **Insurance / TPA desk & billing** | Downstream user | Needs complete discharge docs for claims | ROI evidence |
| P12 | **Pharmacist** (hospital pharmacy in India; community pharmacy in Europe) | Downstream user | Receives structured prescriptions; dispenses; flags queries | Makes the medication loop work |

---

### A.2 Persona profiles

#### P1 — Ward staff nurse ("Anjali")
- **Profile:** 24–32 years old, B.Sc/GNM, 1–6 years of experience. Works 8–12 hour shifts, 6–10 patients (often more at night). Speaks Malayalam, Hindi or Tamil plus English and code-mixes. High attrition; many plan to move abroad.
- **Tools today:** paper nursing charts at the bedside (vitals sheet, intake/output sheet, medication administration record, nurses' notes). Sometimes a HIS nursing module on a shared station PC. WhatsApp for informal coordination.
- **A shift:** care is interrupted constantly. Documentation piles up. Paper charts get filled late in the shift from memory or scraps (gloves, palm notes). HIS entry is often a second copy of the paper.

| ID | Pain point | Severity | Frequency |
|---|---|---|---|
| N1 | **End-of-shift charting backlog**: 1–2+ hours of recording vitals, meds, I/O and notes from memory; overtime or missed breaks | Critical | Every shift |
| N2 | **Double documentation**: same data on paper and then in the HIS | High | Every shift (in HIS hospitals) |
| N3 | **Incomplete or rushed handover**: verbal, unstructured, key items missed (pending labs, fall risk, IV due) | Critical (safety) | 2–3×/day |
| N4 | Remembering timings (meds given, drains, IV rate changes) across many patients | High | Continuous |
| N5 | Shared PCs: queues, logins, and being away from the bedside to chart | Medium | Every shift |
| N6 | NABH audit anxiety: missing signatures and times, blamed for gaps | High | Monthly/audits |
| N7 | Language and English-writing burden for notes | Medium | Daily |
| N8 | Medico-legal exposure: "if it isn't documented, it wasn't done" | High | Rare but serious |

**Good looks like:** "I say what I did right after I do it, in my own words, and the chart is done. At handover the next nurse already has the summary."

#### P2 — Nursing in-charge ("Sister Mary")
| ID | Pain point | Severity |
|---|---|---|
| C1 | Can't see in real time which patients' charts are incomplete or overdue (vitals, turns, pain scores) | High |
| C2 | Handover quality varies by nurse; she has to fill the gaps herself | Critical |
| C3 | Training new or float nurses on documentation standards (high churn) | High |
| C4 | Compiling ward census and incident data for the superintendent | Medium |

#### P3 — Resident doctor ("Dr. Rahul")
- **Profile:** 25–30, 24–36 hour duty cycles, covers 20–40 inpatients. Writes progress notes after rounds and prepares discharge summaries that consultants correct.

| ID | Pain point | Severity |
|---|---|---|
| R1 | **Discharge summary drafting**: 20–45 minutes each; gathering course, meds, investigations from paper and HIS; patients wait hours for discharge and beds stay blocked | Critical |
| R2 | Writing progress notes after rounds from memory while being paged | High |
| R3 | Transcribing consultant's round instructions into orders and notes (error-prone) | High |
| R4 | Insurance queries bouncing back for missing details in the summary | High |
| R5 | Reconstructing the history of a transferred-in patient with no records | Medium |

#### P4 — Consultant ("Dr. Iyer")
| ID | Pain point | Severity |
|---|---|---|
| D1 | Summaries and notes drafted by residents are inconsistent and need rework | Medium |
| D2 | Round instructions not captured and executed accurately | High |
| D3 | Suspicion of AI and fear of liability for AI text | Adoption risk |
| D4 | **High-volume OPD** (often 40–100 patients/day in Indian hospitals): little time per patient, typing or handwriting while talking, eye contact lost | Critical |
| D5 | Writing prescriptions by hand or in a slow HIS screen; illegible or incomplete prescriptions come back as pharmacy queries | High |
| D6 | Follow-up patients arrive without their earlier notes; OPD history and IPD stay live in different places | High |

#### P5 / P6 — Patient and attendant ("Mr. Sharma" and his daughter)
| ID | Pain point | Severity |
|---|---|---|
| PT1 | **Doesn't understand the discharge summary** (English jargon, handwriting): meds, doses, warning signs, follow-up date | Critical (outcomes/readmissions) |
| PT2 | Loses paper records; retells history at every new hospital | High |
| PT3 | Doesn't know what was recorded about them or who sees it; worried about recordings | High (trust) |
| PT4 | Long wait on discharge day for "the file" | High |
| PT5 | Attendant (not the patient) makes decisions but isn't formally in the loop | Medium |
| PT6 | **Medicine confusion**: can't read the prescription, isn't sure of timing, brand substitutions at the pharmacy, runs out and doesn't refill | Critical (adherence/readmissions) |
| PT7 | Walks between OPD, pharmacy and billing; pharmacy stock-outs discovered only at the counter | High |

#### P7 — Nursing superintendent / CNO
| ID | Pain point | Severity |
|---|---|---|
| S1 | **Nurse burnout and attrition** (Apollo cites 25–30%); cost of rehiring and training | Critical |
| S2 | No objective data on documentation workload; can't justify staffing | High |
| S3 | NABH nursing documentation non-compliance in audits | High |
| S4 | Handover-related incidents | High |

#### P8 — Medical director / quality
- Q1 Documentation completeness for NABH (and NABH Digital Health Standards).
- Q2 Discharge TAT (turnaround time) and bed turnover.
- Q3 Incident traceability.

#### P9 — CIO / IT head
- I1 The HIS vendor charges for or delays every integration.
- I2 Data security, DPDP obligations, and where audio goes.
- I3 Device management (shared phones, BYOD policy), and ward Wi-Fi dead zones.

#### P10 — CEO / CFO
- F1 Wants hard ROI: FTE capacity, overtime, discharge TAT, claim denials. Rejects "soft" benefits.
- F2 Sensitive to per-seat pricing because contract nurses rotate.

#### P11 — TPA / billing desk
- B1 Claims queried or denied for incomplete discharge documentation; cash-flow delays.

#### P12 — Pharmacist
| ID | Pain point | Severity |
|---|---|---|
| PH1 | Illegible or incomplete prescriptions (missing strength, frequency, duration) mean calling the doctor, and patients wait | High |
| PH2 | Discharge medicines requested at the last minute, which delays discharge | High |
| PH3 | No view of the patient's other medicines, so duplicates and interactions are caught late or not at all | High (safety) |
| PH4 | *Europe:* e-prescription handled through national systems; free-text or badly coded prescriptions still cause queries | Medium |

---

### A.3 Prioritisation: what to fix first

**Scoring (1–5 each):**
- **Pain** = severity × frequency, normalised
- **AI-fit** = can current speech and LLM tech do it reliably today?
- **Prove-fast** = measurable impact within a 60–90 day pilot?
- **Buyer value** = would P7/P10 pay for it?
- **Low risk** = low patient-safety and regulatory risk (5 = safest)
- **No-integration** = can it deliver value without HIS integration?

| Pain point | Pain | AI-fit | Prove-fast | Buyer value | Low risk | No-integration | **Total /30** |
|---|---|---|---|---|---|---|---|
| **N1 Nurse charting backlog** | 5 | 4 | 5 | 5 | 4 | 4 | **27** |
| **N3/C2 Shift handover** | 5 | 5 | 5 | 4 | 4 | 5 | **28** |
| **R1 Discharge summary drafting** | 5 | 4 | 5 | 5 | 3 | 3 | **25** |
| **PT1 Patient understands discharge** | 5 | 4 | 4 | 3 | 3 | 5 | **24** |
| PT3 Consent and transparency (trust) | 4 | 5 | 4 | 3 | 5 | 5 | 26 → *foundation, not a feature* |
| N2 Double documentation (HIS write-back) | 4 | 4 | 3 | 4 | 4 | 1 | 20 |
| C1 Real-time chart completeness view | 4 | 5 | 4 | 4 | 5 | 4 | 26 → *falls out of N1 data* |
| R2 Progress notes from rounds | 4 | 4 | 4 | 3 | 3 | 3 | 21 |
| R3 Round instructions → orders | 4 | 3 | 3 | 4 | 1 | 1 | 16 |
| PT2 Portable records (ABHA) | 4 | 4 | 2 | 2 | 4 | 2 | 18 |
| B1 Claims completeness | 4 | 3 | 2 | 5 | 4 | 3 | 21 |
| OPD consultation note + prescription draft (hospital OPD, D4–D6) | 4 | 5 | 5 | 4 | 3 | 4 | **25** → *promoted in v0.2* |
| Medication loop: structured Rx → pharmacy → patient schedule (PT6, PH1–PH2) | 5 | 4 | 4 | 4 | 3 | 3 | **23** → *promoted in v0.2* |
| OPD in standalone clinics (not hospital) | 3 | 5 | 4 | 3 | 3 | 3 | 21 (crowded: Eka, HealthPlix; different GTM) |

### A.4 Critical set for the proof of concept

**Fix these six, with consent as the foundation:**

| # | Critical problem | Personas | Why it's in the PoC |
|---|---|---|---|
| **1** | **Voice-to-chart for nurses** (N1, N4, N6, C1) | P1, P2, P7 | Biggest time sink; structured output is verifiable; the voize-proven pattern; directly measurable in minutes per shift |
| **2** | **Auto-generated SBAR shift handover** (N3, C2) | P1, P2, P7, P8 | Built from data we already capture in #1; high safety value; no integration needed; visible to every nurse twice a day, which drives habit |
| **3** | **Discharge summary draft** (R1, R4, PT4) | P3, P4, P8, P10, P11 | Hardest ROI for the CFO (discharge TAT, bed turnover, claim queries); brings doctors onto the same patient timeline |
| **4** | **Patient-friendly discharge instructions** in the patient's language (PT1, PT3) | P5, P6 | The differentiator and the trust story; low build cost once #3 exists |
| **5** | **OPD consultation note + prescription draft** in the same hospitals (D4–D6) | P4, P3, P5 | Reuses ~70% of the engine; consultants spend most of their day in OPD, so this wins the doctors; gives one patient timeline from OPD → admission → discharge → follow-up OPD |
| **6** | **Medication loop**: structured prescription → hospital pharmacy → patient medicine schedule and reminders (PT6, PH1–PH2) | P12, P5, P6, P3 | Closes the loop the patient actually experiences; cuts pharmacy queries and discharge delays; in Europe it is the path into national e-prescription (EHDS priority data from March 2029) |
| **Foundation** | **Consent + clinician-approval + audit** (PT3, D3, I2) | All | Non-negotiable for DPDP and for trust; also a sales asset |

**Explicitly deferred (not in PoC):** HIS write-back for all hospitals (1 adapter only, see §B.9), inpatient orders/CPOE, ICU device feeds, standalone-clinic OPD go-to-market, clinical decision support (including automated drug-interaction alerts), external retail-pharmacy network in India, live national e-prescription in Europe (designed for, built in the Europe phase), coding/billing, full ABHA M3 fetch, iOS, hardware.

**PoC hypotheses**
- **H1:** Nurses using voice-to-chart save **≥30 minutes per 8-hour shift** (≥45 for 12-hour) of documentation time versus baseline.
- **H2:** AI-drafted nursing entries are accepted with no or minor edits **≥85%** of the time, with **zero** unrecovered critical errors (wrong patient, drug, dose or route).
- **H3:** Auto-SBAR handover cuts handover time by **≥25%** and handover omissions (audited) by **≥50%**.
- **H4:** Discharge summary drafting time drops from ~30 to **≤10 minutes**, and discharge-order-to-exit TAT improves by **≥20%**.
- **H5:** **≥80%** of patients/attendants correctly answer 3 teach-back questions (meds, red flags, follow-up) using the multilingual summary, versus baseline.
- **H6:** **≥70%** of eligible nurses on pilot wards are weekly active by week 6. This is the adoption hypothesis and the most likely to fail.
- **H7 (OPD):** Consultants using the OPD module finish the note and prescription **before the patient leaves the room in ≥80% of visits**, with ≥90% of drafts accepted with minor or no edits, and no increase in consultation length.
- **H8 (medication loop):** Pharmacy queries on prescriptions drop by **≥50%**; discharge medicines are ready **before** the discharge summary is signed in ≥70% of discharges; ≥60% of patients who opt in still use the medicine schedule at day 14.
- **Kill / pivot signals:** adoption below 40% at week 6 despite fixes; critical error rate we can't bring to zero with guardrails; time saved under 15 min/shift.

### A.5 Why OPD and medication were deferred in v0.1, and why v0.2 brings them in

**Can the solution just be extended to OPD? Mostly yes.** Capture, speech recognition, grounding, review and approve, consent, audit, patient summary and the FHIR model are shared. The work that is genuinely new:

| Area | Inpatient (IPD) nursing | OPD consultation | Extra work |
|---|---|---|---|
| Capture | Nurse dictates *after* care (push-to-talk) | **Ambient**: doctor–patient conversation, 2–4 speakers | Speaker separation, conversational (not dictation) extraction, more noise |
| Consent | Once at admission | **Every visit**, often in a crowded room | Fast per-visit consent at registration + verbal confirmation |
| Output | Structured chart fields | Note (history, exam, assessment, plan) + **prescription** | New templates per specialty |
| Safety | Records what was done | Prescription drives what *will* be done | Higher bar: drug/strength/frequency/duration all confirmed by the doctor |
| Buyer and metric | CNO; nurse time | Medical director; OPD throughput, doctor time | Separate ROI story |

**Why it was deferred:** focus and proof, not technology. The concerns were (a) the standalone outpatient scribe is the most crowded and commoditised space (Eka, HealthPlix, Doctolib bundling it for free), (b) ambient conversation plus prescriptions is a bigger safety and regulatory step, and (c) a PoC testing too many hypotheses at once is harder to read.

**Why bring it in now:** in **hospital** OPD (not standalone clinics) it strengthens the core thesis rather than diluting it:
1. **One patient timeline.** OPD visit → admission → nursing chart → discharge → follow-up OPD is the continuity story that competitors doing doctor-only *or* nurse-only can't tell.
2. **Doctor adoption.** Consultants spend most of their day in OPD. Winning them there makes them champions for the discharge and ward modules.
3. **The hospital buys once.** Same contract, same integration, same consent framework.

**Guardrails so it doesn't dilute the PoC:** hospital OPD of the **same 2 pilot departments** only; no standalone-clinic sales motion until after the pilot; prescriptions are **drafts** that the doctor confirms line by line; no drug suggestions or auto-dosing.

**Medication loop as part of the end-to-end product, not an add-on.** Agreed. What the patient experiences is "did I get the right medicine and do I know how to take it", not "was the note written". So the product is designed around a closed loop:

```
Doctor speaks (OPD / round / discharge)
  → structured prescription draft (drug, strength, form, dose, route, frequency, duration, instructions)
  → doctor confirms each line
  → hospital pharmacy queue (India)  |  national e-prescription via the certified EHR/PVS (Europe)
  → dispensing recorded (what was actually given, incl. substitutions)
  → patient medicine schedule in their language + reminders + refill prompt
  → adherence and side-effect check-in visible at the next visit
```

**How it differs by market:**

| | India (PoC) | Europe (design now, build in Europe phase) |
|---|---|---|
| Where prescriptions go | Hospital's in-house pharmacy (OPD counter, IPD indent, discharge meds). No national e-prescription mandate for retail pharmacies yet | National e-prescription systems. **Germany:** the E-Rezept is created in the practice or hospital software, sent over the Telematikinfrastruktur (gematik) and redeemed at pharmacies. **EHDS:** ePrescription/eDispensation are priority categories and must be exchangeable across all member states via MyHealth@EU from **March 2029** |
| Our role | Deliver structured prescriptions to the hospital pharmacy (HIS pharmacy module or our own pharmacy queue screen); record dispensing; patient schedule | **Draft** the structured prescription and hand it to the certified EHR/PVS/KIS, which signs and issues it. Becoming a certified e-prescription issuer ourselves is a separate, later decision |
| Standards | FHIR R4 MedicationRequest / MedicationDispense; ABDM PrescriptionRecord to the patient's ABHA (Could) | HL7 Europe Medication Prescription & Dispense IG; national profiles (e.g. gematik FHIR profiles) |
| Retail pharmacy | Later: share via ABHA or a QR on the patient summary so any pharmacy can read it; partnerships with pharmacy chains after the pilot | Handled by the national system; the patient redeems with their health card or app |

**Regulatory line to hold:** turning the doctor's own words into a structured prescription for the doctor to confirm is documentation. **Suggesting** drugs or doses, or automated interaction and allergy alerts, is clinical decision support and very likely moves the product into medical-device territory (CDSCO; EU MDR class IIa or higher). For the PoC: show the patient's allergies and current medicines *as information* next to the draft; formal interaction checking only via a licensed drug database and after a regulatory opinion.

---

## Part B — PRD: "WardVoice" PoC (working name)

### B.1 Overview
| Item | Detail |
|---|---|
| Product | WardVoice PoC (name under review now that OPD is in scope): voice-to-chart for nurses, SBAR handover, OPD note + prescription draft, discharge summary draft, medication loop (pharmacy + patient schedule), patient summary, with a consent and approval layer |
| Owner | Founder / PM (TBD) |
| Clinical lead | Nurse leader + doctor advisor (TBD) |
| Pilot | 2–3 design-partner hospitals × 2 wards each (1 medical, 1 surgical) + the **OPD of the same 2 departments** + the **hospital pharmacy**; ~60–120 nurses, ~15 residents, ~8–12 consultants, pharmacy staff |
| Duration | Build 18–20 weeks; pilot 12 weeks (2 baseline + 10 live) |
| Platforms | Android app (nurses and doctors), web console (in-charge, admin, doctor OPD desktop, pharmacy queue), patient web link (no app install) |

### B.2 Goals and non-goals
**Goals**
1. Prove H1–H8 with credible, pre-registered measurement (time-motion + system logs).
2. Show zero-harm operation with human approval on every entry.
3. Produce a case study and a referenceable ROI for paid conversion.

**Non-goals (PoC)**
- Replacing the HIS or pharmacy system; inpatient order entry; diagnostic, drug or dose suggestions; automated interaction alerts; issuing legally signed e-prescriptions outside a certified system; billing codes; multi-hospital analytics; iOS; hardware; EU compliance (design for it, don't certify).

### B.3 Success metrics
| Metric | Baseline method | Target |
|---|---|---|
| Documentation minutes per nurse per shift | 2-week time-motion (observer + self-log) | −30 min (8h) / −45 min (12h) |
| Draft acceptance (no or minor edit) | System log | ≥85% |
| Critical errors reaching the chart | Daily audit of 10% sample + all flagged | 0 |
| Field-level accuracy (vitals, meds) | Audit vs. observed / paper | ≥95% |
| Handover duration per nurse | Time-motion | −25% |
| Handover omissions | Audit checklist on 20 handovers/ward/week | −50% |
| Discharge summary drafting time | Resident self-log + system time | ≤10 min |
| Discharge TAT (order → exit) | HIS / register | −20% |
| Patient teach-back correct (3 questions) | Structured exit interview | ≥80% |
| Weekly active nurses / eligible | System | ≥70% by week 6 |
| Nurse satisfaction (NASA-TLX workload, NPS) | Pre/post survey | Workload −20%; NPS ≥ +30 |
| Consent opt-out rate | System | Tracked (expect <10%) |
| OPD note + prescription done before patient leaves | System timestamps vs. visit end | ≥80% of visits |
| OPD consultation length | Time-motion / queue system | No increase (target −10%) |
| OPD draft acceptance (minor/no edit) | System log | ≥90% |
| Prescription completeness (strength, frequency, duration, instructions) | Pharmacy audit | ≥98% |
| Pharmacy queries per 100 prescriptions | Pharmacy log | −50% |
| Discharge meds ready before summary sign-off | Pharmacy + system timestamps | ≥70% |
| Patient medicine schedule use at day 14 (opt-in) | System | ≥60% |

### B.4 Scope summary (MoSCoW)
| Capability | Priority |
|---|---|
| Consent capture (admission + per-encounter pause) | **Must** |
| Patient identification (wristband scan / ward list) | **Must** |
| Push-to-talk voice capture, offline-tolerant | **Must** |
| Extraction to structured nursing entries (vitals, meds, I/O, pain, notes, wound photo) | **Must** |
| Review and approve screen | **Must** |
| Digital nursing chart + printable NABH-style chart (paper-mode) | **Must** |
| Auto-SBAR handover | **Must** |
| Discharge summary draft (from stay data + doctor dictation) | **Must** |
| Patient summary in local language (web link via SMS/WhatsApp) | **Must** |
| Audit log + admin console | **Must** |
| In-charge ward dashboard (overdue / incomplete) | **Should** |
| HIS write-back (1 partner HIS) | **Should** |
| Ambient (always-listening) bedside mode | **Could** (behind a flag, 1 ward) |
| Progress note from ward-round dictation | **Could** |
| ABHA link / push discharge summary to ABHA | **Could** |
| OPD ambient capture → consultation note (2 pilot departments) | **Must** |
| Structured prescription draft with line-by-line doctor confirmation (OPD + discharge) | **Must** |
| Hospital pharmacy queue: receive Rx, mark dispensed/substituted, discharge-meds readiness | **Must** |
| Patient medicine schedule in local language + reminders (SMS/WhatsApp) | **Must** |
| Refill prompt and day-7/14 adherence check-in | **Should** |
| Push prescription to HIS pharmacy module (instead of our queue) | **Should** |
| Prescription to ABHA / QR for any pharmacy | **Could** |
| Allergy and current-meds display next to the prescription draft (information only) | **Must** |
| Automated interaction/allergy alerts (licensed drug DB) | **Won't (PoC)**; needs regulatory opinion |
| Inpatient orders/CPOE, CDS, coding, standalone-clinic OPD, retail pharmacy network, EU e-prescription, iOS, hardware | **Won't (PoC)** |

---

### B.5 User journeys

**J1 — Nurse charts after care (core loop)**
1. Nurse finishes vitals and meds for bed 12.
2. Taps the bed on the ward list (or scans the wristband) and holds the talk button: *"Bed 12, Ramesh, BP 130 by 85, pulse 92, temp 99.1, SpO2 96 on room air. Gave Inj. Ceftriaxone 1 gram IV at 10:15, pain score 4, dressing dry, patient ambulated to washroom with support."* Code-mixed speech is fine.
3. Within ≤10 s the app shows structured cards: Vitals (5 fields), Med administration (drug, dose, route, time), Pain (4), Wound (dry), Mobility note. Each field has a confidence indicator; low-confidence and safety-critical fields are highlighted.
4. Nurse taps **Approve all** or edits a field, then approves. The entry is timestamped with her ID.
5. The chart updates, the in-charge dashboard marks the vitals as done, and the handover draft updates.

**J2 — Shift handover**
1. 30 minutes before shift end the app prompts: "Review handover for your 8 patients."
2. Per patient, an SBAR draft is built from the shift's approved entries plus flagged pendings (lab awaited, IV due 14:00, fall-risk high, NPO for surgery).
3. The outgoing nurse adds a voice note, then approves.
4. The incoming nurse sees the handover list, taps "Acknowledged" per patient (bedside or station), and can ask a question that goes back to the outgoing nurse.

**J3 — Discharge summary**
1. The consultant decides to discharge. The resident opens the patient and taps **Draft discharge summary**.
2. The system assembles the stay: admission diagnosis (from admission note / resident input), course in hospital (from nursing + doctor entries), procedures, key investigations (manual or HIS import), discharge meds, and follow-up.
3. The resident dictates missing parts (*"final diagnosis… discharge on tab…"*), edits, and sends to the consultant.
4. The consultant approves on phone or desktop. It is printed on hospital letterhead and optionally sent to the HIS.
5. The patient version is generated (J4).

**J4 — Patient and attendant**
1. At admission the patient/attendant gets a consent explanation (spoken + written, in their language) and gives consent via tap/OTP or a recorded verbal statement.
2. At discharge they receive an SMS/WhatsApp link (no app): a plain-language summary in the chosen language with meds table (name, dose, when, with/without food), red-flag symptoms, follow-up date, and a "read aloud" button.
3. Options: download PDF; "Save to ABHA" (Could); view "what was recorded about me"; withdraw consent for future recording.

**J5 — OPD consultation (ambient)**
1. At registration the patient (or attendant) is asked for AI-documentation consent for the visit; returning patients' standing consent is shown and reconfirmed verbally.
2. The doctor taps **Start visit** on phone or desktop (a visible recording indicator is shown to the patient) and consults normally in any supported language.
3. On **End visit**, within ≤20 s the doctor sees: consultation note (complaints, history, exam, assessment in the doctor's words, plan), prescription lines, investigations requested, follow-up date. Prior OPD and IPD history of this patient is shown alongside.
4. The doctor confirms each prescription line (drug, strength, dose, frequency, duration, instructions) and approves the note. It prints and/or goes to the HIS.
5. The prescription appears in the pharmacy queue before the patient reaches the counter; the patient receives the medicine schedule link.

**J6 — Medication loop**
1. A prescription (from OPD, a ward round, or discharge) is approved by the doctor.
2. The pharmacy screen shows it structured and legible; the pharmacist marks each line dispensed, substituted (with the brand given) or out of stock, or raises a query back to the doctor.
3. For discharges, the pharmacy sees the planned discharge meds as soon as the discharge is decided, so medicines are packed before the summary is signed.
4. The patient gets a schedule in their language: pictograms for morning/noon/night and before/after food, the actual brands dispensed, reminders, and a refill prompt before stock runs out.
5. Day 7/14 check-in ("taking it? any side effects?") appears in the doctor's view at the next visit. Serious answers trigger the hospital's call-back process, not an AI response.

---

### B.6 Functional requirements

#### Consent (CON)
| ID | Requirement | Acceptance criteria |
|---|---|---|
| CON-01 | Capture admission consent for AI-assisted documentation from the patient, or from a legal guardian/attendant when the patient lacks capacity or is a minor | Consent record stores: who consented, relationship, method (tap/OTP/verbal audio), language, version of notice, timestamp, capturing staff ID |
| CON-02 | Consent notice available in English + ≥5 Indian languages, text and audio | Notice versions managed in the admin console |
| CON-03 | Per-patient status visible on every screen (green = consented, amber = pending, red = declined/paused) | Voice capture **disabled** for red; amber allows manual text entry only |
| CON-04 | "Pause recording" per encounter and withdrawal of consent at any time by patient, attendant or nurse | Withdrawal effective ≤1 min; logged; past approved entries retained per medical records law, audio purged |
| CON-05 | Push-to-talk mode records **only the clinician's own voice after care** by default; ambient mode requires additional consent flag | Ambient mode unavailable unless both hospital config and patient flag are on |
| CON-06 | Consent records exportable for DPDP / audit requests | CSV/PDF export by patient or date |

#### Patient identification (PID)
| ID | Requirement | Acceptance criteria |
|---|---|---|
| PID-01 | Select patient from ward list (HIS import or manual admission entry) or by scanning a wristband barcode/QR | Patient name, age/sex, bed, UHID shown before capture begins |
| PID-02 | If speech mentions a different name or bed than the selected patient, block and ask to confirm | Mismatch triggers a hard stop; logged as a near-miss |
| PID-03 | Two identifiers (name + UHID/age) always displayed on the review screen | UI test |

#### Voice capture (CAP)
| ID | Requirement | Acceptance criteria |
|---|---|---|
| CAP-01 | Push-to-talk capture up to 3 minutes per utterance; multiple utterances per patient | Works with gloves (large button, volume-key option) |
| CAP-02 | Works offline: audio stored encrypted on device, processed when connectivity returns; on-device speech recognition where feasible | Queue visible; no data loss after 8h offline test |
| CAP-03 | Supports English, Hindi, code-mixed, and 1 regional language per pilot hospital (e.g. Malayalam, Tamil, Kannada) | Medical WER ≤10% on in-domain test set |
| CAP-04 | Noise robustness (ward alarms, conversations) | Tested with recorded ward noise at 60–70 dB |
| CAP-05 | Optional Bluetooth lapel mic | Supported headsets list |

#### Extraction and structuring (EXT)
| ID | Requirement | Acceptance criteria |
|---|---|---|
| EXT-01 | Extract to structured entry types: Vitals (BP, HR, RR, Temp, SpO2 + O2 device, GRBS/glucose, weight), Medication administration (drug, dose, unit, route, time, site, reason if held), Intake/Output (type, volume, time), Pain score, Fall risk (Morse), Pressure injury risk (Braden), Wound/dressing, Drains/lines, Mobility/position change, Nursing note (free text) | Covered by test suite of ≥500 annotated utterances |
| EXT-02 | **Grounding:** every structured value must link to the transcript span it came from; values without a source span are not produced | Review UI shows the source text on tap |
| EXT-03 | **Safety validation:** vitals out of physiological range flagged; drug names matched to the hospital formulary; dose/unit sanity checks; time defaults to "now" only if not stated, and is shown | Out-of-formulary drug = hard stop needing manual pick |
| EXT-04 | Handle corrections within speech ("BP 140… sorry 130 by 85") | Test cases pass |
| EXT-05 | Numbers spoken in Indian languages / mixed ("ek sau tees by pachasi") parsed correctly | Test cases pass |
| EXT-06 | Never infer a diagnosis or recommend treatment | Prompt and output filters; red-team test set |
| EXT-07 | Latency: draft shown ≤10 s p90 online | Measured |

#### Review and approve (REV)
| ID | Requirement | Acceptance criteria |
|---|---|---|
| REV-01 | Card-based review, one card per entry type, with a confidence indicator; safety-critical fields (drug, dose, route, patient) always need an explicit look (highlighted) | UX test: approval of a typical entry ≤3 taps |
| REV-02 | Inline edit by tap or re-dictation of a single field | — |
| REV-03 | Nothing is written to the chart or HIS without approval by an authenticated clinician | Enforced server-side |
| REV-04 | Approved entries are immutable; corrections create an amendment with reason (standard medical-record practice) | Audit log shows versions |
| REV-05 | Unapproved drafts older than the shift end are flagged to the nurse and the in-charge | Dashboard + push notification |

#### Nursing chart and outputs (CHT)
| ID | Requirement | Acceptance criteria |
|---|---|---|
| CHT-01 | Digital nursing chart per patient: vitals graph, MAR timeline, I/O balance (auto-calculated per shift/24 h), notes | — |
| CHT-02 | **Paper-mode:** print hospital-format charts (vitals sheet, MAR, I/O, nurses' notes) with nurse name and times, so the PoC works in paper-based wards and fits NABH files | Formats configurable per hospital; matched to 1 design partner's forms |
| CHT-03 | HIS write-back via 1 partner adapter (HL7v2/FHIR/REST) for vitals + notes (Should) | Reconciliation report: 100% of approved entries delivered or error-queued |

#### Handover (HND)
| ID | Requirement | Acceptance criteria |
|---|---|---|
| HND-01 | Generate SBAR per patient from approved shift entries + open items (pending labs, due meds, scheduled procedures, NPO, alerts) | Every statement links to its source entry |
| HND-02 | Outgoing nurse can add a voice note and edit; must approve | — |
| HND-03 | Incoming nurse acknowledges per patient; unacknowledged patients visible to the in-charge | — |
| HND-04 | Print / display at station for group handover | — |
| HND-05 | Omission checklist per hospital (e.g. allergies, fall risk, lines, pending tests) highlighted if missing | Configurable |

#### Discharge summary (DIS)
| ID | Requirement | Acceptance criteria |
|---|---|---|
| DIS-01 | Assemble a draft in the hospital's discharge template: identifiers, admission/discharge dates, diagnosis (clinician-entered only), presenting complaints, course in hospital, procedures, key investigations, condition at discharge, discharge meds, advice, follow-up, red flags | Template mapping for 1 design partner |
| DIS-02 | Diagnoses and discharge meds come **only** from clinician dictation or entry, never inferred | Enforced |
| DIS-03 | Resident dictation fills or edits sections; consultant approval step with e-signature | — |
| DIS-04 | Mandatory-field checklist for insurance/TPA (e.g. diagnosis, procedure, dates, treating doctor, investigation summary) before approval | Checklist configurable |
| DIS-05 | Output: PDF on letterhead; HIS upload (Should); FHIR Composition (for future ABDM/EHDS) | — |

#### Patient summary (PAT)
| ID | Requirement | Acceptance criteria |
|---|---|---|
| PAT-01 | Generate a plain-language summary from the **approved** discharge summary only, at ~grade-6 reading level | Readability check; clinician reviews before sending (1 tap) |
| PAT-02 | Languages: English + Hindi + pilot regional language; text-to-speech "read aloud" | — |
| PAT-03 | Medication table with pictograms (morning/noon/night, before/after food) | Teach-back tested |
| PAT-04 | Delivery via SMS/WhatsApp link with OTP to the registered mobile; link expires (configurable) | No login app needed |
| PAT-05 | "What was recorded about me" view + consent withdrawal | — |
| PAT-06 | Save to ABHA / PHR app (Could) | ABDM sandbox |

#### OPD consultation (OPD)
| ID | Requirement | Acceptance criteria |
|---|---|---|
| OPD-01 | Per-visit consent at registration (tap/OTP/verbal), with standing consent for follow-ups that the patient can withdraw | Visit cannot start ambient capture without a green consent status |
| OPD-02 | Ambient capture of a 2–4 speaker consultation up to 30 min, with a visible recording indicator and a pause button | Speaker labels (doctor / patient / attendant) ≥90% correct on test set |
| OPD-03 | Generate a consultation note in the department's template; assessment/diagnosis only in the doctor's own words, never inferred | Enforced; red-team test set |
| OPD-04 | Show the patient's prior OPD notes, IPD stays and discharge summaries from our system alongside the draft | Timeline loads ≤3 s |
| OPD-05 | Specialty templates for the 2 pilot departments (e.g. general medicine, general surgery) | Signed off by department head |
| OPD-06 | Output: printed note + prescription on letterhead; HIS upload (Should); FHIR Encounter + Composition | — |

#### Prescription and medication loop (MED)
| ID | Requirement | Acceptance criteria |
|---|---|---|
| MED-01 | Extract prescription lines from what the doctor says: drug (generic + brand), strength, form, dose, route, frequency, duration, instructions (food timing, taper) | ≥98% line-level accuracy on test set after doctor confirmation |
| MED-02 | Drug must match the hospital formulary / drug master; unmatched names need a manual pick | Hard stop; no free-text drugs |
| MED-03 | Doctor confirms **each line** (not "approve all") before the prescription is issued; missing mandatory fields block issue | Enforced server-side |
| MED-04 | Show allergies and current medicines (from our record) next to the draft as information; no automated alerts in PoC | UI test |
| MED-05 | Pharmacy queue (web): incoming prescriptions by patient/time/location (OPD, ward, discharge); per line dispensed / substituted (brand) / out of stock / query to doctor | Status visible to doctor and nurse ≤1 min |
| MED-06 | Discharge-meds pre-alert: when a discharge is planned, the pharmacy sees draft discharge meds; final list reconciled at sign-off | Differences highlighted to pharmacist |
| MED-07 | Patient medicine schedule from **dispensed** items (not just prescribed): language, pictograms, times, reminders via SMS/WhatsApp, refill prompt | Patient opt-in; stop anytime |
| MED-08 | Day 7/14 check-in: taking as prescribed? side effects? Responses shown at the next visit; red-flag answers route to a hospital-defined call-back list, never auto-advice | Configurable questions |
| MED-09 | Standards: FHIR R4 MedicationRequest, MedicationDispense, MedicationStatement; mapping document to HL7 Europe MPD and gematik E-Rezept profiles for the Europe phase | Mapping reviewed |
| MED-10 | Push prescription to the HIS pharmacy module via the partner adapter (Should); push to ABHA / show QR for any pharmacy (Could) | — |

#### Dashboards and admin (ADM)
| ID | Requirement | Acceptance criteria |
|---|---|---|
| ADM-01 | In-charge ward board: per patient, what's due or overdue (vitals frequency, turns, pain reassessment), unapproved drafts, handover status | Refresh ≤1 min |
| ADM-02 | Superintendent dashboard: time saved (estimated from usage + baseline), adoption, acceptance, errors | Weekly export for the pilot report |
| ADM-03 | Configuration: wards, users/roles, formulary import, templates, languages, consent notice versions, audio retention | — |
| ADM-04 | Roles: nurse, in-charge, resident, consultant, admin, auditor (read-only) | RBAC tests |
| ADM-05 | Full audit log: capture → transcript → draft → edits → approval → outputs, with user, device and time | Immutable, exportable |

---

### B.7 Non-functional requirements
| Area | Requirement |
|---|---|
| Performance | Draft ≤10 s p90; handover generation ≤30 s for 10 patients; discharge draft ≤45 s |
| Availability | 99.5% in pilot hours; full offline capture |
| Devices | Android 10+, 3 GB RAM; hospital-owned shared phones with MDM, per-user PIN/biometric login, 5-minute auto-lock |
| Security | TLS 1.2+, AES-256 at rest, secrets vault, VAPT before go-live, least-privilege access; ISO 27001 roadmap |
| Data residency | All data processed and stored in Indian cloud regions; model providers must offer India-region processing with no training on our data (contractual) |
| Audio retention | Default: delete audio within 24 h of approval; transcripts kept per hospital policy; research use only with separate explicit consent and de-identification |
| Privacy (DPDP) | Notice + consent in local language, purpose limitation, data principal rights (access, correction, withdrawal), breach notification process, grievance officer contact |
| Accessibility | Large touch targets (glove use), high contrast, works one-handed |
| Observability | Per-hospital metrics on acceptance, latency, error types, offline queue depth |
| Quality system | Requirements traceability (these IDs), risk file (ISO 14971 style), versioned models and prompts, change log. Reused later for CDSCO / EU MDR |

---

### B.8 Clinical safety: top hazards
| Hazard | Cause | Controls | Residual check |
|---|---|---|---|
| Entry on wrong patient | Wrong bed selected; name mismatch | Wristband scan; PID-02 mismatch stop; two identifiers on review | Audit of all near-misses |
| Wrong drug, dose or route recorded | ASR error (sound-alike drugs), hallucination | Formulary match; grounding (EXT-02); dose sanity; mandatory look at critical fields | 100% review of med entries in weeks 1–2 |
| Omitted information in handover | Missing source data | Omission checklist (HND-05); outgoing nurse approval | Omission audits |
| Fabricated content in discharge summary | LLM hallucination | Diagnoses/meds clinician-only (DIS-02); source links; consultant approval | Sample audit of 100% of pilot summaries |
| Automation complacency (approve without reading) | Time pressure | Confidence highlighting; periodic "seeded error" checks in training mode; approval time monitoring | Track approvals under 2 s |
| Patient summary misleads | Simplification drops nuance | Generated from approved summary only; clinician 1-tap review; red-flag section mandatory | Teach-back interviews |
| Privacy breach from audio | Device loss, leakage | Encryption, auto-delete, MDM remote wipe | VAPT; incident drill |
| Wrong drug/strength/frequency on a prescription | ASR error, sound-alike brands, misheard numbers | Formulary match; line-by-line confirmation (MED-03); mandatory fields; strength shown next to brand | 100% pharmacist review in pilot + audit of all queries |
| Content attributed to the wrong speaker in OPD (patient's words recorded as doctor's findings) | Diarization error | Speaker labels visible; assessment only from doctor's speech; doctor approval | Weekly OPD note audit |
| Patient follows prescribed, not dispensed, medicine | Substitution at pharmacy | Schedule built from dispensed items (MED-07) | Teach-back sample |
| Check-in answer reports a serious side effect and no one acts | Unmonitored channel | Red flags routed to a staffed call-back list with SLA; patient told to call/visit for emergencies | Review of all red-flag responses |

A **clinical safety officer** (a nurse or doctor from a design partner) signs off the hazard log before go-live.

---

### B.9 Integration strategy for the PoC
- **Primary path: standalone + paper-mode (CHT-02).** Value doesn't depend on HIS access; the pilot can start in weeks.
- **Secondary: 1 HIS adapter** with the most cooperative design partner: read the ward census and patients; write vitals, notes and the discharge PDF.
- **Standards:** internal model mapped to **FHIR R4** (Patient, Encounter, Observation, MedicationAdministration, MedicationRequest, MedicationDispense, MedicationStatement, Procedure, Condition, Composition, Consent, Provenance) so ABDM (NRCeS profiles) and EU (EHDS) paths reuse it.
- **ABDM:** sandbox integration for ABHA linking and pushing the discharge summary and prescriptions (Could).
- **Pharmacy (India):** our pharmacy queue screen by default (works without integration); adapter to the HIS pharmacy module where the partner allows it.
- **Europe (design only in PoC):** we draft structured prescriptions and hand them to the certified EHR/PVS/KIS, which issues the national e-prescription (e.g. Germany's E-Rezept via the Telematikinfrastruktur). The data model already follows the HL7 Europe Medication Prescription & Dispense profiles, so EHDS cross-border exchange (March 2029) needs mapping, not redesign.

### B.10 Data model (core entities)
`Hospital → Ward → Bed → Encounter (admission) → Patient`
`Encounter → ConsentRecord[]`
`Encounter → Capture (audio ref, transcript, language, device, user)`
`Capture → DraftEntry[] (type, fields, source spans, confidence)`
`DraftEntry → ApprovedEntry (immutable, version, approver, Provenance)`
`Encounter → Handover[] (SBAR, author, acknowledger)`
`Encounter → DischargeSummary (draft/approved, template, signatures) → PatientSummary (language, delivery log)`
`Patient → Encounter (OPD visit | admission)`: one timeline across OPD and IPD
`Encounter → Prescription (MedicationRequest[] lines, prescriber, status) → Dispense (MedicationDispense[]: dispensed/substituted/out-of-stock, pharmacist)`
`Dispense → PatientMedSchedule (language, reminders, refill date) → CheckIn[] (adherence, side effects, red-flag routing)`
`AuditEvent (actor, action, object, timestamp, device)`

### B.11 Analytics and instrumentation
Events: `capture_started/finished`, `draft_generated (latency)`, `field_edited (type, before/after)`, `entry_approved (time_to_approve)`, `mismatch_blocked`, `handover_generated/approved/acknowledged`, `discharge_draft_generated/approved`, `patient_summary_sent/opened/read_aloud`, `consent_given/declined/withdrawn`, `offline_queue_depth`, `opd_visit_started/ended`, `opd_draft_generated/approved`, `rx_line_confirmed/edited`, `rx_issued`, `rx_dispensed/substituted/out_of_stock/queried`, `med_schedule_opened`, `reminder_sent/acknowledged`, `checkin_completed/red_flag`.
These feed the pilot report and the error taxonomy used to improve models.

### B.12 Pilot plan
| Week | Activity |
|---|---|
| −4 to 0 | Ethics/IRB approval (if publishing), DPIA, device setup, formulary + template config, consent notice translation, training of "super-user" nurses (2 per shift) |
| 1–2 | **Baseline**: time-motion study (trained observers, ~40 shift-hours per ward), handover omission audits, discharge TAT, patient teach-back baseline |
| 3–4 | Go-live on ward A (medical) with daily huddles and fix-it sprints; 100% audit of med entries |
| 5–6 | Go-live ward B (surgical); discharge summary module on; week-6 adoption checkpoint (H6) |
| 6–7 | OPD go-live in the 2 pilot departments + pharmacy queue + patient medicine schedule; 100% pharmacist review of prescriptions |
| 8–12 | Steady state; audits drop to 10% sample if error rate holds at 0; repeat time-motion (wards and OPD) in week 11 |
| 13 | Pilot report: H1–H8 results, ROI, case study; commercial proposal |

**Support model:** on-site implementation lead for the first 2 weeks per ward; WhatsApp support group with ≤15 min response in pilot hours.

### B.13 Build milestones (before pilot)
| Sprint (2 wk) | Deliverable |
|---|---|
| S1 | Consent flow, patient list, push-to-talk capture, offline queue |
| S2 | Speech recognition pipeline (English/Hindi/code-mixed) + vitals & med extraction with grounding + formulary check |
| S3 | Review/approve UI, digital chart, audit log |
| S4 | Paper-mode print formats, in-charge dashboard, remaining entry types |
| S5 | SBAR handover, discharge draft + consultant approval |
| S6 | Patient summary (languages, TTS, SMS/WhatsApp link), admin console, VAPT, hazard-log sign-off |
| S7 | OPD: per-visit consent, ambient multi-speaker capture, consultation note templates, patient timeline |
| S8 | Prescription extraction + line-by-line confirmation, pharmacy queue, discharge-meds pre-alert |
| S9 | Patient medicine schedule, reminders, refill prompt, check-ins with red-flag routing; hazard-log update for OPD/medication |
| S10 (buffer) | HIS adapter (1 partner, incl. pharmacy if allowed), regional language, hardening |

In parallel: build the **evaluation set** (≥500 annotated nursing utterances, 100 discharge summaries, 150 OPD consultations, 500 prescription lines), recorded with consent in design-partner wards during Phase 0.

### B.14 Dependencies and assumptions
- Design partners provide: formulary / drug master, pharmacy team and workflow access, OPD rooms in 2 departments, chart and discharge templates, 2 wards, super-users, a safety officer, Wi-Fi access, and devices (or we supply ~1 phone per 2 nurses per shift).
- A speech recognition vendor (e.g. Sarvam or equivalent) and LLM provider with India-region processing and no-training terms.
- Regulatory opinion confirming the PoC scope (non-diagnostic documentation aid) is outside CDSCO medical-device licensing, or tells us what we need.

### B.15 Open questions (to answer in discovery)
1. Paper vs HIS nursing charting: what share of target hospitals chart on paper? (This decides how much weight paper-mode vs write-back gets.)
2. Shared hospital phones vs personal phones (BYOD): hospital policy and nurse willingness?
3. Who legally gives consent in practice (patient vs attendant), and is admission-level consent acceptable to hospital legal teams?
4. Which regional language per design partner?
5. Is ambient (listening to the conversation) wanted by nurses, or is "tell it after" enough? voize suggests the latter.
6. Will consultants accept approving AI-drafted discharge summaries on a phone?
7. What price anchor does the CFO use: per bed, per nurse, or per discharge? With OPD in scope, is per-OPD-consultation pricing an extra line?
8. How does the partner hospital pharmacy work today (HIS module, separate pharmacy software, paper)? Who owns substitution decisions?
9. Do OPD patients accept ambient recording in a crowded consultation room? What is the per-visit consent opt-out rate?
10. Europe: which certified EHR/PVS vendor in the first country would take our structured prescription drafts, and on what terms?

### B.16 Out of scope (explicit)
Inpatient orders/CPOE; clinical decision support or early-warning scores; drug/dose suggestions and automated interaction alerts; ICU monitor/device integration; standalone-clinic OPD go-to-market; retail pharmacy network (India); issuing national e-prescriptions (Europe); coding and billing automation; multi-site analytics; iOS app; wearable or edge hardware; EU/UK deployment; research use of data.

---

## Part C — What I need from you to finalise this PRD
1. Agree the **critical six + consent foundation** as PoC scope. v0.2 adds build time (~+6 weeks) and pilot complexity; the alternative is to phase OPD + medication in at pilot week 6, as the plan above already does.
2. Confirm a **working product name**. "WardVoice" no longer fits now that OPD and pharmacy are in scope.
3. Any **design-partner hospitals** you already have access to (city, beds, HIS vendor, paper vs digital charts), so templates, languages and integration can be pinned down.
4. Pick **12-hour or 8-hour shift** hospitals first. This changes the time-saved targets.
