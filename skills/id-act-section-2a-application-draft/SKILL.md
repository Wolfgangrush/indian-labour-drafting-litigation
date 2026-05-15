---
name: id-act-section-2a-application-draft
description: Draft an Application under Section 2A(2) of the Industrial Disputes Act 1947 (as inserted by the ID (Amendment) Act 2010), filed directly by the workman before the Labour Court / Industrial Tribunal, bypassing the conciliation-officer-and-government-reference route under Section 10. Available where the workman's individual dispute relates to discharge / dismissal / retrenchment / termination of services AND the period of three months from the date of communication of the action has elapsed without resolution through conciliation. Encodes the post-2010-amendment direct-filing route, the 3-month statutory pre-condition, the 3-year limitation under Section 2A(3), the workman-classification check under Section 2(s), and the parallel-applicability of Section 25F / 25G / 25N retrenchment-compliance discipline. Auto-fires on "draft Section 2A application", "draft workman application ID Act", "direct workman application", "draft workman dispute application", and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# Section 2A ID Act Application Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_labour_drafting_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Case-type metadata

```yaml
case_type_line: APPLICATION UNDER SECTION 2A(2) OF THE INDUSTRIAL DISPUTES ACT 1947 (AS INSERTED BY THE INDUSTRIAL DISPUTES (AMENDMENT) ACT 2010)
case_short_code: IDA_S2A
case_number_prefix: Application (S.2A IDA)
pleading_type: Workman's Direct Application
typical_forum: Labour Court (where the subject-matter is within Schedule II — propriety of dismissal / discharge / retrenchment) — territorial jurisdiction per Section 2A(2) read with Section 11A (which gives the Labour Court power to set aside dismissal and order reinstatement)
typical_parties: Applicant Workman + Respondent Establishment / Employer / Management
statutory_opening: "This Application is filed under Section 2A(2) of the Industrial Disputes Act 1947 (as inserted by the Industrial Disputes (Amendment) Act 2010) by the Applicant Workman directly before this Hon'ble Labour Court / Industrial Tribunal, the period of three months from the date of communication of dismissal / discharge / retrenchment / termination having elapsed without resolution of the dispute through conciliation under Section 12 of the said Act."
ground_clauses:
  - "Workman status — the Applicant is a 'workman' within the meaning of Section 2(s) of the ID Act 1947, with the duties / KRAs / reporting structure pleaded at paragraph ___ (refer Appointment Letter at Exhibit ___, KRA documents at Exhibit ___, organisation chart at Exhibit ___). The Applicant Workman draws monthly wages of ₹ ___ (refer salary slips at Exhibit ___). The predominant-duty test under *Sonepat Cooperative Sugar Mills v. Ajit Singh* (2005) 3 SCC 232 and *T.P. Srinivasan v. Aspinwall* (2002) 7 SCC 569 establishes workman status irrespective of designation."
  - "240 days of continuous service — the Applicant has completed not less than 240 days of continuous service in the 12 calendar months preceding the date of impugned action, within the meaning of Section 25B ID Act 1947 (refer attendance records at Exhibit ___)."
  - "Cause of action — by Order dated ____ (Exhibit ___), the Respondent Establishment discharged / dismissed / retrenched / terminated the services of the Applicant. The Applicant raised the dispute on ____ through conciliation officer at [Place] (Exhibit ___); the conciliation officer issued failure report dated ____ (Exhibit ___). More than three months have elapsed from the said failure report and / or from the date of communication of the impugned action."
  - "Section 25F / 25G / 25N non-compliance (where retrenchment) — the impugned retrenchment is illegal as: (a) no one-month notice or notice-pay was given; (b) no retrenchment compensation as required by Section 25F(b) was paid; (c) no intimation to the appropriate Government in the prescribed manner was made; (d) the last-come-first-go rule under Section 25G was not followed (where the Establishment is multi-workman); (e) for industrial establishments employing 100+ workmen (or 300+ in States with the 2020 amendment), no prior permission under Section 25N was obtained."
  - "Domestic inquiry defects (where dismissal on alleged misconduct) — (a) defective charge-sheet vague / non-specific; (b) denial of opportunity / cross-examination / inspection of management witnesses' statements; (c) presiding officer pre-determined / mala fide; (d) breach of natural justice; (e) findings against weight of evidence (*Workmen of M/s Firestone Tyre & Rubber Co. v. Management* (1973) 1 SCC 813)."
  - "Section 33 ID Act violation (where dismissal occurred during pendency of conciliation / Reference / Application) — no prior permission of the conciliation officer / Labour Court / Industrial Tribunal was obtained; the impugned action is void."
  - "Limitation — the Application is filed within three years from the date of dispute arising as required by Section 2A(3) ID Act 1947."
prayer_clauses:
  - "(a) Declare that the discharge / dismissal / retrenchment / termination of the Applicant Workman by Order dated ____ is illegal, void, and contrary to law;"
  - "(b) Direct the Respondent Establishment to reinstate the Applicant Workman with continuity of service and full back-wages from the date of termination till the date of reinstatement;"
  - "(c) Direct payment of all consequential benefits including increments, allowances, EPF / ESI / gratuity contributions, and statutory bonus for the entire period of forced unemployment;"
  - "(d) Award costs of the present proceedings to the Applicant Workman."
mandatory_exhibits:
  - appointment_letter
  - employment_agreement_where_applicable
  - salary_slips_for_relevant_period
  - kra_documents_or_job_description
  - organisation_chart_establishing_workman_status
  - attendance_records_establishing_240_days_continuous_service
  - epf_contribution_record
  - esi_contribution_record
  - charge_sheet_where_applicable
  - notice_of_domestic_inquiry_where_applicable
  - domestic_inquiry_findings_where_applicable
  - termination_or_dismissal_or_retrenchment_order
  - conciliation_officer_intimation_and_proceedings
  - conciliation_officer_failure_report
  - pre_litigation_correspondence
accompanying_applications:
  - "I.A. for status-quo on workman's service conditions during pendency (under Section 33 ID Act read with Order 39 CPC framework)"
  - "I.A. for ex-parte interim direction restraining the Establishment from filling the workman's post pending adjudication"
  - "I.A. for urgent listing where workman's livelihood is at immediate risk"
court_fee: "Per applicable State Industrial Disputes Rules — typically nominal fee per Form O / equivalent."
limitation: "Three years from the date of dispute arising — Section 2A(3) ID Act 1947 (as inserted by the 2010 Amendment). Delay condonable under Section 5 of the Limitation Act 1963 on sufficient cause shown."
```

## Section 11A power of the Labour Court

Section 11A ID Act 1947 empowers the Labour Court / Industrial Tribunal / National Industrial Tribunal to (a) set aside the order of discharge / dismissal, (b) direct reinstatement, (c) award lesser punishment in place of dismissal / discharge as it considers appropriate, and (d) give such other relief to the workman as it considers appropriate, including the award of any lesser punishment in lieu of discharge / dismissal. *Workmen of M/s Firestone Tyre & Rubber Co. of India v. Management* (1973) 1 SCC 813 confirms the wide ambit of Section 11A. The Drafter pleads the relief sought with reference to Section 11A.

## Back-wages discipline

Where reinstatement is ordered, back-wages are not automatic — the Labour Court / Tribunal considers whether the workman was gainfully employed during the period of forced unemployment, whether the workman has approached the forum diligently, and the financial condition of the Establishment. *Allahabad Jal Sansthan v. Daya Shankar Rai* (2005) 5 SCC 124 and the lineage thereafter restrict full back-wages to cases where the workman has not been gainfully employed and the Establishment has been mala fide. The Drafter pleads the workman's non-employment during the relevant period and the Establishment's mala fides, to maximise the prospect of full back-wages.

## Anti-fabrication of "240 days" averment

The Verifier checks the 240-days-in-12-preceding-months computation against attendance records at Exhibit ___ . Any averment of 240 days unsupported by attendance records is a hard error — the Establishment's typical defence is precisely that the workman did not complete 240 days.
