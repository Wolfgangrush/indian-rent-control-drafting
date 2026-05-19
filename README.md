# indian-rent-control-drafting

> **Open-source Claude-compatible plugin for drafting Indian rent-control / landlord-tenant litigation pleadings across all major State Rent Control regimes — the rent-control litigation side that complements `indian-property-drafting`'s conveyancing focus and `indian-contracts-drafting`'s commercial-tenancy-agreement focus.**
>
> Six-agent drafting pipeline · eleven case-type skills · case-config-aware + state-config-aware · Transfer of Property Act 1882 (Sections 105-117 + Section 106 termination notice + Section 111 determination + Sections 114 / 114A relief against forfeiture) + Maharashtra Rent Control Act 1999 + Delhi Rent Control Act 1958 + Tamil Nadu Regulation of Rights and Responsibilities of Landlords and Tenants Act 2017 + Karnataka Rent Act 2001 + West Bengal Premises Tenancy Act 1997 + Uttar Pradesh Urban Buildings (Regulation of Letting, Rent and Eviction) Act 1972 + Gujarat Rent Control Act 1947 (as amended) + Andhra Pradesh / Telangana Buildings (Lease, Rent and Eviction) Control Act 1960 + Model Tenancy Act 2021 + Code of Civil Procedure 1908 (Order VI Rule 15 verification + Order VII Rule 1 plaints + Order VIII Rule 1 written statements) + Limitation Act 1963 + Bharatiya Sakshya Adhiniyam 2023 + *Damadilal v. Parashram* (1976) 4 SCC 645 statutory-tenancy heritability + *Gian Devi Anand v. Jeevan Kumar* (1985) 2 SCC 683 Constitution Bench extension to commercial tenancies + *Ragavendra Kumar v. Firm Prem Machinary* (2000) 1 SCC 679 + *Akhileshwar Kumar v. Mustaqim* (2003) 1 SCC 75 + *Sait Nagjee Purushotham* (2005) 8 SCC 252 + *Joginder Pal v. Naval Kishore Behal* (2002) 5 SCC 397 bona-fide need framework + *Resham Singh v. Raghbir Singh* (1999) 7 SCC 263 sub-tenancy doctrine + *V. Dhanapal Chettiar v. Yesodai Ammal* (1979) 4 SCC 214 State-Act-displacement of Section 106 TPA notice + *Hiralal Kapur v. Prabhu Choudhury* (1988) 2 SCC 172 non-payment ground discipline encoded.
>
> Released under MIT. Open infrastructure for the legal community. No commercial engagement offered through this repository — see Disclaimer below.

> ⚠️ **AI can make mistakes. Always verify the output.**
>
> This software generates assistive drafts and suggestions only. Every legal claim, citation, statute reference, procedural step, deadline calculation, and ground of relief must be independently verified by a qualified human practitioner before filing, advising a client, or relying on the output. The publisher accepts no liability for outputs used without verification.

> 🛡️ **Privacy primitive (ecosystem):** PII pseudonymisation across the Wolfgang Rush legal-tech family is handled via [pseudonymisation-gateway](https://github.com/Wolfgangrush/pseudonymisation-gateway) (MIT). When this drafting plugin is used inside an AI Law Firm built on that gateway, client PII is stripped before any cloud-LLM call and restored on response.


---

## Table of contents

1. [What this plugin does](#what-this-plugin-does)
2. [Case-type skills (full inventory with statutory authority)](#case-type-skills-full-inventory-with-statutory-authority)
3. [The 6-agent drafting pipeline](#the-6-agent-drafting-pipeline)
4. [Installation](#installation)
5. [Your first eviction petition — step-by-step walkthrough](#your-first-eviction-petition--step-by-step-walkthrough)
6. [The `case-config.md` file](#the-case-configmd-file)
7. [State coverage and the `state-config/exemplars` layer](#state-coverage-and-the-state-configexemplars-layer)
8. [Built-in compliance disciplines](#built-in-compliance-disciplines)
9. [Privacy firewall — extra discipline for rent-control content](#privacy-firewall--extra-discipline-for-rent-control-content)
10. [Why MIT License](#why-mit-license)
11. [Sibling plugins](#sibling-plugins)
12. [Why this exists](#why-this-exists)
13. [Roadmap](#roadmap)
14. [Contributing](#contributing)
15. [Contact](#contact)
16. [Author and brand](#author-and-brand)
17. [Provenance and privilege statement](#provenance-and-privilege-statement)
18. [Disclaimer and Bar Council of India Rule 36 compliance](#disclaimer-and-bar-council-of-india-rule-36-compliance)
19. [License](#license)

---

## What this plugin does

This plugin lets an Indian advocate, sitting inside the Claude Desktop application or running Claude Code (CLI), point at a case folder on disk and obtain a complete rent-control / landlord-tenant pleading in `.docx` form — Cause Title with the correct forum nomenclature, Statutory Opening invoking the applicable State Rent Control Act provision, Prelude, Facts paragraphs with the rent-history chronology and the eviction-ground-specific factual matrix, Grounds rooted in statute and Supreme Court authority, Prayer in the case-type-specific form, Verification block under Order VI Rule 15 CPC, Counsel block, Index, Synopsis, List of Annexures, and Accompanying Applications — sourced from a `case-config.md` file the user places in the case folder and a `state-config/exemplars/<state>.md` exemplar.

The pipeline is six agents running in sequence:

1. **Reader** — extracts case-facts (parties, tenancy origin, rent payment history, statutory-notice trajectory, ground-specific factual matrix, prior proceedings, standing of the Petitioner, jurisdiction, limitation, court fee) from the case folder with a per-document audit log, and applies the **rent-control-specific privacy firewall** (every party name, premises description, monthly-rent figure, statutory-notice reference, previous-petition number, Rent Controller / Court of Small Causes order reference, and bank account / rent-deposit receipt substituted with structural placeholders before downstream AI processing).
2. **Format** — loads the case-type skill template, reads `case-config.md` and the relevant State exemplar, and pre-substitutes the applicable State Rent Control Act + forum nomenclature (Court of Small Causes / Rent Controller / Civil Judge as Rent Controller / Rent Authority / Rent Tribunal / Prescribed Authority) + relevant statutory opening + court-fee framework + Section 106 TPA notice discipline (or its State-Act-displaced equivalent per *V. Dhanapal Chettiar*) + applicable rent-deposit / standard-rent fixation framework into a `format-shell.md`.
3. **Drafter** — writes the actual pleading: Cause Title + Statutory Opening + Prelude + Facts (rent-history chronology + ground-specific matrix) + Grounds + Prayer + Verification + Counsel block + Index + Synopsis + List of Annexures + Accompanying Applications, in the formal Indian pleading register.
4. **Verifier** — anti-hallucination firewall **plus** Section 106 TPA notice / *V. Dhanapal Chettiar* State-Act-displacement check **plus** State Rent Control Act eviction-ground ingredient check **plus** bona-fide personal need framework check (*Ragavendra Kumar* + *Akhileshwar Kumar* + *Sait Nagjee Purushotham* + *Joginder Pal*) **plus** Section 25B Delhi Rent Control Act summary-procedure ingredient check (where applicable) **plus** sub-tenancy ingredient check (*Resham Singh*) **plus** *Damadilal* / *Gian Devi Anand* statutory-tenancy heritability discipline check **plus** standard-rent / fair-rent fixation methodology cross-foot **plus** rent-deposit framework check **plus** Section 11(4) MRC Act / equivalent interim-deposit application discipline **plus** Limitation Act discipline **plus** pagdi-system Section 56 MRC Act discipline (Maharashtra) **plus** jurisdiction-and-pecuniary-jurisdiction cross-foot **plus** court-fee cross-foot **plus** Order VI Rule 15 CPC verification discipline **plus** Bharatiya Sakshya Adhiniyam 2023 transition.
5. **Refiner** — applies Verifier flags, polishes language to formal Indian pleading register (*"It is most respectfully submitted that"*, *"The Petitioner is constrained to approach this Hon'ble Court"*, *"By reason of the matters aforesaid"*, *"In the premises aforesaid"*), enforces internal numbering and Annexure cross-reference consistency, strips AI-style markers, and re-substitutes real party names, real premises descriptions, real monthly-rent figures, real statutory-notice dates, and real previous-petition references into the final `.docx` (strictly on the user's local machine).
6. **Overseer** — reads the polished draft with an opposing-party / opposing-counsel lens (tenant in eviction / landlord in standard-rent / sub-tenant / statutory-tenant heir / Registry refusing presentation on jurisdiction / court-fee / verification grounds). Flags attackable bona-fide need infirmities, sub-tenancy infirmities, Section 106 TPA notice infirmities, summary-procedure infirmities, standard-rent computation infirmities, rent-deposit infirmities, Limitation Act infirmities, and Order VI Rule 15 CPC verification infirmities.

The output is what an advocate would put before the Court of Small Causes / Rent Controller / Civil Judge as Rent Controller / Rent Authority / Rent Tribunal / Prescribed Authority — **not a template. Not a checklist. A pleading** — ready for the advocate's review, professional verification, signature, court-fee stamping, and filing.

---

## Case-type skills (full inventory with statutory authority)

The plugin ships with eleven case-type skills, each covering a distinct rent-control / landlord-tenant pleading:

### 1. `eviction-non-payment-of-rent-draft`

**Statutory authority:** Section 15 + Section 16(1)(a) Maharashtra Rent Control Act 1999 · Section 14(1)(a) Delhi Rent Control Act 1958 · Section 21(1) UP Urban Buildings Act 1972 (with Section 20 bar) · Section 27(2)(a) Karnataka Rent Act 2001 · Section 6(1)(a) West Bengal Premises Tenancy Act 1997 · Section 11 Tamil Nadu 2017 Act · Section 10(2)(i) AP / Telangana Buildings Act 1960. Anchor case: *Hiralal Kapur v. Prabhu Choudhury* (1988) 2 SCC 172. **Use case:** landlord seeks eviction of tenant for default in payment of rent for the prescribed continuous period despite statutory notice. **Output:** complete Eviction Petition with arrears-period chronology, statutory-notice trajectory recital, non-compliance pleading within the prescribed 30-day window, accompanying Section 11(4) MRC Act 1999 / equivalent interim-deposit application.

### 2. `eviction-bona-fide-personal-need-draft`

**Statutory authority:** Section 16(1)(g) Maharashtra Rent Control Act 1999 · Section 14(1)(e) Delhi Rent Control Act 1958 · Section 21(1)(a) UP Urban Buildings Act 1972 (release application before Prescribed Authority) · Section 27(2)(r) Karnataka Rent Act 2001 · Section 6(1)(f) West Bengal Premises Tenancy Act 1997 · Section 10(3) AP / Telangana Act. Anchor cases: *Ragavendra Kumar v. Firm Prem Machinary* (2000) 1 SCC 679 · *Akhileshwar Kumar v. Mustaqim* (2003) 1 SCC 75 · *Sait Nagjee Purushotham & Co. Ltd. v. Vimalabai Prabhulal* (2005) 8 SCC 252 · *Joginder Pal v. Naval Kishore Behal* (2002) 5 SCC 397. **Use case:** landlord requires premises bona-fide for own occupation / family member dependent / relative carrying on business. **Output:** complete Eviction Petition with bona-fide-need pleading, absence-of-other-accommodation declaration, comparative-hardship recital, landlord-is-best-judge-of-his-own-requirement framework, optional Section 25B Delhi Rent Control Act 1958 Chapter IIIA summary-procedure form where invoked SOLELY on this ground, OR UP-distinctive release application before the Prescribed Authority under Section 21 UP Act 1972.

### 3. `eviction-nuisance-damage-draft`

**Statutory authority:** Section 16(1)(c)(d) Maharashtra Rent Control Act 1999 · Section 14(1)(j)(k) Delhi Rent Control Act 1958 · Section 27(2)(d)(e) Karnataka Rent Act 2001 · Section 6(1)(b)(o) West Bengal Premises Tenancy Act 1997 · Section 10(2)(iii)(iv)(v) AP / Telangana Act. **Use case:** landlord seeks eviction for nuisance / annoyance to neighbours OR damage / impairment to value or utility of premises. **Output:** complete Eviction Petition with date-wise particulars of incidents + police complaint annexures + neighbour affidavits + cost-of-repair estimates + photographic evidence framework.

### 4. `eviction-sub-letting-without-consent-draft`

**Statutory authority:** Section 16(1)(e) Maharashtra Rent Control Act 1999 · Section 14(1)(b) Delhi Rent Control Act 1958 · Section 27(2)(b) Karnataka Rent Act 2001 · Section 6(1)(e) West Bengal Premises Tenancy Act 1997 · Section 10(2)(ii)(a) AP / Telangana Act · Section 20(2)(e) UP Urban Buildings Act 1972. Anchor cases: *Resham Singh v. Raghbir Singh* (1999) 7 SCC 263 (inferential evidence) · *Helper Girdharbhai v. Saiyed Mohmad Mirasaheb Kadri* (1987) 3 SCC 538 · *Bharat Sales v. LIC of India* (1998) 3 SCC 1. **Use case:** landlord seeks eviction for unlawful sub-letting / parting with possession of whole or part without written consent of landlord. **Output:** complete Eviction Petition with identity-of-sub-tenant pleading, period-of-sub-tenancy pleading, consideration-paid pleading (direct or inferential — *Resham Singh* framework), absence-of-written-consent pleading, supporting annexures (sub-tenant's utility bills, photographs, neighbour affidavits, society register entries).

### 5. `standard-rent-fixation-application-draft`

**Statutory authority:** Section 7 Maharashtra Rent Control Act 1999 + Section 8 (procedure) + Section 10 (permitted increases) + Section 11 (4% annual statutory increase) · Sections 6-9 Delhi Rent Control Act 1958 (standard rent — pre-1958 / post-1958 distinctions) · Section 14 Karnataka Rent Act 2001 (fair rent) · Sections 17-22 West Bengal Premises Tenancy Act 1997 · Tamil Nadu 2017 Act fair-rent for tenancies governed by the 1960 Act. **Use case:** tenant (or, less commonly, landlord) seeks fixation of the statutory standard rent / fair rent on the cost-construction methodology. **Output:** complete Standard-Rent Application with cost-construction computation, Section 11 statutory-increase cumulative computation, permitted-increase under Section 10 (where amenities / improvements have been provided), Section 9 MRC Act 1999 excess-rent recovery framework.

### 6. `rent-deposit-application-draft`

**Statutory authority:** Section 8 Maharashtra Rent Control Act 1999 · Section 27 Delhi Rent Control Act 1958 · Section 21 Karnataka Rent Act 2001 · Section 21 West Bengal Premises Tenancy Act 1997 · Section 30 UP Urban Buildings Act 1972 · Section 9 AP / Telangana Act. **Use case:** tenant seeks permission to deposit rent in Court / before Rent Controller where landlord refuses to accept rent, refuses to issue receipts, where landlord is in dispute among multiple claimants, or where landlord is absent. **Output:** complete Rent-Deposit Application with reason-for-deposit pleading, notice-to-landlord framework, regular-and-continuous-deposit discipline (protecting tenant against non-payment eviction).

### 7. `tenancy-termination-notice-draft`

**Statutory authority:** Section 106 Transfer of Property Act 1882 (15-day notice post the 2002 amendment, terminating with the end of the tenancy month) + Section 111 TPA 1882 (determination of lease) + applicable State Rent Control Act notice provisions. Anchor case: *V. Dhanapal Chettiar v. Yesodai Ammal* (1979) 4 SCC 214 (State-Rent-Control-Act displacement of Section 106 TPA notice). **Use case:** landlord serves pre-suit notice terminating the contractual tenancy (and triggering the State Rent Control Act statutory tenancy that follows). **Output:** complete Termination Notice on advocate's letterhead with addressee block, cause-of-termination recital, 15-day period, expiry date, demand for vacant possession, warning of legal action, mode-of-service framework (registered post AD / personal / affixture).

### 8. `landlord-recovery-suit-draft`

**Statutory authority:** Order VII Code of Civil Procedure 1908 + Article 52 Limitation Act 1963 (3 years from when arrears become due) + Section 9 CPC + Court Fees Act 1870 / applicable State Court Fees Act (ad valorem on amount sought) + Section 18 Limitation Act 1963 (acknowledgement-of-debt limitation extension). **Use case:** landlord sues for recovery of rent arrears + mesne profits, either as a money-decree suit alone (where premises have been vacated) or combined with eviction (where the State Rent Control Act permits combination). **Output:** complete Plaint with month-by-month arrears ledger, mesne-profits computation on comparable-rents methodology, prayer for decree + interest + costs.

### 9. `tenant-written-statement-draft`

**Statutory authority:** Order VIII Code of Civil Procedure 1908 + applicable State Rent Control Act tenant-protection provisions + *Damadilal v. Parashram* (1976) 4 SCC 645 + *Gian Devi Anand v. Jeevan Kumar* (1985) 2 SCC 683 (statutory-tenancy heritability). **Use case:** tenant defends an eviction petition by filing the statutory written statement under Order VIII CPC + State Act response procedure. **Output:** complete Written Statement with preliminary objections (jurisdiction · maintainability · limitation · Section 106 TPA notice infirmity), para-by-para reply to the petition, additional pleas (statutory tenancy + heritability protection where applicable + deposit-protection on non-payment ground + comparative-hardship on bona-fide-need ground + sub-tenant denial + landlord's-other-accommodation + sham-need).

### 10. `revision-appeal-rent-controller-draft`

**Statutory authority:** Section 34 + Section 35 Maharashtra Rent Control Act 1999 · Section 38 + Section 39 Delhi Rent Control Act 1958 · Section 28 Karnataka Rent Act 2001 · Sections 29-30 West Bengal Premises Tenancy Act 1997 · Section 22 UP Urban Buildings Act 1972 · Section 115 Code of Civil Procedure 1908 · Articles 226 / 227 of the Constitution of India. **Use case:** appeal from the Rent Controller's order to the Rent Control Appellate Bench / District Judge / Appellate Authority constituted under the State Act, OR revision to the High Court on jurisdictional error / error apparent on face of record / perversity. **Output:** complete Memo of Appeal / Revision Memorandum with grounds of appeal / revision, prayer for setting aside the impugned order, accompanying stay application + condonation of delay application where applicable.

### 11. `model-tenancy-act-2021-framework-draft`

**Statutory authority:** Model Tenancy Act 2021 (Central model law) + Section 4 (registration of tenancy agreement within 90 days) + Section 5 (Rent Authority) + Section 6 (Rent Court) + Section 7 (Rent Tribunal) + Section 24 (security deposit cap — 2 months residential / 6 months commercial) + Section 32 (eviction grounds) + Section 35 (procedure) + Section 41 (appeals). **Adoption status:** Andhra Pradesh (first adopter — notified) · Tamil Nadu (modified-adopter via the parallel TN 2017 Act predating MTA) · Uttar Pradesh (draft Bill in process) · other States to follow. **Use case:** pleading before the Rent Authority / Rent Court / Rent Tribunal in States that have adopted the MTA framework; distinct from State-Rent-Control-Act pleadings. **Output:** complete pleading under MTA framework with compulsory-written-tenancy-agreement recital, security-deposit-cap pleading, three-tier-forum routing.

### Shared infrastructure skills

- **`_drafting_common`** — anti-pollution rules, rent-control privacy firewall, AI-style-marker blacklist (with pleading-register preservation — *"hereby"* and *"thereby"* are STANDARD in pleadings, preserved), citation discipline, **Transfer of Property Act 1882 Sections 105-117 general law of lease**, **Section 106 TPA termination notice discipline (15-day post-2002 amendment)**, ***V. Dhanapal Chettiar v. Yesodai Ammal* (1979) 4 SCC 214 State-Act-displacement check**, **doctrine of statutory tenancy and heritability under *Damadilal v. Parashram* (1976) 4 SCC 645 and *Gian Devi Anand v. Jeevan Kumar* (1985) 2 SCC 683**, **Section 14(1)(e) Delhi Rent Control Act 1958 bona-fide personal need framework** (*Ragavendra Kumar* + *Akhileshwar Kumar* + *Sait Nagjee Purushotham* + *Joginder Pal*), **Section 25B Delhi Rent Control Act Chapter IIIA summary procedure**, **sub-tenancy doctrine under *Resham Singh v. Raghbir Singh* (1999) 7 SCC 263**, **standard-rent / fair-rent fixation methodology**, **rent-deposit framework**, **pagdi-system Section 56 MRC Act 1999 jurisprudence**, **Code of Civil Procedure Order VI Rule 15 verification discipline**, **Limitation Act 1963 Article map for rent-control suits**, **Bharatiya Sakshya Adhiniyam 2023 transition**.
- **`_rent_control_drafting_base`** — universal Indian rent-control pleading skeleton (Cause Title with forum + matter type + parties → Statutory Opening → Prelude → FACTS → GROUNDS → PRAYER → Verification → Counsel block → Index → Synopsis → List of Annexures → Accompanying Applications).

---

## The 6-agent drafting pipeline

| Agent | What it reads | What it writes | Key rent-control specialisation |
|---|---|---|---|
| **`reader`** | Every file in the case folder + the case-type skill's expected exhibits list | `case-facts.md` with per-document audit log + privacy-firewalled placeholder mapping in the header | Privacy firewall — substitutes party names + premises descriptions + monthly-rent figures + statutory-notice references + previous-petition numbers + Rent Controller / Court of Small Causes order references + bank account / rent-deposit receipts before downstream AI processing |
| **`format`** | `case-facts.md` + `case-config.md` + case-type SKILL.md + `_rent_control_drafting_base` + State exemplar | `format-shell.md` with applicable State Rent Control Act section + forum nomenclature + Section 106 TPA notice position + court-fee + standard-rent / rent-deposit framework pre-substituted | Resolves State Rent Control Act and applicable section per case-type; loads forum nomenclature (Court of Small Causes / Rent Controller / Civil Judge as Rent Controller / Rent Authority / Rent Tribunal / Prescribed Authority); applies *V. Dhanapal Chettiar* (1979) check |
| **`drafter`** | `case-facts.md` + `format-shell.md` + case-type SKILL.md + `_rent_control_drafting_base` + law PDFs + State exemplar | `draft-v1.md` + `draft-v1.docx` | Writes Cause Title + Statutory Opening + Prelude + Facts (rent-history chronology + ground-specific factual matrix) + Grounds + Prayer + Verification + Counsel block + Index + Synopsis + List of Annexures + Accompanying Applications in formal Indian pleading register; applies *V. Dhanapal Chettiar* discipline |
| **`verifier`** | `draft-v1.md` + `case-facts.md` + `case-config.md` + law PDFs + State exemplar | `verification-report.md` | Anti-hallucination + Section 106 TPA notice / *V. Dhanapal Chettiar* + State Rent Control Act eviction-ground ingredient check + bona-fide need framework + sub-tenancy ingredient check + *Damadilal* / *Gian Devi Anand* heritability + standard-rent / fair-rent methodology cross-foot + rent-deposit framework + Limitation Act + pagdi Section 56 MRC Act + jurisdiction + court-fee + Order VI Rule 15 CPC verification + BSA 2023 transition |
| **`refiner`** | `draft-v1.md` + `verification-report.md` + `case-config.md` + `case-facts.md` | `draft-v2.md` + `draft-v2.docx` | Polish to formal Indian pleading register + internal numbering / Annexure cross-reference / defined-term consistency + privacy-firewall reversal (real values re-substituted from local mapping into final `.docx`) + filing-ready output |
| **`overseer`** | `draft-v2.docx` + `case-facts.md` + `case-config.md` | `opposing-notes.md` + `final-draft.docx` | Opposing-party / Registry critique — bona-fide need infirmities, sub-tenancy infirmities, Section 106 TPA notice infirmities, summary-procedure infirmities, standard-rent computation infirmities, rent-deposit infirmities, Limitation Act infirmities, Order VI Rule 15 CPC verification infirmities |

---

## Installation

This is a Claude-compatible plugin in the Anthropic plugin format. It runs inside the **Claude Desktop application** (available at <https://claude.ai/download>) OR via Claude Code (CLI).

### Option 1 — Claude Desktop application (easiest)

Download the release `.zip` from the **Releases tab** of this repository, then in the Claude Desktop app: **Settings** → **Plugins** → **Upload local plugin** → drag the `.zip` into the upload box.

### Option 2 — Claude Code (CLI) — via the Wolfgang Rush marketplace

```
/plugin marketplace add Wolfgangrush/wolfgang-rush-marketplace
/plugin install indian-rent-control-drafting@wolfgang-rush
```

### Verifying the install

In a Claude session, type:

- *"draft eviction petition non-payment of rent"* — triggers `eviction-non-payment-of-rent-draft`
- *"draft eviction petition bona-fide need"* — triggers `eviction-bona-fide-personal-need-draft`
- *"draft eviction nuisance"* / *"draft eviction damage"* — triggers `eviction-nuisance-damage-draft`
- *"draft eviction sub-letting"* — triggers `eviction-sub-letting-without-consent-draft`
- *"draft standard rent application"* — triggers `standard-rent-fixation-application-draft`
- *"draft rent deposit application"* — triggers `rent-deposit-application-draft`
- *"draft tenancy termination notice"* / *"draft section 106 notice"* — triggers `tenancy-termination-notice-draft`
- *"draft landlord recovery suit"* — triggers `landlord-recovery-suit-draft`
- *"draft tenant written statement"* — triggers `tenant-written-statement-draft`
- *"draft revision rent controller"* / *"draft appeal rent controller"* — triggers `revision-appeal-rent-controller-draft`
- *"draft model tenancy act pleading"* — triggers `model-tenancy-act-2021-framework-draft`

---

## Your first eviction petition — step-by-step walkthrough

Suppose you wish to draft an **Eviction Petition on Bona-Fide Personal Need** ground for a residential flat in Mumbai (Maharashtra Rent Control Act 1999 regime) — landlord requires premises for own occupation as his existing accommodation is being redeveloped.

### Step 1 — create a case folder

```
~/Desktop/cases/
└── eviction-2026-BONA-FIDE-NEED/
    ├── case-config.md              ← declares State + case type + ground + parties
    ├── inputs/
    │   ├── tenancy-agreement-or-affidavit-of-oral-tenancy.pdf
    │   ├── rent-receipts-counterfoils.pdf
    │   ├── section-106-tpa-notice.pdf
    │   ├── postal-ad-of-section-106-notice.pdf
    │   ├── tenant-reply-to-notice.pdf
    │   ├── landlord-title-document.pdf
    │   ├── landlord-no-other-accommodation-affidavit.pdf
    │   ├── redevelopment-notice-from-society.pdf
    │   └── property-tax-clearance.pdf
    └── laws/
        ├── transfer-of-property-act-1882.pdf
        ├── maharashtra-rent-control-act-1999.pdf
        ├── code-of-civil-procedure-1908.pdf
        └── limitation-act-1963.pdf
```

### Step 2 — write `case-config.md`

```yaml
case_type: "eviction-bona-fide-personal-need"
state: "maharashtra"
state_rent_control_act: "Maharashtra Rent Control Act 1999"
section_invoked: "Section 16(1)(g)"
forum: "Court of Small Causes at Mumbai"
ground: "bona_fide_personal_need_own_occupation"
premises_type: "residential_flat_in_cooperative_housing_society"
tenancy_commencement_date: "[Tenancy-Commencement-Date-Placeholder]"
monthly_rent: "[Monthly-Rent-Placeholder]"
section_106_tpa_notice_date: "[Notice-Date-Placeholder]"
filing_date: "2026-06-01"
parties:
  - role: "Petitioner_Landlord"
    party_name: "[Landlord-Placeholder]"
  - role: "Respondent_Tenant"
    party_name: "[Tenant-Placeholder]"
```

### Step 3 — invoke the plugin

Open Claude Desktop or Claude Code, navigate to the case folder, and type:

> *draft eviction petition bona-fide need*

The pipeline runs through Reader → Format → Drafter → Verifier → Refiner → Overseer and outputs `final-draft.docx` ready for court-fee stamping, signature, and filing.

---

## The `case-config.md` file

Minimum fields: `case_type` · `state` · `state_rent_control_act` · `section_invoked` · `forum` · `ground` (where applicable) · `premises_type` · `tenancy_commencement_date` · `monthly_rent` · `section_106_tpa_notice_date` (where applicable) · `filing_date` · `parties`. Case-type-specific fields layer on top — see each case-type SKILL.md.

`.gitignore` excludes `case-config.md` and `case-facts.md` from any git repo.

---

## State coverage and the `state-config/exemplars` layer

The `state-config/exemplars/` folder contains one Markdown file per supported State, encoding:

- The applicable State Rent Control Act + key sections + eviction grounds map
- The exact forum nomenclature (Court of Small Causes / Rent Controller / Civil Judge as Rent Controller / Rent Authority / Rent Tribunal / Prescribed Authority)
- The Section 106 TPA notice position (REQUIRED / DISPLACED per *V. Dhanapal Chettiar*)
- The standard-rent / fair-rent fixation methodology + section
- The rent-deposit procedure + section + forum
- The summary procedure (if any — e.g. Chapter IIIA Sections 25A-C of the Delhi Rent Control Act 1958)
- The pagdi-system recognition (Maharashtra) / customary tenancy
- The Model Tenancy Act 2021 adoption status

Initial coverage in v0.1.0-alpha: Maharashtra · Delhi · Tamil Nadu · Karnataka · West Bengal · Uttar Pradesh · Gujarat · Andhra Pradesh / Telangana. Kerala · Rajasthan · MP · Bihar · Odisha · Punjab · Haryana · Goa · the North-Eastern States in v0.1.x.

---

## Built-in compliance disciplines

See `skills/_drafting_common/SKILL.md` for the full discipline framework. Headline disciplines:

- ***V. Dhanapal Chettiar v. Yesodai Ammal* (1979) 4 SCC 214 discipline** — Section 106 TPA termination notice is NOT mandatory where the State Rent Control Act provides its own self-contained eviction procedure; the Verifier consults the State exemplar
- **Doctrine of statutory tenancy and heritability** — *Damadilal v. Parashram* (1976) 4 SCC 645 + Constitution Bench in *Gian Devi Anand v. Jeevan Kumar* (1985) 2 SCC 683 — statutory tenancy is heritable; commercial-tenancy heritability extended
- **Section 14(1)(e) Delhi Rent Control Act 1958 bona-fide personal need framework** — *Ragavendra Kumar v. Firm Prem Machinary* (2000) 1 SCC 679 (landlord-best-judge) + *Akhileshwar Kumar v. Mustaqim* (2003) 1 SCC 75 (comparative-hardship) + *Sait Nagjee Purushotham* (2005) 8 SCC 252 (landlord's-choice) + *Joginder Pal v. Naval Kishore Behal* (2002) 5 SCC 397 (relative carrying on business)
- **Section 25B Delhi Rent Control Act Chapter IIIA summary procedure** — for SOLELY-Section-14(1)(e) cases; prescribed-form petition + 15-day leave-to-defend window + affidavit support
- ***Resham Singh v. Raghbir Singh* (1999) 7 SCC 263 sub-tenancy framework** — direct or inferential evidence; absence of landlord's written consent
- ***Hiralal Kapur v. Prabhu Choudhury* (1988) 2 SCC 172 non-payment ground discipline** — statutory notice + non-compliance within prescribed window
- **Standard-rent / fair-rent fixation methodology** — Section 7 MRC Act 1999 cost-construction + Section 11 4%-annual statutory increase / Sections 6-9 DRC Act 1958 / Section 14 KRA 2001 / Sections 17-22 WBPT Act 1997
- **Rent-deposit framework** — Section 8 MRC Act 1999 / Section 27 DRC Act 1958 / equivalents; protection against non-payment eviction via regular and continuous deposits
- **Pagdi-system Section 56 MRC Act 1999** (Maharashtra) — statutory recognition; transfer-with-landlord-consent procedure
- **Section 11(4) MRC Act 1999 interim-deposit application** — accompanying application for interim direction to deposit rent during pendency of eviction petition
- **Order VI Rule 15 CPC verification discipline** — deponent identified; para-by-para personal-knowledge vs information split; place + date + signature
- **Limitation Act 1963 framework** — Article 51 mesne profits (3 years); Article 52 rent arrears (3 years); Article 61 mortgagee possession (12 years); State Act prescribed periods for eviction petitions / appeals / revisions
- **Bharatiya Sakshya Adhiniyam 2023 transition** — Section 132 BSA replaces Section 126 IEA (advocate-client privilege); Section 63 BSA replaces Section 65B IEA (electronic record certificate); pleadings post 01 July 2024 cite BSA section numbers

---

## Privacy firewall — extra discipline for rent-control content

Rent-control pleadings contain highly sensitive material — full names of landlord and tenant family members, premises addresses, monthly-rent figures, rent-deposit account numbers, Section 106 TPA notice references, Rent Controller / Court of Small Causes case-numbers, previous-order references. The plugin's privacy discipline:

1. **Reader** substitutes every real party name, real premises description, real monthly-rent figure, real statutory-notice reference, real previous-petition number, real Rent Controller / Court of Small Causes order reference, and real bank account / rent-deposit receipt with structural placeholders before downstream processing.
2. The placeholder → real-value mapping is stored in the header of `case-facts.md` on the user's local machine **only**.
3. **Format / Drafter / Verifier / Overseer** operate **only** on placeholder-substituted content. The underlying AI runtime never holds raw party names, premises descriptions, or rent figures.
4. **Refiner** re-substitutes real values into the final `.docx`, strictly on the user's machine.
5. `.gitignore` excludes `case-facts.md` and `case-config.md` so they cannot be committed accidentally.

---

## Why MIT License

The MIT licence is the most permissive widely-recognised open-source licence. The accompanying `NOTICE.md` does not modify the licence — it documents the provenance and the privilege position so that any future audit can verify the plugin's clean origin.

---

## Sibling plugins

This plugin is the fourteenth in the **Wolfgang Rush** family of Indian legal-drafting plugins. All siblings ship under the same six-agent pipeline (Reader → Format → Drafter → Verifier → Refiner → Overseer) and the family-of-plugins doctrine — each plugin narrowly scoped to one practice area / forum:

| Plugin | GitHub repo | Scope |
|---|---|---|
| `supreme-court-drafting` | [supreme-court-drafting-litigation](https://github.com/Wolfgangrush/supreme-court-drafting-litigation) | SLPs · Writ Art 32 · Transfer · Review · Curative — Supreme Court of India |
| `indian-hc-drafting` | [indian-hc-drafting-litigation](https://github.com/Wolfgangrush/indian-hc-drafting-litigation) | Pleadings across all 25 Indian High Courts (bench-config-aware) |
| `district-court-drafting` | [district-court-drafting-litigation](https://github.com/Wolfgangrush/district-court-drafting-litigation) | Plaints · WS · CPC applications · BNSS complaints across 25+ States |
| `indian-family-drafting` | [indian-family-drafting-litigation](https://github.com/Wolfgangrush/indian-family-drafting-litigation) | HMA · SMA · IDA · matrimonial · custody · DV Act · maintenance · adoption |
| `indian-consumer-drafting` | [indian-consumer-drafting](https://github.com/Wolfgangrush/indian-consumer-drafting) | District / State / NCDRC + medical-negligence + product liability |
| `indian-mact-drafting` | [indian-mact-drafting](https://github.com/Wolfgangrush/indian-mact-drafting) | MV Act 1988 (2019 amended) · *Sarla Verma* + *Pranay Sethi* · state-config |
| `indian-banking-drafting` | [indian-banking-drafting-litigation](https://github.com/Wolfgangrush/indian-banking-drafting-litigation) | DRT · SARFAESI · NI Act 138 · IBC §7 / §95 · DRAT |
| `indian-labour-drafting` | [indian-labour-drafting-litigation](https://github.com/Wolfgangrush/indian-labour-drafting-litigation) | ID Act · POSH · PG · EPF · ESI · MW · IESO + State exemplars |
| `indian-ip-drafting` | [indian-ip-drafting](https://github.com/Wolfgangrush/indian-ip-drafting) | Copyright · Trade Marks · Patents · Designs + HC IP Divisions + Anton Piller / John Doe |
| `indian-tax-drafting` | [indian-tax-drafting](https://github.com/Wolfgangrush/indian-tax-drafting) | Form 35 CIT(A) · Form 36 ITAT · Form 10A · Sec 148A · 263/264 · 271/270A · 144C · 201 · 260A |
| `indian-property-drafting` | [indian-property-drafting-litigation](https://github.com/Wolfgangrush/indian-property-drafting-litigation) | Gift · Exchange · Release · Trust · Wakf · Easement · Partition · Settlement · Mortgage · TIR |
| `indian-contracts-drafting` | [indian-contracts-drafting-litigation](https://github.com/Wolfgangrush/indian-contracts-drafting-litigation) | MSA · NDA · employment · lease · sale · GPA · SHA · will · loan · arbitration |
| `indian-company-drafting` | [indian-company-drafting](https://github.com/Wolfgangrush/indian-company-drafting) | NCLT (241/242 · 245 · 230-232 · 66 · 252 · 213) · NCLAT (421 + 61) · IBC §9 / §10 |
| `indian-rent-control-drafting` (this) | [indian-rent-control-drafting](https://github.com/Wolfgangrush/indian-rent-control-drafting) | Eviction (non-payment / bona-fide need / nuisance / sub-letting) · standard-rent fixation · rent-deposit · termination notice · recovery suit · tenant WS · revision / appeal · MTA 2021 |

Each plugin can be installed independently, each plugin's Rule 36 firewall is narrow and reviewable, each plugin's forum / state discipline is depth-validated within its scope, and the user installs only what they need.

---

## Why this exists

Indian rent-control practice currently has no open-source rent-control-pleading-drafting infrastructure. The State Rent Control Acts vary widely — Maharashtra retains a pagdi-recognising 1999 Act, Delhi runs a 1958 Act with the distinctive Chapter IIIA Section 25B summary procedure for bona-fide need, Tamil Nadu has moved to a Rent Authority + Rent Tribunal framework under the 2017 Act, Karnataka uses the Court of Small Causes Bengaluru for high-rent and Civil Judge as Rent Controller for low-rent, Uttar Pradesh uses the unique release application before the Prescribed Authority under Section 21 of the 1972 Act, the AP / Telangana 1960 Act has its own self-contained procedure, and the Model Tenancy Act 2021 is being rolled out unevenly. Each State has its own eviction-ground numbering, its own Section 106 TPA notice position (*V. Dhanapal Chettiar* (1979) 4 SCC 214 displacement varies), its own standard-rent / fair-rent methodology, and its own rent-deposit procedure.

This plugin codifies the universal rent-control pleading skeleton, the State-by-State eviction-ground map, the Section 106 TPA notice discipline with the *V. Dhanapal Chettiar* check, the bona-fide need framework with the *Ragavendra Kumar* + *Akhileshwar Kumar* + *Sait Nagjee Purushotham* + *Joginder Pal* anchor, the sub-tenancy framework under *Resham Singh*, the statutory-tenancy heritability framework under *Damadilal* and *Gian Devi Anand*, the standard-rent / fair-rent fixation methodology, the rent-deposit framework, the pagdi-system Maharashtra recognition, and the Model Tenancy Act 2021 framework — into machine-readable form.

Foreign legal-AI tools cannot fill this gap. The procedural conventions are jurisdiction-specific; the pleading register is Indian-English-distinct; the State Rent Control Acts are unique-per-State; the Supreme Court anchor cases are Indian; the Section 106 TPA notice discipline is governed by Indian doctrine.

---

## Roadmap

> 🙏 **Honest note on timelines:** Solo-author OSS · ships as time permits · v0.2.0 / v0.3.0 / v0.4.0+ version-numbered targets are indicative scope, not committed dates. Open an issue if a specific feature on a specific timeline matters to your work.

- [x] **v0.1.0-alpha (current)** — universal rent-control pleading skeleton + 11 case-type skills + 6-agent pipeline + privacy firewall + Verifier disciplines + 8 State exemplars (Maharashtra · Delhi · Tamil Nadu · Karnataka · West Bengal · Uttar Pradesh · Gujarat · Andhra Pradesh / Telangana)
- [ ] **v0.1.x** — bug fixes, register polish, formatting refinements; remaining State exemplars (Kerala · Rajasthan · MP · Bihar · Odisha · Punjab · Haryana · Goa · the North-Eastern States)
- [ ] **v0.2.0** — deeper case-type encoding: rent-escalation arbitration framework · tenancy fixation by negotiation · Maharashtra Pagdi-specific transfer-permission applications under Section 56 MRC Act 1999 · commercial-tenancy specialised pleadings · State-specific revision procedures requiring State-Act-specific authoring depth (Karnataka Section 28; UP Section 22)
- [ ] **v1.0.0** — stable release after community-validated formatting and field-testing

---

## Contributing

Advocates with regular rent-control / landlord-tenant practice are invited to contribute state-config calibration. Open a GitHub issue with: practice State + applicable State Rent Control Act + key eviction-ground sections + forum nomenclature + Section 106 TPA notice position + standard-rent / fair-rent methodology + rent-deposit procedure + Model Tenancy Act 2021 adoption status.

Pull requests welcome with one-paragraph explanation + State Act / Rule reference.

This plugin is open source under MIT.

---

## Contact

Author and maintainer: **Rushikesh R. Mahajan**, Advocate, enrolled with the Bar Council of Maharashtra and Goa.

GitHub: <https://github.com/Wolfgangrush>

---

## Author and brand

The author is **Rushikesh R. Mahajan**, Advocate, practising before the Bombay High Court, Nagpur Bench. The plugin is published under the open-source brand **Wolfgang Rush**, which is the author's publishing handle for legal-technology infrastructure. Personal accountability under the Advocates Act 1961 attaches to the author regardless of the use of a publishing handle.

---

## Provenance and privilege statement

See `NOTICE.md` for the full provenance + privilege + privacy + Rule 36 compliance statement. The short version:

- The plugin contains only universal procedural skeletons, formatting conventions, statutory references, and generic placeholders
- The plugin contains no specific client matter, no client communications, no client documents, no personal data of any data principal, and no tracking / telemetry / analytics
- The plugin is, in legal character, identical to a published rent-control commentary — procedural knowledge in machine-readable form
- The author retains full enrolment, full responsibility, and full liability under the Advocates Act 1961 and the Bar Council of India Rules

---

## Compliance posture — Supreme Court e-Committee AI framework

This plugin is **assistive drafting infrastructure**, not autonomous decision-making software. Its operational posture is aligned with the Supreme Court of India e-Committee's stated position on AI in legal work.

> *"AI and digital tools must be used as supportive instruments and should not be allowed to override judicial reasoning."*
>
> — **Justice Rajesh Bindal**, Judge, Supreme Court of India
> [*Judicial Process Re-engineering and Digital Transformation*](https://www.sci.gov.in/press-release-dated-april-12-2026/) conference, 11–12 April 2026
> Organised by the Supreme Court e-Committee in collaboration with the Department of Justice, Government of India.
> ([Coverage — Law Trend](https://lawtrend.in/ai-must-not-replace-judicial-reasoning-warns-supreme-court-justice-rajesh-bindal/))

The same posture underpins the Supreme Court's own AI infrastructure for the judiciary:

- **[SUPACE](https://www.drishtiias.com/daily-news-analysis/ai-portal-supace)** — *Supreme Court Portal for Assistance in Court Efficiency.* AI-enabled assistive tool launched on 6 April 2021 by then-CJI S.A. Bobde. Provides legal research, fact extraction, document review, and drafting assistance to judges and legal researchers. **By design, SUPACE is not a decision-making system** — it processes facts and surfaces them to the human user. The Supreme Court has recommended adoption across all Indian High Courts.

- **[SUVAS](https://www.drishtijudiciary.com/current-affairs/supreme-court-vidhik-anuvaad-software-suvas)** — *Supreme Court Vidhik Anuvaad Software.* AI-powered translation tool launched in November 2019 by then-CJI S.A. Bobde. Translates judicial documents, orders, and judgments between English and ten Indian regional languages.

### What this plugin does — and does not — do under that framework

**Does:**

- Generate structural skeletons of pleadings, drawing on public statutes, schedule forms, and court rules.
- Run a six-agent assistive pipeline (Reader → Formatter → Drafter → Verifier → Refiner → Overseer) over the user's case facts.
- Surface citations, procedural anchors, and bench-specific conventions for advocate review.

**Does NOT:**

- Generate final filings autonomously.
- Substitute for advocate professional judgment.
- Replace human verification.
- Operate without an enrolled advocate retaining full professional responsibility.

**Every draft produced through this plugin must be advocate-owned and human-verified before filing.** The enrolled advocate using this plugin retains full professional responsibility under the Advocates Act 1961 and the Bar Council of India Rules, including verification of facts, accuracy of citations, correctness of legal grounds, propriety of the prayer, and signature on every pleading filed.

This is the same standard the Supreme Court itself applies to its own AI infrastructure (SUPACE / SUVAS): **AI as supportive instrument, never as decision-maker.**

---

## Disclaimer and Bar Council of India Rule 36 compliance

This repository is published as a personal open-source contribution to the legal-technology ecosystem. It is **not** an advertisement of professional services, **not** a solicitation of work, **not** an undertaking to act as counsel in any matter, and **not** a vehicle through which the author accepts professional engagement.

Bar Council of India Rule 36 of the Standards of Professional Conduct and Etiquette prohibits an advocate from soliciting work or advertising professional services through any medium. This repository complies with Rule 36 in both letter and spirit.

The plugin is published in the same legal character as any practitioner's open-source library, public continuing-legal-education contribution, or published textbook chapter — the medium is software, the content is procedural knowledge, the practitioner retains full Bar discipline and accountability.

---

## License

MIT — see `LICENSE`.
