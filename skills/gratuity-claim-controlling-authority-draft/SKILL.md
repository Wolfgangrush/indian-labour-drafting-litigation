---
name: gratuity-claim-controlling-authority-draft
description: Draft an Application before the Controlling Authority appointed under Section 3 of the Payment of Gratuity Act 1972, for direction to the Employer to pay the gratuity legally due to the Applicant Employee. Encodes the Section 2(e) employee definition, the Section 4(1) eligibility (5 years continuous service waivable on death / disablement), the Section 4(2) computation formula, the Section 4(3) statutory ceiling (currently ₹20 lakh), the Section 4(6) deduction-for-misconduct framework, the Section 7(3) payment-within-30-days rule, the Section 7(3A) interest framework, the Rule 10 90-day filing limitation, and the Section 7(7) appeal route to the Appellate Authority. Auto-fires on "draft gratuity claim", "draft Section 7 PG Act application", "draft Controlling Authority gratuity application", "draft gratuity recovery application", and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# Gratuity Claim Controlling-Authority Application Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_labour_drafting_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Case-type metadata

```yaml
case_type_line: APPLICATION BEFORE THE CONTROLLING AUTHORITY UNDER SECTION 7 OF THE PAYMENT OF GRATUITY ACT 1972
case_short_code: GRATUITY_CA
case_number_prefix: PG Case
pleading_type: Application (Form N under Rule 10 PG Central Rules 1972)
typical_forum: Controlling Authority appointed under Section 3 of the Payment of Gratuity Act 1972 (typically the Assistant Labour Commissioner / Joint Labour Commissioner of the applicable area) — territorial jurisdiction per the location of the establishment
typical_parties: Applicant Employee + Respondent Employer / Establishment
statutory_opening: "This Application is filed under Section 7(4) read with Rule 10 of the Payment of Gratuity (Central) Rules 1972, before the Controlling Authority appointed under Section 3 of the Payment of Gratuity Act 1972, for direction to the Respondent Employer to pay the gratuity legally due to the Applicant Employee under Section 4 of the said Act, together with interest under Section 7(3A) and consequential reliefs."
ground_clauses:
  - "Employee status — the Applicant is an 'employee' within the meaning of Section 2(e) of the Payment of Gratuity Act 1972, having been employed by the Respondent Establishment on the terms set out in the Appointment Letter at Exhibit ___."
  - "Continuous service — the Applicant has completed a continuous service of not less than 5 years within the meaning of Sections 2A and 4(1) of the Act (waived in case of death / disablement), as evidenced by the Appointment Letter at Exhibit ___, salary slips at Exhibit ___, attendance records at Exhibit ___, and EPF contribution record at Exhibit ___."
  - "Cessation of service — the Applicant's service was [terminated / superannuated / resigned / discontinued on disablement / discontinued on death] on ____ (refer Termination Order / Resignation Acceptance / Retirement Letter at Exhibit ___)."
  - "Gratuity computation — applying the Section 4(2) formula [15 × last drawn wages × completed years of service / 26], the gratuity legally due is ₹ ___ (computation set out in detail at Annexure ___)."
  - "Statutory ceiling — the computed gratuity is within the Section 4(3) statutory ceiling of ₹20 lakh (per the 2018 amendment)."
  - "Section 7(2) Employer's obligation — the Employer is obligated under Section 7(2) to determine the gratuity due and pay the same to the Applicant within 30 days of the date when the gratuity becomes payable; in the present case the gratuity became payable on ____ and 30 days have elapsed without payment."
  - "Section 7(3A) interest — the Applicant is entitled to simple interest at the rate notified by the Central Government (currently the rate applicable to deposits in nationalised banks for the corresponding period — typically 10% per annum simple) from the date 30 days after cessation till the date of payment."
  - "No Section 4(6) deduction warranted — there has been no [termination for proven gross misconduct involving moral turpitude / damage caused to the Employer's property / unspent advance against gratuity] that would permit deduction from gratuity. The Respondent's reliance on Section 4(6), if any, is denied as factually unfounded and procedurally defective."
  - "Limitation — the present Application is filed within 90 days of the date of cessation of service as required by Rule 10 of the Payment of Gratuity (Central) Rules 1972 / within the extended period granted by this Hon'ble Controlling Authority on sufficient cause."
prayer_clauses:
  - "(a) Direct the Respondent Employer to pay the gratuity of ₹ ___ to the Applicant Employee, being the amount legally due under Section 4 of the Payment of Gratuity Act 1972;"
  - "(b) Direct payment of simple interest at the rate notified under Section 7(3A) PG Act 1972 from the date 30 days after cessation of service till the date of payment;"
  - "(c) Issue a Certificate of Recovery under Section 8 of the Payment of Gratuity Act 1972 for the gratuity amount and interest, recoverable as arrears of land revenue, in the event of non-compliance by the Employer within the time directed;"
  - "(d) Award costs of these proceedings to the Applicant Employee;"
  - "(e) Pass such further and other reliefs as this Hon'ble Controlling Authority may deem fit and proper."
mandatory_exhibits:
  - appointment_letter
  - employment_agreement_where_applicable
  - salary_slips_for_last_12_months_demonstrating_last_drawn_wages
  - attendance_records_demonstrating_continuous_service
  - epf_contribution_record_demonstrating_service_history
  - termination_order_or_resignation_acceptance_or_retirement_letter
  - notice_of_claim_issued_under_section_7_1_pg_act_to_employer
  - employers_reply_or_denial_or_silence_record
  - section_4_2_computation_worksheet
accompanying_applications:
  - "I.A. for condonation of delay (where the 90-day limitation under Rule 10 is exceeded — with Section 5 Limitation Act 1963 grounds)"
  - "I.A. for ex-parte directions where the Employer has been evading service"
  - "I.A. for production of records by the Employer (salary registers, attendance registers, gratuity-payment records)"
court_fee: "Form N application bears nominal fee per the applicable State PG Rules. Some States exempt employees from fee."
limitation: "90 days from the date of cessation of service per Rule 10 of the Payment of Gratuity (Central) Rules 1972, extendable by the Controlling Authority on sufficient cause shown under the proviso to Rule 10. The Supreme Court has held that the Controlling Authority's discretion to condone delay is wide where the Employer's conduct has misled the Employee — see Y.K. Singla v. PNB (2013) 3 SCC 472 and lineage."
```

## Section 7(2) Employer's determination obligation

Section 7(2) PG Act imposes a positive obligation on the Employer to determine the gratuity due and to send notice in writing to the employee and to the Controlling Authority. Section 7(3) requires payment within 30 days of the date when the gratuity becomes payable. Failure of the Employer to act under Section 7(2) and (3) is itself a ground for the Employee's Section 7(4) application, independent of any further dispute.

## Section 7(7) appeal route

An aggrieved party may file an appeal to the Appellate Authority under Section 7(7) PG Act within 60 days of receipt of the Controlling Authority's order. The Appellate Authority is typically the Joint Labour Commissioner / Deputy Labour Commissioner of the State (designated by State notification).

## Section 4(6) deduction discipline

Section 4(6) permits the Employer to deduct from gratuity (a) to the extent of damage / loss caused to the Employer's property by the wilful misconduct or negligent act / omission of the employee; (b) wholly / partially where the services of the employee have been terminated for riotous / disorderly conduct / any other act of violence on his / her part; (c) wholly / partially where the services have been terminated for any act constituting an offence involving moral turpitude. The Employer must follow due process — show-cause + opportunity + reasoned order. Bare invocation of Section 4(6) without due process is invalid (*P. Lakshmi Devi v. State of Andhra Pradesh* and the lineage on Section 4(6) procedural fairness).

## Section 14 PG Act override of other inconsistent law

The provisions of the PG Act 1972 override any agreement / contract / Standing Order to the contrary that is less favourable to the employee. Settlements / contracts purporting to deny the employee the statutory gratuity or to compute the gratuity below the Section 4(2) formula are void to that extent. The Drafter pleads Section 14 expressly where the Employer relies on a contrary contract.
