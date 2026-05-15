---
name: industrial-employment-standing-orders-certification-draft
description: Draft Standing Orders for certification under Section 3 of the Industrial Employment (Standing Orders) Act 1946 read with the Industrial Employment (Standing Orders) Central Rules 1946 (or the applicable State Rules), to be filed by the Establishment before the Certifying Officer. Encodes the Schedule subjects discipline (every Standing Order must cover the matters in the Schedule — classification of workmen / shift working / attendance and late coming / leave / holidays / termination of employment / suspension or dismissal for misconduct / means of redress for workmen / etc.), the Section 4 conditions for certification (Standing Orders must provide for every matter set out in the Schedule + must be fair and reasonable + must conform to model Standing Orders so far as practicable), the Section 5 certification procedure (forwarding to workmen / trade union, hearing, modification, certification), the Section 10 modification procedure, and the model Standing Orders under the Schedule to the Industrial Employment (Standing Orders) Central Rules 1946 as a baseline. Auto-fires on "draft Standing Orders", "draft IESO Act Standing Orders", "draft Standing Orders certification", and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# Industrial Employment (Standing Orders) Act Certification Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_labour_drafting_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Case-type metadata

```yaml
case_type_line: DRAFT STANDING ORDERS FOR CERTIFICATION UNDER SECTION 3 OF THE INDUSTRIAL EMPLOYMENT (STANDING ORDERS) ACT 1946
case_short_code: IESO_CERTIFICATION
case_number_prefix: IESO Certification
pleading_type: Draft Standing Orders + Application for Certification
typical_forum: Certifying Officer appointed under Section 3 of the Industrial Employment (Standing Orders) Act 1946 — typically the Assistant Labour Commissioner / Regional Labour Commissioner of the area
typical_parties: Submitting Establishment / Employer + Trade Union(s) / Workmen Representatives (heard by the Certifying Officer under Section 5)
statutory_opening: "These Draft Standing Orders are submitted under Section 3 of the Industrial Employment (Standing Orders) Act 1946 read with the Industrial Employment (Standing Orders) Central Rules 1946 / applicable State Industrial Employment (Standing Orders) Rules, by the Submitting Establishment, for certification under Section 5 of the said Act by the Certifying Officer."
schedule_matters_to_be_covered:
  - "(1) Classification of workmen — permanent / temporary / apprentices / probationers / badlis / contract / casual"
  - "(2) Manner of intimating to workmen the periods and hours of work, holidays, pay-days and wage rates"
  - "(3) Shift working"
  - "(4) Attendance and late coming"
  - "(5) Conditions of, procedure in applying for, and the authority which may grant leave and holidays"
  - "(6) Requirement to enter premises by certain gates, and liability to search"
  - "(7) Closing and re-opening of sections of the establishment, and temporary stoppages of work, and the rights and liabilities of the employer and workmen arising therefrom"
  - "(8) Termination of employment, and the notice thereof to be given by employer and workmen"
  - "(9) Suspension or dismissal for misconduct, and acts or omissions which constitute misconduct"
  - "(10) Means of redress for workmen against unfair treatment or wrongful exactions by the employer or his agents or servants"
  - "(11) Any other matter which may be prescribed (e.g. Service rules; Confidentiality; IP assignment; Anti-bribery and conflict-of-interest; POSH-internal-committee mention)"
draft_skeleton:
  - "Cover Page — Standing Orders of [Submitting Establishment] for certification under the Industrial Employment (Standing Orders) Act 1946"
  - "Article 1 — Short title, applicability, definitions"
  - "Article 2 — Classification of workmen (permanent / probationary / temporary / apprentice / casual / badli / contract)"
  - "Article 3 — Intimation of working hours, holidays, pay-days, wage rates"
  - "Article 4 — Shift working arrangements"
  - "Article 5 — Attendance, late coming, half-days, absent-without-leave consequences"
  - "Article 6 — Leave — earned leave / casual leave / sick leave / maternity leave / paternity leave (where applicable) / festival holidays / national holidays — eligibility, accrual, encashment, lapsing, application procedure, authority granting"
  - "Article 7 — Gate-pass, identity card, premises-entry, search of person and belongings"
  - "Article 8 — Closure and re-opening of sections, lay-off (subject to ID Act Sections 25C-25E discipline), temporary stoppages, force-majeure"
  - "Article 9 — Termination of employment — notice period, notice-pay-in-lieu, retirement age, resignation, retrenchment (subject to Sections 25F / 25G / 25N ID Act), discharge, dismissal"
  - "Article 10 — Misconduct — itemised list of acts / omissions constituting misconduct (theft / fraud / dishonesty / wilful disobedience / habitual late coming / absence without leave / habitual breach of standing orders / bribery / corruption / acceptance of gifts from suppliers / commercial mis-statement / sexual harassment at workplace under Section 2(n) POSH Act 2013 / breach of confidentiality / unauthorised IP transfer / drunkenness during duty / striking work in breach of Section 22 / 23 ID Act / use of violence / theft of company property / unauthorised possession of company property / negligence causing damage)"
  - "Article 11 — Disciplinary procedure — show-cause notice / suspension pending inquiry / charge-sheet / inquiry officer / domestic inquiry / opportunity to cross-examine / opportunity to defence-witness / inquiry report / show-cause on quantum of punishment / final order / right of appeal"
  - "Article 12 — Means of redress — grievance officer / grievance committee / appeal to higher authority within the establishment / referral to conciliation officer / referral to Labour Court / Industrial Tribunal"
  - "Article 13 — POSH compliance — Internal Committee under Section 4 POSH Act 2013 / complaint procedure / Section 16 confidentiality / consequences for Respondent on proven complaint"
  - "Article 14 — IP assignment and confidentiality (where applicable to the establishment's industry)"
  - "Article 15 — Anti-bribery and conflict-of-interest"
  - "Article 16 — Service Rules consistency / governance over any prior rules / amendment procedure"
  - "Schedule — Definitions, Forms, Annexures"
ground_clauses_for_certification_application:
  - "Applicability — the Submitting Establishment is an 'industrial establishment' within the meaning of Section 2(e) IESO Act 1946 read with Section 2(ii) Payment of Wages Act 1936 / applicable State definition, and employs not less than 100 workmen (50 workmen in some States by State amendment) within the meaning of Section 1(3) IESO Act 1946."
  - "Conformity with Model Standing Orders — the Draft Standing Orders herein conform to the Model Standing Orders in the Schedule to the Industrial Employment (Standing Orders) Central Rules 1946 / applicable State Rules, so far as practicable, as required by Section 4."
  - "Coverage of Schedule matters — the Draft Standing Orders provide for every matter set out in the Schedule to the IESO Act 1946 (items 1 to 11)."
  - "Fairness and reasonableness — the Draft Standing Orders are fair and reasonable and do not curtail any statutory protection of workmen below the statutory minimum (in particular: Section 25F / 25G / 25N ID Act on retrenchment; Sections 17 — 18 EPF Act on contribution withholding; Sections 4 / 7(2) PG Act on gratuity; Section 13 POSH Act on inquiry; Sections 79 — 82 ID Act on holidays-with-wages where relevant)."
prayer_clauses:
  - "(a) Forward a copy of the Draft Standing Orders to the workmen / trade union(s) as required by Section 5(1) IESO Act 1946;"
  - "(b) Provide opportunity to the workmen / trade union(s) to raise objections / suggestions within 15 days under Section 5(1);"
  - "(c) After hearing the parties and modifying the Standing Orders as may be required, certify the Standing Orders under Section 5(2) IESO Act 1946;"
  - "(d) Issue authenticated copies of the certified Standing Orders to the Submitting Establishment and to the workmen / trade union(s)."
mandatory_exhibits:
  - certificate_of_registration_under_state_shops_and_establishments_act_or_factories_act_licence
  - latest_audited_financial_statements_evidencing_workmen_employed_above_threshold
  - existing_service_rules_or_employment_handbook_being_modified
  - copies_of_trade_union_registration_certificates_under_trade_unions_act_1926_where_relevant
  - statement_of_workmen_categories_and_strength_at_the_establishment
  - model_standing_orders_under_the_schedule_to_the_central_rules_1946_or_state_rules_for_certifying_officer_reference
no_certification_fee: "Per applicable State Rules — typically nominal."
limitation: "Within 6 months from the date the Act becomes applicable to the establishment (Section 3(1) IESO Act 1946). Modifications under Section 10 may be submitted thereafter at any time, with workmen / trade union notice and certifying officer process."
```

## Schedule subjects discipline

Section 4 IESO Act 1946 read with the Schedule mandates that Standing Orders must provide for every matter set out in the Schedule. Omission of any item is a ground for the Certifying Officer to refuse certification or to direct modification. The Drafter ensures that each of the 11 items in the Schedule is addressed (items 1 to 11 above).

## Model Standing Orders baseline

The Model Standing Orders in the Schedule to the Industrial Employment (Standing Orders) Central Rules 1946 (and the applicable State Rules) set the baseline. Section 4(b) requires that the Standing Orders, "so far as is practicable", conform to the Model Standing Orders. Material deviations require justification before the Certifying Officer.

## Certification procedure under Section 5

- The Employer submits 5 copies of the Draft Standing Orders to the Certifying Officer along with a statement of workmen-particulars and trade-union particulars (Section 3(2))
- The Certifying Officer forwards a copy to the workmen / trade union(s) and provides 15 days for objections (Section 5(1))
- The Certifying Officer hears the parties and certifies the Standing Orders with such modifications as he / she considers necessary to render them fair and reasonable (Section 5(2))
- Certified Standing Orders become operative on the date of certification + 30 days
- Workmen / Employer aggrieved by the Certifying Officer's decision may appeal to the Appellate Authority under Section 6 within 30 days

## Section 10 modification procedure

Either the Employer or the workmen / trade union may submit modifications to the certified Standing Orders under Section 10 — with notice + hearing + Certifying Officer process — at any time after the initial certification.

## Maharashtra-specific MRTU & PULP Act overlay

In Maharashtra, the Maharashtra Recognition of Trade Unions and Prevention of Unfair Labour Practices Act 1971 adds an additional discipline — the recognised union (if any) has standing to participate in the Section 5 hearing, and any victimisation of the recognised union's representative during the certification proceedings is itself an unfair labour practice complaint before the Industrial Court.

## Post-amendment Industrial Relations Code 2020 status

The Industrial Relations Code 2020, Chapter VIII (Sections 28-39) — when notified for the relevant State — will subsume the IESO Act 1946 framework. As of 2026, the Code is partially notified. The Drafter checks the Code's notification status under `case-config.md` and applies the operative statute (legacy IESO Act 1946 or IR Code 2020) accordingly.
