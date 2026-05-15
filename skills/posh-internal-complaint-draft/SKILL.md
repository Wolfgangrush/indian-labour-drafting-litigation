---
name: posh-internal-complaint-draft
description: Draft a Written Complaint under Section 9 of the Sexual Harassment of Women at Workplace (Prevention, Prohibition and Redressal) Act 2013, filed by an aggrieved woman before the Internal Committee constituted under Section 4 of the said Act. Encodes the Section 2(a) aggrieved-woman status, the Section 2(o) workplace nexus, the Section 2(n) acts-of-sexual-harassment ingredients, the Section 9(1) three-month limitation with the three-month-extension proviso, the Section 11 inquiry-procedure framework, the Section 12 interim-relief framework (transfer / leave / protective measure), the Section 13 inquiry-report-and-action framework, the Section 15 compensation framework, and the Section 16 confidentiality discipline that governs every aspect of the draft. Auto-fires on "draft POSH complaint", "draft sexual harassment workplace complaint", "draft Internal Committee complaint", and similar trigger phrases. POSH discipline is strictest in this plugin — the Reader applies stricter placeholder substitution, the Drafter restrains incident-detail paraphrasing, the Refiner strips metadata and applies a Section 16 confidentiality header on every page.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# POSH Section 9 Internal Complaint Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_labour_drafting_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Section 16 confidentiality preamble

This Skill operates under the statutory confidentiality discipline of Section 16 POSH Act 2013. The Drafter does not record or paraphrase identifying details about the Complainant, the Respondent, the witnesses, the Internal Committee members, or the workplace beyond what is strictly necessary to plead the Section 2(a), Section 2(n), Section 2(o), and Section 9 ingredients. Real-value re-substitution is local-only, on the Complainant's machine. The final draft carries a Section 16 confidentiality header on every page. Metadata is stripped from the docx file (author / last-saved-by / company / revision-history).

## Case-type metadata

```yaml
case_type_line: WRITTEN COMPLAINT UNDER SECTION 9 OF THE SEXUAL HARASSMENT OF WOMEN AT WORKPLACE (PREVENTION, PROHIBITION AND REDRESSAL) ACT 2013
case_short_code: POSH_S9_COMPLAINT
case_number_prefix: IC No. (assigned by Internal Committee)
pleading_type: Written Complaint to Internal Committee
typical_forum: Internal Committee constituted under Section 4 POSH Act 2013, of the workplace within the meaning of Section 2(o)
typical_parties: Complainant (aggrieved woman within Section 2(a)) + Respondent (person against whom the complaint is made within Section 2(m))
statutory_opening: "This Written Complaint is filed under Section 9(1) of the Sexual Harassment of Women at Workplace (Prevention, Prohibition and Redressal) Act 2013, by the Complainant, an aggrieved woman within the meaning of Section 2(a) of the said Act, before the Internal Committee constituted under Section 4 of the said Act at the workplace within Section 2(o)."
ingredient_paragraphs:
  - "1. Aggrieved-woman status — the Complainant is an aggrieved woman within the meaning of Section 2(a) of the POSH Act 2013. The Complainant is an employee / contract worker / trainee / probationer / volunteer / visitor at the workplace at the relevant time (refer document establishing engagement at Exhibit ___, marked confidential under Section 16)."
  - "2. Workplace nexus — the workplace falls within the meaning of Section 2(o) POSH Act 2013, being [employer's premises / hospital / educational institution / sports complex / dwelling place / any place visited by the employee arising out of or during the course of employment / a transit place]. The incidents complained of arose at, in, or in connection with, the said workplace."
  - "3. Acts of sexual harassment — the Complainant alleges that the Respondent, on the dates and at the locations particularised at Annexure ____ (marked confidential under Section 16), engaged in one or more of the following acts of sexual harassment within the meaning of Section 2(n) POSH Act 2013: [physical contact and advances / demand or request for sexual favours / sexually coloured remarks / showing pornography / any other unwelcome physical, verbal or non-verbal conduct of sexual nature]."
  - "4. Section 3 connected circumstances — one or more of the connected circumstances in Section 3(2) POSH Act 2013 is also present: [implied or explicit promise of preferential treatment in employment / implied or explicit threat of detrimental treatment in employment / implied or explicit threat about present or future employment status / interference with work or creating an intimidating, offensive or hostile work environment / humiliating treatment likely to affect health or safety]."
  - "5. Section 9(1) three-month limitation — the present Complaint is filed within three months of the date of the last incident / extended by [number] days under the proviso to Section 9(1) on sufficient cause shown to this Internal Committee, particularised at Annexure ____."
  - "6. Internal Committee jurisdiction — this Internal Committee has jurisdiction under Section 4 POSH Act 2013, having been constituted on ____ with the composition prescribed by Section 4(2) — presiding officer is a senior-level woman, two members are from amongst employees, one member is from an NGO familiar with sexual-harassment issues, and at least half the members are women."
prayer_clauses:
  - "(a) Initiate inquiry under Section 11 POSH Act 2013 in accordance with the procedure prescribed by the POSH Rules 2013 read with the applicable Service Rules / Standing Orders of the workplace;"
  - "(b) Grant interim relief under Section 12 POSH Act 2013 — direct transfer of the Complainant or the Respondent to a different location / grant of leave to the Complainant up to a period of three months / restrain the Respondent from reporting on the Complainant's work performance / restrain the Respondent from supervising or evaluating the Complainant / such other protective measure as may be appropriate;"
  - "(c) On finding the allegation proved at inquiry, recommend action under Section 13 read with Section 15 POSH Act 2013 — disciplinary action against the Respondent under the applicable Service Rules / Standing Orders, deduction of compensation payable by the Respondent to the Complainant from the wages of the Respondent under Section 13(3)(b), and / or such further action as the Internal Committee considers appropriate;"
  - "(d) Maintain the strict confidentiality discipline under Section 16 POSH Act 2013 throughout the proceedings;"
  - "(e) Grant such further and other reliefs as this Internal Committee may deem fit and proper in the circumstances of the case."
mandatory_exhibits:
  - document_establishing_complainants_engagement_at_workplace
  - documents_evidencing_workplace_nexus_under_section_2_o
  - chronology_of_incidents_with_dates_locations_and_context_marked_confidential
  - any_contemporaneous_communications_witnessing_the_alleged_conduct
  - any_pre_complaint_internal_grievance_redressal_record
  - medical_or_counselling_records_relevant_to_the_complainants_health_impact_only_with_complainants_consent
  - documents_establishing_section_9_3_month_compliance_or_grounds_for_extension
  - posh_act_2013_and_posh_rules_2013_certified_copies
no_fee: "Section 9 POSH Act 2013 provides for filing without fee."
limitation: "Three months from the date of last incident under Section 9(1) POSH Act 2013, extendable for a further three months by the Internal Committee on recording of reasons. The proviso to Section 9(1) authorises extension where the Internal Committee is satisfied that the circumstances were such as to prevent the woman from filing within the original three months."
```

## Section 11 inquiry procedure framework

Once the Section 9 Complaint is filed, the Internal Committee:

- Provides a copy of the Complaint to the Respondent within 7 working days of receipt (Rule 7(1) POSH Rules 2013)
- Affords the Respondent an opportunity to reply within 10 working days (Rule 7(1) POSH Rules 2013)
- Conducts the inquiry in accordance with the applicable Service Rules / Standing Orders of the workplace, the POSH Act 2013, and the principles of natural justice
- May summon documents, examine witnesses, and adopt procedures aligned with *Vishaka v. State of Rajasthan* (1997) 6 SCC 241 principles read with Section 11 POSH Act 2013
- Completes the inquiry within 90 days of receipt of the Complaint (Section 11(4))
- Submits its inquiry report under Section 13(1) within 10 days of completion of the inquiry (Section 13(1))

The Drafter notes the procedural timeline in the Complaint for record but does not pre-empt the Internal Committee's procedure.

## Section 12 interim-relief framework

Available reliefs (cumulative or alternative):

- (a) Transfer of the aggrieved woman or the respondent to any other workplace
- (b) Grant of leave to the aggrieved woman up to a period of three months
- (c) Restrain the respondent from reporting on the work performance of the aggrieved woman or writing her confidential report
- (d) Grant any other relief which the Internal Committee may consider appropriate

The Drafter pleads the specific interim relief sought, with reasons.

## Section 14 false / malicious complaint discipline

Section 14 POSH Act 2013 prescribes consequences for a false or malicious complaint — the same disciplinary action as may be taken in the case of the Respondent if the allegation is proved. The Drafter is careful to plead only what the Complainant can demonstrate; embellishment is structurally avoided.

## Section 16 confidentiality discipline — operational

- The Complaint, the Annexures particularising the incidents, the witness statements, the inquiry record, the inquiry report under Section 13, and the recommendations under Section 13 read with Section 15 are NOT to be disclosed outside the statutory channel.
- The Refiner's output `final-draft.docx` carries a header on every page: *"CONFIDENTIAL UNDER SECTION 16 OF THE POSH ACT 2013 — NOT FOR DISCLOSURE OUTSIDE THE INTERNAL COMMITTEE PROCEEDINGS"*.
- Metadata is stripped from the `.docx` file (author, last-saved-by, company name, revision history).
- Physical copies served on the Respondent or the Respondent's counsel follow the Internal Committee's Section 16 protocol — typically under acknowledgement, paper copy only, not electronic.
