---
name: _labour_drafting_base
description: Universal Indian labour pleading skeleton. Shared base for all 10 case-type drafting skills. Holds the standard structure (Cause Title -> Parties block -> Statutory Opening -> Prelude -> Facts -> Grounds -> Prayer -> Verification -> Affidavit-in-support -> Index -> List of Documents -> accompanying applications). NOT invoked directly — extended by every case-type skill in this plugin.
allowed-tools: Read
---

# `_labour_drafting_base` — universal Indian labour pleading skeleton

This base skill defines the **structural shape** of any labour / industrial-disputes / employment-rights / social-security / workplace-protection pleading drafted by the plugin. Case-type skills extend this base with case-type-specific statutory openings, fact-sequences, grounds, prayer clauses, and accompanying applications.

## Universal skeleton

```
1. CAUSE TITLE
   {{forum.name}} {{forum.bench_or_authority}}
   {{case_type.case_number_prefix}} No. ____ of {{year}}

   {{party_block_template}}
   {{applicant_or_complainant_party}} ... {{applicant_role}}
                                  Versus
   {{respondent_or_employer_party}} ... {{respondent_role}}

2. STATUTORY OPENING
   {{case_type.statutory_opening}}

3. PRELUDE
   (Short paragraph identifying the Applicant's status — workman within
   Section 2(s) ID Act / employee within Section 2(e) PG Act / insured
   person within Section 2(14) ESI Act / aggrieved woman within
   Section 2(a) POSH Act / Internal Committee under Section 4 POSH Act /
   trade union representative — and the Respondent's status (Employer /
   Establishment / ESI Corporation / EPF Authority / Internal Committee
   under POSH Act / Inspector under State Shops and Establishments Act),
   with relevant registrations.)

4. FACTS (numbered narrative paragraphs)
   4.1 Appointment — date of joining, designation, terms (refer
       Appointment Letter at Exhibit / Annexure A).
   4.2 Pre-dispute working relationship — period of service, salary
       progression, increments, leave / EPF / ESI / gratuity service
       record (refer salary slips at Exhibit / Annexure B; refer EPF
       contribution record at Exhibit / Annexure C; refer ESI
       contribution record at Exhibit / Annexure D).
   4.3 Workman / employee status — pleaded with reference to actual
       duties / KRAs / reporting structure under Section 2(s) ID Act /
       Section 2(e) PG Act / Section 2(14) ESI Act / Section 2(f) POSH
       Act (refer KRA documents / organisation chart at Exhibit /
       Annexure E).
   4.4 Continuous service — 240 days of continuous service in 12
       preceding months under Section 25B ID Act (where Section 25F /
       25G / 25N invoked); 5 years continuous service under Section 4
       PG Act (where gratuity claimed) (refer attendance records at
       Exhibit / Annexure F).
   4.5 Trigger incident — date and circumstances of the incident
       giving rise to the cause of action (charge-sheet / domestic
       inquiry / dismissal / retrenchment / POSH-incident / gratuity
       non-payment / EPF determination / ESI contribution demand /
       minimum wages shortfall / show-cause notice / certification
       proceeding) (refer Exhibits / Annexures G, H, I).
   4.6 Pre-litigation correspondence — notices issued / replies
       received / conciliation officer engagement / Internal Committee
       proceedings (where applicable) (refer Exhibits / Annexures
       J, K, L).
   4.7 Cause of action for the present pleading — the specific event
       crystallising the present cause of action (e.g. failure of
       conciliation under Section 12 ID Act; expiry of 30-day window
       under PG Act; passing of Section 7A determination order under
       EPF Act; issue of show-cause notice under State Shops and
       Establishments Act).
   4.8 Limitation — applicable Section / Article / Rule of the
       Limitation Act 1963 or the case-type-specific statute, date of
       accrual, date of filing, days within limitation.
   4.9 Jurisdiction — territorial jurisdiction of the Court /
       Tribunal / Authority / Internal Committee, with statutory
       anchor (Section 10 ID Act / Section 7 PG Act / Section 7-I EPF
       Act / Section 75 ESI Act / Section 20 MW Act / Section 4
       read with Section 9 POSH Act / applicable State Shops and
       Establishments Act).

5. GROUNDS (numbered)
   5.1 {{case_type.ground_1}}
   5.2 {{case_type.ground_2}}
   5.3 {{case_type.ground_3}}
   ...
   (Grounds anchor each prayer clause; every ground cites the
    operative provision and the document supporting the ground.)

6. PRAYER
   {{case_type.prayer_clauses}}

   And for such further and other reliefs as this Hon'ble [Labour
   Court / Industrial Tribunal / Authority / Internal Committee] may
   deem fit and proper.

7. VERIFICATION
   I, [Name of Applicant Workman / Authorised Signatory of
   Complainant / Authorised Signatory of Establishment], aged ___
   years, do hereby verify that the contents of paragraphs ___ to
   ___ of the {{case_type.pleading_type}} are true to my personal
   knowledge and the contents of paragraphs ___ to ___ are true on
   the basis of information received and believed to be true. No
   part of this verification is false and nothing material has been
   concealed therefrom.

   Verified at [Place] on this __ day of [Month, Year].

                                       [Verifier-Signatory]
                                       [Designation, where applicable]

8. AFFIDAVIT-IN-SUPPORT
   I, [Name of Applicant / Authorised Signatory], aged ___ years,
   occupation [Designation], having office / residence at [Address],
   do hereby solemnly affirm on oath and state as under:
   1. That I am the Applicant Workman / duly authorised signatory of
      the Applicant / Complainant / Establishment herein and am
      acquainted with the facts and circumstances of the case.
   2. That I have read and understood the contents of the
      {{case_type.pleading_type}} comprising paragraphs 1 to ___ and
      the same are true and correct.
   3. That the documents annexed are true copies / certified true
      copies / true print-outs of the originals.

   Affirmed at [Place] on this __ day of [Month, Year].

                                       [Affidavit-Signatory]
                                       [Designation, where applicable]

   Solemnly affirmed before me on solemn affirmation under the
   Bharatiya Sakshya Adhiniyam 2023.

                                       [Notary Public / Oath
                                        Commissioner / Tribunal
                                        Officer]

9. INDEX
   (Running paragraph-anchored index — paragraph numbers, content
   summary, exhibit references.)

10. LIST OF DOCUMENTS / EXHIBITS / ANNEXURES
    Exhibit / Annexure A — Appointment letter dated ____
    Exhibit / Annexure B — Salary slips for the relevant period
    Exhibit / Annexure C — EPF contribution record
    Exhibit / Annexure D — ESI contribution record
    Exhibit / Annexure E — KRA / organisation chart establishing
                          workman status
    Exhibit / Annexure F — Attendance records establishing
                          continuous service
    Exhibit / Annexure G — Charge-sheet dated ____ (where
                          applicable)
    Exhibit / Annexure H — Domestic inquiry findings dated ____
                          (where applicable)
    Exhibit / Annexure I — Termination / dismissal / retrenchment
                          order dated ____ (where applicable)
    Exhibit / Annexure J — Pre-litigation correspondence
    Exhibit / Annexure K — Conciliation officer's failure-of-
                          conciliation report (where applicable)
    Exhibit / Annexure L — Section 10 ID Act reference order
                          (where applicable)
    Exhibit / Annexure M — Section 7A EPF determination order
                          (where applicable)
    Exhibit / Annexure N — ESI contribution-demand order (where
                          applicable)
    Exhibit / Annexure O — Internal Committee proceedings (under
                          POSH Section 16 confidentiality discipline;
                          where applicable)
    Exhibit / Annexure P — State Shops and Establishments
                          show-cause notice (where applicable)
    Exhibit / Annexure Q — Standing Orders / draft Standing Orders
                          (where applicable)
    Exhibit / Annexure R — Board Resolution authorising the
                          Establishment-side litigation (where the
                          Applicant is the Establishment)

11. ACCOMPANYING APPLICATIONS
    {{case_type.accompanying_applications}}
    (Common examples: Section 33 ID Act application for status-quo
    on workman's service conditions during pendency; Section 12 POSH
    Act application for transfer / leave / protective measure;
    application for waiver / reduction of pre-deposit under Section
    7-O EPF Act; application for condonation of delay under Section
    5 Limitation Act 1963; application for ex-parte interim order;
    application for urgent listing where workman's livelihood is at
    immediate risk.)
```

## Statute references the plugin handles

- Industrial Disputes Act 1947 (Sections 2(s), 2(oo), 2A, 10, 11A, 25B, 25F, 25G, 25N, 33)
- Industrial Disputes (Central) Rules 1957 + applicable State Industrial Disputes Rules
- Industrial Employment (Standing Orders) Act 1946 + Central Rules + applicable State Rules
- Trade Unions Act 1926
- POSH Act 2013 (Sections 2, 3, 4, 9, 11, 13, 15, 16, 17)
- POSH Rules 2013
- Payment of Gratuity Act 1972 (Sections 2(e), 3, 4, 7, 7(3), 7(3A))
- Payment of Gratuity (Central) Rules 1972
- EPF and Miscellaneous Provisions Act 1952 (Sections 2, 7A, 7-I, 7-O)
- Employees' Provident Funds Scheme 1952 + EPS 1995 + EDLI 1976
- EPF Appellate Tribunal (Procedure) Rules 1997
- ESI Act 1948 (Sections 2(14), 75, 77, 80)
- ESI (Central) Rules 1950 + ESI (General) Regulations 1950
- Minimum Wages Act 1948 (Sections 1, 3, 14, 18, 20, 22A)
- Applicable Central / State Minimum Wages Rules
- Factories Act 1948
- Maternity Benefit Act 1961
- Equal Remuneration Act 1976
- Contract Labour (Regulation and Abolition) Act 1970
- Apprentices Act 1961
- Code on Wages 2019 (variable State notification)
- Industrial Relations Code 2020 (variable State notification)
- Code on Social Security 2020 (variable State notification)
- Occupational Safety, Health and Working Conditions Code 2020 (variable State notification)
- Maharashtra Recognition of Trade Unions and Prevention of Unfair Labour Practices Act 1971 (Maharashtra-only)
- Applicable State Shops and Establishments Acts + Rules (full list in `_drafting_common`)
- Applicable State Labour Welfare Fund Acts (where relevant)
- Applicable State Profession Tax Acts (where relevant)
- Bharatiya Nagarik Suraksha Sanhita 2023 (for prosecution under labour penal provisions)
- Bharatiya Sakshya Adhiniyam 2023 (for proof of records)
- Indian Contract Act 1872 (employment contracts; Section 27 restraint-of-trade caveat for non-compete)
- Limitation Act 1963
- Code of Civil Procedure 1908 (Section 80 / Order 1 / Order 21 for execution of Labour Court awards under Section 11(8) ID Act read with Section 33C(1))


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
