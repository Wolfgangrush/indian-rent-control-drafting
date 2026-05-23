# Changelog

All notable changes to the `indian-rent-control-drafting` plugin are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/) and this project adheres to [Semantic Versioning](https://semver.org/).

---

## [0.2.2-alpha] — 2026-05-24

### Output-pairing discipline — every `.md` paired with `.docx`

Advocates do not natively read Markdown. Every pipeline output artifact (case-facts.md from Reader, format-shell.md from Format, draft-v1.md from Drafter, verification-report.md from Verifier, draft-v2.md from Refiner, opposing-notes.md + final-draft.md from Overseer) is now paired with a corresponding `.docx` rendered using the same locked Word styles in the shipped reference.docx.

### Added

- **`pair_md_to_docx.sh`** — helper script in `skills/<base>/` that every agent calls after writing a `.md` output. Wraps the two-step pandoc + fix_docx_tables.py pipeline so every agent produces a paired `.docx` without re-implementing the conversion logic.
- **OUTPUT-PAIRING DISCIPLINE** section in `_drafting_common/SKILL.md` documenting the per-agent output-pairing map (Reader → case-facts.{md,docx}; Format → format-shell.{md,docx}; Drafter → draft-v1.{md,docx}; Verifier → verification-report.{md,docx}; Refiner → draft-v2.{md,docx}; Overseer → opposing-notes.{md,docx} + final-draft.{md,docx}).

### Why the change

User feedback from the 2026-05-24 EPFO test demonstrated that the QC pipeline output (`verification-report.md`, `opposing-notes.md`) was not accessible to the advocate in their normal Word workflow. The advocate explicitly stated: "every note … needs to be docx too." v0.2.2 closes this gap.

### Clarification — per-court formatting

v0.2.1 propagated a single Bombay HC Nagpur pleading-style reference.docx across all 14 plugins. The structural styling (TNR 14pt 1.5 spacing 4cm-left margin Heading 1/2/3/4) is broadly defensible for pleading-style plugins (HC / SC / Tax / Rent / MACT / Banking / Company / Consumer / Labour / Family / IP / District Court) because the court-specific differences (cause-title text, annexure prefix, statutory opening, AOR Certificate language) live in the case-type SKILL.md (Drafter content) not the reference.docx (style template). For SC the universal style is correct as the SC Registry mandate matches the HC convention (A4 + TNR 14pt + 1.5 spacing + 4cm left margin). Court-specific content (P-1/P-2 annexure prefix instead of ANNEXURE-A; SYNOPSIS + LIST OF DATES instead of just INDEX; AOR Certificate verbatim) is rendered by the Drafter from the case-type skill. Per-bench fine-tuning (e.g., Delhi HC double-spacing under Original Side Rules 2018; Punjab & Haryana watermarked paper) is achieved by supplying a case-folder reference.docx override.

For the two TRANSACTIONAL plugins (indian-contracts-drafting-litigation + indian-property-drafting-litigation), v0.2.1 wrongly applied the pleading-style reference.docx. Those two plugins now ship a transactional-instrument variant (TNR 12pt single-spaced, no spaced section headers, no underline on headings) under their own v0.2.2 release.

---

## [0.2.1-alpha] — 2026-05-24

### Filing-grade format calibration

Inherits the v0.2.1 calibration from `indian-hc-drafting-litigation` (anchored to an actual filed Bombay HC Nagpur Second Appeal pleading) and applies it to the rent-control pipeline.

### Added

- **`fix_docx_tables.py`** post-pandoc script at `skills/_rent_control_drafting_base/fix_docx_tables.py`. Forces column widths on every table in the rendered .docx — 5-col (Sr.No / Annx / Particulars / Date / Pgs) = 8/8/60/14/10; 4-col = 10/10/65/15; 3-col = 10/75/15; 2-col (Synopsis Dates–Events / Rent-history columns) = 18/82. Locks first-row bold + centered. Drafter runs this as the final post-pandoc step.
- **Heading 2 with UNDERLINE** in reference.docx for spaced section headers (`F A C T S`, `G R O U N D S`, `P R A Y E R`, `V E R I F I C A T I O N`, etc.).
- **Heading 3 + Heading 4 styles** in reference.docx for unspaced bold-underlined section headers and left-anchored bold-underlined headings.

### Changed

- **Drafter pandoc command** is now TWO steps (pandoc → .docx, then `fix_docx_tables.py`). Step 2 is non-negotiable; skipping it produces stacking-column table defects.
- **reference.docx Heading 2 style** now includes UNDERLINE.

---

## [0.2.0-alpha] — 2026-05-24

### Critical render-defect repair + pipeline-optionality

This release inherits the v0.2.0-alpha fixes from `indian-hc-drafting-litigation` and adapts them to the rent-control pipeline. The v0.1.0 render path produced filing-grade Markdown but the pandoc → `.docx` conversion failed Rent Controller / Court of Small Causes / Rent Authority Registry expectations on multiple counts.

### Added

- **Pre-customised rent-control `reference.docx`** at `skills/_rent_control_drafting_base/reference.docx` with locked Word styles (TNR 14pt body, 1.5 line spacing, 4cm left / 2.5cm right-top-bottom margins, Heading 1 bold centered, Heading 2 bold centered with letter-spacing for the spaced `F A C T S` effect, Heading 3 bold left, fixed table layout).
- **`build_reference_docx.py`** — reproducible build script for the shipped reference.docx.
- **MARKDOWN HEADING DISCIPLINE** section in `_drafting_common/SKILL.md` and `agents/drafter/drafter.md` documenting the Markdown → Word-style mapping the Drafter must follow.
- **VERBOSITY DISCIPLINE** in `_drafting_common/SKILL.md` setting per-case-type word-count targets (Eviction 3,000–4,500 / ceiling 6,000; Standard Rent Fixation 2,500–3,500 / 4,500; Rent Deposit Application 1,500–2,500 / 3,500; Tenancy Termination Notice 800–1,500 / 2,000; Recovery Suit 3,000–4,500 / 6,000; Tenant Written Statement 2,500–4,000 / 5,500; Revision/Appeal 4,000–5,500 / 7,500).
- **PIPELINE-OPTIONALITY** section in `_drafting_common/SKILL.md` — Verifier / Refiner / Overseer now OPTIONAL QC layers. Default exit point is after Stage 3 (Drafter); the advocate decides whether to invoke the QC stages.
- **COVER-PAGE DISCIPLINE** — INDEX, SYNOPSIS, LIST OF ANNEXURES each begin on `\newpage` and carry ONLY forum header + case-number + short cause-title + section header + content + counsel block.

### Changed

- **Drafter agent prompt** extended with the Markdown-heading discipline, verbosity ceilings, cover-page discipline, and pandoc invocation against the shipped reference.docx.
- **Pandoc invocation documented end-to-end.** The Drafter MUST use the shipped reference.docx; auto-generating one in the case folder is now banned (it was the v0.1.0 defect source).

### Cost / token-budget note

Running the full 6-agent pipeline burns approximately 600K tokens per draft, which can exhaust an advocate's Claude session limit. v0.2.0 makes Stages 4–6 OPTIONAL so a baseline Reader → Format → Drafter run (~280K tokens) is sufficient for routine pleadings (rent deposit applications, tenancy termination notices). The optional QC stages remain available for contested eviction matters and standard-rent fixations with significant pecuniary impact.

---

## [0.1.0-alpha] — 2026-05-17 (initial release)

### Added

- **Plugin scaffolding** — `.claude-plugin/plugin.json` manifest · MIT `LICENSE` · `NOTICE.md` provenance and privilege statement · `.gitignore` · this `CHANGELOG.md` · comprehensive `README.md`.
- **Six-agent drafting pipeline** — Reader → Format → Drafter → Verifier → Refiner → Overseer. Each agent is a markdown file under `agents/<name>/<name>.md` with YAML frontmatter declaring `name`, `description`, and `allowed-tools`.
- **Shared infrastructure skills:**
  - `_drafting_common` — anti-pollution rules, encoding standards, language conventions, AI-style-marker blacklist, rent-control-specific privacy firewall (party names, premises descriptions, monthly-rent figures, statutory-notice references, previous-petition references, previous-order references, Rent Controller / Court of Small Causes / Rent Authority case-numbers, rent-deposit receipts), Transfer of Property Act 1882 Sections 105-117 general law of lease + Section 106 termination notice + Section 111 determination + Sections 114 / 114A relief against forfeiture, the doctrine of statutory tenancy and heritability under *Damadilal v. Parashram* (1976) 4 SCC 645 and the Constitution Bench in *Gian Devi Anand v. Jeevan Kumar* (1985) 2 SCC 683, the Section 14(1)(e) Delhi Rent Control Act 1958 bona-fide personal need framework anchored in *Ragavendra Kumar v. Firm Prem Machinary* (2000) 1 SCC 679 + *Akhileshwar Kumar v. Mustaqim* (2003) 1 SCC 75 + *Sait Nagjee Purushotham & Co. Ltd. v. Vimalabai Prabhulal* (2005) 8 SCC 252 + *Joginder Pal v. Naval Kishore Behal* (2002) 5 SCC 397, the Section 25B Delhi Rent Control Act summary procedure for bona-fide need, the sub-tenancy doctrine anchored in *Resham Singh v. Raghbir Singh* (1999) 7 SCC 263, the *V. Dhanapal Chettiar v. Yesodai Ammal* (1979) 4 SCC 214 discipline on State-Rent-Control-Act displacement of Section 106 TPA termination notice, the *Hiralal Kapur v. Prabhu Choudhury* (1988) 2 SCC 172 non-payment-ground discipline, the standard-rent / fair-rent fixation methodology, the rent-deposit framework under Section 8 Maharashtra Rent Control Act 1999 / Section 27 Delhi Rent Control Act 1958, the pagdi system jurisprudence under Section 56 Maharashtra Rent Control Act 1999, the Code of Civil Procedure 1908 Order VI Rule 15 verification discipline, the Limitation Act 1963 framework for rent-control suits (Article 51 mesne profits, Article 52 rent arrears, Article 61 mortgagee possession), and the Bharatiya Sakshya Adhiniyam 2023 transition.
  - `_rent_control_drafting_base` — universal Indian rent-control pleading skeleton (Cause Title with forum + matter type + parties → Statutory Opening invoking the applicable State Rent Control Act provisions → Prelude → FACTS with rent-history chronology and ground-specific factual matrix → GROUNDS → PRAYER → Verification block under Order VI Rule 15 CPC → Counsel block → Index → Synopsis → List of Annexures → Accompanying Applications).
- **Eleven case-type skill scaffolds:**
  - `eviction-non-payment-of-rent-draft` — Eviction Petition on default in payment of rent ground under Section 16(1)(a) MRC Act 1999 / Section 14(1)(a) DRC Act 1958 / parallel grounds in other State Rent Control Acts; non-compliance within prescribed 30-day window of statutory notice; *Hiralal Kapur* (1988) 2 SCC 172 discipline; accompanying interim-deposit application under Section 11(4) MRC Act 1999 / equivalent.
  - `eviction-bona-fide-personal-need-draft` — Eviction Petition on landlord's bona-fide personal need ground under Section 16(1)(g) MRC Act 1999 / Section 14(1)(e) DRC Act 1958 / Section 21(1)(a) UP Urban Buildings Act 1972 / parallel grounds; *Ragavendra Kumar* (2000) + *Akhileshwar Kumar* (2003) + *Sait Nagjee Purushotham* (2005) + *Joginder Pal* (2002) framework; optional Section 25B DRC Act Chapter IIIA summary procedure where invoked SOLELY on this ground; UP-distinctive release application before the Prescribed Authority under Section 21 UP Act 1972.
  - `eviction-nuisance-damage-draft` — Eviction Petition on nuisance / damage ground under Section 16(1)(c)(d) MRC Act 1999 / Section 14(1)(j)(k) DRC Act 1958 / parallel grounds; documentary evidence framework (police complaints + neighbour affidavits + cost-of-repair estimates + photographs).
  - `eviction-sub-letting-without-consent-draft` — Eviction Petition on unlawful sub-letting / parting with possession ground under Section 16(1)(e) MRC Act 1999 / Section 14(1)(b) DRC Act 1958 / parallel grounds; *Resham Singh v. Raghbir Singh* (1999) 7 SCC 263 inferential evidence framework (exclusive possession of sub-tenant + consideration to tenant); *Helper Girdharbhai* (1987) 3 SCC 538 + *Bharat Sales v. LIC of India* (1998) 3 SCC 1 lineage.
  - `standard-rent-fixation-application-draft` — Standard-Rent / Fair-Rent Fixation Application under Section 7 MRC Act 1999 + Section 11 4%-annual statutory increase / Sections 6-9 DRC Act 1958 / Section 14 KRA 2001 / Sections 17-22 WBPT Act 1997; cost-construction + Section 10 MRC Act permitted-increases-for-amenities methodology.
  - `rent-deposit-application-draft` — Rent-Deposit Application under Section 8 MRC Act 1999 / Section 27 DRC Act 1958 / Section 21 KRA 2001 / Section 21 WBPT Act 1997 / Section 30 UP Urban Buildings Act 1972 / Section 9 AP/Telangana Act 1960; protection against non-payment eviction ground via regular and continuous deposits.
  - `tenancy-termination-notice-draft` — Tenancy Termination Notice under Section 106 Transfer of Property Act 1882 (15-day notice post-2002 amendment, terminating with end of tenancy month) read with Section 111 TPA 1882; *V. Dhanapal Chettiar v. Yesodai Ammal* (1979) 4 SCC 214 State-Rent-Control-Act-displacement check; mode-of-service framework (registered post AD / personal / affixture); pre-suit notice document drafted on advocate's letterhead.
  - `landlord-recovery-suit-draft` — Landlord Recovery Suit for rent arrears + mesne profits under Order VII CPC 1908 + Article 52 Limitation Act 1963 + applicable State Court Fees Act; comparable-rents mesne-profits methodology; Section 18 Limitation Act 1963 acknowledgement-of-debt limitation extension.
  - `tenant-written-statement-draft` — Tenant Written Statement to an eviction petition under Order VIII CPC 1908; preliminary objections (jurisdiction · maintainability · limitation · Section 106 TPA notice infirmity) + para-by-para reply + additional pleas (statutory tenancy under *Damadilal* + *Gian Devi Anand* + heritability + deposit-protection + comparative-hardship + sub-tenant denial + acquiescence + landlord's other accommodation + sham-need).
  - `revision-appeal-rent-controller-draft` — Revision / Appeal before the Rent Control Appellate Bench / District Judge / High Court under Section 34-35 MRC Act 1999 / Section 38-39 DRC Act 1958 / Section 28 KRA 2001 / Sections 29-30 WBPT Act 1997 / Section 22 UP Act / Section 115 CPC 1908 / Articles 226-227 of the Constitution.
  - `model-tenancy-act-2021-framework-draft` — Pleading under the Model Tenancy Act 2021 framework (Central model law) for States that have adopted (Andhra Pradesh notified) or are in process (Uttar Pradesh draft) or operate parallel modified-MTA frameworks (Tamil Nadu 2017 Act); compulsory written tenancy agreement + Rent Authority + Rent Court + Rent Tribunal three-tier forum + capped security deposit framework.
- **State-aware design** — `state-config/exemplars/` provides State-specific Rent Control Act references, eviction-ground section maps, Section 106 TPA notice position (REQUIRED / DISPLACED per *V. Dhanapal Chettiar*), forum nomenclature (Court of Small Causes / Rent Controller / Prescribed Authority / Rent Authority / Rent Tribunal / Civil Judge as Rent Controller), standard-rent / fair-rent fixation methodology, rent-deposit procedure, summary-procedure availability, pagdi-system recognition, and Model Tenancy Act 2021 adoption status. Initial coverage: Maharashtra · Delhi · Tamil Nadu · Karnataka · West Bengal · Uttar Pradesh · Gujarat · Andhra Pradesh / Telangana.

### Notes on this release

This is a **v0.1.0-alpha scaffold release**. The structural skeletons, agent pipeline, base skills, 11 case-type skill frames, and 8 State exemplars are in place. Deep per-skill encoding planned for v0.2.0 onward:

- Rent-escalation arbitration framework (where tenancy agreement provides for arbitral fixation)
- Tenancy fixation by negotiation under the Model Tenancy Act 2021 framework
- Maharashtra Pagdi-specific transfer-permission applications under Section 56 MRC Act 1999
- State-specific revision procedures requiring State-Act-specific authoring depth (Karnataka Section 28 KRA 2001; UP Section 22 UP Act 1972)
- Commercial-tenancy specialised pleadings where the State Rent Control Act draws a residential / non-residential distinction with separate eviction procedures
- Additional State exemplars (Kerala Buildings (Lease and Rent Control) Act 1965 · Rajasthan Premises (Control of Rent and Eviction) Act 1950 · MP Accommodation Control Act 1961 · Bihar Buildings (Lease, Rent and Eviction) Control Act 1982 · Odisha House Rent Control Act 1967 · Punjab Urban Rent Restriction Act 1949 · Haryana Urban (Control of Rent and Eviction) Act 1973 · the North-Eastern States · Goa Buildings (Lease, Rent and Eviction) Control Act 1968)

### Released under

MIT License. Authored by Rushikesh R. Mahajan, Advocate, publishing under the Wolfgang Rush open-source brand for legal-tech infrastructure.
