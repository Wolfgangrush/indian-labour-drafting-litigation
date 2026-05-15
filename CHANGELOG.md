# Changelog

All notable changes to the `indian-labour-drafting` plugin are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/) and this project adheres to [Semantic Versioning](https://semver.org/).

---

## [0.1.0-alpha] — 2026-05-16 (initial release)

### Added

- **Plugin scaffolding** — `.claude-plugin/plugin.json` manifest · MIT `LICENSE` · `NOTICE.md` provenance and privilege statement · `.gitignore` · this `CHANGELOG.md` · comprehensive `README.md`.
- **Six-agent drafting pipeline** — Reader → Format → Drafter → Verifier → Refiner → Overseer. Each agent is a markdown file under `agents/<name>/<name>.md` with YAML frontmatter declaring `name`, `description`, and `allowed-tools`.
- **Shared infrastructure skills:**
  - `_drafting_common` — anti-pollution rules, encoding standards, language conventions, AI-style-marker blacklist, labour-specific privacy firewall (workman names, establishment names, complainant names in POSH matters, employee identification numbers, EPF / ESI / UAN numbers, salary figures, dismissal-letter references), citation discipline, statutory currency rules (CrPC 1973 → BNSS 2023 transitions for prosecution; IEA 1872 → BSA 2023 transitions for proof; four Labour Codes 2019-2020 variable State-notification status), Industrial Disputes Act 1947 jurisdictional rules, POSH Act 2013 confidentiality discipline (Section 16), workman-vs-non-workman classification rule (Sections 2(s) and 2(oo) ID Act), workman direct application under Section 2A (post-2010 amendment) rule, retrenchment compliance under Sections 25F / 25G / 25N ID Act, Limitation Act 1963 Article map for labour disputes, and Workmen Compensation Act 1923 versus Employees' Compensation Act 1923 statutory currency.
  - `_labour_drafting_base` — universal Indian labour pleading skeleton (Cause Title with correct forum nomenclature — Labour Court / Industrial Tribunal / Authority under Minimum Wages Act / Controlling Authority under Gratuity Act / Internal Committee under POSH Act / EPF Appellate Tribunal / Employees' Insurance Court / Inspector under Shops and Establishments Act / Certifying Officer under IESO Act — Parties block, Statutory Opening invoking the operative section, Prelude, Facts, Grounds, Prayer, Verification, Affidavit-in-support, Index, List of Documents, accompanying applications).
- **Ten case-type skill scaffolds:**
  - `id-act-section-10-reference-draft` — Government reference of an industrial dispute under Section 10 of the Industrial Disputes Act 1947 to the Labour Court / Industrial Tribunal / National Industrial Tribunal
  - `id-act-section-2a-application-draft` — Workman's direct application under Section 2A of the Industrial Disputes Act 1947 (post-2010 amendment route, bypassing conciliation officer reference)
  - `labour-court-claim-statement-draft` — Statement of Claim before the Labour Court / Industrial Tribunal post-reference, with full pleading of cause of action, reinstatement / back-wages claim, and consequential reliefs
  - `posh-internal-complaint-draft` — Complaint under Section 9 of the Sexual Harassment of Women at Workplace (Prevention, Prohibition and Redressal) Act 2013, filed before the Internal Committee of the workplace
  - `shops-establishments-show-cause-reply-draft` — Reply to a show-cause notice issued by the Inspector / Chief Inspector under the State Shops and Establishments Act (state-config-aware)
  - `gratuity-claim-controlling-authority-draft` — Application before the Controlling Authority under Section 7 of the Payment of Gratuity Act 1972 for recovery of gratuity
  - `epf-determination-challenge-draft` — Appeal before the EPF Appellate Tribunal under Section 7-I of the Employees' Provident Funds and Miscellaneous Provisions Act 1952 challenging a Section 7A determination by the PF Authority
  - `esic-section-75-application-draft` — Application before the Employees' Insurance Court under Section 75 of the Employees' State Insurance Act 1948 for adjudication of disputed contributions / benefits
  - `minimum-wages-claim-draft` — Application before the Authority appointed under Section 20 of the Minimum Wages Act 1948 for recovery of wages less than the minimum rates, with compensation up to ten times
  - `industrial-employment-standing-orders-certification-draft` — Draft Standing Orders for certification under the Industrial Employment (Standing Orders) Act 1946 read with the Industrial Employment (Standing Orders) Central Rules 1946 (and the applicable State Rules)
- **State-aware design** — `state-config/exemplars/` provides State-specific Shops and Establishments Act / Labour Welfare Fund Act / Industrial Court hierarchy / Profession Tax rules per State. The user supplies `case-config.md` declaring the chosen forum, claim quantum, establishment type, workman status, applicable State Shops and Establishments Act, and the limitation-clock anchor.

### Notes on this release

This is a **v0.1.0-alpha scaffold release**. The structural skeletons, agent pipeline, base skills, and 10 case-type skill frames are in place. Deep per-skill encoding (full pleading exemplars for each case type, State-specific Shops and Establishments calibration per Maharashtra / Karnataka / Tamil Nadu / Delhi / UP / Gujarat / West Bengal / Telangana / Andhra Pradesh / Kerala / Rajasthan / Madhya Pradesh / Odisha / Punjab / Haryana / Bihar, deeper four-Labour-Codes overlay as Codes are notified by individual States, MRTU & PULP Act 1971 Maharashtra-specific Labour Court hierarchy, and bench-specific Practice Directions for prominent Labour Court / Industrial Tribunal / EPFAT / ESI Court benches) will land in v0.1.0 and onward.

### Released under

MIT License. Authored by Rushikesh R. Mahajan, Advocate, publishing under the Wolfgang Rush open-source brand for legal-tech infrastructure.
