# indian-labour-drafting

> **Open-source Claude-compatible plugin for drafting Indian labour, industrial-disputes, employment-rights, social-security, and workplace-protection pleadings.**
>
> Six-agent drafting pipeline · ten case-type skills · case-config-aware + state-config-aware · ID Act 1947 + Trade Unions Act 1926 + POSH Act 2013 + Payment of Gratuity Act 1972 + EPF Act 1952 + ESI Act 1948 + Minimum Wages Act 1948 + IESO Act 1946 + Factories Act 1948 + four Labour Codes 2019-2020 (variable State notification) + State Shops and Establishments Acts (16 States) + Bharatiya Nagarik Suraksha Sanhita 2023 + Bharatiya Sakshya Adhiniyam 2023 discipline encoded.
>
> Released under MIT. Open infrastructure for the legal community. No commercial engagement offered through this repository — see Disclaimer below.

> ⚠️ **AI can make mistakes. Always verify the output.**
>
> This software generates assistive drafts and suggestions only. Every legal claim, citation, statute reference, procedural step, deadline calculation, and ground of relief must be independently verified by a qualified human practitioner before filing, advising a client, or relying on the output. The publisher accepts no liability for outputs used without verification.

---

## Table of contents

1. [What this plugin does](#what-this-plugin-does)
2. [Case-type skills (full inventory with statutory authority)](#case-type-skills-full-inventory-with-statutory-authority)
3. [The 6-agent drafting pipeline (what each agent does)](#the-6-agent-drafting-pipeline)
4. [Installation](#installation) — Claude Desktop application
5. [Your first pleading — step-by-step walkthrough](#your-first-pleading--step-by-step-walkthrough)
6. [The `case-config.md` file](#the-case-configmd-file)
7. [State coverage and the `state-config/exemplars` layer](#state-coverage-and-the-state-configexemplars-layer)
8. [Built-in compliance disciplines](#built-in-compliance-disciplines)
9. [Privacy firewall — extra discipline for labour content + POSH Section 16](#privacy-firewall--extra-discipline-for-labour-content--posh-section-16)
10. [Why MIT License](#why-mit-license)
11. [Sibling plugins](#sibling-plugins)
12. [Why this exists](#why-this-exists)
13. [Roadmap](#roadmap)
14. [Contributing](#contributing)
15. [Contact](#contact)
16. [Author and brand](#author-and-brand)
17. [Provenance and privilege statement](#provenance-and-privilege-statement)
18. [Disclaimer and Bar Council of India Rule 36 compliance](#disclaimer-and-bar-council-of-india-rule-36-compliance)
19. [License](#license)

---

## What this plugin does

This plugin lets an Indian advocate, sitting inside the Claude Desktop application, point at a case folder on disk and obtain a complete labour / industrial-disputes / employment-rights / social-security / workplace-protection pleading in `.docx` form — Cause Title, Parties, Statutory Opening, Prelude, Facts, Grounds, Prayer, Verification, Affidavit-in-support, Index, List of Documents, and the accompanying applications (Section 33 ID Act interim relief, Section 12 POSH Act interim relief, pre-deposit reduction under Section 7-O EPF Act, condonation of delay, urgent listing, production of records, summoning of witnesses) — formatted in the forum's idiom and the State's Shops and Establishments / Labour Welfare Fund / Industrial Court hierarchy, sourced from a `case-config.md` file the user places in the case folder and a `state-config/exemplars/<state>.md` exemplar.

The pipeline is six agents running in sequence:

1. **Reader** — extracts labour case-facts (parties, appointment, service progression, wages, EPF / ESI / UAN identifiers, trigger incident, conciliation / Internal Committee engagement) from the case folder with a per-document audit log, and applies the **labour-specific privacy firewall** plus the stricter **POSH Section 16 confidentiality discipline** for any POSH content (every workman name, every establishment name, every EPF / ESI / UAN identifier, every salary figure, every charge-sheet / domestic-inquiry / termination reference substituted with structural placeholders; for POSH matters, every complainant / respondent / witness / Internal Committee member identifier additionally substituted; the placeholder → real-value mapping stored locally on the user's machine only).
2. **Format** — loads the case-type skill template, reads the user's `case-config.md` and the relevant State exemplar from `state-config/exemplars/<state>.md`, and pre-substitutes forum name / presiding-officer or Authority / Controlling Authority / Internal Committee designation / case-number prefix / court-fee / applicable State Shops and Establishments Act + Rules / applicable State Labour Welfare Fund Act / applicable State Industrial Court hierarchy (two-tier or three-tier) / Profession Tax applicability / limitation anchor into a `format-shell.md` ready for the Drafter.
3. **Drafter** — writes the actual pleading. Cause Title in the correct forum nomenclature, Parties block, Statutory Opening invoking the operative section, Prelude, Facts as numbered narrative paragraphs with inline exhibit markers, Grounds with statutory anchors and document anchors, Prayer with case-type-specific reliefs, Verification, Affidavit-in-support, Index, List of Documents, and accompanying applications.
4. **Verifier** — anti-hallucination firewall **plus** workman-vs-non-workman classification check under Section 2(s) ID Act **plus** Section 25F / 25G / 25N retrenchment-compliance check **plus** Section 33 ID Act protected-workman check **plus** POSH Section 9 ingredient check **plus** POSH Section 16 confidentiality discipline **plus** Section 4 PG Act gratuity-eligibility check **plus** Section 7A EPF determination trace **plus** Section 75 ESI Court jurisdictional check **plus** Section 20(2) Minimum Wages limitation check **plus** statutory currency check (CrPC → BNSS / IEA → BSA / four Labour Codes State-notification status) **plus** applicable State Shops and Establishments Act applicability check.
5. **Refiner** — applies Verifier flags, polishes language to formal Indian Labour Court / Tribunal / Authority / Internal Committee register, enforces internal numbering and exhibit-cross-reference consistency, strips AI-style markers, applies POSH Section 16 confidentiality header on every page of POSH drafts, strips docx metadata for POSH drafts, and re-substitutes real workman names, real establishment names, real salary figures, and real EPF / ESI / UAN identifiers into the final `.docx` (strictly on the user's local machine — the underlying AI never holds real values).
6. **Overseer** — reads the polished draft with an opposing-counsel lens (Establishment counsel for a workman's pleading; workman's union counsel for an Establishment defence; respondent counsel for a POSH complaint; ESI Corporation counsel for an insured-person's claim; EPF authority counsel for an EPF appellate-tribunal-level appeal). Flags workman-classification challenges, retrenchment-compliance defects, domestic inquiry procedural defects, POSH Section 9 ingredient gaps, Internal Committee composition challenges, gratuity-computation mistakes, EPF / ESI procedural defects, Minimum Wages Section 20 limitation gaps, Standing Orders procedural defects, contradictions between fact paragraphs and grounds, and Section 33 ID Act protected-workman violation challenges.

The output is what an advocate would put before the Labour Court / Industrial Tribunal / Controlling Authority / Internal Committee / EPF Appellate Tribunal / Employees' Insurance Court / Minimum Wages Authority / Inspector / Certifying Officer for filing — **not a template. Not a checklist. A pleading** — ready for the advocate's review, professional verification, signature, court fee, and filing.

---

## Case-type skills (full inventory with statutory authority)

The plugin ships with ten case-type skills, each covering a distinct labour / industrial-disputes / employment-rights / social-security / workplace-protection case-type:

### 1. `id-act-section-10-reference-draft`

**Statutory authority:** Industrial Disputes Act 1947 — Section 10(1) Government reference + Section 12 conciliation-failure framework + Schedule II / Schedule III subject-matter discipline + Section 18(3) binding-on-all-parties effect of resulting Award + *Excel Wear v. Union of India* (1978) 4 SCC 224 framework. **Use case:** appropriate Government (Central / State) referring an industrial dispute for adjudication to the Labour Court / Industrial Tribunal / National Industrial Tribunal post conciliation-failure. **Output:** complete Reference Order with Schedule formulating the question for adjudication, party particulars, ID Act 1947 statutory framework, and pre-reference conciliation discipline.

### 2. `id-act-section-2a-application-draft`

**Statutory authority:** Industrial Disputes Act 1947 — Section 2A(2) (as inserted by the ID (Amendment) Act 2010) + Section 25B 240-days computation + Section 25F / 25G / 25N retrenchment-compliance + Section 11A relief framework + *Sonepat Cooperative Sugar Mills v. Ajit Singh* (2005) 3 SCC 232 + *T.P. Srinivasan v. Aspinwall* (2002) 7 SCC 569 (workman-classification predominant-duty test) + *Workmen of Firestone Tyre & Rubber* (1973) 1 SCC 813 (domestic inquiry defects). **Use case:** workman's direct application before Labour Court / Industrial Tribunal — bypassing the conciliation-officer-and-government-reference route — where 3 months have elapsed from communication of dismissal / discharge / retrenchment / termination. **Output:** complete Application with workman-classification, 240-days continuous service, Section 25F / 25G / 25N non-compliance, domestic inquiry defects, prayer for reinstatement + back-wages + continuity of service + Section 11A consequential reliefs.

### 3. `labour-court-claim-statement-draft`

**Statutory authority:** Industrial Disputes Act 1947 — Section 11A relief framework + Section 17 Notification of Award + Section 33C(1) / Section 33C(2) execution framework + *Allahabad Jal Sansthan v. Daya Shankar Rai* (2005) 5 SCC 124 (back-wages discipline) + *Deepali Gundu Surwase v. Kranti Junior Adhyapak Mahavidyalaya* (2013) 10 SCC 324 (full back-wages framework). **Use case:** workman's Statement of Claim before Labour Court / Industrial Tribunal post-admission of Section 10 reference or Section 2A(2) application. **Output:** complete Statement of Claim with detailed cause-of-action narrative, grounds for reinstatement / back-wages / consequential reliefs, prayer for Award under Section 11A.

### 4. `posh-internal-complaint-draft`

**Statutory authority:** Sexual Harassment of Women at Workplace (Prevention, Prohibition and Redressal) Act 2013 — Section 2(a) aggrieved-woman + Section 2(o) workplace nexus + Section 2(n) acts of sexual harassment + Section 3(2) connected circumstances + Section 4 Internal Committee + Section 9 complaint + Section 11 inquiry + Section 12 interim relief + Section 13 inquiry report + Section 15 compensation + Section 16 confidentiality + *Vishaka v. State of Rajasthan* (1997) 6 SCC 241 + *Apparel Export Promotion Council v. A.K. Chopra* (1999) 1 SCC 759. **Use case:** aggrieved woman's Section 9 complaint to the Internal Committee. **Output:** complete Complaint with aggrieved-woman status, workplace nexus, Section 2(n) acts pleaded with discipline, prayer for inquiry + Section 12 interim relief + Section 13/15 action + Section 16 confidentiality. **POSH discipline is strictest** — Reader applies stricter placeholder substitution, Drafter restrains incident-detail paraphrasing, Refiner strips docx metadata and applies Section 16 confidentiality header on every page.

### 5. `shops-establishments-show-cause-reply-draft`

**Statutory authority:** Applicable State Shops and Establishments Act — 16 States supported (Maharashtra 2017 · Karnataka 1961 · Tamil Nadu 1947 · Delhi 1954 · Uttar Pradesh 1962 · Gujarat 2019 · West Bengal 1963 · Telangana 1988 · Andhra Pradesh 1988 · Kerala 1960 · Rajasthan 1958 · Madhya Pradesh 1958 · Odisha 1956 · Punjab 1958 · Haryana 1958 · Bihar 1953) + applicable State Rules + State Labour Welfare Fund Acts (cognate compliance) + State Profession Tax Acts (cognate compliance). **Use case:** Establishment's reply to a Show-Cause Notice from the Inspector / Chief Inspector for alleged registration / working-hours / weekly-holiday / leave / overtime / women-working / annual-return / employee-register / Trade Licence violations. **Output:** complete Reply with State-specific statutory framework, ground-by-ground denial, mitigating-circumstances pleading, prayer for dropping of proceedings / nominal penalty / personal hearing.

### 6. `gratuity-claim-controlling-authority-draft`

**Statutory authority:** Payment of Gratuity Act 1972 — Section 2(e) employee + Section 3 Controlling Authority + Section 4(1) eligibility (5 years continuous service, waivable on death / disablement) + Section 4(2) computation (15 × last drawn wages × completed years / 26) + Section 4(3) statutory ceiling (₹20 lakh per 2018 amendment) + Section 4(6) deduction-for-misconduct framework + Section 7(2) Employer's determination obligation + Section 7(3) 30-day payment + Section 7(3A) interest + Section 8 Recovery as land revenue + Section 7(7) Appellate Authority + Section 14 override + Rule 10 of the Payment of Gratuity (Central) Rules 1972 (90-day filing limitation, extendable). **Use case:** employee's application for direction to pay gratuity legally due. **Output:** complete Application with employee status, continuous-service computation, Section 4(2) gratuity computation, Section 7(3A) interest claim, Section 8 Recovery prayer, prayer for direction to pay.

### 7. `epf-determination-challenge-draft`

**Statutory authority:** Employees' Provident Funds and Miscellaneous Provisions Act 1952 — Section 7A inquiry + Section 7D EPF Appellate Tribunal + Section 7-I appeal (60-day filing per Rule 7(2) EPF AT Rules 1997) + Section 7-O pre-deposit (75%, reducible by EPFAT, not waivable) + Section 14B damages framework + Sections 16 / 17 exclusion / exemption + *Surya Roshni Ltd. v. EPFO* (2019) 6 SCC 401 (basic-wages discipline) + *Hindustan Times v. Union of India* (1998) 2 SCC 242 + *Organo Chemical Industries v. Union of India* (1979) 4 SCC 573 (Section 14B mens rea framework) + *Provident Fund Inspector v. T.S. Hariharan* (1971) 2 SCC 68. **Use case:** Establishment's appeal before EPFAT against a Section 7A determination by the Regional / Additional / Assistant PF Commissioner. **Output:** complete Memorandum of Appeal with procedural-defects ground / factual-error ground / coverage-challenge ground / Surya-Roshni basic-wages ground / Section 14B procedural-fairness ground / limitation ground; pre-deposit application or reduction-of-pre-deposit application.

### 8. `esic-section-75-application-draft`

**Statutory authority:** Employees' State Insurance Act 1948 — Section 74 EI Court + Section 75 enumeration of disputes (coverage / wages / rate / period / contribution / benefit / recovery) + Section 76 cause-of-action framework + Section 77 limitation (3 years; extendable on sufficient cause) + Section 80 60-day notice before instituting against ESIC + Section 82 appeal to High Court on substantial question of law + *Goetze (India) Ltd. v. ESIC* (1998) framework + Sections 45A — 45-I recovery scheme. **Use case:** insured person / employer / dependent / principal employer challenging ESIC determination / claiming benefit before the EI Court. **Output:** complete Application with case-type-specific grounds (coverage / wages / rate / contribution / benefit / recovery), Section 80 notice exhibit, Section 77 limitation paragraph, prayer for declaration + set-aside + benefit / refund.

### 9. `minimum-wages-claim-draft`

**Statutory authority:** Minimum Wages Act 1948 — Section 3 minimum-rate notification + Section 14 overtime + Section 18 wage-register and pay-slip discipline + Section 20(1) Authority + Section 20(2) 12-month limitation (extendable) + Section 20(3)(i) compensation up to 10x + Section 21 single application by class of employees + Section 22A bar on civil court jurisdiction + *People's Union for Democratic Rights v. Union of India* (1982) 3 SCC 235 (forced-labour constitutional dimension under Article 23). **Use case:** Employee's application before Authority for recovery of difference between minimum wages and wages actually paid + compensation. **Output:** complete Application with scheduled-employment identification, applicable minimum wage notification, wages-actually-paid computation, difference computation, overtime under-payment claim, prayer for difference + Section 20(3)(i) compensation up to 10x.

### 10. `industrial-employment-standing-orders-certification-draft`

**Statutory authority:** Industrial Employment (Standing Orders) Act 1946 — Section 3 (Submission) + Section 4 (Conditions for certification: cover all Schedule items + conform to Model + fair-and-reasonable) + Section 5 (Certification procedure) + Section 6 (Appellate Authority) + Section 10 (Modification) + Schedule (11 mandatory subjects); Industrial Employment (Standing Orders) Central Rules 1946 (Model Standing Orders); applicable State Industrial Employment (Standing Orders) Rules. **Use case:** Establishment submitting Draft Standing Orders for certification by the Certifying Officer (typically the Assistant Labour Commissioner / Regional Labour Commissioner). **Output:** complete Draft Standing Orders covering 11 Schedule subjects (classification of workmen / shift working / attendance / leave / gate-pass / closure / termination / misconduct / disciplinary procedure / means of redress / POSH compliance / IP and confidentiality / anti-bribery / Service Rules consistency) + Application for Certification with Schedule-coverage grounds + Model-Standing-Orders-conformity grounds + Fairness-and-reasonableness grounds.

### Shared infrastructure skills

- **`_drafting_common`** — anti-pollution rules, labour-specific privacy firewall, **POSH Section 16 stricter discipline**, AI-style-marker blacklist, citation discipline, **statutory currency rules** (CrPC → BNSS / IEA → BSA / four Labour Codes State-notification status), **workman-vs-non-workman classification rule** under Section 2(s) ID Act, **Section 25F / 25G / 25N retrenchment-compliance rule**, **Section 33 ID Act protected-workman rule**, **POSH Section 16 confidentiality rule**, **Section 4 PG Act gratuity-eligibility rule**, **Section 7-O EPF pre-deposit rule**, **Section 75 / Section 77 / Section 80 ESI Act framework**, **Section 20(2) Minimum Wages Act framework**, **Limitation Act 1963 Article map for labour disputes**, **State Shops and Establishments applicability rule** (16 States), **Maharashtra-only MRTU & PULP Act 1971 overlay**, **four Labour Codes 2019-2020 variable State-notification framework**.
- **`_labour_drafting_base`** — universal Indian labour pleading skeleton (Cause Title with correct forum nomenclature, Parties block, Statutory Opening, Prelude, Facts, Grounds, Prayer, Verification, Affidavit-in-support, Index, List of Documents, accompanying applications).

---

## The 6-agent drafting pipeline

| Agent | What it reads | What it writes | Key labour-domain specialisation |
|---|---|---|---|
| **`reader`** | Every file in the case folder + the case-type skill's expected exhibits list | `case-facts.md` with per-document audit log + privacy-firewalled placeholder mapping in the header | Privacy firewall — substitutes party names + EPF/ESI/UAN identifiers + salary figures + designations + charge-sheet/DI/termination references before downstream AI processing; **POSH stricter discipline** — additional substitution of complainant / respondent / witness / IC member identifiers per Section 16 POSH Act |
| **`format`** | `case-facts.md` + `case-config.md` + case-type SKILL.md + `_labour_drafting_base` + relevant State exemplar | `format-shell.md` with forum / case-number-prefix / court-fee / statutory-opening / applicable State Shops and Establishments Act / Industrial Court hierarchy / limitation-anchor pre-substituted | Resolves Labour Court vs Industrial Tribunal vs Authority vs Internal Committee vs EPFAT vs EI Court vs Inspector vs Certifying Officer nomenclature; resolves State-specific Shops and Establishments Act + Rules |
| **`drafter`** | `case-facts.md` + `format-shell.md` + case-type SKILL.md + `_labour_drafting_base` + law PDFs + State exemplar | `draft-v1.md` + `draft-v1.docx` | Writes Cause Title + Parties + Statutory Opening + Prelude + Facts + Grounds + Prayer + Verification + Affidavit + Index + List of Documents + accompanying applications; **POSH discipline** — restrains incident-detail paraphrasing, no detail beyond what is strictly necessary to plead Section 2(n) ingredients |
| **`verifier`** | `draft-v1.md` + `case-facts.md` + `case-config.md` + law PDFs + State exemplar | `verification-report.md` | Anti-hallucination + workman-vs-non-workman classification + Section 25F / 25G / 25N retrenchment-compliance + Section 33 ID Act + POSH Section 9 ingredients + POSH Section 16 confidentiality + Section 4 PG Act gratuity + Section 7A EPF determination + Section 75 ESI + Section 20 MW + statutory currency + State Shops and Establishments applicability |
| **`refiner`** | `draft-v1.md` + `verification-report.md` + `case-config.md` + `case-facts.md` | `draft-v2.md` + `draft-v2.docx` | Polish to Indian Labour Court / Tribunal / Authority register + internal numbering / cross-reference / exhibit-marker consistency + **POSH Section 16 confidentiality header on every page + docx metadata stripping** + privacy-firewall reversal (real values re-substituted from local mapping into final `.docx`) |
| **`overseer`** | `draft-v2.docx` + `case-facts.md` + `case-config.md` | `opposing-notes.md` + `final-draft.docx` | Opposing-counsel critique — workman-classification challenges, retrenchment compliance defects, domestic inquiry defects, POSH ingredient gaps, Internal Committee composition challenges, gratuity computation mistakes, EPF / ESI procedural defects, Standing Orders procedural defects, Section 33 ID Act violation challenges |

---

## Installation

This is a Claude-compatible plugin in the Anthropic plugin format, designed to run inside the **Claude Desktop application** (available at <https://claude.ai/download>). The plugin folder location depends on your OS:

| OS | Plugin folder path |
|---|---|
| **macOS** | `~/Library/Application Support/Claude/plugins/` |
| **Windows** | `%APPDATA%\Claude\plugins\` (typically `C:\Users\<you>\AppData\Roaming\Claude\plugins\`) |
| **Linux** | `~/.config/Claude/plugins/` |

Clone the plugin into that folder:

```bash
# macOS / Linux
mkdir -p ~/Library/Application\ Support/Claude/plugins   # adjust per OS table
cd ~/Library/Application\ Support/Claude/plugins
git clone https://github.com/Wolfgangrush/indian-labour-drafting-litigation.git indian-labour-drafting

# Windows (PowerShell)
mkdir -Force $env:APPDATA\Claude\plugins
cd $env:APPDATA\Claude\plugins
git clone https://github.com/Wolfgangrush/indian-labour-drafting-litigation.git indian-labour-drafting
```

Restart the Claude Desktop application. The plugin is auto-discovered on the next session start.

### Anthropic Plugin Marketplace (when available)

When the plugin lands on the Anthropic Plugin Marketplace, you will be able to install it from inside the application's plugin browser without `git`. Until then, the manual clone steps above are canonical.

### Verifying the install

In a Claude session, type:

- *"draft Section 10 reference"* — triggers `id-act-section-10-reference-draft`
- *"draft Section 2A application"* — triggers `id-act-section-2a-application-draft`
- *"draft labour court claim"* — triggers `labour-court-claim-statement-draft`
- *"draft POSH complaint"* — triggers `posh-internal-complaint-draft`
- *"draft shops establishments reply"* — triggers `shops-establishments-show-cause-reply-draft`
- *"draft gratuity claim"* — triggers `gratuity-claim-controlling-authority-draft`
- *"draft EPF appeal"* — triggers `epf-determination-challenge-draft`
- *"draft ESI Court application"* — triggers `esic-section-75-application-draft`
- *"draft minimum wages claim"* — triggers `minimum-wages-claim-draft`
- *"draft Standing Orders"* — triggers `industrial-employment-standing-orders-certification-draft`

---

## Your first pleading — step-by-step walkthrough

Suppose you wish to draft a **Section 2A ID Act Application** before the Labour Court at Nagpur, for a workman dismissed without complying with Section 25F.

### Step 1 — create a case folder

```
~/Desktop/cases/
└── s2a-2026-WORKMAN-MATTER/
    ├── case-config.md         ← declares forum + state + workman status + cause of action
    ├── inputs/
    │   ├── appointment-letter.pdf
    │   ├── salary-slips-12-months.pdf
    │   ├── kra-document.pdf
    │   ├── attendance-records.pdf
    │   ├── epf-contribution-record.pdf
    │   ├── charge-sheet.pdf
    │   ├── domestic-inquiry-findings.pdf
    │   ├── termination-order.pdf
    │   ├── conciliation-failure-report.pdf
    │   └── pre-litigation-correspondence.pdf
    └── laws/
        ├── industrial-disputes-act-1947.pdf
        ├── id-central-rules-1957.pdf
        ├── maharashtra-id-rules.pdf
        └── limitation-act-1963.pdf
```

### Step 2 — write `case-config.md`

```yaml
forum: "Labour Court at Nagpur"
state: "maharashtra"
case_type: "id-act-section-2a-application"
case_number_year: 2026
workman_status: "workman_within_section_2s_id_act"
designation: "[Designation-Placeholder]"
last_drawn_wages_per_month: "[Wages-Placeholder]"
date_of_joining: "[Date-of-Joining-Placeholder]"
date_of_termination: "[Date-of-Termination-Placeholder]"
applicable_state_shops_and_establishments_act: "Maharashtra Shops and Establishments (Regulation of Employment and Conditions of Service) Act 2017"
applicable_state_industrial_court_tier: "three_tier"   # MH: Labour Court → Industrial Court → Industrial Tribunal
applicable_state_industrial_disputes_rules: "Maharashtra Industrial Disputes Rules 1957"
mrtu_pulp_act_applicable: true                          # Maharashtra-only
limitation_section: "Section 2A(3) ID Act 1947"
limitation_anchor_date: "[Date-of-Dispute-Arising-Placeholder]"
limitation_filing_date: "[Date-of-Filing-Placeholder]"
parties:
  - role: "Applicant Workman"
    party_name: "[Workman-Placeholder]"
  - role: "Respondent Establishment"
    party_type: "Pvt Ltd Company"
    party_name: "[Establishment-Placeholder]"
```

### Step 3 — invoke the plugin

Open Claude Desktop, navigate to the case folder, and type:

> *draft Section 2A application*

The pipeline runs:

1. **Reader** reads every PDF in `inputs/`, builds `case-facts.md` with privacy-firewalled placeholder mapping, validates that all required statutes are in `laws/`.
2. **Format** loads the `id-act-section-2a-application-draft` skill, reads `case-config.md`, loads `state-config/exemplars/maharashtra.md`, builds `format-shell.md`.
3. **Drafter** writes `draft-v1.md` and `draft-v1.docx`.
4. **Verifier** reads `draft-v1.md` against `case-facts.md`, writes `verification-report.md`.
5. **Refiner** applies the verification flags, polishes the prose, re-substitutes real values, writes `draft-v2.docx`.
6. **Overseer** reads `draft-v2.docx` with the Establishment's-counsel lens, writes `opposing-notes.md` and `final-draft.docx`.

The advocate now reviews `final-draft.docx` against `opposing-notes.md`, makes professional adjustments, signs the verification, swears the affidavit, and files before the Labour Court at Nagpur.

---

## The `case-config.md` file

This file declares all forum-level / case-type-level / matter-level constants that the plugin substitutes into the format shell. Keep it on the user's local machine — `.gitignore` excludes it from any git repo.

Minimum fields:

- `forum` — exact name of the Labour Court / Industrial Tribunal / Authority / Internal Committee / EPFAT / EI Court / Inspector / Certifying Officer
- `state` — for State exemplar loading
- `case_type` — one of the ten supported case types
- `case_number_year` — current year for case-number placeholder
- `workman_status` / `designation` / `last_drawn_wages_per_month` / `date_of_joining` / `date_of_termination` — workman / employee particulars
- `applicable_state_shops_and_establishments_act` — for Shops & Estab show-cause replies
- `applicable_state_industrial_court_tier` — two-tier (most States) or three-tier (Maharashtra-MRTU)
- `mrtu_pulp_act_applicable` — Maharashtra-only true
- `limitation_section` + `limitation_anchor_date` + `limitation_filing_date`
- `parties` — list of party-role + party-type + party-name-placeholder

Case-type-specific fields layer on top of the minimum schema — see each case-type SKILL.md.

---

## State coverage and the `state-config/exemplars` layer

The `state-config/exemplars/` folder contains one Markdown file per supported State, encoding:

- The full name of the applicable State Shops and Establishments Act + Rules
- The Section numbers of the applicable State Act commonly invoked in Show-Cause Notices
- The penalty provisions for contraventions
- The Inspector / Chief Inspector / Deputy Chief Inspector designations
- The applicable State Labour Welfare Fund Act + Rules
- The applicable State Profession Tax Act + Rules
- The State Industrial Disputes Rules
- The State Industrial Court hierarchy (two-tier or three-tier)
- The applicable State-notification status of the four Labour Codes 2019-2020

Initial coverage in v0.1.0-alpha: Maharashtra · Karnataka · Tamil Nadu · Delhi · Uttar Pradesh · Gujarat · West Bengal · Telangana. Andhra Pradesh · Kerala · Rajasthan · Madhya Pradesh · Odisha · Punjab · Haryana · Bihar will arrive in v0.1.x as community contributions land.

---

## Built-in compliance disciplines

The Verifier enforces several disciplines mandatory in Indian labour practice — see `skills/_drafting_common/SKILL.md` for the full discipline framework. Headline disciplines:

- **Workman-vs-non-workman classification rule** under Section 2(s) ID Act with the predominant-duty test (*Sonepat Cooperative Sugar Mills* / *T.P. Srinivasan*)
- **Section 25F / 25G / 25N retrenchment-compliance** — 240-days continuous service + one-month notice / notice-pay + 15-days × completed-years compensation + Government intimation + last-come-first-go + Section 25N permission for 100+ / 300+ workmen establishments
- **Section 33 ID Act protected-workman** — alteration of service conditions during pendency of conciliation / Reference / Application requires prior permission
- **POSH Section 9 ingredient discipline** — aggrieved-woman status + workplace nexus + Section 2(n) acts + Section 3(2) connected circumstances + 3-month limitation + Internal Committee composition
- **POSH Section 16 confidentiality** — strictest discipline in this plugin; complainant / respondent / witness / IC member identifiers placeholder-substituted at Reader stage; confidentiality header on every page of final draft; docx metadata stripped
- **Section 4 PG Act gratuity-eligibility** — 5 years continuous service (waivable on death / disablement) + Section 4(2) formula + Section 4(3) ceiling (₹20 lakh per 2018 amendment) + Section 4(6) deduction discipline + Section 7(3) 30-day payment + Section 7(3A) interest + Section 8 Recovery
- **Section 7-O EPF pre-deposit** — 75% of amount due as determined; reducible by EPFAT but not waivable
- **Section 75 / 77 / 80 ESI Act framework** — EI Court's exclusive jurisdiction + 3-year limitation + 60-day notice before instituting against ESIC
- **Section 20(2) Minimum Wages framework** — 12-month limitation + Section 20(3)(i) compensation up to 10x + Section 22A bar on civil court jurisdiction
- **Statutory-currency discipline** — CrPC 1973 → BNSS 2023 (Section 200 → 223) for prosecution under labour penal provisions; IEA 1872 → BSA 2023 (Section 65B → 63) for proof
- **Four Labour Codes 2019-2020 State-notification check** — Verifier confirms whether the Code on Wages 2019 / Industrial Relations Code 2020 / Code on Social Security 2020 / OSH Code 2020 has been notified for the applicable State as of the date of pleading; reliance on a Code not yet notified is a hard error

---

## Privacy firewall — extra discipline for labour content + POSH Section 16

Labour pleadings contain highly sensitive material — KYC data of workmen, EPF / ESI / UAN identifiers, salary figures, designations, dismissal-order references, charge-sheet references, domestic-inquiry findings. POSH content carries the additional statutory confidentiality discipline of Section 16 POSH Act 2013. The plugin's privacy discipline is the strictest among the Wolfgang Rush family:

1. **Reader** substitutes every workman name, every establishment name, every EPF / ESI / UAN identifier, every salary figure, every designation, and every charge-sheet / domestic-inquiry / termination-order reference with structural placeholders before downstream processing. For POSH matters, the Reader additionally substitutes every complainant identifier, every respondent identifier, every witness name, and every Internal Committee member identifier — under stricter discipline aligned with Section 16 POSH Act 2013.
2. The placeholder → real-value mapping is stored in the header of `case-facts.md` on the user's local machine **only**.
3. **Format / Drafter / Verifier / Overseer** operate **only** on placeholder-substituted content. The underlying AI runtime never holds raw identifiers or raw salary figures.
4. **Refiner** re-substitutes real values into the final `.docx`, strictly on the user's machine. For POSH drafts, the Refiner additionally: (a) applies a Section 16 confidentiality header on every page; (b) strips all metadata from the docx file (author / last-saved-by / company / revision history); (c) advises the user to follow the Internal Committee's Section 16 protocol for serving copies on the Respondent (typically physical-copy-under-acknowledgement, not electronic).
5. `.gitignore` excludes `case-facts.md` and `case-config.md` so they cannot be committed accidentally.

The user can verify the firewall by inspecting `case-facts.md` after the Reader runs — every workman name appears as `[Workman-Placeholder]`, every salary figure as `[Wages-Placeholder]`. For POSH matters, every complainant identifier appears as `[Complainant-Placeholder]`. The mapping is in the header of the same file.

---

## Why MIT License

The MIT licence is the most permissive widely-recognised open-source licence. Anyone may use, modify, distribute, sublicense, or sell the plugin or any derivative. The licence is short, well-understood, and compatible with every other open-source licence the legal community is likely to encounter. No proprietary gating, no field-of-use restriction, no contributor licence agreement (CLA) gymnastics. The accompanying `NOTICE.md` does not modify the licence — it documents the provenance and the privilege position (including POSH Section 16 confidentiality discipline) so that any future audit can verify the plugin's clean origin.

---

## Sibling plugins

This plugin is one in the **Wolfgang Rush** family of Indian legal-drafting plugins. All thirteen siblings ship under the same six-agent pipeline (Reader → Format → Drafter → Verifier → Refiner → Overseer) and the family-of-plugins doctrine — each plugin narrowly scoped to one practice area / forum:

| Plugin | GitHub repo | Scope |
|---|---|---|
| `supreme-court-drafting` | [supreme-court-drafting-litigation](https://github.com/Wolfgangrush/supreme-court-drafting-litigation) | SLPs · Writ Art 32 · Transfer · Review · Curative — Supreme Court of India |
| `indian-hc-drafting` | [indian-hc-drafting-litigation](https://github.com/Wolfgangrush/indian-hc-drafting-litigation) | Pleadings across all 25 Indian High Courts (bench-config-aware) |
| `district-court-drafting` | [district-court-drafting-litigation](https://github.com/Wolfgangrush/district-court-drafting-litigation) | Plaints · WS · CPC applications · BNSS complaints across 25+ States (state-config) |
| `indian-family-drafting` | [indian-family-drafting-litigation](https://github.com/Wolfgangrush/indian-family-drafting-litigation) | HMA · SMA · IDA · matrimonial · custody · DV Act · maintenance · adoption |
| `indian-contracts-drafting` | [indian-contracts-drafting-litigation](https://github.com/Wolfgangrush/indian-contracts-drafting-litigation) | MSA · NDA · employment · lease · sale · GPA · SHA · will · loan · arbitration |
| `indian-banking-drafting` | [indian-banking-drafting-litigation](https://github.com/Wolfgangrush/indian-banking-drafting-litigation) | DRT · SARFAESI · NI Act 138 · IBC §7 / §95 · DRAT |
| `indian-labour-drafting` (this) | [indian-labour-drafting-litigation](https://github.com/Wolfgangrush/indian-labour-drafting-litigation) | ID Act · POSH · PG · EPF · ESI · MW · IESO + State exemplars |
| `indian-property-drafting` | [indian-property-drafting-litigation](https://github.com/Wolfgangrush/indian-property-drafting-litigation) | Gift · Exchange · Release · Trust · Wakf · Easement · Partition · Settlement · Mortgage · TIR |
| `indian-company-drafting` | [indian-company-drafting](https://github.com/Wolfgangrush/indian-company-drafting) | NCLT (241/242 · 245 · 230-232 · 66 · 252 · 213) · NCLAT (421 + 61) · IBC §9 / §10 |
| `indian-tax-drafting` | [indian-tax-drafting](https://github.com/Wolfgangrush/indian-tax-drafting) | Form 35 CIT(A) · Form 36 ITAT · Form 10A · Sec 148A · 263/264 · 271/270A · 144C · 201 · 260A |
| `indian-consumer-drafting` | [indian-consumer-drafting](https://github.com/Wolfgangrush/indian-consumer-drafting) | District / State / NCDRC + medical-negligence + product liability |
| `indian-mact-drafting` | [indian-mact-drafting](https://github.com/Wolfgangrush/indian-mact-drafting) | MV Act 1988 (2019 amended) · Sarla Verma + Pranay Sethi · state-config |
| `indian-ip-drafting` | [indian-ip-drafting](https://github.com/Wolfgangrush/indian-ip-drafting) | Copyright · Trade Marks · Patents · Designs + HC IP Divisions (post-IPAB-abolition) + Anton Piller / John Doe |

Each plugin can be installed independently, each plugin's Rule 36 firewall is narrow and reviewable, each plugin's bench / forum discipline is depth-validated within its scope, and the user installs only what they need.

---

## Why this exists

Indian labour practice has fragmentary open-source infrastructure. Practising advocates piece together pleadings from their own past drafts, from senior advocates' templates, from the various textbook precedent collections (Saharay's *Industrial and Labour Laws of India*, Misra's *Labour and Industrial Laws*, Malhotra's *The Law of Industrial Disputes*, Indrajit Dube's *Industrial Law in India*, the POSH Handbook of the Ministry of Women and Child Development), and from the manuals of the EPFO / ESIC / State Labour Commissionerates. The result is uneven quality, uneven compliance with the latest statutory-currency rules (BNSS 2023 / BSA 2023 / four Labour Codes State-notification status), uneven workman-classification discipline, uneven Section 25F / 25G / 25N retrenchment-compliance, uneven POSH Section 16 confidentiality discipline, uneven Section 4 PG Act gratuity computation, uneven Section 7-O EPF pre-deposit discipline, and routine omissions that opposing counsel (typically the Establishment's well-resourced legal team) exploit.

A plugin that codifies the procedural skeletons + the statutory-currency rules + the workman-classification predominant-duty test + the retrenchment-compliance check-list + the POSH Section 16 confidentiality discipline + the Verifier-side discipline + the privacy firewall is foundational infrastructure for the labour-side advocate practising for a single workman or for a class of workmen who cannot afford a senior advocate's chamber rate.

Foreign legal-AI tools cannot fill this gap. The procedural conventions are jurisdiction-specific; the statutory framework is ID Act 1947 / IESO Act 1946 / PG Act 1972 / EPF Act 1952 / ESI Act 1948 / POSH Act 2013 / MW Act 1948 / four Labour Codes 2019-2020 which no foreign training data has indexed at depth; the formatting requirements at the Registry counter of a Labour Court / Industrial Tribunal / Controlling Authority / Internal Committee / EPFAT / EI Court are matters of bench practice that no foreign tool has encountered; and the State-specific Shops and Establishments / Labour Welfare Fund / Profession Tax overlay is variable across 28 States and 8 Union Territories.

This plugin opens that door. It is most-deeply-validated for the practice idiom of the author at the Bombay High Court Nagpur Bench (and at Maharashtra labour fora), and shall be deepened with respect to other States as community contributors raise GitHub issues and Pull Requests with their State's specific overlay.

---

## Roadmap

- [x] **v0.1.0-alpha (current)** — universal labour pleading skeleton + 10 case-type skills + 6-agent pipeline + privacy firewall + POSH Section 16 stricter discipline + Verifier disciplines + 8 State exemplars (Maharashtra · Karnataka · Tamil Nadu · Delhi · UP · Gujarat · West Bengal · Telangana)
- [ ] **v0.1.x** — bug fixes, quality-gate iteration, language-register polish, formatting refinements driven by user feedback; remaining 8 State exemplars (Andhra Pradesh · Kerala · Rajasthan · MP · Odisha · Punjab · Haryana · Bihar)
- [ ] **v0.x onward** — four Labour Codes 2019-2020 overlay as Codes are notified by individual States; additional case-type skills (apprenticeship dispute under Apprentices Act 1961, maternity-benefit dispute under MBA 1961, employee-compensation claim under EC Act 1923, equal-remuneration claim under ERA 1976, Contract Labour (R&A) Act 1970 principal-employer dispute); deeper Maharashtra MRTU & PULP Act 1971 calibration (unfair-labour-practice complaints before Industrial Court); bench-specific Practice Directions for major Labour Court / Industrial Tribunal benches; deeper POSH discipline including District Officer / Local Committee escalation under Sections 5-8 POSH Act
- [ ] **v1.0.0** — stable release after community-validated formatting and field-testing

Per-State / per-bench deep validation will arrive in the order advocates contribute. The plugin's state-config architecture means any advocate practising in a specific State can deepen the calibration for that State by opening an issue or pull request with their State's Shops and Establishments overlay + Industrial Court hierarchy + applicable State Labour Welfare Fund / Profession Tax overlay — no central roadmap is needed to enable that. The roadmap above is therefore intentionally open-ended.

---

## Contributing

Advocates with regular labour / industrial-disputes / employment-rights / social-security / POSH-Internal-Committee practice are invited to contribute state-config calibration for the specific State they practise in. Open a GitHub issue with:

- Your practice State (e.g., *"Karnataka"* / *"Kerala"* / *"Punjab"*)
- Your State's Shops and Establishments Act name + key Section references
- Your State's Industrial Court / Labour Court hierarchy (two-tier or three-tier; bench locations)
- Your State's Labour Welfare Fund Act + linkages
- Your State's Profession Tax Act + linkages
- Your State's notification status of the four Labour Codes 2019-2020
- Your State's bench-specific Practice Directions affecting labour-pleading format

Pull requests are welcome with a one-paragraph explanation of the change and a reference to the State Act / Rule / Practice Direction that justifies it.

This plugin is open source under MIT.

---

## Contact

Author and maintainer: **Rushikesh R. Mahajan**, Advocate, enrolled with the Bar Council of Maharashtra and Goa.

GitHub: <https://github.com/Wolfgangrush>

Issues raised with reproducible context are handled on a best-effort basis; this is an open-source contribution maintained outside the author's professional engagements and does not constitute a vehicle for legal services.

---

## Author and brand

The author is **Rushikesh R. Mahajan**, Advocate, practising before the Bombay High Court, Nagpur Bench. The plugin is published under the open-source brand **Wolfgang Rush**, which is the author's publishing handle for legal-technology infrastructure. Personal accountability under the Advocates Act 1961 attaches to the author regardless of the use of a publishing handle.

---

## Provenance and privilege statement

See `NOTICE.md` for the full provenance + privilege + privacy + POSH Section 16 confidentiality + Rule 36 compliance statement. The short version:

- The plugin contains only universal procedural skeletons, formatting conventions, statutory references, and generic placeholders
- The plugin contains no specific client matter, no client communications, no client documents, no personal data of any data principal, no specific POSH complaint, and no tracking / telemetry / analytics
- The plugin is, in legal character, identical to a published labour-law textbook — procedural knowledge in machine-readable form
- The author retains full enrolment, full responsibility, and full liability under the Advocates Act 1961 and the Bar Council of India Rules

---

## Compliance posture — Supreme Court e-Committee AI framework

This plugin is **assistive drafting infrastructure**, not autonomous decision-making software. Its operational posture is aligned with the Supreme Court of India e-Committee's stated position on AI in legal work.

> *"AI and digital tools must be used as supportive instruments and should not be allowed to override judicial reasoning."*
>
> — **Justice Rajesh Bindal**, Judge, Supreme Court of India
> [*Judicial Process Re-engineering and Digital Transformation*](https://www.sci.gov.in/press-release-dated-april-12-2026/) conference, 11–12 April 2026
> Organised by the Supreme Court e-Committee in collaboration with the Department of Justice, Government of India.
> ([Coverage — Law Trend](https://lawtrend.in/ai-must-not-replace-judicial-reasoning-warns-supreme-court-justice-rajesh-bindal/))

The same posture underpins the Supreme Court's own AI infrastructure for the judiciary:

- **[SUPACE](https://www.drishtiias.com/daily-news-analysis/ai-portal-supace)** — *Supreme Court Portal for Assistance in Court Efficiency.* AI-enabled assistive tool launched on 6 April 2021 by then-CJI S.A. Bobde. Provides legal research, fact extraction, document review, and drafting assistance to judges and legal researchers. **By design, SUPACE is not a decision-making system** — it processes facts and surfaces them to the human user. The Supreme Court has recommended adoption across all Indian High Courts.

- **[SUVAS](https://www.drishtijudiciary.com/current-affairs/supreme-court-vidhik-anuvaad-software-suvas)** — *Supreme Court Vidhik Anuvaad Software.* AI-powered translation tool launched in November 2019 by then-CJI S.A. Bobde. Translates judicial documents, orders, and judgments between English and ten Indian regional languages.

### What this plugin does — and does not — do under that framework

**Does:**

- Generate structural skeletons of pleadings, drawing on public statutes, schedule forms, and court rules.
- Run a six-agent assistive pipeline (Reader → Formatter → Drafter → Verifier → Refiner → Overseer) over the user's case facts.
- Surface citations, procedural anchors, and bench-specific conventions for advocate review.

**Does NOT:**

- Generate final filings autonomously.
- Substitute for advocate professional judgment.
- Replace human verification.
- Operate without an enrolled advocate retaining full professional responsibility.

**Every draft produced through this plugin must be advocate-owned and human-verified before filing.** The enrolled advocate using this plugin retains full professional responsibility under the Advocates Act 1961 and the Bar Council of India Rules, including verification of facts, accuracy of citations, correctness of legal grounds, propriety of the prayer, and signature on every pleading filed.

This is the same standard the Supreme Court itself applies to its own AI infrastructure (SUPACE / SUVAS): **AI as supportive instrument, never as decision-maker.**

---

## Disclaimer and Bar Council of India Rule 36 compliance

This repository is published as a personal open-source contribution to the legal-technology ecosystem. It is **not** an advertisement of professional services, **not** a solicitation of work, **not** an undertaking to act as counsel in any matter, and **not** a vehicle through which the author accepts professional engagement.

Bar Council of India Rule 36 of the Standards of Professional Conduct and Etiquette prohibits an advocate from soliciting work or advertising professional services through any medium. This repository complies with Rule 36 in both letter and spirit:

- No commercial offering is made through this repository
- No representation of professional results is made
- No invitation to engage the author professionally is made
- The README contains no contact details inviting professional retainer

The plugin is published in the same legal character as any practitioner's open-source library, public continuing-legal-education contribution, or published textbook chapter — the medium is software, the content is procedural knowledge, the practitioner retains full Bar discipline and accountability.

---

## License

MIT — see `LICENSE`.
