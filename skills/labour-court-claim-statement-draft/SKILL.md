---
name: labour-court-claim-statement-draft
description: Draft a Statement of Claim before the Labour Court / Industrial Tribunal, filed by the workman / trade union pursuant to (a) a Reference under Section 10 ID Act 1947 by the appropriate Government, or (b) an Application under Section 2A(2) ID Act 1947 admitted by the Labour Court. Encodes the post-admission pleading structure (cause of action narrative + grounds for reinstatement / back-wages / consequential reliefs + workman-classification + Section 11A relief discipline + Section 17 Notification of Award), the Section 33 ID Act protected-workman discipline during pendency, the Section 33C(1) / Section 33C(2) execution route for the Award once made, and the limitation-and-laches framework. Auto-fires on "draft labour court claim", "draft statement of claim", "draft labour court pleading", "draft industrial tribunal claim", and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# Labour Court Statement of Claim Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_labour_drafting_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Case-type metadata

```yaml
case_type_line: STATEMENT OF CLAIM BEFORE THE LABOUR COURT / INDUSTRIAL TRIBUNAL
case_short_code: LC_CLAIM
case_number_prefix: Ref. (IDA) / Application (S.2A IDA) / Claim Stmt.
pleading_type: Statement of Claim
typical_forum: Labour Court (for Schedule II matters) / Industrial Tribunal (for Schedule III matters) — territorial jurisdiction per Section 10 Reference Order or Section 2A(2) Application
typical_parties: First Party / Applicant Workman / Trade Union (Claimant) + Second Party / Respondent Establishment / Employer / Management
statutory_opening_post_reference: "This Statement of Claim is filed pursuant to the Reference No. ____ dated ____ made under Section 10(1) of the Industrial Disputes Act 1947 by the Government of [State] / the Central Government, in respect of the industrial dispute between the parties named in the Schedule to the said Reference, for adjudication by this Hon'ble Labour Court / Industrial Tribunal."
statutory_opening_post_2a_application: "This Statement of Claim is filed pursuant to the Application No. ____ filed under Section 2A(2) of the Industrial Disputes Act 1947 by the Applicant Workman, admitted by this Hon'ble Labour Court by Order dated ____, for adjudication of the industrial dispute pleaded therein."
ground_clauses:
  - "Workman status (Section 2(s) ID Act) — pleaded with reference to the Applicant's actual duties / KRAs / reporting structure / wages / nature of work, demonstrating workman status irrespective of designation (predominant-duty test per Sonepat Cooperative Sugar Mills v. Ajit Singh (2005) 3 SCC 232)."
  - "Cause of action — full chronological narrative of the workman's engagement, the working relationship, the trigger incident (retrenchment / dismissal / discharge / termination), the conciliation / pre-litigation channel, and the present claim."
  - "Section 25F / 25G / 25N non-compliance (where retrenchment) — itemised non-compliance with statutory pre-conditions (notice / compensation / Government intimation / seniority rule / Section 25N permission for establishments with 100+ / 300+ workmen)."
  - "Domestic inquiry defects (where dismissal on alleged misconduct) — itemised procedural and substantive defects in the domestic inquiry, with reference to Workmen of Firestone Tyre & Rubber (1973) 1 SCC 813 framework."
  - "Section 33 ID Act protected-workman violation — where the Respondent altered service conditions during pendency of conciliation / Reference / Application without obtaining prior permission of the appropriate authority."
  - "Section 11A relief framework — Labour Court / Tribunal's power to set aside dismissal, direct reinstatement, award lesser punishment, and grant such other relief as appropriate."
  - "Back-wages discipline — the Applicant has not been gainfully employed during the period of forced unemployment, the Respondent has acted mala fide, and full back-wages are the appropriate relief (Allahabad Jal Sansthan v. Daya Shankar Rai (2005) 5 SCC 124 + lineage)."
  - "Continuity of service — direction for restoration of continuity of service with consequential benefits including increments, allowances, statutory bonus, EPF / ESI / gratuity contributions for the entire period."
prayer_clauses:
  - "(a) Declare that the action of the Respondent Establishment in [retrenching / dismissing / discharging / terminating] the Applicant Workman is illegal, void, and contrary to law;"
  - "(b) Direct the Respondent Establishment to reinstate the Applicant Workman with continuity of service and full back-wages from the date of impugned action till the date of reinstatement, together with all consequential benefits including increments, allowances, statutory bonus, EPF / ESI / gratuity contributions for the entire intervening period;"
  - "(c) Pass such Award under Section 11A and other applicable provisions of the Industrial Disputes Act 1947 as may, in the discretion of this Hon'ble Labour Court / Industrial Tribunal, be just and proper;"
  - "(d) Award costs of these proceedings to the Applicant Workman / Union."
mandatory_exhibits:
  - reference_order_or_section_2a_admission_order
  - appointment_letter_and_employment_documents
  - salary_slips_and_wage_progression_records
  - kra_documents_and_organisation_chart
  - attendance_records_establishing_continuous_service
  - epf_esi_gratuity_service_records
  - charge_sheet_and_domestic_inquiry_record_where_applicable
  - dismissal_or_retrenchment_or_termination_order
  - conciliation_officer_proceedings_and_failure_report
  - pre_litigation_correspondence
  - any_settlement_or_award_relied_on_by_either_party
accompanying_applications:
  - "I.A. for status-quo / interim direction under Section 33 ID Act 1947 to restrain the Respondent from filling the workman's post during pendency"
  - "I.A. for production of records by the Respondent Establishment — attendance registers, salary registers, EPF / ESI records, Domestic Inquiry record, Standing Orders certified copy"
  - "I.A. for summoning witnesses under the relevant ID Rules"
  - "I.A. for amendment of pleadings (where new facts emerge during the proceedings)"
court_fee: "Per applicable State Industrial Disputes Rules — typically nominal fee."
limitation: "Statement of Claim is to be filed within the timeframe directed by the Labour Court / Industrial Tribunal post-admission of Section 2A application / post-receipt of Reference Order — typically 30 to 45 days."
```

## Section 17 Notification of Award discipline

Once the Labour Court / Industrial Tribunal makes an Award, the Award is published by the appropriate Government in the Official Gazette under Section 17 ID Act and becomes enforceable 30 days after publication. The Drafter notes this discipline in the prayer clauses (where reinstatement is sought, the prayer is for an Award; the Award becomes operative 30 days after Section 17 Notification).

## Section 33C(1) / Section 33C(2) execution

- **Section 33C(1)** — workman entitled to money due under settlement / Award may apply to the appropriate Government for issue of a Certificate of Recovery; the Government recovers the amount as arrears of land revenue.
- **Section 33C(2)** — for computation of money or benefit capable of being computed in terms of money, the Labour Court itself determines the amount due. Useful where the workman's claim post-Award is for back-wages computation, continuity-benefits computation, gratuity computation, etc.

The Drafter notes the execution route for post-Award benefits in the Statement of Claim. Once the Award is implemented (or implementation refused), the workman's recovery proceedings under Section 33C(1) / 33C(2) follow.

## Back-wages framework — *Deepali Gundu Surwase* line

*Deepali Gundu Surwase v. Kranti Junior Adhyapak Mahavidyalaya* (2013) 10 SCC 324 sets out the framework for back-wages — full back-wages is the rule where the workman has been wronged; partial / no back-wages where the workman was gainfully employed during the unemployment period or where the workman was found responsible for delay. The Drafter pleads the workman's non-employment during the intervening period, supported by evidence (e.g. unemployment exchange registration, employment-search records).
