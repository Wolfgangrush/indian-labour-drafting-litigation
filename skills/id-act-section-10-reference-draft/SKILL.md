---
name: id-act-section-10-reference-draft
description: Draft a Reference under Section 10 of the Industrial Disputes Act 1947 by the appropriate Government, referring an industrial dispute for adjudication to a Labour Court (Section 7) / Industrial Tribunal (Section 7A) / National Industrial Tribunal (Section 7B). Encodes the Section 12 conciliation-failure pre-condition, the Schedule II / Schedule III subject-matter discipline, the State / Central appropriate-Government framework, the Section 18(3) binding-on-all-parties effect of the resulting award, and the workman-vs-non-workman classification rule at the threshold. Auto-fires on "draft Section 10 reference", "draft government reference ID Act", "draft industrial dispute reference", and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# Section 10 ID Act Reference Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_labour_drafting_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Case-type metadata

```yaml
case_type_line: REFERENCE UNDER SECTION 10(1) OF THE INDUSTRIAL DISPUTES ACT 1947
case_short_code: IDA_S10_REFERENCE
case_number_prefix: Reference (IDA)
pleading_type: Reference (Government Order of Reference)
typical_forum: Labour Court (for matters specified in Schedule II) / Industrial Tribunal (for matters specified in Schedule II or Schedule III) / National Industrial Tribunal (for disputes of national importance under Section 7B) — territorial jurisdiction per the appropriate Government's Reference Order
typical_parties: First Party (Workman or Workmen / Trade Union) + Second Party (Employer / Establishment / Management)
statutory_opening: "In exercise of the powers conferred by Section 10(1)(c) / 10(1)(d) of the Industrial Disputes Act 1947, the Government of [State] / the Central Government, being of the opinion that an industrial dispute exists between the parties named in the Schedule, hereby refers the said dispute to the Labour Court / Industrial Tribunal at [Place] for adjudication."
ground_clauses_for_reference_order:
  - "Existence of industrial dispute — within the meaning of Section 2(k) ID Act 1947, between [First Party] and [Second Party], in respect of the matters set out in the Schedule."
  - "Failure of conciliation — conciliation proceedings under Section 12 ID Act 1947 having failed; the conciliation officer's report dated ____ confirming non-resolution (Exhibit ___)."
  - "Appropriate Government jurisdiction — the appropriate Government within Section 2(a) ID Act 1947, being either (a) the Central Government for establishments listed in Schedule IV / under central administrative control, or (b) the State Government otherwise — has jurisdiction over the present matter."
  - "Schedule II / Schedule III subject-matter — the dispute falls within the subject-matter of Schedule II / Schedule III of the ID Act 1947 (e.g. propriety of dismissal / retrenchment / discharge; classification of workmen; standing orders interpretation; bonus / wages; gratuity / pension)."
schedule_to_reference_format: |
  SCHEDULE
  Question for adjudication:
  Whether the action of the Second Party in [retrenching / dismissing / discharging / not paying gratuity to / reclassifying] [First Party / the workman(s) named at Annexure A] with effect from ____ is legal, justified, and proper? If not, to what relief is / are the First Party / workman(s) entitled, including reinstatement, back-wages, continuity of service, and consequential benefits?
mandatory_exhibits:
  - workmens_charter_of_demands_or_individual_grievance_petition
  - employer_response_to_charter_of_demands
  - conciliation_officer_intimation_and_proceedings
  - conciliation_officer_failure_report_under_section_12_4
  - government_consideration_note_recommending_reference
  - workman_appointment_letter_and_service_records
  - charge_sheet_domestic_inquiry_findings_termination_order_where_applicable
filing_route: "The Reference Order is issued by the appropriate Government. The workman / union does NOT file the Reference; the Reference is the Government Order that vests jurisdiction in the Labour Court / Industrial Tribunal. The workman thereafter files a Statement of Claim before the Labour Court / Industrial Tribunal — see the `labour-court-claim-statement-draft` skill."
court_fee: "N/A — Reference Orders are issued by the appropriate Government and bear no court fee."
limitation: "No statutory time-bar on the issuance of a Reference Order, but the Government is expected to act within a reasonable time of the conciliation officer's failure report; unreasonable delay challenged before the High Court under Article 226 writ jurisdiction."
```

## Schedule II / Schedule III subject-matter discipline

- **Schedule II (Labour Court matters):** propriety of dismissal / discharge / retrenchment of workmen; reinstatement of workmen wrongfully dismissed; legality of an order passed under Standing Orders; withdrawal of a customary concession; illegality of strike or lock-out; matters not included in Schedule III.
- **Schedule III (Industrial Tribunal matters):** wages including period and mode of payment; compensatory and other allowances; hours of work and rest intervals; leave with wages and holidays; bonus / profit-sharing / provident fund / gratuity; classification of workmen; rules of discipline; rationalisation; retrenchment / closure; any other matter prescribed.

The Drafter checks `case-config.md` and routes to Labour Court (Schedule II) or Industrial Tribunal (Schedule III) accordingly.

## Pre-reference conciliation discipline

Under Section 12 ID Act, the conciliation officer's role is to investigate the dispute, attempt to bring about a settlement, and submit a report. The Reference under Section 10 typically follows the conciliation officer's failure report under Section 12(4) (in respect of public-utility-service disputes) or Section 12(5). The Drafter pleads the conciliation officer's failure report as a foundation for the Reference.

## *Excel Wear v. Union of India* discipline

The appropriate Government's discretion under Section 10 to make or refuse a Reference is not arbitrary — refusal must be for reasons recorded in writing. *Excel Wear v. Union of India* (1978) 4 SCC 224 and the lineage of Supreme Court precedent thereafter constrain the Government's discretion. Where the Government refuses a Reference, the workman's remedy is a writ petition under Article 226 challenging the refusal. The Drafter / Verifier flags any Reference Order that does not record reasons for proceeding with the Reference (rare; refusal-of-reference is the more common challenge).
