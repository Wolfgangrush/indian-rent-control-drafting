---
name: _drafting_common
description: Shared reference for all 11 rent-control / landlord-tenant case-type drafting skills. Holds the anti-pollution rules, the rent-control privacy firewall protocol (party names + premises descriptions + monthly-rent figures + notice references + Rent Controller / Court of Small Causes case-numbers + previous-order references substituted with placeholders before downstream AI processing; real-value re-substitution local-only in the Refiner step), the AI-style-marker blacklist, citation discipline, Transfer of Property Act 1882 Sections 105-117 general law of lease, Section 106 termination notice discipline, Section 111 determination-of-lease discipline, the doctrine of statutory tenancy and heritability under Damadilal v. Parashram (1976) 4 SCC 645 and Gian Devi Anand v. Jeevan Kumar (1985) 2 SCC 683, the Section 14(1)(e) Delhi Rent Control Act 1958 bona-fide personal need framework with Ragavendra Kumar v. Firm Prem Machinary (2000) 1 SCC 679 and Akhileshwar Kumar v. Mustaqim (2003) 1 SCC 75, the Section 25B Delhi Rent Control Act summary procedure for bona-fide need, the sub-tenancy doctrine under Resham Singh v. Raghbir Singh (1999) 7 SCC 263, the standard-rent / fair-rent fixation methodology, the rent-deposit framework under Section 8 Maharashtra Rent Control Act 1999 / Section 27 Delhi Rent Control Act 1958, the pagdi system jurisprudence under Section 56 Maharashtra Rent Control Act 1999, the Code of Civil Procedure 1908 Order VI Rule 15 verification discipline, the Limitation Act 1963 framework for rent-control suits, and the Bharatiya Sakshya Adhiniyam 2023 transition. NOT invoked directly — referenced from every case-type skill in this plugin.
allowed-tools: Read
---

# `_drafting_common` — shared rent-control drafting infrastructure

## Privacy firewall

Rent-control pleadings routinely contain highly sensitive material — full names of landlord and tenant family members, premises addresses, monthly-rent figures, rent-deposit account numbers, Section 106 TPA notice references, Rent Controller / Court of Small Causes case-numbers, previous-order references, and any documentary exhibits filed by the parties. The plugin's privacy discipline:

1. **Reader** substitutes every real party name, every real premises description, every real monthly-rent figure, every real notice reference, every real Rent Controller / Court of Small Causes / Rent Authority case-number, every real previous-order reference, and every real bank account / deposit receipt reference with structural placeholders before downstream processing.
2. The placeholder → real-value mapping is stored in the header of `case-facts.md` on the user's local machine **only**.
3. **Format / Drafter / Verifier / Overseer** operate **only** on placeholder-substituted content. The underlying AI runtime never holds raw party names, premises descriptions, or rent figures.
4. **Refiner** re-substitutes real values into the final `.docx`, strictly on the user's machine.
5. `.gitignore` excludes `case-facts.md` and `case-config.md` so they cannot be committed accidentally.

## AI-style-marker blacklist

Stripped by the Refiner before output:

- Em-dash (`—`) used as sentence-internal pause (replaced with semicolon or comma-bounded clause); however, em-dashes for genuine appositive structures in pleadings are preserved
- Sentence-final *thereby* / *hereby* / *whereby* without an attached verb (note: *"hereby"* and *"thereby"* are STANDARD in pleading-register and are preserved; this rule applies only to incorrect uses)
- *Moreover*, *furthermore*, *additionally*, *in addition* as sentence-openers — incompatible with pleading register; replaced by *"It is further submitted that"* / *"It is humbly submitted that"*
- *Navigate*, *delve*, *foster*, *robust*, *seamless* (metaphorical uses) — never appear in pleading register
- *It is important to note that*, *it should be noted that*, *worthy of note* — replaced with direct submission
- Bullet-list-style structure in Facts / Grounds (Facts and Grounds are numbered paragraphs, not bullet lists)

## Citation discipline

The Drafter does **not** generate case names + citations from training memory. Every case citation in any Ground or paragraph must trace to a user-supplied source. Untraceable citations become `[CITATION NEEDED]` placeholders for the advocate to fill before filing.

Headline cases the Verifier scans for fabrication:

- *Damadilal v. Parashram* (1976) 4 SCC 645 — statutory tenancy is heritable
- *Gian Devi Anand v. Jeevan Kumar* (1985) 2 SCC 683 — extension of heritability of statutory tenancy to commercial premises (Constitution Bench)
- *Ragavendra Kumar v. Firm Prem Machinary* (2000) 1 SCC 679 — landlord is the best judge of his own requirement under Section 14(1)(e) Delhi Rent Control Act 1958
- *Akhileshwar Kumar v. Mustaqim* (2003) 1 SCC 75 — bona-fide personal need; tenant's comparative hardship under Section 14(6); ingredients
- *Resham Singh v. Raghbir Singh* (1999) 7 SCC 263 — sub-tenancy ground; proof and inference
- *Joginder Pal v. Naval Kishore Behal* (2002) 5 SCC 397 — bona-fide need including for relatives carrying on business
- *Sait Nagjee Purushotham & Co. Ltd. v. Vimalabai Prabhulal* (2005) 8 SCC 252 — bona-fide need; landlord's choice of premises
- *Hiralal Kapur v. Prabhu Choudhury* (1988) 2 SCC 172 — non-payment of rent ground; default and notice
- *V. Dhanapal Chettiar v. Yesodai Ammal* (1979) 4 SCC 214 — Section 106 TPA notice not required where State Rent Control Act provides its own procedure for termination

## Transfer of Property Act 1882 — Sections 105-117 general law of lease

The TPA Sections 105-117 form the bedrock general law of lease that operates wherever the State Rent Control Act does not displace it:

- **Section 105** — Lease defined: a transfer of a right to enjoy immovable property for a certain time, express or implied, in consideration of a price paid or promised
- **Section 106** — Duration of certain leases in absence of written contract or local usage: month-to-month tenancy terminable by 15 days' notice expiring with the end of the tenancy month (post the 2002 amendment, the notice is treated as valid even if it terminates on an earlier date provided 15 days have elapsed)
- **Section 107** — Mode of execution: lease for a term exceeding one year must be by registered instrument
- **Section 108** — Rights and liabilities of lessor and lessee
- **Section 111** — Determination of lease: by efflux of time / by happening of event / by termination notice / by forfeiture / by implied surrender / by express surrender / by merger
- **Section 114 / 114A** — Relief against forfeiture for non-payment of rent / for other breach

## Section 106 TPA termination notice discipline

For any month-to-month tenancy, before instituting an eviction suit (and before invoking the State Rent Control Act eviction grounds in those jurisdictions where the State Act requires it), the landlord must serve a notice terminating the tenancy:

- **Period of notice:** 15 days (Section 106 as amended in 2002)
- **Manner of service:** by post / by personal service / by affixture / by registered post acknowledgement due (mode prescribed by Section 106(4))
- **Form:** in writing, signed by or on behalf of the person giving the notice
- **Expiry:** terminating with the end of the tenancy month, OR (post-2002 amendment) treated as valid if 15 days have elapsed even if expiry is on an earlier date

However, per *V. Dhanapal Chettiar v. Yesodai Ammal* (1979) 4 SCC 214 — where the State Rent Control Act provides its own self-contained eviction procedure (as in Tamil Nadu / Karnataka / Andhra-Telangana / Delhi for some grounds), a Section 106 TPA notice is NOT mandatory; the State Rent Control Act notice provisions govern. The Verifier checks the State exemplar to confirm whether a Section 106 notice is required, dispensed with, or read together with the State Act notice.

## Doctrine of statutory tenancy and heritability

A contractual tenancy, once terminated, gives way to a *statutory tenancy* — a status conferred by the State Rent Control Act under which the tenant retains possession by force of statute notwithstanding the termination of the contractual tenancy. The statutory tenant cannot be evicted save under the State Rent Control Act's enumerated grounds.

Per *Damadilal v. Parashram* (1976) 4 SCC 645 and the Constitution Bench in *Gian Devi Anand v. Jeevan Kumar* (1985) 2 SCC 683 — the statutory tenancy is HERITABLE on the death of the tenant. The heirs step into the shoes of the statutory tenant and continue to enjoy the protection of the State Rent Control Act. This applies to residential and commercial premises alike (Gian Devi Anand extended the heritability doctrine to commercial tenancies, settling earlier conflicting High Court views).

State Rent Control Acts may modify the heritability doctrine — e.g. the Maharashtra Rent Control Act 1999 Section 7(15) lists the categories of heirs entitled to succeed and limits the period of post-death succession.

## Section 14(1)(e) Delhi Rent Control Act 1958 — bona-fide personal need framework

The ground of *bona-fide personal need* (variously named — bona-fide requirement / reasonable and bona-fide requirement / personal occupation) is the most commonly invoked eviction ground in Indian rent-control litigation. The Section 14(1)(e) Delhi Rent Control Act 1958 framework, and the parallel provisions in other State Rent Control Acts, share these ingredients:

1. The landlord must require the premises for his own occupation, OR for the occupation of any member of his family dependent on him, OR for any person for whose benefit the premises are held (a beneficial-owner concept), OR for any of his relatives (per *Joginder Pal v. Naval Kishore Behal* (2002) 5 SCC 397, the relative may carry on business in the premises and that still counts as bona-fide need of the landlord)
2. The premises are residential (Section 14(1)(e) DRC Act is specifically for residential premises; non-residential premises under DRC Act go under Section 14A and other sub-clauses) — State Rent Control Acts vary on whether they cover residential, non-residential, or both
3. The landlord has no other reasonably suitable residential accommodation
4. The need is bona-fide (genuine, not a cloak for a higher rent / a sale, not a tactical eviction)

Per *Ragavendra Kumar v. Firm Prem Machinary* (2000) 1 SCC 679 — the landlord is the best judge of his own requirement; the Court does not sit in judgment over the wisdom of the landlord's choice of premises. Per *Akhileshwar Kumar v. Mustaqim* (2003) 1 SCC 75 — the Court must, however, consider the comparative hardship of the tenant under Section 14(6) and similar provisions. Per *Sait Nagjee Purushotham & Co. Ltd. v. Vimalabai Prabhulal* (2005) 8 SCC 252 — the landlord's choice of which premises to occupy among multiple owned is his alone.

## Section 25B Delhi Rent Control Act — summary procedure for bona-fide need

Where the eviction is sought ONLY on Section 14(1)(e) DRC Act bona-fide personal need ground (NOT in combination with other grounds), the landlord may invoke the SUMMARY PROCEDURE under Chapter IIIA of the DRC Act (Sections 25A to 25C):

- Application in the prescribed form
- Summons issued in the Section 25B(2) prescribed form
- Tenant must apply for leave to defend within 15 days of service of summons
- Tenant's leave application must be supported by an affidavit disclosing facts which would disentitle the landlord from obtaining an order for recovery of possession
- If leave is refused, the application is decreed forthwith
- If leave is granted, the application proceeds in the manner of an ordinary suit

The Verifier checks whether the petition is under the summary procedure and, if so, confirms the prescribed-form leave-to-defend recitals are observed.

## Sub-tenancy doctrine

State Rent Control Acts generally prohibit sub-letting / parting with possession without the landlord's written consent. The eviction ground is invoked where the tenant has (a) sub-let the whole or any part of the premises, OR (b) parted with possession of the whole or any part, WITHOUT the written consent of the landlord.

Per *Resham Singh v. Raghbir Singh* (1999) 7 SCC 263 — sub-tenancy may be proved by direct evidence (sub-tenancy agreement / rent receipts issued by the tenant to the sub-tenant) OR by inference from circumstances (exclusive possession of the sub-tenant + payment of consideration to the tenant). The landlord must plead and prove BOTH (a) parting with possession AND (b) for consideration / for value, although mere parting with possession even without consideration may be an offence under some State Acts.

## Standard-rent / fair-rent fixation methodology

Most State Rent Control Acts provide a methodology for fixation of *standard rent* (Maharashtra) / *fair rent* (Karnataka, Tamil Nadu 2017 Act for old tenancies, Delhi, Kerala) — a statutory cap on the rent leviable in respect of the premises. The methodology typically rests on:

- **Cost-construction basis** — a percentage return (e.g. 6.25% to 8.25%) on the cost of construction + land value, with depreciation
- **Market-rent basis** (in some Acts) — comparable rents of similar premises in the locality
- **Statutory increase basis** — periodic statutory increases (e.g. 4% annual under Section 11 Maharashtra Rent Control Act 1999) capped above the base rent

The standard-rent / fair-rent application is filed by either party (more commonly the tenant) and is decided by the Rent Controller / Rent Court. Pending fixation, the tenant must continue to pay the agreed rent or the provisional rent fixed by the Court.

The Maharashtra Rent Control Act 1999, Section 7 read with Section 8, provides:

- Standard rent fixation per the cost-construction formula
- Section 11 statutory increase of 4% per annum on standard rent
- Permitted increases for amenities / improvements (Section 10)
- Tenant entitled to recover excess rent paid above standard rent (Section 9)

## Rent-deposit framework

Where the landlord refuses to accept rent or where the tenant is unsure whom to pay (e.g. landlord disputed, multiple claimants), the State Rent Control Act provides a rent-deposit procedure:

- **Section 8 Maharashtra Rent Control Act 1999** — deposit with the Court of Small Causes; notice to landlord; landlord may withdraw without prejudice
- **Section 27 Delhi Rent Control Act 1958** — deposit with the Rent Controller; notice; landlord may withdraw
- Parallel provisions in Tamil Nadu, Karnataka, Andhra Pradesh / Telangana, West Bengal, UP Acts

Deposit of rent in accordance with the State Rent Control Act procedure constitutes valid tender and PROTECTS the tenant against the non-payment-of-rent eviction ground, provided the deposits are regular and continuous.

## Pagdi system (Maharashtra)

The *pagdi* system, recognised in Section 56 of the Maharashtra Rent Control Act 1999, is a customary tenancy arrangement under which the tenant pays a substantial lump sum (the *pagdi*) at the inception of the tenancy in addition to a nominal monthly rent. The pagdi tenant has heightened rights — including the right to transfer the tenancy with the landlord's consent and a share in the redevelopment proceeds — and is recognised as a special class of tenant under the Maharashtra Act.

The Maharashtra Rent Control Act 1999 was the first State legislation to give statutory recognition to the pagdi system; prior to 1999, the system operated under customary law and judicial recognition (see the line of Bombay High Court decisions).

## Code of Civil Procedure 1908 — verification discipline

Order VI Rule 15 CPC requires every pleading to be verified at the foot by the party or by one of the parties pleading or by some other person proved to the satisfaction of the Court to be acquainted with the facts of the case. The Verification block:

- Identifies the deponent
- States which paragraphs are verified on personal knowledge
- States which paragraphs are verified on information received and believed to be true
- States the place and date

Post the Commercial Courts Act 2015 amendment, every pleading must additionally be accompanied by a Statement of Truth in the prescribed form (in commercial matters; not generally applicable in rent-control pleadings but the Statement of Truth discipline is creeping into rent-control practice in some High Courts).

## Limitation Act 1963 — rent-control suits framework

| Matter | Article | Period |
|---|---|---|
| Suit for recovery of arrears of rent | Article 52 | 3 years from when the arrears become due |
| Suit for recovery of mesne profits | Article 51 | 3 years from when the profits are received by the person in wrongful possession |
| Suit by mortgagee for possession of immovable property | Article 61 | 12 years from when the mortgagee becomes entitled to possession |
| Eviction petition under State Rent Control Act | State Act prescribed (typically no limitation; the cause of action runs from the date of default / notice / accrual of ground) | — |
| Appeal under State Rent Control Act | State Act prescribed (typically 30 days from order; extendable on sufficient cause) | — |
| Revision under State Rent Control Act / Article 227 Constitution / Section 115 CPC | 90 days (revision) / reasonable time (Article 227); some State Acts prescribe a shorter period | — |
| Standard-rent / fair-rent fixation application | No specified limitation; runs with the tenancy | — |
| Rent-deposit application | No specified limitation; runs as long as the tenant tenders rent | — |

## Bharatiya Sakshya Adhiniyam 2023 transition

The Indian Evidence Act 1872 is now replaced by the Bharatiya Sakshya Adhiniyam 2023 (BSA), in force from 01 July 2024. Key transitional impacts on rent-control practice:

- Section 132 BSA replaces Section 126 IEA (advocate-client privilege)
- Section 60 BSA replaces Section 65 IEA (secondary evidence)
- Section 63 BSA replaces Section 65B IEA (electronic record certificate)
- Section 65 BSA replaces Section 67 IEA (proof of execution by attesting witness)

Pleadings filed after 01 July 2024 cite BSA section numbers (with parenthetical IEA reference for the transition period). Citations in pleadings drawn before the transition retain IEA section numbers. The Drafter applies the rule from `case-config.md` `filing_date` field.

## OUTPUT FORMAT — pandoc + shipped reference.docx

The Drafter writes a Markdown intermediate (`draft-v1.md`) and converts to `.docx` via pandoc using the shipped reference.docx at `${CLAUDE_PLUGIN_ROOT}/skills/_rent_control_drafting_base/reference.docx` — pre-customised with locked Word styles (TNR 14pt body 1.5 line spacing 4cm-left margin, Heading 1 bold centered, Heading 2 bold centered with letter-spacing for the spaced `F A C T S` effect, Heading 3 bold left, fixed table layout).

```bash
pandoc draft-v1.md -o draft-v1.docx \
  --reference-doc="${CLAUDE_PLUGIN_ROOT}/skills/_rent_control_drafting_base/reference.docx" \
  --from=markdown+pipe_tables+raw_tex
```

The Drafter MUST use the shipped reference.docx or a per-case override. NEVER auto-generate a fresh one (that produces v0.1.0 render defects — title not bold, section headers left-aligned, tables wrapping). Filename convention: `<case-type>_draft-v<N>_<YYYY-MM-DD>.docx`. Never overwrite an existing draft.

## PIPELINE-OPTIONALITY (load-bearing — advocate-cost discipline)

The full 6-agent pipeline (Reader → Format → Drafter → Verifier → Refiner → Overseer) is **NOT** mandatory. As of v0.2.0-alpha, only the first three stages are required to produce a filing-grade draft. The remaining three are OPTIONAL QC layers the advocate explicitly invokes.

```
┌────────────────────────────────────────────────────────────┐
│  REQUIRED (default exit point)                              │
│  Stage 1  Reader   →  case-facts.md                         │
│  Stage 2  Format   →  format-shell.md                       │
│  Stage 3  Drafter  →  draft-v1.docx   (filing-grade)        │
│  ── default exit ──                                         │
│  OPTIONAL QC (advocate opts in)                             │
│  Stage 4  Verifier  →  verification-report.md               │
│  Stage 5  Refiner   →  draft-v2.docx                        │
│  Stage 6  Overseer  →  final-draft.docx + opposing-notes.md │
└────────────────────────────────────────────────────────────┘
```

Each stage is itself a Claude subagent run (~80–120K tokens). Running all six on every draft can exhaust the advocate's Claude session limit. The QC stages are valuable for contested eviction matters with significant pecuniary stakes, but disproportionate for routine tenancy-termination notices and rent-deposit applications.

## VERBOSITY DISCIPLINE

| Case type | Main pleading target | Hard ceiling |
|---|---|---|
| Eviction (any ground) | 3,000–4,500 words | 6,000 |
| Standard rent fixation | 2,500–3,500 words | 4,500 |
| Rent deposit application | 1,500–2,500 words | 3,500 |
| Tenancy termination notice | 800–1,500 words | 2,000 |
| Recovery suit | 3,000–4,500 words | 6,000 |
| Tenant written statement | 2,500–4,000 words | 5,500 |
| Revision / Appeal | 4,000–5,500 words | 7,500 |

Compression rules: one paragraph per ground (not three); ceremonial phrases used sparingly; Synopsis ≤ 2 pages; if draft exceeds ceiling, compress before signalling Verifier.

## MARKDOWN HEADING DISCIPLINE

Drafter writes Markdown using `# Heading 1` for forum header / case-number / cover-page anchors, `## Heading 2` for section headers (`## F A C T S`, `## G R O U N D S`, `## P R A Y E R`, `## V E R I F I C A T I O N`, `## I N D E X`, `## S Y N O P S I S`, `## L I S T   O F   A N N E X U R E S`), `### Heading 3` for ground sub-headers and Accompanying Application titles. Pandoc maps the headings to the locked Word styles in `_rent_control_drafting_base/reference.docx`. The rendered .docx shows them as bold-centered-spaced section titles, not as `##` characters.

Cover-page discipline: INDEX, SYNOPSIS, LIST OF ANNEXURES each begin on `\newpage` and carry ONLY forum header + case-number + short cause-title + section header + content + counsel block. Full party address block stays on the Main Petition cover only.


---

## v0.2.2 OUTPUT-PAIRING DISCIPLINE (load-bearing — every agent must follow)

**Every `.md` output artifact MUST be paired with a `.docx`.** Advocates do not natively read Markdown — they read Word. Every pipeline output (case-facts.md from Reader, format-shell.md from Format, draft-v1.md from Drafter, verification-report.md from Verifier, draft-v2.md from Refiner, opposing-notes.md from Overseer) must have a corresponding `.docx` rendered with the same locked Word styles.

**This plugin produces pleadings** — the shipped reference.docx is the pleading variant (TNR 14pt 1.5 spacing, Heading 2 bold + UNDERLINED + centered with letter-spacing for the spaced `F A C T S` effect).

### How to produce the paired `.docx`

Every agent runs the shipped helper script as its final post-`.md`-write step:

```bash
bash "${CLAUDE_PLUGIN_ROOT}/skills/_rent_control_drafting_base/pair_md_to_docx.sh" <output.md>
```

The helper:
1. Resolves the reference.docx in `${CLAUDE_PLUGIN_ROOT}/skills/_rent_control_drafting_base/reference.docx`
2. Runs pandoc with `--reference-doc` and `--from=markdown+pipe_tables+raw_tex` to produce the `.docx`
3. Runs the shipped `fix_docx_tables.py` to force column widths on every table

For overriding (e.g., a per-case-folder reference.docx), pass the reference.docx as the second argument:

```bash
bash "${CLAUDE_PLUGIN_ROOT}/skills/_rent_control_drafting_base/pair_md_to_docx.sh" \
    <output.md> <case-folder>/reference.docx
```

### Per-agent output-pairing map

| Agent | `.md` output | Paired `.docx` |
|---|---|---|
| Reader | `case-facts.md` | `case-facts.docx` |
| Format | `format-shell.md` | `format-shell.docx` |
| Drafter | `draft-v1.md` | `draft-v1.docx` |
| Verifier | `verification-report.md` | `verification-report.docx` |
| Refiner | `draft-v2.md` | `draft-v2.docx` |
| Overseer | `opposing-notes.md` + `final-draft.md` | `opposing-notes.docx` + `final-draft.docx` |

Every agent calls `pair_md_to_docx.sh` once for each `.md` it writes. Skipping this step leaves the advocate with `.md` files that cannot be opened natively in Word.
