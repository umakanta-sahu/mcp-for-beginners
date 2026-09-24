# Personas, Pain Points & Proof-of-Concept PRD

> Companion to [README.md](./README.md) (market & GTM plan).
> Status: **Draft v0.1 for review. Nothing built yet.** Pain-point scores are hypotheses to confirm in discovery (Phase 0 shadowing).
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

#### P5 / P6 — Patient and attendant ("Mr. Sharma" and his daughter)
| ID | Pain point | Severity |
|---|---|---|
| PT1 | **Doesn't understand the discharge summary** (English jargon, handwriting): meds, doses, warning signs, follow-up date | Critical (outcomes/readmissions) |
| PT2 | Loses paper records; retells history at every new hospital | High |
| PT3 | Doesn't know what was recorded about them or who sees it; worried about recordings | High (trust) |
| PT4 | Long wait on discharge day for "the file" | High |
| PT5 | Attendant (not the patient) makes decisions but isn't formally in the loop | Medium |

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
| OPD consultation notes | 3 | 5 | 4 | 3 | 3 | 3 | 21 (crowded market) |

### A.4 Critical set for the proof of concept

**Fix these four, with consent as the foundation:**

| # | Critical problem | Personas | Why it's in the PoC |
|---|---|---|---|
| **1** | **Voice-to-chart for nurses** (N1, N4, N6, C1) | P1, P2, P7 | Biggest time sink; structured output is verifiable; the voize-proven pattern; directly measurable in minutes per shift |
| **2** | **Auto-generated SBAR shift handover** (N3, C2) | P1, P2, P7, P8 | Built from data we already capture in #1; high safety value; no integration needed; visible to every nurse twice a day, which drives habit |
| **3** | **Discharge summary draft** (R1, R4, PT4) | P3, P4, P8, P10, P11 | Hardest ROI for the CFO (discharge TAT, bed turnover, claim queries); brings doctors onto the same patient timeline |
| **4** | **Patient-friendly discharge instructions** in the patient's language (PT1, PT3) | P5, P6 | The differentiator and the trust story; low build cost once #3 exists |
| **Foundation** | **Consent + clinician-approval + audit** (PT3, D3, I2) | All | Non-negotiable for DPDP and for trust; also a sales asset |

**Explicitly deferred (not in PoC):** HIS write-back for all hospitals (1 adapter only, see §B.9), orders/CPOE, ICU device feeds, OPD scribe, clinical decision support, coding/billing, full ABHA M3 fetch, iOS, hardware.

**PoC hypotheses**
- **H1:** Nurses using voice-to-chart save **≥30 minutes per 8-hour shift** (≥45 for 12-hour) of documentation time versus baseline.
- **H2:** AI-drafted nursing entries are accepted with no or minor edits **≥85%** of the time, with **zero** unrecovered critical errors (wrong patient, drug, dose or route).
- **H3:** Auto-SBAR handover cuts handover time by **≥25%** and handover omissions (audited) by **≥50%**.
- **H4:** Discharge summary drafting time drops from ~30 to **≤10 minutes**, and discharge-order-to-exit TAT improves by **≥20%**.
- **H5:** **≥80%** of patients/attendants correctly answer 3 teach-back questions (meds, red flags, follow-up) using the multilingual summary, versus baseline.
- **H6:** **≥70%** of eligible nurses on pilot wards are weekly active by week 6. This is the adoption hypothesis and the most likely to fail.
- **Kill / pivot signals:** adoption below 40% at week 6 despite fixes; critical error rate we can't bring to zero with guardrails; time saved under 15 min/shift.

---

## Part B — PRD: "WardVoice" PoC (working name)

### B.1 Overview
| Item | Detail |
|---|---|
| Product | WardVoice PoC: voice-to-chart for nurses, SBAR handover, discharge summary draft, patient summary, with a consent and approval layer |
| Owner | Founder / PM (TBD) |
| Clinical lead | Nurse leader + doctor advisor (TBD) |
| Pilot | 2–3 design-partner hospitals × 2 wards each (1 medical, 1 surgical); ~60–120 nurses, ~15 residents |
| Duration | Build 12–16 weeks; pilot 10 weeks (2 baseline + 8 live) |
| Platforms | Android app (nurses and doctors), web console (in-charge, admin, doctor desktop), patient web link (no app install) |

### B.2 Goals and non-goals
**Goals**
1. Prove H1–H6 with credible, pre-registered measurement (time-motion + system logs).
2. Show zero-harm operation with human approval on every entry.
3. Produce a case study and a referenceable ROI for paid conversion.

**Non-goals (PoC)**
- Replacing the HIS; placing orders; diagnostic or treatment suggestions; billing codes; multi-hospital analytics; iOS; hardware; EU compliance (design for it, don't certify).

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
| Orders, CDS, coding, OPD, iOS, hardware | **Won't (PoC)** |

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

A **clinical safety officer** (a nurse or doctor from a design partner) signs off the hazard log before go-live.

---

### B.9 Integration strategy for the PoC
- **Primary path: standalone + paper-mode (CHT-02).** Value doesn't depend on HIS access; the pilot can start in weeks.
- **Secondary: 1 HIS adapter** with the most cooperative design partner: read the ward census and patients; write vitals, notes and the discharge PDF.
- **Standards:** internal model mapped to **FHIR R4** (Patient, Encounter, Observation, MedicationAdministration, Procedure, Condition, Composition, Consent, Provenance) so ABDM (NRCeS profiles) and EU (EHDS) paths reuse it.
- **ABDM:** sandbox integration for ABHA linking and pushing the discharge summary (Could).

### B.10 Data model (core entities)
`Hospital → Ward → Bed → Encounter (admission) → Patient`
`Encounter → ConsentRecord[]`
`Encounter → Capture (audio ref, transcript, language, device, user)`
`Capture → DraftEntry[] (type, fields, source spans, confidence)`
`DraftEntry → ApprovedEntry (immutable, version, approver, Provenance)`
`Encounter → Handover[] (SBAR, author, acknowledger)`
`Encounter → DischargeSummary (draft/approved, template, signatures) → PatientSummary (language, delivery log)`
`AuditEvent (actor, action, object, timestamp, device)`

### B.11 Analytics and instrumentation
Events: `capture_started/finished`, `draft_generated (latency)`, `field_edited (type, before/after)`, `entry_approved (time_to_approve)`, `mismatch_blocked`, `handover_generated/approved/acknowledged`, `discharge_draft_generated/approved`, `patient_summary_sent/opened/read_aloud`, `consent_given/declined/withdrawn`, `offline_queue_depth`.
These feed the pilot report and the error taxonomy used to improve models.

### B.12 Pilot plan
| Week | Activity |
|---|---|
| −4 to 0 | Ethics/IRB approval (if publishing), DPIA, device setup, formulary + template config, consent notice translation, training of "super-user" nurses (2 per shift) |
| 1–2 | **Baseline**: time-motion study (trained observers, ~40 shift-hours per ward), handover omission audits, discharge TAT, patient teach-back baseline |
| 3–4 | Go-live on ward A (medical) with daily huddles and fix-it sprints; 100% audit of med entries |
| 5–6 | Go-live ward B (surgical); discharge summary module on; week-6 adoption checkpoint (H6) |
| 7–10 | Steady state; audits drop to 10% sample if error rate holds at 0; repeat time-motion in week 9 |
| 11 | Pilot report: H1–H6 results, ROI, case study; commercial proposal |

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
| S7 (buffer) | HIS adapter (1 partner), regional language, hardening |

In parallel: build the **evaluation set** (≥500 annotated nursing utterances, 100 discharge summaries), recorded with consent in design-partner wards during Phase 0.

### B.14 Dependencies and assumptions
- Design partners provide: formulary list, chart and discharge templates, 2 wards, super-users, a safety officer, Wi-Fi access, and devices (or we supply ~1 phone per 2 nurses per shift).
- A speech recognition vendor (e.g. Sarvam or equivalent) and LLM provider with India-region processing and no-training terms.
- Regulatory opinion confirming the PoC scope (non-diagnostic documentation aid) is outside CDSCO medical-device licensing, or tells us what we need.

### B.15 Open questions (to answer in discovery)
1. Paper vs HIS nursing charting: what share of target hospitals chart on paper? (This decides how much weight paper-mode vs write-back gets.)
2. Shared hospital phones vs personal phones (BYOD): hospital policy and nurse willingness?
3. Who legally gives consent in practice (patient vs attendant), and is admission-level consent acceptable to hospital legal teams?
4. Which regional language per design partner?
5. Is ambient (listening to the conversation) wanted by nurses, or is "tell it after" enough? voize suggests the latter.
6. Will consultants accept approving AI-drafted discharge summaries on a phone?
7. What price anchor does the CFO use: per bed, per nurse, or per discharge?

### B.16 Out of scope (explicit)
Orders/CPOE; clinical decision support or early-warning scores; ICU monitor/device integration; OPD scribe; coding and billing automation; multi-site analytics; iOS app; wearable or edge hardware; EU/UK deployment; research use of data.

---

## Part C — What I need from you to finalise this PRD
1. Agree the **critical four + consent foundation** as PoC scope (or swap one).
2. Confirm a **working product name** (placeholder: WardVoice).
3. Any **design-partner hospitals** you already have access to (city, beds, HIS vendor, paper vs digital charts), so templates, languages and integration can be pinned down.
4. Pick **12-hour or 8-hour shift** hospitals first. This changes the time-saved targets.
