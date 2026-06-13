# NOTICE — Provenance and Privilege Statement

This document is part of the public release of the `indian-rent-control-drafting` plugin (v0.1.0-alpha and onwards). It declares the provenance of the plugin's content, in order to address any question about advocate-client privilege, client confidentiality, professional ethics, personal-data protection, commercial confidentiality, and Rent Controller / Court of Small Causes recognition that may be raised by any reader, complainant, regulator, or Bar Council disciplinary authority.

The plugin is **case-config-aware** and **state-config-aware**: the universal structural skeleton of any Indian rent-control / landlord-tenant pleading is uniform across pleading-types, and the user supplies the parties' chosen Rent Controller / Court of Small Causes / Rent Authority / Rent Tribunal / Prescribed Authority forum, the applicable State Rent Control Act, the ground of eviction relied upon, the tenancy commencement date, the last paid rent figure, the statutory notice trajectory, and the standard-rent / fair-rent / rent-deposit history via a `case-config.md` file in the case folder and the relevant `state-config/exemplars/<state>.md` exemplar.

This NOTICE is published in plain language so that any reader — practising advocate, Rent Controller, Judge of the Court of Small Causes, Rent Authority officer, Rent Tribunal Member, Bar Council officer, regulator, member of the public, fellow developer — can understand the position without ambiguity.

---

## 1. What this plugin contains

This plugin contains the following categories of content, and **only** the following categories of content:

(a) **Universal rent-control / landlord-tenant pleading skeleton** — the structural shape of any Indian rent-control eviction petition, standard-rent fixation application, rent-deposit application, tenancy-termination notice, landlord recovery suit, tenant written statement, and revision / appeal (Cause Title with forum + matter type + parties; Statutory Opening invoking the applicable State Rent Control Act provisions; Prelude with tenancy origin, last paid rent, statutory notice history, and standing of the petitioner; Facts paragraphs with the rent-history chronology and the eviction-ground-specific factual matrix; Grounds; Prayer; Verification; Counsel block; Index; Synopsis; List of Annexures; Accompanying Applications).

(b) **Formatting conventions** — text-formatting conventions for Indian rent-control pleadings (Cause Title in title case; statutory opening citing the section and the State Rent Control Act; defined terms in bold on first use; numbered paragraphs in Facts; numbered Grounds; Prayer in capitalised sub-paragraphs; Annexure markers in inline brackets; Verification block in the standard CPC Order VI Rule 15 form; signature block).

(c) **Statutory references** — citations to public statutes (Transfer of Property Act 1882 — particularly Sections 105-117 [general law of lease], Section 106 [termination notice], Section 111 [determination of lease]; Maharashtra Rent Control Act 1999; Delhi Rent Control Act 1958; Tamil Nadu Regulation of Rights and Responsibilities of Landlords and Tenants Act 2017; Karnataka Rent Act 2001; West Bengal Premises Tenancy Act 1997; Uttar Pradesh Urban Buildings (Regulation of Letting, Rent and Eviction) Act 1972; Gujarat Rent Control Act 1947 [as amended]; Andhra Pradesh / Telangana Buildings (Lease, Rent and Eviction) Control Act 1960; Model Tenancy Act 2021; Code of Civil Procedure 1908 — including Order VI Rule 15 [verification], Order VII Rule 1 [plaints], Order VIII Rule 1 [written statements]; Limitation Act 1963; Bharatiya Sakshya Adhiniyam 2023; Bharatiya Nagarik Suraksha Sanhita 2023 [for execution-side cross-references]; Indian Stamp Act 1899 [for stamp on plaints / petitions]; Court Fees Act 1870 / applicable State Court Fees Act).

(d) **Procedural rule references** — citations to public rules (the various State Rent Control Rules made under the parent State Rent Control Acts; the Court of Small Causes Rules and Practice Directions of the High Courts having jurisdiction; the Rent Controller Practice Directions issued by the State Governments; the Rent Authority and Rent Tribunal Regulations under the Tamil Nadu / Model Tenancy regimes; the Civil Procedure Code Rules of the High Courts; the Limitation Act Schedule).

(e) **Generic placeholders** — every variable in every template is a placeholder (`[Landlord]`, `[Tenant]`, `[Sub-Tenant]`, `[Premises]`, `[Tenancy-Commencement-Date]`, `[Monthly-Rent]`, `[Last-Paid-Rent-Date]`, `[Notice-Date]`, `[Standard-Rent-Application-No.]`, `[Rent-Deposit-Receipt-No.]`, `[Rent-Controller-Court]`, `[Court-of-Small-Causes-Bench]`, `[Petition-Number]`, `[Prayer-Eviction-Ground]`). No placeholder is filled with any specific tenancy, party, premises description, rent figure, notice reference, or identifying information.

(f) **Anti-hallucination and privacy-firewall workflow** — six agents (Reader, Format, Drafter, Verifier, Refiner, Overseer) that operate on a case folder supplied by the user. The plugin itself contains no case folder. The Reader substitutes every party name, every premises description, every rent figure, every notice reference, every previous petition reference, every previous order reference, and every Court of Small Causes / Rent Controller case-number with placeholders before downstream AI processing.

---

## 2. What this plugin does NOT contain

This plugin does **not** contain any of the following, and has never contained any of the following at any point in any committed version:

(a) **No specific client matter or tenancy.** No client of the author, and no specific landlord, tenant, sub-tenant, premises, or rent dispute handled by the author or any client, appears in the plugin — by name, by premises description, by rent figure, by tenancy-commencement date, by notice-date, by Rent Controller / Court of Small Causes / Rent Authority case-number, by previous-order reference, or by any other identifying signature.

(b) **No client communications.** No oral or written communication made to the author by or on behalf of any client (whether a landlord, tenant, sub-tenant, co-owner of demised premises, mortgagee in possession, or any other party) appears in the plugin in any form.

(c) **No client documents.** No document or instrument with which the author has become acquainted in the course of professional employment as an advocate appears in the plugin, in original, in redacted, in summary, in extract, or in pattern. This includes — but is not limited to — tenancy agreements, rent receipts, rent deposit receipts, statutory notices issued under Section 106 TPA / Section 15 Maharashtra Rent Control Act / Section 14 Delhi Rent Control Act, replies to notices, eviction petitions, standard-rent applications, rent-deposit applications, written statements, orders of the Rent Controller, decrees of the Court of Small Causes, and appellate orders.

(d) **No personal data of any data principal.** The plugin processes no personal data, collects no personal data, stores no personal data.

(e) **No specific premises description, no specific monthly-rent figure, no specific notice trajectory, no specific Rent Controller or Court of Small Causes case-number** of any specific tenancy.

(f) **No client list, no chamber list, no associate list, no opposing-counsel list, no Rent-Controller-specific intelligence, no Court-of-Small-Causes-bench-specific intelligence.**

(g) **No tracking, no telemetry, no analytics, no opt-in error reporting, no login, no account, no cloud sync.** The plugin runs entirely on the user's machine. The author receives no information about who installs the plugin, who uses it, on what tenancies, with what rent figures, with what outcomes. The Claude Code runtime itself does not track plugin usage, and the plugin author neither operates nor integrates with any analytics, telemetry, or remote logging service.

---

## 3. The legal distinction

Indian law has long recognised a clear distinction between two categories:

(i) **Specific client communications and documents** — protected under Section 132 of the Bharatiya Sakshya Adhiniyam 2023 (formerly Section 126 of the Indian Evidence Act 1872) and under Rule 17 of the Bar Council of India Standards of Professional Conduct and Etiquette. This category is privileged and confidential.

(ii) **General professional knowledge of rent-control law, landlord-tenant practice, and rent-control pleading drafting** — an advocate's accumulated knowledge of how an eviction petition is structured under Section 16 of the Maharashtra Rent Control Act 1999 or Section 14 of the Delhi Rent Control Act 1958, what the Section 106 TPA notice requires (15-day notice for month-to-month tenancy after the 2002 amendment, terminating with the end of the tenancy month), how the *Damadilal v. Parashram* (1976) 4 SCC 645 and *Gian Devi Anand v. Jeevan Kumar* (1985) 2 SCC 683 discipline on the heritability of statutory tenancy works, how the *Ragavendra Kumar v. Firm Prem Machinary* (2000) 1 SCC 679 and *Akhileshwar Kumar v. Mustaqim* (2003) 1 SCC 75 framework on bona-fide personal need operates under Section 14(1)(e) of the Delhi Rent Control Act 1958, how the Section 25B summary procedure functions, how the *Resham Singh v. Raghbir Singh* (1999) 7 SCC 263 discipline on sub-tenancy without written consent applies, how standard-rent / fair-rent is computed under Section 7 of the Maharashtra Rent Control Act 1999, how rent-deposit is effected under Section 8 of the Maharashtra Rent Control Act 1999 / Section 27 of the Delhi Rent Control Act 1958, and the State-specific Rent Controller / Court of Small Causes / Rent Authority forum-nomenclature taxonomy. This category is the advocate's own professional knowledge. It is not the property of any specific client. It is not privileged.

This plugin operates **entirely within category (ii)**.

Every Indian advocate accumulates this knowledge through years of practice, through study of Mulla on the Transfer of Property Act, Sarkar's Tenancy and Rent Control Laws, Tandon's Transfer of Property Act, the Maharashtra Rent Control Act commentaries, the Delhi Rent Control Act commentaries, the Karnataka Rent Act commentary, the Tamil Nadu 2017 Act commentary, the Code of Civil Procedure commentaries (Mulla CPC, Sarkar CPC), the Limitation Act commentaries, and the case-law of the Supreme Court and the High Courts on rent control, tenancy, and landlord-tenant disputes. The plugin codifies that accumulated procedural knowledge into machine-readable form. It does not codify any client's confidential information.

The plugin is, in this respect, identical in legal character to a published rent-control commentary, a continuing legal education handout, or a senior advocate's drafting-style lecture. The medium is software. The content is procedural knowledge.

---

## 4. The author's professional position

The author is **Rushikesh R. Mahajan**, Advocate, enrolled with the Bar Council of Maharashtra and Goa, practising before the High Courts of India. The plugin is published under the open-source brand **wolfgang_rush**, which is the author's publishing handle for legal-technology infrastructure; the real-identity accountability declared in this section attaches to the author personally and is not displaced by the use of a publishing handle.

The author retains full enrolment, full responsibility, and full liability under the Advocates Act 1961, the Bar Council of India Rules, and the Standards of Professional Conduct and Etiquette.

The plugin is published as a personal contribution to the open-source legal-technology ecosystem. It is published without any commercial channel, without any solicitation of professional work, without any advertisement of professional services, and without any acceptance of work through this repository.

This NOTICE is filed of record in this open-source repository so that any person who reads, reviews, audits, or assesses this plugin has full transparency about its provenance and its scope from the moment of release.

---

## 5. Verification of clean provenance

The repository owner shall maintain, on a private offline record, a build log demonstrating that every line of every file in the plugin was either:

(a) authored from scratch as procedural skeleton, OR
(b) derived from public statute, public rule, public judgment, or public rent-control / landlord-tenant textbook, OR
(c) derived from the author's own original procedural knowledge as a practitioner.

No line of any file was, at any stage, copied from, paraphrased from, summarised from, or pattern-matched against any specific client matter, tenancy, client communication, or client document.

This NOTICE is the author's signed declaration of that position.

---

## 6. Reporting concerns

If any reader, regulator, fellow advocate, Rent Controller, Judge of the Court of Small Causes, or member of the public believes any specific content in this plugin is derived from a specific client matter or specific confidential communication, the reader is requested to:

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
