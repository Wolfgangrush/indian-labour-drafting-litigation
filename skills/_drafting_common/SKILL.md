---
name: _drafting_common
description: Shared reference for all 10 labour / industrial-disputes / employment-rights / social-security / workplace-protection drafting skills. Holds the anti-pollution rules, the labour privacy firewall protocol (workman names + establishment names + complainant names in POSH matters + employee identifiers + EPF / ESI / UAN identifiers + salary figures substituted with placeholders before downstream AI processing; real-value re-substitution local-only in the Refiner step), the AI-style-marker blacklist, citation discipline, statutory currency rules (CrPC / IEA transition; four Labour Codes State-notification status), the workman-vs-non-workman classification rule under Sections 2(s) and 2(oo) ID Act, the Section 25F / 25G / 25N retrenchment-compliance rule, the Section 33 ID Act protected-workman rule, the POSH Act 2013 Section 16 confidentiality discipline, the Section 4 PG Act gratuity-eligibility rule, the Section 7-O EPF pre-deposit rule, the Section 77 / Section 80 ESI Act time-bar and notice rule, the Section 20(2) Minimum Wages claim limitation rule, the IESO Act 1946 Schedule rule, the State Shops and Establishments applicability rule, and the Limitation Act 1963 Article map for labour disputes. NOT invoked directly — referenced from every case-type skill in this plugin.
allowed-tools: Read
---

# `_drafting_common` — shared labour drafting infrastructure

## Privacy firewall

Labour pleadings routinely contain highly sensitive material — KYC data of workmen, EPF / ESI / UAN identifiers, salary figures, designations, dismissal-order references, charge-sheet references, domestic-inquiry findings, POSH-complainant identifiers, Internal Committee proceedings, witness statements. The plugin's privacy discipline:

1. **Reader** substitutes every party name, every workman / employer identifier, every EPF / ESI / UAN identifier, every salary figure, every designation, every charge-sheet / domestic-inquiry / termination-order reference, and (with stricter discipline) every POSH-complainant / respondent / witness / Internal Committee member identifier with structural placeholders before downstream processing.
2. The placeholder → real-value mapping is stored in the header of `case-facts.md` on the user's local machine **only**.
3. **Format / Drafter / Verifier / Overseer** operate **only** on placeholder-substituted content. The underlying AI runtime never holds raw identifiers or raw salary figures.
4. **Refiner** re-substitutes real values into the final `.docx`, strictly on the user's machine.
5. `.gitignore` excludes `case-facts.md` and `case-config.md` so they cannot be committed accidentally.

For POSH-Act-2013 pleadings, the discipline is stricter — Section 16 POSH Act prohibits disclosure of complainant / respondent / witness / Internal Committee proceedings identity to anyone not entitled to receive it under the statutory channel.

## AI-style-marker blacklist

Stripped by the Refiner before output:

- Em-dash (`—`) used as sentence-internal pause (replaced with semicolon or comma-bounded clause)
- Sentence-final *thereby* / *hereby* / *whereby* without an attached verb
- *Moreover*, *furthermore*, *additionally*, *in addition* as sentence-openers — replaced with *"The Applicant Workman submits that"* / *"The Applicant Workman further submits that"* / *"The Complainant submits that"*
- *Navigate*, *delve*, *foster*, *robust*, *seamless* (metaphorical uses)
- *It is important to note that*, *it should be noted that*, *worthy of note* — replaced with direct prose
- Bullet-list-style structure in operative paragraphs (operative paragraphs are numbered, not bulleted)

## Citation discipline

The Drafter does **not** generate case names + citations from training memory. Every case citation in any explanatory note or recital must trace to a user-supplied source. Untraceable citations become `[CITATION NEEDED]` placeholders.

Headline cases the Verifier scans for fabrication:

- *Workmen of M/s Firestone Tyre & Rubber Co. of India v. Management* (1973) 1 SCC 813 — domestic inquiry defects + Labour Court's power to set aside dismissal
- *Sonepat Cooperative Sugar Mills Ltd. v. Ajit Singh* (2005) 3 SCC 232 — predominant-duty test for workman classification
- *T.P. Srinivasan v. Aspinwall & Co. Ltd.* (2002) 7 SCC 569 — workman / supervisor classification
- *Bombay Union of Journalists v. Hindu* (1961) — workman-classification framework
- *Vishaka v. State of Rajasthan* (1997) 6 SCC 241 — workplace sexual harassment guidelines (codified in POSH Act 2013)
- *Apparel Export Promotion Council v. A.K. Chopra* (1999) 1 SCC 759 — sexual-harassment workplace test extended pre-POSH
- *Bhuvnesh Kumar Dwivedi v. Hindalco Industries* (2014) 11 SCC 85 — supervisor / managerial test
- *Indian Hume Pipe Co. v. Workmen* (1976) 3 SCC 487 — continuous service for gratuity
- *Air India Statutory Corporation v. United Labour Union* (1997) 9 SCC 377 — contract-labour-as-direct-employee doctrine
- *Steel Authority of India Ltd. v. National Union Waterfront Workers* (2001) 7 SCC 1 — overruled Air India SC doctrine; Section 10 Contract Labour Act framework
- *Bharat Aluminium v. Kaiser Aluminium (BALCO)* (2012) 9 SCC 552 — seat-vs-venue arbitration; relevant where employer pleads pre-dispute arbitration in employment contract (typically held non-arbitrable for statutory labour rights)
- *Vidya Drolia v. Durga Trading Corporation* (2021) 2 SCC 1 — non-arbitrability framework (statutory labour rights non-arbitrable per the four-fold test)

## Statutory currency rules

Every pleading filed today should cite the operative statute. Common substitution checks:

- **Code of Criminal Procedure 1973 → Bharatiya Nagarik Suraksha Sanhita 2023** for prosecution under labour penal provisions (e.g. Section 22B ID Act prosecution).
- **Indian Evidence Act 1872 → Bharatiya Sakshya Adhiniyam 2023** for proof of records (Section 65B → Section 63 for electronic records; Section 126 → Section 132 for privilege).
- **Workmen's Compensation Act 1923 → Employees' Compensation Act 1923** (post the 2009 amendment, the title and definitional sections have changed; the Act is otherwise the same).
- **Four Labour Codes 2019-2020 vs legacy Acts** — the Code on Wages 2019, Industrial Relations Code 2020, Code on Social Security 2020, and Occupational Safety, Health and Working Conditions Code 2020 have variable State-notification status. As of 2026, several States have notified all four Codes for selected provisions; many States have not. The Drafter and Verifier check the applicable State's notification status before citing either the Code or the legacy Act. Dual-citation is acceptable in any transitional pleading.

## Workman-vs-non-workman classification rule

Section 2(s) ID Act 1947 defines "workman" — any person (skilled / unskilled / manual / supervisory / clerical / technical / operational) employed in any industry, with the following exclusions:

- (i) any person subject to the Air Force Act / Army Act / Navy Act
- (ii) any person employed in police service / prison service
- (iii) any person employed mainly in managerial or administrative capacity
- (iv) any person employed in supervisory capacity drawing wages exceeding ₹10,000 per month (post the 2010 amendment) AND who, either by the nature of duties attached to the office or by reason of the powers vested in him, functions mainly in managerial nature

The Supreme Court applies the **predominant-duty test** — designation alone is not determinative; the workman's actual functions, KRAs, reporting structure, and authority to take independent decisions are examined. The Drafter pleads the predominant-duty test for any workman whose designation might be challenged.

For "retrenchment" under Section 2(oo), the Verifier checks the exclusions in the proviso:

- (a) voluntary retirement
- (b) retirement on reaching age of superannuation per contract
- (bb) termination as a result of non-renewal of contract on its expiry (where the contract had a fixed term)
- (c) termination on the ground of continued ill-health

## Section 25F / 25G / 25N retrenchment-compliance rule

- **Section 25F** — applies to all retrenchments. Conditions: (i) one month's notice OR notice-pay in lieu, (ii) retrenchment compensation = 15 days' average pay × completed years of service, (iii) notice to appropriate Government in the prescribed manner. Non-compliance → retrenchment is illegal.
- **Section 25G** — "last come, first go" principle within the same category of workmen.
- **Section 25N** — applies to industrial establishments employing 100 or more workmen (300 or more post the 2020 amendment in certain States). Conditions: prior permission of the appropriate Government for retrenchment / lay-off / closure.

## Section 33 ID Act protected-workman rule

Section 33 ID Act prohibits an Establishment from altering, to the prejudice of a workman, the conditions of service applicable to the workman during the pendency of any conciliation / Reference / Application — without express written permission of the conciliation officer / Labour Court / Industrial Tribunal. Section 33(2) creates an additional carve-out for misconduct not connected with the pending dispute (the Establishment must pay the workman one month's wages and make application to the authority for permission). Section 33A creates a cause of action for the workman where Section 33 has been contravened.

## POSH Act 2013 Section 16 confidentiality discipline

Section 16 prohibits publication or disclosure of:

- The contents of the complaint
- The identity and addresses of the complainant / respondent / witnesses
- Any information about the conciliation / inquiry proceedings
- Recommendations of the Internal Committee
- Action taken by the Employer / DO

Disclosure other than for the purpose of giving information about justice secured to the victim is punishable under Section 17. The plugin's POSH skill scaffolding carries this discipline at every layer — Reader's stricter placeholder substitution, Drafter's restraint on incident-detail paraphrasing, Refiner's Section 16 footer / header on every page, metadata stripping on the final `.docx`.

## Section 4 PG Act gratuity-eligibility rule

- **Eligibility:** continuous service of 5 years (waived in case of death / disablement)
- **Computation:** (15 × last drawn wages × completed years of service) / 26 — for monthly-paid employees
- For seasonal / piece-rated employees: separate formulas apply per Section 4(2) proviso
- **Ceiling under Section 4(3):** currently ₹20 lakh (per the 2018 amendment)
- **Time-bar for claim under Rule 10 PG Central Rules 1972:** within 90 days of date of cessation; extendable on sufficient cause
- **Interest under Section 7(3A):** at the rate notified by the Central Government (currently the rate applicable to deposits in nationalised banks for the corresponding period — typically 10% per annum simple)
- **Time-bar for payment by Employer:** within 30 days of cessation; failing which Section 7(3) interest accrues

## Section 7-O EPF Act pre-deposit rule

For appeals before the EPF Appellate Tribunal under Section 7-I against a Section 7A determination, Section 7-O EPF Act 1952 requires pre-deposit of 75% of the amount due under the impugned Section 7A order. The EPFAT may, for reasons recorded in writing, reduce the deposit — but cannot waive it entirely.

## Section 75 / Section 77 / Section 80 ESI Act framework

- **Section 75 ESI Act 1948** — Employees' Insurance Court's jurisdiction over contribution / benefit / coverage / rate / quantum disputes
- **Section 77** — time-bar of 3 years from cause of action; extendable on sufficient cause
- **Section 80** — 60-day notice before instituting against ESIC, where applicable

## Section 20(2) Minimum Wages Act framework

- **Section 20(1)** — Authority appointed by the appropriate Government (typically the Labour Commissioner or designated official)
- **Section 20(2)** — application within 12 months of date wages became payable; extendable on sufficient cause
- **Section 20(3)(i)** — direction for payment of difference + compensation up to 10 times the difference
- **Section 22A** — bar on civil court jurisdiction in matters falling within Section 20

## Limitation Act 1963 — Article / Section map for labour disputes

| Case-type | Reference | Period |
|---|---|---|
| Section 2A ID Act workman application | Section 2A(3) ID Act 1947 | 3 years from date dispute arises |
| Reference under Section 10 ID Act | no specific Article — governed by appropriate Government's reasonable-time discretion + writ jurisdiction | reasonable time |
| POSH Section 9 complaint | Section 9(1) POSH Act 2013 | 3 months + 3-month proviso |
| Gratuity controlling-authority claim | Rule 10 Payment of Gratuity Central Rules 1972 | 90 days from cessation, extendable |
| EPF Appellate Tribunal appeal | Rule 7(2) EPF AT Rules 1997 | 60 days from receipt of Section 7A order |
| ESI Court application | Section 77 ESI Act 1948 | 3 years from cause of action |
| Minimum Wages Section 20 claim | Section 20(2) MW Act 1948 | 12 months from when wages became payable |
| Standing Orders certification | no time-bar (regulatory submission) | N/A |
| State Shops and Establishments show-cause reply | per applicable State Act | typically 15 — 30 days |

## State Shops and Establishments applicability rule

The Drafter and Verifier check `case-config.md` for the State and load the applicable State Shops and Establishments Act + Rules:

- **Maharashtra:** Maharashtra Shops and Establishments (Regulation of Employment and Conditions of Service) Act 2017 + Rules 2018
- **Karnataka:** Karnataka Shops and Commercial Establishments Act 1961 + Rules
- **Tamil Nadu:** Tamil Nadu Shops and Establishments Act 1947 + Rules
- **Delhi:** Delhi Shops and Establishments Act 1954 + Rules
- **Uttar Pradesh:** Uttar Pradesh Dookan Aur Vanijya Adhishthan Adhiniyam 1962 + Rules
- **Gujarat:** Gujarat Shops and Establishments (Regulation of Employment and Conditions of Service) Act 2019 + Rules
- **West Bengal:** West Bengal Shops and Establishments Act 1963 + Rules
- **Telangana:** Telangana Shops and Establishments Act 1988 + Rules
- **Andhra Pradesh:** Andhra Pradesh Shops and Establishments Act 1988 + Rules
- **Kerala:** Kerala Shops and Commercial Establishments Act 1960 + Rules
- **Rajasthan:** Rajasthan Shops and Commercial Establishments Act 1958 + Rules
- **Madhya Pradesh:** Madhya Pradesh Shops and Establishments Act 1958 + Rules
- **Odisha:** Odisha Shops and Commercial Establishments Act 1956 + Rules
- **Punjab:** Punjab Shops and Commercial Establishments Act 1958 + Rules
- **Haryana:** Punjab Shops and Commercial Establishments Act 1958 (as extended to Haryana) + Rules
- **Bihar:** Bihar Shops and Establishments Act 1953 + Rules

Each State exemplar in `state-config/exemplars/` contains the corresponding Act name + key Section references + working-hours rules + leave entitlement rules + registration requirements + Labour Welfare Fund applicability + Profession Tax applicability.

## Maharashtra-only: MRTU & PULP Act 1971

For Establishments in Maharashtra, the Maharashtra Recognition of Trade Unions and Prevention of Unfair Labour Practices Act 1971 creates an additional layer of forum — the Industrial Court (in addition to the Labour Court and the Industrial Tribunal). Complaints of unfair labour practices listed in Schedules II, III, and IV of the Act lie before the Industrial Court. The Drafter checks `case-config.md` for Maharashtra State and applies the MRTU & PULP forum where the cause of action is an unfair labour practice (e.g. victimisation of workmen for union activities; refusal to bargain in good faith; refusal to implement an award).


---

## v0.2.1 RENDER DISCIPLINE (load-bearing — Drafter must follow)

**Pandoc + reference.docx + post-pandoc fix script.** The Drafter writes Markdown using the heading discipline below. Pandoc converts the Markdown to `.docx` using the SHIPPED reference.docx at `${CLAUDE_PLUGIN_ROOT}/skills/_labour_drafting_base/reference.docx` — pre-customised with locked Word styles matching the filing-grade Bombay HC Nagpur convention (extracted from an actual filed Second Appeal pleading):

- **Body (Normal)** — TNR 14pt, 1.5 line spacing, justified, 0.5cm first-line indent
- **Heading 1** — TNR 14pt **bold + centered** (NOT underlined) — for the Court / Forum / Tribunal header line and the case-number line
- **Heading 2** — TNR 14pt **bold + UNDERLINED + centered + letter-spacing** — for spaced section headers (`F A C T S`, `G R O U N D S`, `P R A Y E R`, `I N D E X`, `S Y N O P S I S`, `L I S T   O F   A N N E X U R E S`, `V E R I F I C A T I O N`)
- **Heading 3** — TNR 14pt **bold + UNDERLINED + centered** — for unspaced section headers (`SUBSTANTIAL QUESTIONS OF LAW`, `ACTS & RULES`, `CITATIONS`) and statutory opening (`WRIT PETITION UNDER ARTICLE 226 …`)
- **Heading 4** — TNR 14pt **bold + UNDERLINED + left-aligned** — for left-anchored bold-underlined headings (`MOST RESPECTFULLY SHEWETH:`)
- **Tables** — `tblLayout = fixed`; first row bold centered; cell margins locked

### Markdown heading mapping

| Markdown | Rendered as | Used for |
|---|---|---|
| `# Heading 1` | Bold centered (no underline) | Court header line; case-number line; cover-page anchors |
| `## Heading 2` | Bold centered UNDERLINED with letter-spacing | Spaced section headers (`## F A C T S`, `## G R O U N D S`, `## P R A Y E R`, `## I N D E X`, `## S Y N O P S I S`, `## L I S T   O F   A N N E X U R E S`, `## V E R I F I C A T I O N`) |
| `### Heading 3` | Bold centered UNDERLINED | Unspaced section headers + statutory opening |
| `#### Heading 4` | Bold left UNDERLINED | `#### MOST RESPECTFULLY SHEWETH:` |
| Body paragraph | TNR 14pt justified 1.5 spacing 0.5cm first-line indent | Everything else |
| `**Bold inline**` | Bold | Property descriptors / annexure markers / key terms inline within Facts narrative |

### Bold-number paragraph convention

Facts and Grounds paragraphs use **BOLD NUMBERS**: `**1.**`, `**2.**`, `**3.**` followed by a tab + body. Renders as the gold-standard pleading layout.

### Two-step pandoc command (Step 2 is NON-NEGOTIABLE)

```bash
# Step 1 — pandoc → .docx with locked Word styles
pandoc draft-v1.md -o draft-v1.docx \
  --reference-doc="${CLAUDE_PLUGIN_ROOT}/skills/_labour_drafting_base/reference.docx" \
  --from=markdown+pipe_tables+raw_tex

# Step 2 — force table column widths
python3 "${CLAUDE_PLUGIN_ROOT}/skills/_labour_drafting_base/fix_docx_tables.py" draft-v1.docx
```

Step 2 forces column widths on every table — 5-col (Sr.No / Annx / Particulars / Date / Pgs) = 8/8/60/14/10; 4-col = 10/10/65/15; 3-col = 10/75/15; 2-col Dates–Events = 18/82. Locks first-row bold + centered + vertically-centered cells. **Skipping the fix script reproduces the v0.2.0 Index-table defect (Sr.No / Annx columns stacking vertically).**

Do NOT auto-generate a fresh reference.docx in the case folder. Use the shipped one or a `<case-folder>/reference.docx` override.

### Cover-page discipline

INDEX, SYNOPSIS, LIST OF ANNEXURES each begin on a new page (`\newpage` in Markdown) and carry ONLY: forum header (`#`) + case-number line (`#`) + short cause-title (Petitioner short name `///VERSUS///` Respondent short name) + section header (`##`) + table + Counsel block. DO NOT repeat the full party address block on cover pages.

### Pipeline-optionality (advocate-cost discipline)

The full 6-agent pipeline (Reader → Format → Drafter → Verifier → Refiner → Overseer) is **NOT** mandatory. Only the first three stages are required to produce a filing-grade draft. Stages 4–6 are OPTIONAL QC layers the advocate explicitly invokes. Default exit point is here, after Drafter (~280K tokens). Full pipeline ~600K tokens — disproportionate for routine pleadings.

When `draft-v1.docx` is written, the Drafter's job is complete. The advocate decides whether to invoke the QC stages.


---

## v0.2.2 OUTPUT-PAIRING DISCIPLINE (load-bearing — every agent must follow)

**Every `.md` output artifact MUST be paired with a `.docx`.** Advocates do not natively read Markdown — they read Word. Every pipeline output (case-facts.md from Reader, format-shell.md from Format, draft-v1.md from Drafter, verification-report.md from Verifier, draft-v2.md from Refiner, opposing-notes.md from Overseer) must have a corresponding `.docx` rendered with the same locked Word styles.

**This plugin produces pleadings** — the shipped reference.docx is the pleading variant (TNR 14pt 1.5 spacing, Heading 2 bold + UNDERLINED + centered with letter-spacing for the spaced `F A C T S` effect).

### How to produce the paired `.docx`

Every agent runs the shipped helper script as its final post-`.md`-write step:

```bash
bash "${CLAUDE_PLUGIN_ROOT}/skills/_labour_drafting_base/pair_md_to_docx.sh" <output.md>
```

The helper:
1. Resolves the reference.docx in `${CLAUDE_PLUGIN_ROOT}/skills/_labour_drafting_base/reference.docx`
2. Runs pandoc with `--reference-doc` and `--from=markdown+pipe_tables+raw_tex` to produce the `.docx`
3. Runs the shipped `fix_docx_tables.py` to force column widths on every table

For overriding (e.g., a per-case-folder reference.docx), pass the reference.docx as the second argument:

```bash
bash "${CLAUDE_PLUGIN_ROOT}/skills/_labour_drafting_base/pair_md_to_docx.sh" \
    <output.md> <case-folder>/reference.docx
```

### Per-agent output-pairing map

| Agent | `.md` output | Paired `.docx` |
|---|---|---|
| Reader | `case-facts.md` | `case-facts.docx` |
| Format | `format-shell.md` | `format-shell.docx` |
| Drafter | `draft-v1.md` | `draft-v1.docx` |
| Verifier | `verification-report.md` | `verification-report.docx` |
| Refiner | `draft-v2.md` | `draft-v2.docx` |
| Overseer | `opposing-notes.md` + `final-draft.md` | `opposing-notes.docx` + `final-draft.docx` |

Every agent calls `pair_md_to_docx.sh` once for each `.md` it writes. Skipping this step leaves the advocate with `.md` files that cannot be opened natively in Word.
