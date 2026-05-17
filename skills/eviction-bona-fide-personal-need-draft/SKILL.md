---
name: eviction-bona-fide-personal-need-draft
description: Draft an Eviction Petition on the ground of BONA FIDE PERSONAL NEED / REQUIREMENT FOR OWN OCCUPATION under Section 16(1)(g) of the Maharashtra Rent Control Act 1999, Section 14(1)(e) of the Delhi Rent Control Act 1958 (with the Section 25B summary-procedure overlay where applicable), Section 21(1)(a) of the UP Urban Buildings Act 1972 (release application before the Prescribed Authority), Section 27(2)(r) of the Karnataka Rent Act 2001, Section 6(1)(f) of the West Bengal Premises Tenancy Act 1997, and Section 10(3) of the AP / Telangana Buildings Control Act 1960. Encodes the bona-fide-need ingredients (landlord requires the premises for self / family member / dependent relative; no other reasonably suitable accommodation; need is honest, real, and not a mere desire), the comparative-hardship discipline under Section 14(6) DRC Act / Section 16(2) MRC Act / equivalent, the Section 25B DRC summary procedure (leave-to-defend stage), and the binding SCC framework (Ragavendra Kumar v. Firm Prem Machinary (2000) 1 SCC 679; Akhileshwar Kumar v. Mustaqim (2003) 1 SCC 75; Sait Nagjee Purushotham (2005) 8 SCC 252; Joginder Pal v. Naval Kishore Behal (2002) 5 SCC 397). Auto-fires on "draft eviction petition bona fide need", "draft eviction bona fide personal need", "draft eviction own use", "draft RAE bona fide", and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# Eviction (Bona Fide Personal Need) Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_rent_control_drafting_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Case metadata

```yaml
case_type_line: PETITION FOR EVICTION (BONA FIDE PERSONAL NEED)
case_short_code: EVICTION_BFN
role_party_1: Landlord / Petitioner
role_party_2: Tenant / Respondent
typical_forum: "Maharashtra — Court of Small Causes / Civil Judge as Rent Controller · Delhi — Additional Rent Controller (with Section 25B summary procedure available SOLELY on bona-fide ground) · UP — Prescribed Authority under Section 21 (release application; NOT a suit) · Karnataka — Court of Small Causes / Civil Judge as Rent Controller · West Bengal — Civil Judge (Junior Division) · AP/Telangana — Rent Controller"
typical_court_fee: "Fixed court fee on eviction relief (per State Court Fees Act). UP release application before Prescribed Authority — application fee per UP Rules; not ad valorem."
operative_paragraphs:
  - "Facts paragraph — *'It is most respectfully submitted that the Petitioner is the lawful owner / landlord of the premises bearing No. [_____] situate at [_____] (hereinafter \"the suit premises\"), and the Respondent has been in occupation of the suit premises as a monthly tenant under the Petitioner at a monthly rent of Rs. [_____].'*"
  - "Bona-fide need recital — *'The Petitioner reasonably and bona fide requires the suit premises for his / her own occupation / for the occupation of [his son / her daughter / his spouse / dependent parent / etc.], who is wholly dependent upon the Petitioner. The Petitioner / the said family member is presently constrained to reside in [describe present cramped / inadequate / inconvenient accommodation], which is wholly inadequate having regard to [family size / changed circumstances / specific need such as setting up of independent business / accommodation of dependent elderly parents / etc.].'*"
  - "No other suitable accommodation — *'The Petitioner verily submits that he / she has no other reasonably suitable residential / non-residential accommodation of his / her own in [city / municipal limits] which can meet the said requirement. The properties owned by the Petitioner, if any, are: [list with explanations of why unsuitable / occupied / encumbered].'*"
  - "Comparative hardship — *'It is submitted that greater hardship would be caused to the Petitioner by refusing the decree of eviction than would be caused to the Respondent by granting it, having regard to [Respondent's alternate accommodation / Respondent's financial means / Respondent's family circumstances]. The Respondent owns / has access to alternate accommodation at [_____] and / or has the means to secure alternative tenancy at the prevailing market rate.'*"
  - "Statutory notice — *'The Petitioner has caused to be served upon the Respondent a notice dated [_____] under Section 16(1)(g) of the Maharashtra Rent Control Act 1999 [or State equivalent] terminating the tenancy and calling upon the Respondent to quit and deliver vacant possession of the suit premises on the expiry of the tenancy.'*"
  - "Prayer — *'It is therefore most respectfully prayed that this Hon'ble Court may be pleased to: (a) pass a decree for eviction directing the Respondent to quit, vacate, and deliver vacant and peaceful possession of the suit premises to the Petitioner on the ground of bona fide personal requirement; (b) award mesne profits at the prevailing market rate from the date of the petition until vacant possession is delivered; (c) award costs of the petition; and (d) pass such further and other orders as this Hon'ble Court may deem fit and proper.'*"
statutory_anchors:
  - "Section 16(1)(g) read with Section 16(2) Maharashtra Rent Control Act 1999"
  - "Section 14(1)(e) read with Section 14(6) Delhi Rent Control Act 1958"
  - "Section 25B Delhi Rent Control Act 1958 (summary procedure — SOLELY on bona-fide ground)"
  - "Section 21(1)(a) UP Urban Buildings Act 1972 (release application before Prescribed Authority)"
  - "Section 27(2)(r) Karnataka Rent Act 2001"
  - "Section 6(1)(f) West Bengal Premises Tenancy Act 1997"
  - "Section 10(3) AP/Telangana Buildings Control Act 1960"
notice_requirement: "Notice under State Rent Act terminating tenancy on bona-fide need ground. Where State Act exhaustively governs (Dhanapal Chettiar (1979) 4 SCC 214), separate Section 106 TPA notice is dispensed with — but the safer practice is dual-notice. UP Act Section 21 release application requires statutory notice under UP Rules + landlord-need declaration."
v_dhanapal_chettiar_check: "Bona-fide need is exclusively a State Rent Act ground; Section 106 TPA notice is not the source of right to evict. The petition stands or falls on the State Act notice + ingredients."
bharatiya_sakshya_check: "Documentary proof of family-member dependence (PAN / Aadhaar / school records / dependent relationship), proof of current cramped accommodation (sale deed / lease deed / photographs), and proof of need (occupational requirement / marriage / business expansion) to be marked as Bharatiya Sakshya Adhiniyam 2023 compliant exhibits."
section_25B_summary_procedure: "DRC Act Section 25B — summary procedure available SOLELY where eviction is sought on Section 14(1)(e) ground (and certain other narrow grounds). Tenant must obtain leave-to-defend within 15 days of summons by filing affidavit disclosing triable issues. Drafter checks whether the petition combines bona-fide ground with any other ground — if so, summary procedure is UNAVAILABLE."
```

## Statutory framework summary

- **Section 16(1)(g) MRC Act 1999** — Eviction lies where the premises are reasonably and bona fide required by the landlord for occupation by himself or by any person for whose benefit the premises are held, or where the landlord is a trustee of a public charitable trust, that the premises are required for occupation for the purposes of the trust.
- **Section 16(2) MRC Act 1999** — Comparative-hardship test — no decree for eviction shall be passed if the Court is satisfied that, having regard to all the circumstances of the case including the question whether other reasonable accommodation is available for the landlord or the tenant, greater hardship would be caused by passing the decree than by refusing to pass it.
- **Section 14(1)(e) DRC Act 1958** — Premises let for residential purposes are required bona fide by the landlord for occupation as a residence for himself or any member of his family dependent on him, and that he has no other reasonably suitable residential accommodation.
- **Section 14(6) DRC Act 1958** — Comparative hardship (Delhi equivalent).
- **Section 25B DRC Act 1958** — Summary procedure when eviction is sought SOLELY on Section 14(1)(e), Section 14A, or Section 14B-D. Tenant must seek leave to defend within 15 days.
- **Section 21 UP Urban Buildings Act 1972** — Release application before Prescribed Authority. Distinct from regular suit. Land-and-building owner-tenant equation tested with sympathy to landlord-need + comparative hardship.

## SCC framework (binding)

- **Ragavendra Kumar v. Firm Prem Machinary (2000) 1 SCC 679** — Bona-fide need of landlord must be honest and real; landlord is the best judge of his requirement; Court cannot dictate the manner in which landlord must use his property.
- **Akhileshwar Kumar v. Mustaqim (2003) 1 SCC 75** — Landlord's choice of premises among his properties is to be respected if bona fide; tenant cannot dictate which premises landlord must occupy.
- **Sait Nagjee Purushotham (2005) 8 SCC 252** — Reiterates the principle; landlord is the best judge of his requirement; need need not be one of "absolute necessity" but must be more than a mere desire.
- **Joginder Pal v. Naval Kishore Behal (2002) 5 SCC 397** — Landlord's need for adult son's occupation is a valid bona-fide need; dependent-family-member need is recognised even though son is independently earning.

## Ingredients to be pleaded

1. **Landlord-tenant relationship** — title, tenancy, rent, premises particulars.
2. **Bona-fide requirement** — for whose occupation (self / family member / dependent relative), the precise need (residence / business / professional chamber / specific use), the surrounding circumstances giving rise to the need (changed family size / dependent elderly / setting up business / etc.).
3. **No other reasonably suitable accommodation** — landlord's existing properties listed with reasons of unsuitability (location, size, occupied by other tenant, encumbered, etc.).
4. **Comparative hardship** — landlord's hardship from refusal vs. tenant's hardship from grant; tenant's alternate options pleaded.
5. **Statutory notice** — State Rent Act notice terminating tenancy on the bona-fide ground.

## Dependent-family-member doctrine

The "dependent family member" includes — Hindu Undivided Family (HUF) constituents · spouse · minor children · adult children residing with landlord · dependent parents · dependent siblings. Joginder Pal (2002) 5 SCC 397 expressly recognises adult-son need. The Drafter pleads the precise dependence (financial / residential / care-providing) with documentary support.

## Comparative-hardship framework

The comparative-hardship inquiry under Section 14(6) DRC Act / Section 16(2) MRC Act / equivalent requires:

- Landlord's existing accommodation (size, location, suitability)
- Family size and changed circumstances
- Tenant's existing accommodation alternatives (own property, other tenancies, family-arrangement options)
- Tenant's financial means to secure alternative accommodation
- Duration of tenancy and historic relationship
- Location-specific factors (children's school / hospital access / employment proximity)

The Drafter pleads the landlord-side facts; the tenant's Written Statement (use `tenant-written-statement-draft`) responds with tenant-side facts.

## Section 25B DRC summary procedure (Delhi only)

Where the petition invokes SOLELY Section 14(1)(e) (or Sections 14A / 14B / 14C / 14D), the Delhi summary procedure under Section 25B is available:

- Petition + Affidavit of Landlord stating the need
- Summons in the prescribed form
- Tenant has 15 days from service to apply for leave to defend, supported by affidavit disclosing facts entitling to defend
- Court grants leave only if the affidavit discloses such facts as would disentitle the landlord from obtaining decree
- On refusal of leave, decree of eviction is passed forthwith

The Drafter notes that combining bona-fide ground with any other ground (non-payment, sub-letting, nuisance) DISQUALIFIES the summary procedure — the petition then proceeds as a regular eviction suit.

## UP Section 21 release procedure (UP only)

UP Urban Buildings Act 1972 provides a distinct procedure — RELEASE APPLICATION before the Prescribed Authority (not a civil suit):

- Release application under Section 21(1)(a) / (b) (residential / non-residential)
- Prescribed Authority issues notice to tenant
- Tenant files reply
- Inquiry; comparative-hardship test applied under Rule 16 of UP Rules
- Order of release; appeal under Section 22 to District Judge

## Personal-law overlay — HUF / coparcener

For HUF property, the Karta files the petition; need of any coparcener / dependent constitutes valid landlord-need. The Drafter pleads HUF status, Karta's authority, and the dependent coparcener's need.

## Common opposing-counsel challenges

1. **Mala fide need / sham need** — tenant pleads that landlord's real intent is to re-let at higher rent or sell.
2. **Other accommodation available** — tenant identifies other premises owned / accessible to landlord.
3. **Comparative hardship favouring tenant** — long tenancy, school-going children, no alternate accommodation, financial inability.
4. **Family-member not dependent** — adult son independent / married daughter living separately / etc.
5. **Section 25B leave-to-defend** — tenant files affidavit raising triable issues.
6. **Landlord's prior-bad-faith conduct** — pattern of harassment, parallel proceedings, attempts to coerce vacation.
7. **Premises let for non-residential — Section 14(1)(e) DRC Act applies ONLY to residential** — tenant pleads non-residential use is established; the Section 14(1)(e) ground is unavailable.

The Drafter pre-empts these by: (a) detailed need-pleading with documentary support; (b) exhaustive listing of landlord's other properties with reasons of unsuitability; (c) affidavit of comparative-hardship facts; (d) family-member dependence proof; (e) verifying premises-use (residential / non-residential) before invoking Section 14(1)(e). The Overseer surfaces residual gaps for the advocate's review.
