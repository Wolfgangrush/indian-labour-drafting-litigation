# NOTICE — Provenance and Privilege Statement

This document is part of the public release of the `indian-labour-drafting` plugin (v0.1.0-alpha and onwards). It declares the provenance of the plugin's content, in order to address any question about advocate-client privilege, client confidentiality, professional ethics, personal-data protection, and POSH-Act Section 16 confidentiality discipline that may be raised by any reader, complainant, regulator, or Bar Council disciplinary authority.

The plugin is **case-config-aware** and **state-config-aware**: the universal structural skeleton of any Indian labour pleading is uniform, and the chosen forum (Labour Court / Industrial Tribunal / Controlling Authority under Payment of Gratuity Act / Authority under Minimum Wages Act / Internal Committee under POSH Act / EPF Appellate Tribunal / Employees' Insurance Court / Inspector or Chief Inspector under State Shops and Establishments Act / Certifying Officer under Industrial Employment (Standing Orders) Act), the applicable State Shops and Establishments Act, the State-specific Industrial Court hierarchy (two-tier or three-tier), and the workman / establishment particulars are supplied by the user via a `case-config.md` file in the case folder.

This NOTICE is published in plain language so that any reader — practising advocate, judge, Bar Council officer, regulator, Internal Committee member, member of the public, fellow developer — can understand the position without ambiguity.

---

## 1. What this plugin contains

This plugin contains the following categories of content, and **only** the following categories of content:

(a) **Universal labour-pleading skeleton** — the structural shape of any Indian labour / industrial-disputes / employment-rights / social-security / workplace-protection pleading (Cause Title with correct forum nomenclature, Parties block, Statutory Opening invoking the operative section, Prelude, Facts, Grounds, Prayer, Verification, Affidavit-in-support, Index, List of Documents, accompanying applications).

(b) **Formatting conventions** — text-formatting conventions for pleadings before the Labour Court, the Industrial Tribunal, the National Industrial Tribunal, the Controlling Authority under the Payment of Gratuity Act 1972, the Authority under the Minimum Wages Act 1948, the Internal Committee under the POSH Act 2013, the EPF Appellate Tribunal, the Employees' Insurance Court, the Inspector or Chief Inspector under any State Shops and Establishments Act, and the Certifying Officer under the Industrial Employment (Standing Orders) Act 1946.

(c) **Statutory references** — citations to public statutes (Industrial Disputes Act 1947, Trade Unions Act 1926, Sexual Harassment of Women at Workplace (Prevention, Prohibition and Redressal) Act 2013, Factories Act 1948, Payment of Wages Act 1936, Minimum Wages Act 1948, Workmen's Compensation Act 1923 / Employees' Compensation Act 1923, Employees' Provident Funds and Miscellaneous Provisions Act 1952, Employees' State Insurance Act 1948, Payment of Gratuity Act 1972, Maternity Benefit Act 1961, Contract Labour (Regulation and Abolition) Act 1970, Industrial Employment (Standing Orders) Act 1946, Code on Wages 2019, Industrial Relations Code 2020, Code on Social Security 2020, Occupational Safety, Health and Working Conditions Code 2020 (with variable State notification status), Equal Remuneration Act 1976, Apprentices Act 1961, applicable State Shops and Establishments Acts, applicable State Labour Welfare Fund Acts, applicable State Profession Tax Acts, Bharatiya Nagarik Suraksha Sanhita 2023, Bharatiya Sakshya Adhiniyam 2023, Indian Contract Act 1872, Limitation Act 1963, Code of Civil Procedure 1908).

(d) **Procedural rule references** — citations to public rules (Industrial Disputes (Central) Rules 1957, applicable State Industrial Disputes Rules, Industrial Employment (Standing Orders) Central Rules 1946 and applicable State Rules, Employees' Provident Funds Scheme 1952, Employees' Pension Scheme 1995, Employees' Deposit Linked Insurance Scheme 1976, Employees' State Insurance (Central) Rules 1950, Employees' State Insurance (General) Regulations 1950, Payment of Gratuity (Central) Rules 1972, Sexual Harassment of Women at Workplace Rules 2013, applicable State Shops and Establishments Rules, applicable State Labour Welfare Fund Rules, applicable State Profession Tax Rules, Apprenticeship Rules 1992, and the various Standing Orders and Practice Directions of the Labour Court / Industrial Tribunal / EPF Appellate Tribunal / Employees' Insurance Court benches).

(e) **Generic placeholders** — every variable in every template is a placeholder (`[Workman]`, `[Establishment]`, `[Employer]`, `[Designation]`, `[Date-of-Joining]`, `[Date-of-Termination]`, `[Last-Drawn-Wages]`, `[EPF-Member-ID]`, `[ESI-Insurance-Number]`, `[UAN]`, `[Standing-Orders-Reference]`, `[Charge-Sheet-Reference]`, `[Domestic-Inquiry-Reference]`, `[Termination-Order-Reference]`, `[Internal-Committee-Reference]`, `[Complainant]`, `[Respondent]`). No placeholder is filled with any specific workman, establishment, complainant, employer, salary, designation, or any other identifying information.

(f) **Anti-hallucination and privacy-firewall workflow** — six agents (Reader, Format, Drafter, Verifier, Refiner, Overseer) that operate on a case folder supplied by the user. The plugin itself contains no case folder. The Reader substitutes every workman name, every establishment name, every complainant identifier in any POSH matter, every EPF / ESI / UAN number, and every salary figure with placeholders before downstream AI processing.

---

## 2. What this plugin does NOT contain

This plugin does **not** contain any of the following, and has never contained any of the following at any point in any committed version:

(a) **No specific client matter or labour dispute.** No client of the author, and no specific workman, employer, establishment, trade union, or POSH complainant handled by the author or any client, appears in the plugin — by name, by establishment registration, by EPF / ESI / UAN identifier, by designation, by wage figure, by party name, by registration number (Factories-Act-Licence / Shops-and-Establishments-Registration / EPF-Code / ESI-Code), or by any other identifying signature.

(b) **No client communications.** No oral or written communication made to the author by or on behalf of any client (whether a workman, an employer, a trade union, a POSH Internal Committee member, an Inspector, or any other party) appears in the plugin in any form.

(c) **No client documents.** No document or instrument with which the author has become acquainted in the course of professional employment as an advocate appears in the plugin, in original, in redacted, in summary, in extract, or in pattern. This includes — but is not limited to — appointment letters, employment agreements, charge-sheets, domestic inquiry reports, dismissal orders, retrenchment notices, conciliation officer reports, government reference orders, Section 7A determination orders, ESI contribution-disputes, POSH Internal-Committee proceedings, and Standing Orders certifications of any specific establishment.

(d) **No personal data of any data principal.** The plugin processes no personal data, collects no personal data, stores no personal data.

(e) **No specific POSH complaint.** No specific complaint, no specific Internal Committee proceedings, no specific complainant, no specific respondent, and no specific workplace appears in the plugin. POSH Act Section 16 confidentiality is preserved by design — the plugin's POSH-skill scaffolding contains only the procedural skeleton; the user's case folder is the only repository of complaint-specific content, and it is local-only.

(f) **No client list, no panel-counsel list of any employer or trade union, no chamber list, no associate list, no opposing-counsel list, no Presiding Officer-specific intelligence.**

(g) **No tracking, no telemetry, no analytics, no opt-in error reporting, no login, no account, no cloud sync.** The plugin runs entirely on the user's machine. The author receives no information about who installs the plugin, who uses it, on what cases, with what wages, with what outcomes.

---

## 3. The legal distinction

Indian law has long recognised a clear distinction between two categories:

(i) **Specific client communications and documents** — protected under Section 132 of the Bharatiya Sakshya Adhiniyam 2023 (formerly Section 126 of the Indian Evidence Act 1872) and under Rule 17 of the Bar Council of India Standards of Professional Conduct and Etiquette. This category is privileged and confidential. POSH Act Section 16 further imposes a statutory confidentiality discipline on the identity and proceedings relating to a sexual-harassment complainant.

(ii) **General professional knowledge of labour law, industrial-disputes procedure, social-security adjudication, and POSH compliance practice** — an advocate's accumulated knowledge of how a Section 10 ID Act reference is structured, what the workman-vs-non-workman test under Sections 2(s) and 2(oo) requires, how a Section 2A workman direct application is filed post the 2010 amendment, what the Section 25F retrenchment-compliance checklist contains, what the POSH Act 2013 Internal-Committee Section 9 complaint must aver, how a Payment of Gratuity Act 1972 controlling-authority claim is computed, what the EPF Act 1952 Section 7A determination challenge before the EPFAT requires, how a Section 75 ESI Act application is framed, what the Minimum Wages Act 1948 Section 20 claim must plead, how a Standing Orders certification draft under the IESO Act 1946 is structured. This category is the advocate's own professional knowledge. It is not the property of any specific client. It is not privileged.

This plugin operates **entirely within category (ii)**.

Every Indian advocate accumulates this knowledge through years of practice, through study of Saharay's *Industrial and Labour Laws of India*, Misra's *Labour and Industrial Laws*, Malhotra's *The Law of Industrial Disputes*, Indrajit Dube's *Industrial Law in India*, the POSH Handbook of the Ministry of Women and Child Development, the EPFO Manual, the ESIC Manual, the various State Shops-and-Establishments Manuals, and the case-law of the Supreme Court and the High Courts on workman-vs-non-workman classification, retrenchment compliance, POSH-procedural-fairness, EPF / ESI contribution-determination, and gratuity adjudication. The plugin codifies that accumulated procedural knowledge into machine-readable form. It does not codify any client's confidential information.

The plugin is, in this respect, identical in legal character to a published labour-law textbook, a continuing legal education handout, or a senior advocate's drafting-style lecture. The medium is software. The content is procedural knowledge.

---

## 4. The author's professional position

The author is **Rushikesh R. Mahajan**, Advocate, enrolled with the Bar Council of Maharashtra and Goa, practising before the Bombay High Court, Nagpur Bench. The plugin is published under the open-source brand **Wolfgang Rush**, which is the author's publishing handle for legal-technology infrastructure; the real-identity accountability declared in this section attaches to the author personally and is not displaced by the use of a publishing handle.

The author retains full enrolment, full responsibility, and full liability under the Advocates Act 1961, the Bar Council of India Rules, and the Standards of Professional Conduct and Etiquette.

The plugin is published as a personal contribution to the open-source legal-technology ecosystem. It is published without any commercial channel, without any solicitation of professional work, without any advertisement of professional services, and without any acceptance of work through this repository.

This NOTICE is filed of record in this open-source repository so that any person who reads, reviews, audits, or assesses this plugin has full transparency about its provenance and its scope from the moment of release.

---

## 5. Verification of clean provenance

The repository owner shall maintain, on a private offline record, a build log demonstrating that every line of every file in the plugin was either:

(a) authored from scratch as procedural skeleton, OR
(b) derived from public statute, public rule, public judgment, or public labour-law textbook, OR
(c) derived from the author's own original procedural knowledge as a practitioner.

No line of any file was, at any stage, copied from, paraphrased from, summarised from, or pattern-matched against any specific client matter, labour dispute, client communication, client document, or POSH complaint.

This NOTICE is the author's signed declaration of that position.

---

## 6. Reporting concerns

If any reader, regulator, fellow advocate, Internal Committee member, or member of the public believes any specific content in this plugin is derived from a specific client matter, specific confidential communication, or specific POSH complaint, the reader is requested to:

(a) identify the file and line at issue in the plugin,
(b) identify the specific client matter or communication believed to be the source,
(c) explain the basis of the belief,

and raise the concern via a GitHub Issue on this repository.

Concerns raised with these particulars will be investigated and the file or line will be removed or rewritten if the concern is well-founded. Concerns raised without these particulars cannot be acted upon.

---

## 7. Standing instruction to forks and derivatives

Any fork, derivative, downstream redistribution, or commercial integration of this plugin or its content shall preserve this NOTICE in unmodified form, and shall extend the same provenance discipline to any content added in the fork or derivative.

This NOTICE travels with the code under the same MIT licence that governs the source.

---

*Signed and dated by way of public commit history on the repository. The author stands by every line of this notice.*
