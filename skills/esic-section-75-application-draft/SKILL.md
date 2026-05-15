---
name: esic-section-75-application-draft
description: Draft an Application before the Employees' Insurance Court under Section 75 of the Employees' State Insurance Act 1948, for adjudication of disputes between an insured person / employer / dependent / ESI Corporation relating to contributions, benefits, coverage, rate, period, or quantum. Encodes the Section 75 enumeration of disputes within the EI Court's jurisdiction, the Section 76 cause-of-action framework, the Section 77 limitation (3 years from cause of action, extendable on sufficient cause), the Section 80 60-day notice before instituting against ESIC, and the Section 82 appeal route to the High Court on substantial questions of law. Auto-fires on "draft ESI Court application", "draft Section 75 ESI Act application", "challenge ESI determination", "ESI contribution dispute", and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# ESI Section 75 Application Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_labour_drafting_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Case-type metadata

```yaml
case_type_line: APPLICATION UNDER SECTION 75 OF THE EMPLOYEES' STATE INSURANCE ACT 1948 BEFORE THE EMPLOYEES' INSURANCE COURT
case_short_code: ESI_S75
case_number_prefix: ESI Case
pleading_type: Application before the Employees' Insurance Court
typical_forum: Employees' Insurance Court constituted under Section 74 ESI Act 1948 (typically the District Court of the area / a Court designated by the State Government) — territorial jurisdiction per Section 75(2) (where the cause of action arises / where the applicant resides / where the establishment is situated)
typical_parties: Applicant (Insured Person / Employer / Dependent of deceased insured person / Principal Employer) + Respondent (Employees' State Insurance Corporation / its Regional Director / Branch Office Manager)
statutory_opening: "This Application is filed under Section 75 of the Employees' State Insurance Act 1948, before this Hon'ble Employees' Insurance Court, for adjudication of the dispute between the Applicant and the Employees' State Insurance Corporation in respect of [contribution / benefit / coverage / rate / period / quantum] for the period ____ to ____."
ground_clauses_by_dispute_type:
  - "Coverage dispute (Section 75(1)(a)) — the Applicant Establishment is / is not an 'establishment' to which the Act applies under Section 1(4) read with notified industries. The ESI Corporation's coverage determination [erroneously / correctly] includes / excludes the Applicant for the period ____."
  - "Wages dispute (Section 75(1)(b)) — the wages payable to the insured person have been [over-/under-] computed by the ESI Corporation for the purposes of contribution / benefit, contrary to the Section 2(22) wages definition. The correct wage particulars are at Annexure ____."
  - "Rate / period of contribution (Section 75(1)(c) / (cc)) — the rate / period of contribution applied by the ESI Corporation for the Applicant Employer is contrary to Section 39 and the applicable notification."
  - "Coverage of insured person (Section 75(1)(d)) — the Applicant is / is not an 'employee' within the meaning of Section 2(9) ESI Act 1948, with the wages within / above the threshold."
  - "Benefit dispute (Section 75(1)(e) / (f) / (g) / (h)) — the Applicant is entitled to [sickness benefit / maternity benefit / disablement benefit / dependant's benefit / medical benefit / funeral expenses] under Sections 46 to 56 ESI Act 1948, which the ESI Corporation has [denied / reduced / discontinued]."
  - "Recovery dispute (Section 75(2)(a) / (b)) — the recovery proceedings initiated by the Corporation under Section 45A / 45B / Sections 45D to 45-I against the Applicant Employer are challenged on grounds particularised at Annexure ____."
ground_clauses_procedural:
  - "Limitation under Section 77 ESI Act — the present Application is filed within three years from the date on which the cause of action arose (cause of action arose on ____; date of filing ____; days within limitation: ___). Delay, if any, condoned under the proviso to Section 77(1A) on sufficient cause."
  - "Section 80 notice — the Applicant has issued the 60-day notice under Section 80 ESI Act dated ____ to the Director-General of the ESI Corporation, copy at Exhibit ___, evidencing pre-litigation compliance."
prayer_clauses:
  - "(a) Declare that the impugned [coverage determination / contribution levy / benefit denial / recovery action] of the Respondent ESI Corporation is contrary to the provisions of the ESI Act 1948 and the Regulations made thereunder;"
  - "(b) Set aside the impugned action / order and direct the Respondent to act in accordance with law;"
  - "(c) Direct the Respondent to [refund the contributions / grant the benefit / withdraw the recovery / classify the Applicant correctly] as the case may be;"
  - "(d) Where benefit is claimed: direct the Respondent to pay the benefit due from the date of entitlement together with interest at the rate notified;"
  - "(e) Award costs of these proceedings."
mandatory_exhibits:
  - certified_copy_of_the_impugned_esic_order_or_determination_or_denial
  - esic_show_cause_notice_received_by_the_applicant_and_applicants_reply
  - employment_record_or_insured_person_documents_under_section_2_9
  - wage_records_for_the_period_in_dispute
  - section_80_notice_issued_by_the_applicant_to_the_esic_director_general
  - any_medical_records_or_certificates_supporting_benefit_claim
  - any_correspondence_with_esic_branch_office_or_regional_office
  - certified_copy_of_the_relevant_esic_notification_or_regulation
accompanying_applications:
  - "I.A. for ad-interim direction for grant of benefit pending adjudication (where livelihood / medical need is immediate)"
  - "I.A. for stay of recovery proceedings under Section 45A / 45B / 45D — 45-I against the Employer"
  - "I.A. for condonation of delay under the proviso to Section 77(1A)"
  - "I.A. for production of records by the ESIC (contribution registers / wage abstracts / medical records / benefit-disbursement records)"
court_fee: "Per applicable State ESI Court Rules — typically nominal fee."
limitation: "Three years from the date on which the cause of action arose — Section 77 ESI Act 1948. The proviso to Section 77(1A) permits the EI Court to extend the period on sufficient cause shown. Section 80 60-day notice before instituting against ESIC is a procedural pre-condition where the action is against the Corporation."
```

## Section 75 enumeration of disputes within the EI Court's jurisdiction

Section 75(1) enumerates the matters within the EI Court's jurisdiction:

- (a) whether any person is an employee within the meaning of the Act
- (b) the rate of wages or average daily wages of an employee
- (c) the rate of contribution payable by a principal employer
- (cc) the person who is or was the principal employer
- (d) the right of any person to any benefit and the amount and duration thereof
- (e) the recovery of contributions from the principal employer
- (f) any direction issued by the Corporation under Section 75(2) or any decision of the Corporation
- (g) any matter arising out of the action of the Corporation

Section 75(3) bars the civil court's jurisdiction in matters falling within Section 75(1).

## Section 82 appeal to the High Court

An appeal lies to the High Court from an order of the EI Court on a substantial question of law under Section 82 ESI Act 1948. The appeal must be filed within 60 days of the EI Court's order. The High Court will not re-appreciate facts; the appeal is limited to questions of law.

## *Goetze (India) Ltd. v. ESIC* coverage discipline

*Goetze (India) Ltd. v. ESIC* (1998) and the lineage of Supreme Court precedent set out the framework for "establishment" coverage — including the question whether the establishment is "engaged in" an industry notified under Section 1(5) or governed by a statutory exemption. The Drafter applies the coverage discipline at the threshold of any coverage-dispute case.

## Section 45A determination + Section 45-I recovery — challenge route

Where the Corporation has passed a Section 45A determination order and is proceeding to recover under Sections 45-D to 45-I, the Employer's challenge must be staged in the EI Court under Section 75 within the Section 77 limitation. A writ petition before the High Court under Article 226 is ordinarily declined on the ground of the alternative remedy under Section 75 (*Mafatlal Industries v. ESIC* and related precedent on alternative-remedy doctrine in ESI matters).

## Post-amendment Social Security Code 2020 status

The Code on Social Security 2020 — when notified for the relevant State / industry — will subsume the ESI Act 1948 framework. As of 2026, the Code is partially notified. The Drafter checks the Code's notification status under `case-config.md` and applies the operative statute (legacy ESI Act 1948 or Code on Social Security 2020) accordingly.
