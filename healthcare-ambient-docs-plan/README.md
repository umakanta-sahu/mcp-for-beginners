# Ambient Clinical Documentation for Frontline Workers — India & Europe Plan

> Status: **planning only, nothing built yet.** Research snapshot as of September 2026.
> Next: [Personas, pain points & PoC PRD](./PRD-personas-poc.md)
> Figures marked *(est.)* are our own bottom-up estimates; everything else is cited under [Sources](#sources).

---

## 1. Executive summary

- **What:** A consent-first, voice-driven assistant that listens to (or is told about) the care a nurse or doctor has just given, turns it into structured record entries, asks the patient's consent and the clinician's approval, then writes it into the hospital's EHR/HIS. The patient gets a plain-language summary they can carry to the next hospital.
- **Why now:** Documentation takes about a quarter of a nurse's shift. India's digital rails are live: 96 crore ABHA IDs, 110 crore linked records, 10.5 lakh professionals on HPR. Europe now has clear rules for AI scribes (NHS/MHRA guidance, MDR class IIa precedents), and investors are putting large sums into the category.
- **Where the gap is:**
  - *India:* every scale player (Eka Care, Augnito, HealthPlix) is **doctor/OPD-first**. Inpatient **nursing** documentation in India is largely unserved.
  - *Europe:* the doctor scribe space is crowded (Tandem, Heidi, Nabla, Tortus, Doctolib). Nursing is served in DACH long-term care by **voize**, but acute-hospital nursing outside the Microsoft/Oracle ecosystems is still open.
- **Recommendation:** Go **India first, nurse-first, private hospitals (IPD)**. Add doctor ward-round notes and discharge summaries on the same patient timeline. Build the EU medical-device quality system (QMS) in parallel. Enter **one** European country in about year 2–3. Start software-only on existing phones; hardware (a clip-on mic or a ward edge box) comes only after product-market fit.

---

## 2. Problem statement

**Core problem (clinician side)**
> Nurses and doctors in Indian and European hospitals spend 25–35% of each shift on documentation. Physicians spend roughly half their EHR-facing day in the EHR versus ~27% face-to-face with patients. They document from memory, after the fact, often on shared terminals. This pulls attention away from patients, forces constant context switching, causes omissions at handover, and drives burnout and attrition. Apollo Hospitals reports 25–30% nurse attrition.

**Core problem (patient side)**
> Patients leave a consultation or discharge without a complete, understandable picture of what happened and what to do next. When they switch doctors or hospitals, their history does not follow them in usable form. They have to retell it, and clinicians decide with partial context.

**Core problem (institution side)**
> Incomplete or late documentation hurts accreditation (NABH), insurance pre-authorisation and claims, medico-legal defensibility, and in Germany even revenue: KHZG penalises hospitals up to 2% of DRG revenue if they have not digitised nursing documentation and other measures.

**Why existing tools don't solve it (India)**
- Current AI scribes produce **free-text SOAP notes for OPD doctors**. Nursing documentation is **structured** (vitals, intake/output, medication administration, wound care, fall-risk scores, SBAR handover) and happens **on the move, at the bedside**.
- Speech recognition error rates reach 15–25% on Indian accents and code-mixed (Hinglish etc.) speech, which is the normal way consultations happen here. Always-online cloud tools fail on ward Wi-Fi.
- Consent is usually an afterthought. Under DPDP (full obligations from May 2027), patient audio is regulated personal data.

**Problem statement (one line)**
> *Frontline clinicians lose a quarter of their shift to documentation they complete from memory, and patients lose their story between providers. We give care time back by turning natural bedside speech into approved, structured, consented records that flow into the hospital system and the patient's own health record.*

---

## 3. Market potential

### 3.1 India

**Supply side (who we sell to)**
| Metric | Value |
|---|---|
| Registered allopathic doctors | 13.88 lakh (+7.5 lakh AYUSH) |
| Nursing personnel | 39.4 lakh (+3.8 lakh graduating/yr) |
| Health facilities on ABDM HFR | 5.47 lakh |
| Professionals on ABDM HPR | 10.5 lakh |
| ABHA IDs / linked records | 96.4 crore / 110 crore (Aug 2026) |
| NABH digital-health-accredited hospitals | 115+ (2nd edition of standards Sept 2025) |
| India digital health market | ~USD 17.8B (2025) → ~USD 107B (2033), 25% CAGR |

**Bottom-up TAM (software, annual recurring) *(est., ₹87 = $1)***
| Segment | Units | Assumed price | Annual TAM |
|---|---|---|---|
| Doctors (practising ≈ 80% of registered ≈ 11 lakh) | 11,00,000 | ₹1,500 / month | ≈ ₹1,980 Cr (~$230M) |
| Nurses | 39,40,000 | ₹400 / month (enterprise seat) | ≈ ₹1,890 Cr (~$215M) |
| **Total clinician TAM** | | | **≈ ₹3,900 Cr (~$450M)** |
| Cross-check: ~19 lakh hospital beds at ₹500/bed/month | | | ≈ ₹1,140 Cr (~$130M) (hospital-only view) |

- **SAM *(est.)*:** private multi-specialty hospitals of 50+ beds in tier-1 and tier-2 cities that already run a HIS, plus urban specialist doctors in digitised clinics. This is roughly 20–25% of TAM, **~₹800–1,000 Cr (~$90–115M)**.
- **SOM, 5-year target *(est.)*:** 400–600 hospitals plus 15–25k paying doctors, **₹60–100 Cr ARR (~$7–12M)**.
- **Upside not counted above:** insurer/TPA documentation-quality services (clean claims, NHCX), a patient premium health vault, government/state programmes (PHCs, district hospitals via tenders), and HIS vendor OEM licensing.

**Honest read:** India's price per seat is 5–10× lower than Europe's. It is a volume-and-efficiency market. The reasons to start here are fast iteration, a real product gap in nursing, ABDM rails for patient portability, and a cost base that lets us reach product-market fit (PMF) cheaply. India alone will not justify European-scale revenue per seat.

### 3.2 Europe (for sequencing)
| Metric | Value |
|---|---|
| Practising physicians (EU, 2024) | 2.03M |
| Practising nurses (EU, 2023) | ~3.7M (UK not included) |
| Germany nursing homes | ~13,000 |
| Global ambient scribe market (2025) | $0.6–1.75B (by source), ~24–38% CAGR |
| voize public price point | €12–15 per nurse per month (DE) |

- **EU TAM *(est.)*:** 3.7M nurses × €180/yr ≈ **€670M**, plus 2.03M physicians × ~€1,000/yr ≈ **€2B**.
- Funding signals: Tandem $100M Series B (Sept 2026), Heidi $340M (Sept 2026), voize $50M Series A (Nov 2025), Nabla $70M Series C (Jun 2025).

---

## 4. Competitive landscape

### 4.1 India
| Player | Focus | Traction / notes | Gap we exploit |
|---|---|---|---|
| **Eka Care – EkaScribe** | OPD doctor scribe + EMR + ABDM | 65k doctors (12k paid); $20–25/mo; building offline, code-mixed model with NVIDIA | Doctor/clinic-centric; not inpatient nursing |
| **Augnito** (Spectra, Omni) | Hospital dictation + ambient; 37+ languages | $7.2M raised, Apollo-backed; India, Middle East, US | Radiology/doctor dictation heritage; nursing workflows not the core |
| **HealthPlix** | Clinic EMR with voice prescription (Sarvam ASR, 11 languages) | 14k+ doctors; NABH-certified EMR | Clinic prescriptions, not hospital wards |
| **Microsoft Dragon Copilot** | Doctors + nurses (US GA Dec 2025) | Global reach, Epic-centric | Expensive; limited Indic/HIS fit in India |
| **Hospital HIS vendors / in-house (Apollo etc.)** | Build or bundle | Apollo investing to cut nurse workload | Potential **partners/channel** rather than rivals |
| **Sarvam AI** | Indic speech/LLM infrastructure | 22 languages | **Supplier** option, not a competitor |

### 4.2 Europe
| Player | HQ | Focus | Traction | Takeaway |
|---|---|---|---|---|
| **voize** | Berlin | **Nurses**, long-term care → hospitals, US | 1,100+ facilities, 75k nurses, up to 30% admin time saved; $50M Series A | The template for nurse-first (see §5) |
| **Tandem Health** | Stockholm | Doctors → "clinic OS" | 5,000 providers, 12 countries, UK largest; MDR IIa for scribe, coding, decision support | Regulation is a moat; expand from scribe to platform |
| **Heidi Health** | Australia | Doctors, all specialties | 2M consults/week, 116 countries; DACH MAU +205% | Product-led growth wins with individual clinicians |
| **Nabla** | Paris | Doctors, moving to agentic + nursing | 130+ orgs, $120M total | Heading toward nursing, so the window is closing |
| **Corti** | Copenhagen | Clinical AI infra / APIs | ~$13M revenue est.; 250k interactions/day | Possible model/infra partner |
| **Tortus** | London | NHS ambient scribe | 9 NHS sites, 17k encounters, ~23% more patient time | NHS evidence-led GTM |
| **Doctolib Assistant** | Paris | GP consult assistant, bundled | 6M+ consultations | Bundling by incumbents commoditises the doctor scribe |
| **Microsoft / Oracle** | US | EHR-native nursing AI | Dragon Copilot nursing; Oracle nursing agent (Sept 2026) | Avoid head-on competition in Epic/Oracle hospitals |

**Positioning map:** most players sit in *doctor × free-text note*. Our square is **nurse + doctor on one patient timeline × structured EHR write-back × consent-first × patient-portable (ABHA/EHDS)**, and in India **Indic code-mixed + offline**.

---

## 5. What to learn from voize

1. **Pick the underserved persona.** Nurses are the largest clinical workforce and their documentation is structured and repetitive, so AI can fill fields, not just write prose. voize built its business on that.
2. **Output structured data, not notes.** voize maps speech to discrete EHR fields (vitals, wound care, medication, scheduling) with two-way sync. Structured output is easier to verify, easier to audit, and more valuable to the hospital.
3. **Distribute through the incumbent software, don't replace it.** Native integrations with MEDIFOX DAN and Connext Vivendi turned the incumbent systems into a channel. voize hires onboarding managers per EHR partner. *India equivalent:* partner with 2–3 mid-market HIS vendors early.
4. **Work offline, on-device.** Speech recognition runs locally on the phone, so it works when Wi-Fi drops and less data leaves the ward. This matters even more in Indian hospitals and under DPDP.
5. **Start where buying is easier.** Long-term care in DACH has tighter budgets but simpler workflows, fewer vendors and faster decisions than university hospitals. voize went there first, then Charité and hospitals, then the US. *India equivalent:* mid-size private hospitals (100–300 beds), not AIIMS or large chains first.
6. **Price for the nurse budget.** At €12–15 per user per month, voize is an easy yes against 30% time saved. Price by seat or bed so ROI is obvious.
7. **Win the home market before going abroad.** voize reached 1,100+ facilities in DACH before its US push. Don't split focus across India and the EU before India PMF.
8. **What voize does *not* do, which is our opening:** doctor and nurse on a shared patient timeline, a patient-facing summary with record portability, Indic languages, and ABDM integration.

Also from others: **Tandem** shows MDR IIa certification becomes a sales moat in Europe. **Tortus** shows NHS-style evidence (time saved per encounter) sells. **Doctolib** shows an incumbent can bundle a doctor scribe for free, so don't build the business on a standalone doctor scribe.

---

## 6. Product strategy

### 6.1 Principles
1. **Clinician in control:** nothing is written to the record without explicit clinician approval.
2. **Consent-first:** patient consent is captured, stored and revocable. The patient sees what was recorded.
3. **Structured by default:** output as FHIR resources and HIS fields, with free text only where it belongs (narratives, discharge summary).
4. **Works on a bad day:** offline capture, noisy wards, code-mixed speech, shared devices.
5. **Integrate, don't replace:** we are a layer on top of the HIS/EHR, not a new EHR.
6. **Assistive, not diagnostic (v1):** no clinical decision support in v1. This keeps the regulatory class low while we learn (see §6.6).

### 6.2 Personas and jobs-to-be-done
| Persona | Job | Win condition |
|---|---|---|
| Ward nurse | Record vitals, meds given, I/O, wound/fall-risk, nursing notes; hand over the shift | Charting done by end of shift with no memory backlog; ≥45 min saved per shift |
| Resident / consultant | Ward-round notes, progress notes, orders drafted, discharge summary | Discharge summary draft in <2 min; round notes without typing |
| OPD doctor (hospital OPD in PoC; standalone clinic app later) | Consultation note + prescription | Note and prescription ready when patient leaves |
| Pharmacist | Legible, structured prescriptions; discharge meds early | Fewer queries; no discharge delays |
| Patient / family | Understand care; keep and share records | Plain-language summary in own language; linked to ABHA |
| Nursing superintendent / CNO | Compliance, handover quality, staffing | NABH audit-ready documentation completeness |
| CIO / CMIO | Safe integration, security | Clean HIS integration, audit logs, data residency |

### 6.3 MVP scope (India, months 3–9)
**Nurse app (Android first, iOS later)**
- Push-to-talk "tell me what you did" capture after care (voize model) **plus** optional ambient mode for bedside conversations.
- Patient identification by wristband QR/barcode or HIS patient list, to avoid wrong-patient entries.
- Structured extraction: vitals, medication administration (drug, dose, route, time), intake/output, pain score, wound description + photo, fall/pressure-ulcer risk, nursing notes.
- **SBAR shift handover**, auto-generated from the shift's entries and read aloud or displayed for the incoming nurse.
- Review screen: highlighted fields with a confidence score; one-tap approve or edit.

**Doctor module**
- Ward-round ambient capture → progress note + suggested orders as a draft (not auto-placed).
- Discharge summary draft assembled from the whole stay (nursing + doctor entries).

**Consent and approval layer**
- Patient consent at admission (digital form in the patient's language; OTP/ABHA-linked; guardian flow) with a per-encounter "pause recording" option. Verbal consent is logged with a timestamp.
- Clinician approval gate before any write-back. An immutable audit trail records who said what, what the AI proposed, what was edited, who approved, and when.
- Audio retention: **deleted by default after approval** (configurable per hospital policy). Only structured data persists.

**Patient summary**
- Discharge and visit summary in plain language, available in English plus 5 Indic languages at launch, sent via SMS/WhatsApp link and pushed to the patient's ABHA locker.

**Medication loop (core, see [PRD §A.5](./PRD-personas-poc.md#a5-why-opd-and-medication-were-deferred-in-v01-and-why-v02-brings-them-in))**
- Spoken prescription → structured draft the doctor confirms line by line → hospital pharmacy queue (India) or certified EHR for the national e-prescription (Europe; EHDS ePrescription exchange from March 2029) → dispensing recorded → patient medicine schedule, reminders, refill prompt and check-ins.

**Integrations**
- 2 HIS partners via API/HL7v2/FHIR adapters; a CSV/print fallback for hospitals without an API.
- ABDM: M1 (ABHA), M2 (hospital as health-information provider, linking records), M3 (consented fetch of prior records).

**Languages**
- English, Hindi, and code-mixed Hinglish at launch. Then Tamil, Telugu, Kannada, Marathi, Bengali.

### 6.4 Non-functional requirements
| Area | Requirement |
|---|---|
| Accuracy | ≥95% field-level accuracy on vitals/meds; <1% critical errors (wrong drug, dose or patient) in pilot audits; medical word error rate ≤10% on code-mixed speech |
| Latency | Structured draft ≤10 s after capture; handover ≤30 s |
| Offline | Capture plus on-device speech recognition offline; queue-and-sync when back online |
| Security | Encryption in transit and at rest; SSO/role-based access; device MDM; shared-device session timeout; ISO 27001 + SOC 2 by month 18 |
| Data residency | India data in Indian cloud regions; EU data in the EU (Germany: BSI C5-attested cloud; France: HDS-certified host) |
| Privacy | DPDP-compliant notices and consent (in local language); GDPR Art. 9 + DPIA for EU; no training on customer data without an explicit opt-in agreement |
| Safety | Hallucination guardrails: every extracted field must trace to a span in the transcript; unsupported fields are blocked; drug names checked against the hospital formulary |
| Quality system | IEC 62304 software lifecycle, ISO 14971 risk management, ISO 13485 QMS started by month 9 (required for EU MDR) |

### 6.5 Architecture (conceptual)
```
[Phone / clip mic] --audio--> [On-device VAD + ASR + speaker diarization]
        |                                  |
   consent check                    transcript (+ audio, temporary)
        v                                  v
[Consent ledger] <----------- [Structuring service: LLM + clinical rules]
                                   -> FHIR Observation, MedicationAdministration,
                                      Procedure, CarePlan, Composition (notes)
                                           v
                              [Clinician review & approve UI]
                                           v
          +-------------------+------------+--------------+
          v                   v                           v
   [HIS/EHR adapter]   [ABDM HIP / EHDS summary]   [Patient summary app]
          |
   [Audit log, metrics, evaluation pipeline]
```
- **Model strategy:** use the best available foundation model for structuring, behind an abstraction layer. Indic speech recognition from a specialist (e.g. Sarvam) or fine-tuned open models. Build our own evaluation sets from consented de-identified data. Keep the ability to switch model vendors per country for sovereignty reasons (Tandem publicly avoids single-vendor dependence).

### 6.6 Regulatory stance
| Jurisdiction | Implication | Plan |
|---|---|---|
| India – DPDP Act & Rules 2025 | Consent-manager framework Nov 2026; full obligations May 2027 | Build DPDP-grade consent from day 1; appoint a DPO; DPIA per hospital |
| India – CDSCO (MDR 2017) | Scribes without decision support are likely not a medical device, but this is **unconfirmed** | Obtain a regulatory opinion; keep v1 non-diagnostic |
| India – ABDM / NABH | M1–M3 certification; NABH HIS/EMR certification needs ≥3 live deployments + ABDM M3 | Target NABH software certification in year 2 as a sales lever |
| EU – MDR | Summarising scribes are being treated as medical devices (Tandem holds class IIa; UK MHRA says AVT with summarisation is SaMD) | Plan for class IIa: notified body, 12–18 months, budget €300–600k *(est.)* |
| EU – AI Act | MDR IIa+ AI = high-risk; application for AI in medical devices moved to Aug 2028 (Digital Omnibus, still in flux) | Build AI Act technical documentation alongside MDR |
| EU – EHDS | In force Mar 2025; patient summaries and cross-border exchange | Patient-portability feature maps well to EHDS |
| UK (if chosen) | NHSE AVT guidance, DTAC, DSPT, DCB0129/0160 clinical safety | Only if UK is picked as the European entry |

### 6.7 Hardware roadmap (after software PMF)
1. **v0 (MVP):** hospital-issued or personal Android phones plus a ₹1,000–2,000 wireless lapel mic. Zero hardware risk.
2. **v1 (year 2):** a **ward edge box**, an on-premise GPU appliance running speech recognition and structuring inside the hospital. This solves connectivity and data-residency objections and is the likely first hardware revenue.
3. **v2 (year 3+):** a **wearable clinician badge** (mic + button + haptic + NFC patient tap), comparable to a Vocera-class device. Consider only if data shows phones are the adoption bottleneck (hygiene, pocket friction). The hardware business adds certification, supply-chain and support cost, so don't lead with it.

---

## 7. Revenue strategy

### 7.1 Pricing *(est., validate in pilots)*
| Segment | Model | Price |
|---|---|---|
| India hospital (IPD) | Per **occupied bed per month**, unlimited nurse and doctor seats on those wards | ₹450–700 / bed / month |
| India hospital implementation | One-time integration + training | ₹3–10 lakh per site (waived for design partners) |
| India clinic doctor | Freemium → Pro | Free 30 notes/mo; Pro ₹1,499/mo or ₹14,999/yr |
| India HIS vendor OEM | White-label / embedded | 20–30% revenue share or per-bed wholesale |
| India edge box (year 2) | Hardware + annual maintenance or lease | ₹4–8 lakh + 18% AMC |
| Europe nurse seat | Per user per month | €15–25 (acute hospital, above voize's LTC price) |
| Europe physician seat | Per user per month | €79–149 |
| Europe enterprise | Site licence, 3-year | Custom |
| Patient app | Free; premium family vault later | ₹499 / year *(later)* |

### 7.2 Why per-bed pricing in India
- Hospitals budget per bed. Nurse headcount fluctuates and many are contract staff.
- It aligns with ROI: a 200-bed hospital with ~220 nurses saving 45 min/shift frees ~165 nurse-hours a day, about 20 FTE. At ₹30k/month per nurse, that is ~₹6 lakh/month of capacity. Price: 200 × ₹550 = ₹1.1 lakh/month, **≈5× ROI**.

### 7.3 Unit economics targets
- Gross margin ≥70% (on-device speech recognition and model routing keep inference cost ≤10% of revenue).
- CAC payback ≤12 months in India hospitals; net revenue retention ≥120% (ward → hospital → group expansion).
- Year-5 revenue mix target *(est.)*: 60% India hospitals, 10% India clinics/OEM, 30% Europe, with Europe the growth driver after year 3.

### 7.4 Rules we will not break
- **Never sell patient or clinician data**, and no pharma-sponsored notes. Trust is the product.

---

## 8. Sales strategy

### 8.1 Ideal customer profile (India, first 24 months)
- Private or trust hospitals with **100–500 beds**, NABH-accredited or preparing, with a HIS in use (even basic), in tier-1 and tier-2 cities.
- Nursing attrition pain (≥20%), an active quality/NABH team, and an owner or CEO who decides within about 90 days.
- Then: mid-size hospital chains (5–30 hospitals), and after that large groups (Apollo, Manipal, Narayana, Max etc.) once we have case studies.

### 8.2 Buying committee
| Role | Cares about | Our proof |
|---|---|---|
| Nursing superintendent / CNO (**champion**) | Nurse time, attrition, handover safety | Time-motion before/after; nurse NPS |
| Medical director | Doctor time, discharge turnaround, quality | Discharge summary time; bed turnover |
| CIO / IT head | Integration, security, residency | HIS adapter, audit logs, on-prem option |
| CFO / owner | ROI, claims | FTE-equivalents freed; claim denial reduction |
| Quality / NABH coordinator | Audit completeness | Documentation completeness scores |

### 8.3 Sales motion
1. **Founder-led design partnerships (3–5 hospitals):** free or discounted, 90 days, co-designed. Success criteria agreed in writing (e.g. ≥30 min saved/nurse/shift, ≥80% weekly active nurses on pilot wards).
2. **Paid pilot → hospital-wide contract:** 1–2 wards for 60 days, then a 12–36 month contract. Land in medicine/surgery wards; expand to ICU and OPD.
3. **Channel partnerships:**
   - **HIS vendors** (mid-market Indian HIS players), the voize playbook.
   - **NABH consultants** and hospital associations (e.g. AHPI) for referrals.
   - **Insurers/TPAs** later, around documentation completeness for faster pre-auth and claims.
4. **Clinic doctors (product-led):** app store, a free tier, specialist communities and conferences, IMA chapter talks, and referral credits. Avoid pharma field-force distribution because of conflict of interest.
5. **Sales assets:** ROI calculator, time-motion study kit, security/DPDP pack, clinical safety case, one case study per specialty.

**Expected cycles:** India private hospitals 2–6 months; chains 6–12 months; European hospitals 9–18 months (public procurement, frameworks).

### 8.4 Team to hire (first 18 months)
- Founding clinical lead (a nurse leader) plus a doctor advisor
- 2 implementation/onboarding managers (one per HIS partner)
- 1 enterprise account executive (after 5 paying hospitals)
- Regulatory/QMS lead (by month 9)

---

## 9. Go-to-market plan

### Phase 0 — Discovery (months 0–3)
- 50+ interviews and **shadowing shifts** (nurses and residents) in 5 hospitals. Measure baseline documentation time.
- Sign 3–5 design-partner letters of intent, including 1 HIS vendor.
- Regulatory opinions (CDSCO classification, DPDP), a consent design review, and a data-collection protocol with ethics committee approval for consented audio.
- **Exit criteria:** validated top-3 nursing documentation tasks; signed design partners; decision on nurse-first vs doctor-first confirmed by data.

### Phase 1 — MVP and pilots (months 3–9)
- Build the MVP in §6.3 (Android nurse app, doctor ward-round and discharge draft, consent/approval, 1 HIS adapter, ABDM M1/M2).
- Pilot on 2–3 wards per design partner. Run weekly accuracy audits and measure time saved.
- **Exit criteria:** ≥30 min/nurse/shift saved; ≥80% weekly active nurses; <1% critical errors; 2 hospitals converting to paid.

### Phase 2 — India commercial launch (months 9–18)
- 20–30 paying hospitals; 2nd HIS integration; ABDM M3; 5 Indic languages.
- Launch the clinic doctor app (freemium) and the patient summary + ABHA link.
- Start ISO 13485 / IEC 62304 / ISO 27001; publish a peer-reviewed or white-paper time-motion study.
- Raise a Seed/Series A on India traction.

### Phase 3 — Europe readiness (months 12–24)
- Choose **one** entry country using these criteria: reimbursement or funding push, crowding, language cost, notified-body access, team fit.
  - **Recommended shortlist:** *Germany (acute hospital nursing):* the largest market, with KHZG pressure on digital nursing documentation; voize is LTC-centric, but Heidi and Microsoft are active. *Netherlands/Belgium:* high digital maturity, English-friendly buyers, smaller and faster. *UK (not EU):* clearest AVT rules and English-only, but crowded (Tortus, Heidi, Tandem, Accurx).
- Engage a notified body for MDR class IIa; set up an EU entity, EU hosting (C5/HDS as needed), GDPR DPO, and a local clinical lead.
- One EU design partner hospital; localise the language model.

### Phase 4 — Europe launch + hardware (months 24–36)
- Europe: 5–10 hospitals in the entry country via 1 local HIS/EHR partner; CE mark.
- India: 150+ hospitals; ward edge box launch; first hospital chain agreements; NABH software certification.
- Then evaluate a second EU country and the wearable badge.

### Top-line milestones *(est.)*
| Month | Hospitals (India) | Paid clinic doctors | EU sites | ARR |
|---|---|---|---|---|
| 9 | 2 | — | — | ₹0.2 Cr |
| 18 | 25 | 1,500 | 0 (design partner) | ₹4–6 Cr |
| 24 | 60 | 4,000 | 1 | ₹12–15 Cr |
| 36 | 150+ | 10,000 | 5–10 | ₹35–50 Cr (~$4–6M) |

### KPIs to track from day one
- Minutes saved per nurse/doctor per shift (time-motion validated)
- AI draft acceptance rate and edit distance; critical error rate
- Weekly active clinicians / eligible clinicians
- Documentation completeness (NABH audit items); handover omission rate
- Discharge summary turnaround; claim query/denial rate
- Patient comprehension score and summary open rate; consent opt-out rate
- NRR, CAC payback, gross margin, inference cost per encounter

---

## 10. Key risks and mitigations
| Risk | Mitigation |
|---|---|
| AI error (wrong patient, drug or dose) harms a patient | Wristband ID; formulary validation; transcript-grounded fields; mandatory approval; clinical safety case; incident process |
| Code-mixed Indic speech accuracy | Consented in-domain data collection; specialist ASR partner; per-hospital vocabulary |
| Fragmented or homegrown Indian HIS with no APIs | HIS vendor partnerships; FHIR adapter; print/CSV fallback; later robotic/overlay entry |
| Low willingness to pay | Per-bed ROI pricing; start with hospitals already paying for HIS; tie to NABH/claims outcomes |
| Incumbents bundle (Microsoft, Oracle, Doctolib, HIS vendors add AI) | Nursing + India depth, structured write-back, consent/patient portability; partner with HIS vendors instead of fighting them |
| Regulatory reclassification (CDSCO / MDR / AI Act) | Start the QMS early; keep v1 non-diagnostic; budget for class IIa |
| Clinician adoption fatigue | Nurse champions per ward; fewer than 3 taps per entry; measure and share time saved weekly |
| Patient trust in recording | Clear visual indicator; pause button; delete audio by default; local-language notice |

---

## 11. Decisions for you (before we build)
1. **Beachhead:** nurse-first IPD in private hospitals (recommended) or doctor-first OPD clinics (faster sign-ups but crowded).
2. **Europe entry country:** Germany, Netherlands/Belgium, or UK (see Phase 3).
3. **Hardware ambition:** is the edge box/badge core to the company thesis, or a later add-on? (Recommended: later.)
4. **Funding path:** bootstrap through design partners vs raise pre-seed now to fund the QMS and data collection in parallel.
5. **Build vs partner for Indic speech recognition** (Sarvam or others vs our own fine-tuned model).

---

## Sources
- voize funding & metrics: [EU-Startups](https://www.eu-startups.com/2025/11/berlins-voize-raises-e43-million-to-use-their-ai-companion-to-give-nurses-time-for-what-matters-most-care/), [HIT Consultant](https://hitconsultant.net/2025/11/17/voize-nabs-50m-to-scale-ai-nursing-companion-to-u-s-and-europe/), [mainsights](https://www.mainsights.io/ma-news/german-software-company-voize-raises-usd-50m-series-a-funding-for-speech-based-nursing-care-ai-assistant)
- voize product, pricing, integrations: [HokAI review](https://hokai.io/hub/tools/voize), [MEDIFOX DAN blog](https://www.medifoxdan.de/wissen-einblicke/blog/voize-x-medifox-dan-der-pflege-noch-mehr-stimme-geben), [voize US](https://www.voize.ai/us), [Glassdoor – onboarding manager roles](https://www.glassdoor.de/job-listing/onboarding-manager-connext-vivendi-medifox-dan-mfd-voize-JV_IC2632180_KO0,50_KE51,56.htm?jl=1009722126880)
- Ambient scribe market: [Becker's market share](https://www.beckershospitalreview.com/healthcare-information-technology/ai/ambient-ai-scribes-by-market-share/), [Astute Analytica](https://www.astuteanalytica.com/industry-report/ai-clinical-documentation-ambient-scribe-market), [Growth Market Reports](https://growthmarketreports.com/report/ambient-ai-scribe-market)
- Eka Care: [YourStory](https://yourstory.com/2025/11/healthtech-startup-eka-care-ai-standardise-medical-records-doctor-patient), [Eka × NVIDIA offline scribe](https://www.biotechreality.com/2026/02/eka-care-offline-medical-scribe-nvidia-india-ai.html), [EkaScribe](https://ekascribe.ai/)
- Augnito: [Tracxn](https://tracxn.com/d/companies/augnito/__JaSGSbuDQDhdJjM4vEZPKWkhUB91KKgsvK3QyOcOgS0), [tooldirectory review](https://tooldirectory.ai/tools/augnito)
- HealthPlix & Sarvam: [Sarvam × HealthPlix](https://www.sarvam.ai/stories/HealthPlix), [HealthPlix](https://www.healthplix.com/), [Sarvam speech-to-text](https://www.sarvam.ai/speech-to-text)
- Tandem: [Tech.eu](https://tech.eu/2026/09/14/swedish-healthtech-tandem-health-scores-100m-series-b-led-by-eus-eur5bn-tech-startup-fund), [TFN](https://techfundingnews.com/tandem-health-raises-100m-series-b-eqt-scaleup-europe-fund/), [Let's Data Science](https://letsdatascience.com/news/tandem-health-expands-europe-rejects-dependence-on-openai-5d5751fe)
- Nabla: [press release](https://www.nabla.com/press-release/nabla-raises-70m-series-c-to-deliver-agentic-ai-to-the-heart-of-clinical-workflows-bringing-total-funding-to-120m)
- Heidi: [Digital Health](https://www.digitalhealth.net/2025/10/heidi-health-raises-48m-in-series-b-funding-to-expand-globally/), [Trending Topics](https://www.trendingtopics.eu/heidi-health-ai-startup-raises-340-million-at-a-900-million-valuation/)
- Corti: [CNBC](https://www.cnbc.com/2025/12/30/corti-will-go-public-but-not-in-2026-says-ai-healthcare-startups-ceo.html), [Latka](https://getlatka.com/companies/corti.ai)
- Tortus: [NHS Innovation Accelerator](https://nhsaccelerator.com/innovations/tortus-ai/), [tortus.ai](https://tortus.ai/)
- Doctolib: [Doctolib Assistant de consultation](https://about.doctolib.fr/news/intelligence-artificielle-doctolib-lance-lassistant-de-consultation/)
- Microsoft Dragon Copilot nursing: [Microsoft](https://news.microsoft.com/source/2025/10/16/microsoft-extends-ai-advancements-in-dragon-copilot-to-nurses-and-partners-to-enhance-patient-care/), [Fierce Healthcare](https://www.fiercehealthcare.com/ai-and-machine-learning/microsoft-debuts-dragon-copilot-ai-clinical-assistant-nurses-expands-access)
- Oracle nursing AI: [Health System CIO](https://healthsystemcio.com/2026/09/16/oracle-health-ai-nursing-documentation/)
- India workforce & market: [IBEF healthcare](https://www.ibef.org/industry/healthcare-india), [IMARC India digital health](https://www.imarcgroup.com/india-digital-health-market), [South First – beds](https://thesouthfirst.com/health/india-has-only-0-79-beds-per-1000-population-in-government-hospitals-short-by-2-4-million-hospital-beds/)
- ABDM: [PIB – 100 crore records](https://www.pib.gov.in/PressReleasePage.aspx?PRID=2264241&reg=3&lang=1), [IBEF – 93.95 crore ABHA](https://www.ibef.org/news/ayushman-bharat-digital-mission-crosses-93-95-crore-abha-ids-strengthens-india-s-digital-healthcare-ecosystem), [Digital Health News – 2026 progress](https://www.digitalhealthnews.com/india-s-state-wise-digital-health-progress-in-2026-from-scale-to-utilization-interoperability-and-connected-care)
- NABH: [Digital Health Standards HIS/EMR](https://nabh.co/programmes/digital-health-standards-his-emr-systems/), [PMC scoping review](https://pmc.ncbi.nlm.nih.gov/articles/PMC13032403/)
- DPDP: [PIB – DPDP Rules 2025](https://static.pib.gov.in/WriteReadData/specificdocs/documents/2025/nov/doc20251117695301.pdf), [Glocert timeline](https://www.glocertinternational.com/resources/guides/dpdp-rules-2025-compliance-timeline/)
- Apollo & India scribe challenges: [Business Standard](https://www.business-standard.com/companies/news/apollo-hospitals-expands-ai-to-reduce-doctor-nurse-workload-in-india-125031300779_1.html), [RDP – on-prem GPU scribes](https://rdp.in/gpu-mart/knowledge-base/ambient-clinical-ai-scribes-on-prem-gpu-indian-hospitals/), [arXiv – multilingual scribe evaluation in India](https://arxiv.org/pdf/2609.17355)
- Documentation burden: [PMC – ambient scribes & burnout](https://pmc.ncbi.nlm.nih.gov/articles/PMC12492056/), [AMA](https://www.ama-assn.org/practice-management/physician-health/doctors-work-fewer-hours-ehr-still-follows-them-home), [ScienceDirect – nursing documentation](https://www.sciencedirect.com/science/article/abs/pii/S0029655425001162)
- EU regulation: [Tandem – MDR/GDPR/AI Act](https://tandemhealth.ai/resources/knowledge/eu-healthcare-ai-regulations-mdr-gdpr-ai-act), [Legalithm – AI Act omnibus tracker](https://www.legalithm.com/en/blog/ai-act-medical-devices-deadlines-omnibus-tracker), [IntuitionLabs](https://intuitionlabs.ai/articles/eu-ai-act-pharma-medical-device-compliance)
- UK AVT: [NHS England guidance](https://www.england.nhs.uk/long-read/guidance-on-the-use-of-ai-enabled-ambient-scribing-products-in-health-and-care-settings/), [MHRA](https://www.gov.uk/government/news/mhra-clarifies-regulatory-status-of-ambient-voice-technologies-used-in-the-nhs)
- Germany KHZG: [BMG](https://www.bundesgesundheitsministerium.de/krankenhauszukunftsgesetz), [Charité](https://medinfo.charite.de/digitale_krankenversorgung_cmio/krankenhauszukunfts_gesetz_khzg/)
- EU workforce: [Eurostat physicians](https://ec.europa.eu/eurostat/statistics-explained/index.php?title=Healthcare_personnel_statistics_-_physicians), [Eurostat nurses](https://ec.europa.eu/eurostat/statistics-explained/index.php?title=Healthcare_personnel_statistics_-_nursing_and_caring_professionals), [Destatis nursing facilities](https://www.destatis.de/EN/Themes/Society-Environment/Health/Long-Term-Care/Tables/nursing-care-facilities.html)
