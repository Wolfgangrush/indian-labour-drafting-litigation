---
name: epf-determination-challenge-draft
description: Draft an Appeal before the Employees' Provident Funds Appellate Tribunal under Section 7-I of the Employees' Provident Funds and Miscellaneous Provisions Act 1952, challenging a Section 7A determination order passed by the Regional / Additional / Assistant Provident Fund Commissioner. Encodes the Section 7A inquiry framework, the Section 7-I appeal route, the Section 7-O pre-deposit discipline (75% of the amount due as determined; reducible by the Tribunal for reasons recorded in writing but NOT waivable), the 60-day filing window under Rule 7(2) EPF AT Rules 1997, and the typical grounds (procedural defects in the Section 7A inquiry / factual errors / coverage challenges / contribution-quantum challenges / wage-definition disputes). Auto-fires on "draft EPF appeal", "draft Section 7-I appeal", "draft EPFAT appeal", "challenge Section 7A order", and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# EPF Section 7-I Appeal Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_labour_drafting_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Case-type metadata

```yaml
case_type_line: APPEAL UNDER SECTION 7-I OF THE EMPLOYEES' PROVIDENT FUNDS AND MISCELLANEOUS PROVISIONS ACT 1952 BEFORE THE EMPLOYEES' PROVIDENT FUNDS APPELLATE TRIBUNAL
case_short_code: EPF_APPEAL
case_number_prefix: EPF Appeal
pleading_type: Memorandum of Appeal
typical_forum: Employees' Provident Funds Appellate Tribunal (constituted under Section 7D EPF Act 1952; located at New Delhi for matters from northern and central States; territorial benches as notified by the Central Government from time to time)
typical_parties: Appellant Establishment (Employer aggrieved by Section 7A determination) + Respondent Regional Provident Fund Commissioner / Additional PF Commissioner / Assistant PF Commissioner who passed the impugned Section 7A order + Employees' Provident Fund Organisation (EPFO)
statutory_opening: "This Appeal is filed under Section 7-I of the Employees' Provident Funds and Miscellaneous Provisions Act 1952 read with Rule 7 of the Employees' Provident Funds Appellate Tribunal (Procedure) Rules 1997, against the Order dated ____ passed by the Respondent Regional / Additional / Assistant Provident Fund Commissioner under Section 7A of the said Act in EPF Case No. ____ at [Place] (Exhibit P-1), determining the amount due from the Appellant Establishment as ₹ ___ towards [Employee contributions / Employer contributions / administrative charges / interest / damages under Section 14B] for the period ____ to ____."
ground_clauses:
  - "Procedural defects in the Section 7A inquiry — the Respondent (a) did not afford reasonable opportunity to the Appellant Establishment to produce its records; (b) did not summon the relevant material at the Appellant's request; (c) did not permit cross-examination of witnesses relied on by the Respondent; (d) passed the impugned order without recording adequate reasons; (e) failed to comply with the principles of natural justice."
  - "Factual errors in the determination — the Respondent (a) misclassified the Appellant Establishment as covered when it falls below the Section 1(3) employee threshold / outside the notified industry schedule; (b) misclassified certain employees as 'employee' under Section 2(f) when they are excluded; (c) included wages above the statutory ceiling (currently ₹15,000 per month under Para 26A EPF Scheme); (d) computed interest / damages under Section 14B on an erroneous basis; (e) extended liability backward beyond the applicable limitation under Section 11."
  - "Coverage challenges — the Appellant Establishment (a) is engaged in an excluded industry / activity under Section 16(1) / paragraph 26B EPF Scheme; (b) is exempted under Section 17 read with Para 27 EPF Scheme; (c) the impugned order applies the Act retrospectively to a period before coverage."
  - "Contribution-quantum challenges — the Respondent's computation of the basic-wage component is contrary to Vivekananda Sevak Samiti v. RPFC (2008) and Surya Roshni Ltd. v. EPFO (2019) 6 SCC 401 — basic-wages-vs-allowances jurisprudence on splitting of wage components."
  - "Section 14B damages — the Respondent's levy of damages under Section 14B is excessive / arbitrary / not preceded by show-cause / inquiry into mens rea per Hindustan Times v. Union of India (1998) 2 SCC 242 and Organo Chemical Industries v. Union of India (1979) 4 SCC 573 framework."
  - "Limitation under Section 11 — the impugned determination covers periods barred by limitation."
  - "Filing within time — the present Appeal is filed within 60 days of receipt of the impugned order as required by Rule 7(2) EPF AT Rules 1997 (proof of receipt at Exhibit ___)."
  - "Pre-deposit — the Appellant has [deposited ₹ ___ being 75% of the amount due / made application for reduction of pre-deposit under the proviso to Section 7-O EPF Act 1952 for the reasons set out at Annexure ___]."
prayer_clauses:
  - "(a) Allow this Appeal;"
  - "(b) Set aside the impugned Section 7A Order dated ____ passed by the Respondent;"
  - "(c) Direct the Respondent to refund the pre-deposit / amounts paid by the Appellant under the impugned order, with applicable interest;"
  - "(d) In the alternative, remand the matter to the Respondent for fresh determination in accordance with law after affording due opportunity to the Appellant Establishment;"
  - "(e) Pass such further and other reliefs as this Hon'ble Tribunal may deem fit and proper."
mandatory_exhibits:
  - certified_copy_of_the_section_7a_impugned_order
  - section_7a_show_cause_notice_received_by_the_appellant
  - appellants_reply_to_the_section_7a_show_cause_notice
  - records_produced_by_the_appellant_before_the_respondent
  - any_appellants_application_for_summoning_witnesses_or_records
  - epf_returns_filed_by_the_appellant_for_the_period_in_dispute
  - salary_registers_and_wage_records_for_the_period
  - section_14b_damages_levy_order_and_show_cause_where_separate
  - proof_of_receipt_of_impugned_order_for_limitation_compliance
  - pre_deposit_receipt_or_application_for_reduction
accompanying_applications:
  - "I.A. for reduction of pre-deposit under the proviso to Section 7-O EPF Act 1952 — typically pleaded with grounds (undue hardship / merits of the appeal favouring the appellant / disproportionate impact on the Establishment's working capital)"
  - "I.A. for stay of recovery proceedings during pendency of the appeal"
  - "I.A. for condonation of delay (where the 60-day Rule 7(2) limitation is exceeded — with Section 5 Limitation Act 1963 grounds)"
  - "I.A. for urgent listing where recovery proceedings are imminent"
filing_fee: "Appeal fee under Rule 6 of the Employees' Provident Funds Appellate Tribunal (Procedure) Rules 1997 — slab fee linked to the amount in dispute."
limitation: "60 days from the date of receipt of the impugned Section 7A order — Rule 7(2) of the EPF AT (Procedure) Rules 1997. Delay condonable on sufficient cause shown."
```

## Section 7-O pre-deposit discipline

Section 7-O EPF Act 1952 mandates pre-deposit of 75% of the amount due under the impugned Section 7A order, as a condition precedent to entertaining the appeal. The Tribunal may, for reasons recorded in writing, reduce the deposit — but cannot waive it entirely. The Drafter prepares the appeal in one of two postures:

- **Pre-deposit complied** — deposit receipt for 75% (or reduced 25% / 50% if a prior order so directs) is annexed to the appeal memo
- **Pre-deposit reduction sought** — a separate I.A. is filed seeking reduction with detailed grounds (undue hardship demonstrated by audited financial statements / merits of the appeal favouring the appellant on the face of the record / disproportionate impact on the establishment's working capital and going-concern status)

The I.A. for reduction must be filed contemporaneously with the appeal — failure to file pre-deposit / failure to obtain reduction leads to dismissal under Section 7-O at the threshold.

## *Surya Roshni* and the basic-wages controversy

*Surya Roshni Ltd. v. EPFO* (2019) 6 SCC 401 settled the long-running controversy on whether special allowances are includible in "basic wages" for EPF contribution computation — the Supreme Court held that special allowances are *includible* unless they vary across employees of similar status or are tied to a productivity / incentive criterion. The Drafter analyses the impugned order's basic-wage methodology against *Surya Roshni* and the post-*Surya Roshni* lineage; bare misapplication is a strong ground of appeal.

## Section 14B damages — *Organo Chemical* / *Hindustan Times* framework

Section 14B empowers the PF Authority to levy damages for delayed remittance. *Organo Chemical Industries v. Union of India* (1979) 4 SCC 573 holds that damages are not automatic — the levy requires inquiry into the defaulting employer's mens rea + show-cause + reasoned order. *Hindustan Times v. Union of India* (1998) 2 SCC 242 and the lineage refine the discipline. The Drafter challenges Section 14B levies on procedural-fairness grounds where applicable.

## Sections 16 and 17 exemption challenges

Where the Appellant Establishment is exempted (or claims to be exempt) under Section 17 read with Para 27 EPF Scheme 1952 — or is excluded under Section 16(1) — the Drafter pleads the exemption / exclusion with reference to the exempting notification / governing facts. *Provident Fund Inspector v. T.S. Hariharan* (1971) 2 SCC 68 sets out the framework for "industry" classification under the Act.

## Post-amendment Social Security Code 2020 status

The Code on Social Security 2020 — when notified for the relevant State / industry — will subsume the EPF Act 1952 framework. As of 2026, the Code is partially notified. The Drafter checks the Code's notification status under `case-config.md` and applies the operative statute (legacy EPF Act 1952 or Code on Social Security 2020) accordingly.
