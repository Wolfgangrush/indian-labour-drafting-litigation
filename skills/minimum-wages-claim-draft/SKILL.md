---
name: minimum-wages-claim-draft
description: Draft an Application before the Authority appointed under Section 20 of the Minimum Wages Act 1948, for direction to the Employer to pay the difference between the minimum wages prescribed by the appropriate Government notification and the wages actually paid to the Applicant Employee, together with compensation up to ten times the difference. Encodes the Section 3 minimum-rate-of-wages notification framework, the Section 14 overtime framework, the Section 18 wage-register-and-pay-slip discipline, the Section 20(2) 12-month limitation (extendable on sufficient cause), the Section 20(3)(i) compensation framework, the Section 22A bar on civil court jurisdiction, and the Section 21 (single-application-by-class-of-employees) framework for collective claims. Auto-fires on "draft minimum wages claim", "draft Section 20 MW Act application", "draft MW Authority application", and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# Minimum Wages Section 20 Claim Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_labour_drafting_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Case-type metadata

```yaml
case_type_line: APPLICATION UNDER SECTION 20(2) OF THE MINIMUM WAGES ACT 1948 BEFORE THE AUTHORITY APPOINTED UNDER SECTION 20(1)
case_short_code: MW_S20
case_number_prefix: MW Case
pleading_type: Application
typical_forum: Authority appointed by the appropriate Government under Section 20(1) MW Act — typically the Labour Commissioner / Assistant Labour Commissioner of the area where the establishment is located
typical_parties: Applicant Employee (or, under Section 21, single application by a class of employees) + Respondent Employer / Establishment
statutory_opening: "This Application is filed under Section 20(2) of the Minimum Wages Act 1948 read with Rule 21 of the applicable Minimum Wages Rules, before the Authority appointed under Section 20(1) of the said Act, for direction to the Respondent Employer to pay the difference between the minimum wages payable to the Applicant Employee under the [scheduled employment] notification dated ____ and the wages actually paid, together with compensation as may be directed by this Hon'ble Authority under Section 20(3) of the said Act."
ground_clauses:
  - "Scheduled employment — the Applicant is employed by the Respondent in [Scheduled Employment name] under the Schedule to the Minimum Wages Act 1948 / under the State Schedule notified under Section 3 / Section 27, evidence whereof is at Exhibit ___ (Appointment Letter), Exhibit ___ (Salary Slips), Exhibit ___ (Job Description)."
  - "Applicable minimum wage — the minimum rate of wages fixed by the appropriate Government for the scheduled employment, by Notification dated ____ at Exhibit ___, is ₹ ___ per day / per month, with variable Dearness Allowance of ₹ ___."
  - "Wages actually paid — the Respondent has paid the Applicant Employee wages at the rate of ₹ ___ per day / per month for the period ____ to ____, as evidenced by salary slips at Exhibit ___ and wage register at Exhibit ___."
  - "Computation of difference — the difference between the minimum wage payable and the wage actually paid, for the period ____ to ____, aggregates ₹ ___ (detailed computation at Annexure ____)."
  - "Overtime under-payment (where applicable) — the Respondent has failed to pay overtime at twice the ordinary wage for hours worked beyond the Schedule limits (8 hours daily / 48 hours weekly under most State schedules), as evidenced by attendance / clock-in records at Exhibit ___."
  - "Wage-register and pay-slip non-compliance (where applicable) — the Respondent has failed to maintain the wage register / pay-slips in the prescribed forms under Section 18 read with the applicable State Rules."
  - "Limitation — the present Application is filed within 12 months from the date when the wages became payable, as required by Section 20(2). [Where exceeded:] delay, if any, condoned under the proviso to Section 20(2) on sufficient cause as set out at Annexure ____."
  - "Section 22A bar on civil court jurisdiction — the present claim falls within the exclusive jurisdiction of this Hon'ble Authority under Section 20; the civil court's jurisdiction is barred."
prayer_clauses:
  - "(a) Direct the Respondent Employer to pay the Applicant Employee the difference of wages of ₹ ___ for the period ____ to ____, being the difference between the minimum wages payable under the [scheduled employment notification] and the wages actually paid;"
  - "(b) Direct payment of compensation under Section 20(3)(i) of the Minimum Wages Act 1948 up to ten times the amount of difference computed above, as this Hon'ble Authority may deem fit;"
  - "(c) Where overtime under-payment is alleged: direct payment of overtime arrears of ₹ ___ at twice the ordinary wage rate for the period ____ to ____ with compensation;"
  - "(d) Issue directions under the applicable State Rules for due compliance with Section 18 wage-register and pay-slip discipline going forward;"
  - "(e) Award costs of these proceedings to the Applicant Employee."
mandatory_exhibits:
  - appointment_letter_establishing_employment_in_scheduled_employment
  - copy_of_the_applicable_minimum_wages_notification_for_the_relevant_period
  - salary_slips_for_the_period_in_dispute
  - wage_register_extract_where_available
  - attendance_or_clock_in_records_evidencing_actual_hours_worked
  - any_pre_litigation_demand_or_notice_issued_to_employer
  - employers_reply_or_denial_or_silence_record
  - computation_worksheet_showing_difference_and_overtime_arrears
accompanying_applications:
  - "I.A. for production of records by the Employer (wage register / muster roll / overtime register)"
  - "I.A. for joint application by class of employees under Section 21 (where applicable)"
  - "I.A. for condonation of delay under the proviso to Section 20(2)"
  - "I.A. for ex-parte interim direction restraining the Employer from dismissing / victimising the Applicant during pendency of the proceedings"
court_fee: "Form L application bears nominal fee per the applicable State Minimum Wages Rules. Most State Rules exempt employees from fee."
limitation: "12 months from the date on which the wages became payable — Section 20(2) MW Act 1948. The proviso to Section 20(2) permits the Authority to admit the application after the expiry of the said period on sufficient cause shown."
```

## Section 21 collective claim

Under Section 21 MW Act 1948, a single application may be filed in respect of a class / group of employees similarly situated. The Drafter prepares a single application with a Schedule listing each employee, the period claimed, the wages paid, and the wages payable. The Authority may, on adjudication, pass a consolidated order.

## Section 20(3)(i) compensation — 10x rule

The Authority is empowered to direct payment of compensation up to ten times the difference (in the case of payment of less than the minimum wages) or compensation up to ten rupees (in the case of payment of wages outside Section 5 schedule). The compensation is in addition to the direction for payment of the wage difference itself. The Drafter pleads the maximum compensation in the prayer, leaving the Authority's discretion to scale.

## Bar on civil court jurisdiction — Section 22A

Section 22A bars the civil court's jurisdiction in matters falling within Section 20. The employee's remedy is exclusively the Section 20 application. *Hindustan Sugar Mills v. State of Uttar Pradesh* and the lineage of Supreme Court precedent confirm the exclusivity of the Authority's jurisdiction.

## *People's Union for Democratic Rights v. Union of India* discipline

*People's Union for Democratic Rights v. Union of India* (1982) 3 SCC 235 holds that payment of less than minimum wages constitutes "forced labour" within Article 23 of the Constitution. The Drafter pleads this constitutional dimension where the Employer is a public-sector / Government / municipal authority, to invoke the higher writ-jurisdiction route in tandem with the Section 20 application (without overlapping the relief).

## Post-amendment Code on Wages 2019 status

The Code on Wages 2019 — when notified for the relevant State — will subsume the Minimum Wages Act 1948 framework. As of 2026, the Code is partially notified. The Drafter checks the Code's notification status under `case-config.md` and applies the operative statute (legacy MW Act 1948 or Code on Wages 2019) accordingly.
