---
name: shops-establishments-show-cause-reply-draft
description: Draft a Reply to a Show-Cause Notice issued by the Inspector / Chief Inspector under the applicable State Shops and Establishments Act, on behalf of the Establishment / Occupier / Employer. The State-applicable Act (Maharashtra 2017 / Karnataka 1961 / Tamil Nadu 1947 / Delhi 1954 / Uttar Pradesh 1962 / Gujarat 2019 / West Bengal 1963 / Telangana 1988 / Andhra Pradesh 1988 / Kerala 1960 / Rajasthan 1958 / Madhya Pradesh 1958 / Odisha 1956 / Punjab 1958 / Haryana 1958 / Bihar 1953 — and the corresponding Rules) is supplied by the user via case-config.md, and the Format agent loads the appropriate State exemplar from state-config/exemplars/. Common contraventions: registration failure / non-display of registration certificate / working-hours violation / weekly-holiday violation / leave-with-wages violation / overtime violation / women working hours violation / annual return / employee-register failure. Auto-fires on "draft shops establishments reply", "draft show cause reply labour department", "draft shops establishments show cause", and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# State Shops and Establishments Show-Cause Reply Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_labour_drafting_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`
State exemplar: `${CLAUDE_PLUGIN_ROOT}/state-config/exemplars/<state>.md`

## Case-type metadata

```yaml
case_type_line: REPLY TO SHOW-CAUSE NOTICE UNDER THE [STATE] SHOPS AND ESTABLISHMENTS ACT
case_short_code: SHOPS_REPLY
case_number_prefix: SE-SCN Reply
pleading_type: Reply to Show-Cause Notice
typical_forum: Inspector / Chief Inspector under the applicable State Shops and Establishments Act — territorial jurisdiction per the State's notified Inspector circles
typical_parties: Issuing Inspector (Show-Cause Notice originator) + Respondent Establishment / Occupier / Employer
statutory_opening: "This Reply is filed on behalf of the Respondent Establishment in reply to the Show-Cause Notice dated ____ bearing reference No. ____, issued under Section ___ of the [State] Shops and Establishments Act read with Rule ____ of the [State] Shops and Establishments Rules. The contents of the Show-Cause Notice are denied as set out below, save and except those expressly admitted."
common_contraventions_addressed:
  - "Registration failure — alleged non-registration under Section ___ of the applicable State Act within the prescribed period from commencement of business / occupation of premises"
  - "Non-display of registration certificate — alleged failure to display the registration certificate in a conspicuous place at the establishment"
  - "Working-hours violation — alleged breach of daily / weekly working-hour limits prescribed by the applicable State Act"
  - "Weekly holiday violation — alleged failure to grant the prescribed weekly holiday(s) to employees"
  - "Leave-with-wages violation — alleged failure to grant earned leave / casual leave / sick leave per the applicable State schedule"
  - "Overtime violation — alleged failure to pay overtime at the prescribed rate (typically twice the ordinary wage) for hours beyond statutory daily / weekly limits"
  - "Women working-hours violation — alleged employment of women employees during prohibited night hours or non-provision of statutory safety measures during permitted night work"
  - "Annual return failure — alleged failure to file the annual return in the prescribed form by the prescribed date"
  - "Employee-register failure — alleged failure to maintain the muster roll / wage register / leave register / overtime register / fines register in the prescribed forms"
  - "Trade Licence / Labour Welfare Fund / Profession Tax compliance — alleged related non-compliance under cognate State laws"
ground_clauses:
  - "Denial of contravention — the Respondent denies each alleged contravention, save and except those expressly admitted with explanation."
  - "Substantive compliance — the Respondent has substantively complied with the requirements of the applicable State Act, with documentary proof annexed (registration certificate at Exhibit ___; employee registers at Exhibit ___; weekly-holiday roster at Exhibit ___; overtime payments record at Exhibit ___; annual return acknowledgement at Exhibit ___)."
  - "Procedural defects in the Show-Cause Notice (where applicable) — the Show-Cause Notice (a) does not particularise the alleged contravention; (b) does not cite the specific Section and Rule alleged to have been violated; (c) does not afford a reasonable opportunity for response within the meaning of natural justice; (d) is issued by an Inspector outside the territorial jurisdiction; (e) is barred by limitation under the applicable State Act."
  - "Mitigating circumstances (where contravention partially admitted) — where the contravention is partially admitted, the Respondent pleads (a) inadvertence / first-time non-compliance / no mala fide intent; (b) corrective steps already taken; (c) no resulting harm to employees; (d) cooperation with the Inspector during inspection."
  - "Constitutional and Limitation safeguards — Article 14 / Article 19 protection against arbitrary action; limitation under the applicable State Act for prosecution / penalty action."
prayer_clauses:
  - "(a) Drop the proceedings initiated by the Show-Cause Notice as the alleged contraventions are not made out / are denied;"
  - "(b) In the alternative, where any contravention is partially admitted, impose only the minimum penalty / a nominal penalty considering the mitigating circumstances pleaded above;"
  - "(c) Provide a personal hearing to the authorised representative of the Respondent Establishment before passing any adverse order;"
  - "(d) Pass such further and other orders as may be just and proper in the circumstances of the case."
mandatory_exhibits:
  - copy_of_the_show_cause_notice_received
  - registration_certificate_under_the_applicable_state_shops_and_establishments_act
  - employee_registers_muster_roll_wage_register_leave_register
  - weekly_holiday_roster_and_actual_holiday_compliance_records
  - overtime_payments_record
  - latest_annual_return_acknowledgement
  - any_inspector_inspection_report_or_findings_referenced_in_the_show_cause_notice
  - applicable_state_shops_and_establishments_act_certified_copy
  - applicable_state_shops_and_establishments_rules_certified_copy
no_fee: "No fee for filing a Reply to a Show-Cause Notice."
limitation: "Within the period specified in the Show-Cause Notice — typically 15 to 30 days from receipt, depending on the applicable State Act. Extension may be sought by written application before expiry."
```

## State-specific overlays

The Drafter / Format agent loads the relevant State exemplar from `${CLAUDE_PLUGIN_ROOT}/state-config/exemplars/<state>.md` to substitute:

- The full name of the applicable State Shops and Establishments Act
- The Section numbers corresponding to the alleged contravention
- The Rule numbers under the State Rules
- The penalty provisions (fines, additional fines for continuing contravention)
- The Inspector / Chief Inspector / Deputy Chief Inspector designations specific to the State
- The applicable State Labour Welfare Fund Act linkages (where relevant)
- The applicable State Profession Tax linkages (where relevant)

## Maharashtra overlay (2017 Act)

Under the Maharashtra Shops and Establishments (Regulation of Employment and Conditions of Service) Act 2017, the threshold for applicability is 10 or more workers. Registration is under Section 6. Penalties for contraventions are under Section 26. The Maharashtra Labour Welfare Fund Act 1953 attaches as a cognate compliance — separate biannual contributions of ₹ ___ per employee are payable.

## Karnataka overlay (1961 Act)

Under the Karnataka Shops and Commercial Establishments Act 1961, applicability extends to all shops and commercial establishments in notified areas. Registration is under Section 4. Penalty for contraventions is under Section 30. The Karnataka Labour Welfare Fund Act 1965 attaches as a cognate compliance — biannual contributions are payable.

(Tamil Nadu / Delhi / Gujarat / West Bengal / Telangana / Andhra Pradesh / Kerala / Rajasthan / Madhya Pradesh / Odisha / Punjab / Haryana / UP / Bihar overlays specified in the respective state-config exemplar files.)

## Prosecution / penalty discipline

Where the Inspector proceeds beyond the show-cause stage and institutes prosecution under the penal provisions of the applicable State Act, the matter shifts from the Inspector's office to the Magistrate's Court. The applicable forum then becomes the Magistrate Court of competent jurisdiction, and the procedure follows BNSS 2023 (formerly CrPC 1973). The Drafter prepares a separate Reply / preliminary objection at that stage if so required.
