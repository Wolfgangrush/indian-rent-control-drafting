---
name: eviction-sub-letting-without-consent-draft
description: Draft an Eviction Petition on the ground of UNLAWFUL SUB-LETTING / TRANSFER / PARTING WITH POSSESSION WITHOUT LANDLORD'S CONSENT under Section 16(1)(e) of the Maharashtra Rent Control Act 1999, Section 14(1)(b) of the Delhi Rent Control Act 1958, Section 27(2)(b) of the Karnataka Rent Act 2001, Section 6(1)(e) of the West Bengal Premises Tenancy Act 1997, Section 20(2)(e) of the UP Urban Buildings Act 1972, and Section 10(2)(ii)(a) of the AP / Telangana Buildings Control Act 1960. Encodes the two-fold ingredient (a) parting with possession of the whole or part of the premises AND (b) for consideration / monetary or non-monetary benefit, the absence-of-landlord's-written-consent discipline, the direct-proof vs inferential-proof distinction, and the binding SCC framework on inferential proof of sub-tenancy (Resham Singh v. Raghbir Singh (1999) 7 SCC 263; Helper Girdharbhai v. Saiyed Mohmad Mirasaheb Kadri (1987) 3 SCC 538; Bharat Sales v. LIC of India (1998) 3 SCC 1). Auto-fires on "draft eviction sub-letting", "draft eviction sub-letting without consent", "draft eviction parting with possession", "draft eviction unlawful sub-tenancy", and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# Eviction (Sub-Letting Without Consent) Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_rent_control_drafting_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Case metadata

```yaml
case_type_line: PETITION FOR EVICTION (UNLAWFUL SUB-LETTING)
case_short_code: EVICTION_SUBLET
role_party_1: Landlord / Petitioner
role_party_2: Tenant / Respondent No. 1
role_party_3: Sub-Tenant / Alleged Occupant / Respondent No. 2 (joined as necessary party)
typical_forum: "Maharashtra — Court of Small Causes / Civil Judge as Rent Controller · Delhi — Additional Rent Controller · Karnataka — Court of Small Causes / Civil Judge as Rent Controller · West Bengal — Civil Judge (Junior Division) · UP — Civil Judge under Section 20 · AP/Telangana — Rent Controller"
typical_court_fee: "Fixed court fee on eviction relief per State Court Fees Act."
operative_paragraphs:
  - "Facts paragraph — *'It is most respectfully submitted that the Petitioner is the lawful owner / landlord of the premises bearing No. [_____] situate at [_____] (hereinafter \"the suit premises\"), and the Respondent No. 1 has been in occupation of the suit premises as a monthly tenant under the Petitioner at a monthly rent of Rs. [_____].'*"
  - "Sub-letting incident — *'The Respondent No. 1 has, since approximately [date], unlawfully sub-let / transferred / parted with possession of the whole / part of the suit premises in favour of the Respondent No. 2, who has been in exclusive possession of [the entire suit premises / specific portion thereof identified as _____] for valuable consideration paid to the Respondent No. 1, without obtaining the prior written consent of the Petitioner / Landlord. The Petitioner has at no point in time consented, either orally or in writing, to the said sub-letting or parting with possession.'*"
  - "Inferential particulars — *'The fact of sub-letting is established by, inter alia: (i) the exclusive and undisturbed possession of Respondent No. 2 over the suit premises / identified portion; (ii) utility bills (electricity / water / gas) standing in the name of Respondent No. 2 — copies annexed and marked Annexure [_____]; (iii) entries in the society / apartment owners association records identifying Respondent No. 2 as occupant — copy annexed; (iv) affidavits of neighbours identifying Respondent No. 2 as occupant — copies annexed; (v) photographs of Respondent No. 2 nameplate at the entrance / occupancy indicia.'*"
  - "Consideration recital — *'It is verily believed and submitted that the said sub-letting / parting with possession has been for monetary consideration, the precise amount whereof is within the special knowledge of the Respondents. The Petitioner relies on the inferential framework laid down by the Hon'ble Supreme Court in Resham Singh v. Raghbir Singh (1999) 7 SCC 263 and Helper Girdharbhai v. Saiyed Mohmad Mirasaheb Kadri (1987) 3 SCC 538, whereby once exclusive possession of the alleged sub-tenant is established, the consideration component is presumed unless rebutted by the tenant.'*"
  - "Statutory notice — *'The Petitioner caused to be served upon the Respondent No. 1 a notice dated [_____] under Section 16(1)(e) of the Maharashtra Rent Control Act 1999 [or State equivalent] terminating the tenancy and calling upon the Respondent No. 1 to quit and deliver vacant possession of the suit premises.'*"
  - "Prayer — *'It is therefore most respectfully prayed that this Hon'ble Court may be pleased to: (a) pass a decree for eviction directing the Respondents to quit, vacate, and deliver vacant and peaceful possession of the suit premises to the Petitioner; (b) award mesne profits / damages for use and occupation at the prevailing market rate from the date of the petition until vacant possession; (c) award costs; and (d) pass such further and other orders as this Hon'ble Court may deem fit and proper.'*"
statutory_anchors:
  - "Section 16(1)(e) Maharashtra Rent Control Act 1999"
  - "Section 14(1)(b) Delhi Rent Control Act 1958"
  - "Section 27(2)(b) Karnataka Rent Act 2001"
  - "Section 6(1)(e) West Bengal Premises Tenancy Act 1997"
  - "Section 20(2)(e) UP Urban Buildings Act 1972"
  - "Section 10(2)(ii)(a) AP/Telangana Buildings Control Act 1960"
notice_requirement: "Statutory notice under State Rent Act terminating tenancy on the sub-letting ground, specifying the alleged sub-tenant and approximate date of sub-letting. Where the State Act exhaustively governs, separate Section 106 TPA notice is dispensed with under Dhanapal Chettiar (1979) 4 SCC 214 — safer practice is dual-notice."
v_dhanapal_chettiar_check: "Sub-letting is exclusively a State Rent Act ground; notice under State Act suffices."
bharatiya_sakshya_check: "Utility bills, society records, neighbour affidavits, photographic / video evidence (Section 63 BSA electronic-record certificate), corporate records (where Respondent No. 2 is a company / firm) — all to be marked as Bharatiya Sakshya Adhiniyam 2023 compliant exhibits."
joinder_position: "The alleged sub-tenant / Respondent No. 2 MUST be joined as a necessary party — without joinder, decree of eviction cannot be enforced against the sub-tenant in possession. Order I Rule 10 CPC for impleadment."
```

## Statutory framework summary

- **Section 16(1)(e) MRC Act 1999** — Eviction lies where the tenant has, after coming into operation of this Act, unlawfully sub-let or otherwise parted with the possession of the whole or any part of the premises.
- **Section 14(1)(b) DRC Act 1958** — Tenant has, on or after the 9th day of June 1952, sub-let, assigned, or otherwise parted with the possession of the whole or any part of the premises without obtaining the consent in writing of the landlord.
- **Section 27(2)(b) KRA 2001** — Sub-letting ground equivalent.
- **Section 6(1)(e) WBPT Act 1997** — Sub-letting ground equivalent.
- **Section 20(2)(e) UP Urban Buildings Act 1972** — Sub-letting without consent; same construction.

## SCC framework (binding)

- **Resham Singh v. Raghbir Singh (1999) 7 SCC 263** — Once landlord establishes (a) exclusive possession of alleged sub-tenant and (b) absence of landlord s consent, the burden shifts to the tenant to prove that the alleged sub-tenant is NOT a sub-tenant. The inferential framework permits proof of consideration through circumstantial evidence.
- **Helper Girdharbhai v. Saiyed Mohmad Mirasaheb Kadri (1987) 3 SCC 538** — Establishes the two-fold ingredient: parting with possession + for consideration. Where exclusive possession is shown, consideration is to be presumed unless rebutted.
- **Bharat Sales v. LIC of India (1998) 3 SCC 1** — Sub-tenancy can be inferred from conduct; direct documentary proof is not always available, since sub-tenancy is by its nature a clandestine arrangement; circumstantial proof suffices.

## Ingredients to be pleaded

1. **Landlord-tenant relationship** — title, tenancy, rent, premises particulars (between landlord and Respondent No. 1).
2. **Parting with possession** — exclusive possession of Respondent No. 2 over whole / specified part; vacation of premises by Respondent No. 1 (whole) OR sharing of arrangement (part).
3. **Consideration** — monetary OR non-monetary benefit flowing from Respondent No. 2 to Respondent No. 1 (the inferential framework permits presumption).
4. **Absence of landlord s written consent** — landlord s express denial of any oral / written consent.
5. **Identification of Respondent No. 2** — name, address, mode of identification (utility bill, society register, nameplate).
6. **Statutory notice** — State Rent Act notice on the sub-letting ground.

## Direct vs inferential proof

| Direct Proof | Inferential Proof |
|---|---|
| Sub-tenancy agreement (rare) | Exclusive possession of Respondent No. 2 |
| Rent receipts from sub-tenant to tenant | Utility bills in Respondent No. 2 s name |
| Tenant's admission | Society / RWA records identifying Respondent No. 2 |
| Bank transfers from sub-tenant to tenant | Neighbour affidavits |
| Email / WhatsApp correspondence | Photographs of Respondent No. 2 s nameplate |

Direct proof is uncommon; inferential proof is the norm. The Resham Singh / Helper Girdharbhai / Bharat Sales framework permits inferential proof to ground the petition.

## Documentary stack (mandatory)

- **Utility bills** — electricity (BESCOM / MSEDCL / BSES / TPDDL / etc.) / water / gas / piped gas / broadband in Respondent No. 2 s name
- **Society / Apartment Owners Association records** — entries identifying Respondent No. 2 as occupant; intimation letters
- **Neighbour affidavits** — sworn statements identifying Respondent No. 2 s exclusive occupation, approximate duration, and any oral admissions of sub-tenancy
- **Photographs / videos** — nameplate, occupancy indicia, vehicle parking allotment; Section 63 BSA electronic-record certificate
- **Corporate records** (where Respondent No. 2 is a company / LLP / firm) — RoC records showing registered office / branch office address at the suit premises
- **Postal / courier evidence** — couriers / Speed Post deliveries addressed to Respondent No. 2 at the suit premises
- **Aadhaar / voter ID / KYC indicators** (where lawfully obtainable) — Respondent No. 2 s address registered as the suit premises

## Joinder of sub-tenant (mandatory)

The alleged sub-tenant (Respondent No. 2) MUST be joined as a necessary party under Order I Rule 10 CPC. Without joinder:

- Decree of eviction cannot be enforced against Respondent No. 2 (sub-tenant in possession)
- Petition may be defeated on the ground of non-joinder
- Sub-tenant may later claim he was not heard and challenge the eviction decree on natural-justice grounds

The petition is captioned with both Respondents; both are separately served.

## Family-member / licence exception

Sub-letting does NOT include:

- Family members of the tenant (spouse / children / parents / dependent siblings) in joint occupation
- Caretaker / paying guest arrangements that do not amount to exclusive possession for consideration
- Pure licence arrangements without exclusive possession
- Business-partner / employee arrangements where the tenant retains effective control

The petition must allege EXCLUSIVE possession + CONSIDERATION; the tenant s defence will typically traverse on this distinction.

## Common opposing-counsel challenges

1. **Respondent No. 2 is a family member** — sub-letting denied; family-member residence pleaded.
2. **Respondent No. 2 is a paying guest / caretaker** — no exclusive possession; no consideration; mere licence.
3. **Landlord's oral consent** — tenant pleads landlord knew and tacitly consented for an extended period (waiver / acquiescence).
4. **Respondent No. 2 is a business partner / employee** — no sub-tenancy; common business use.
5. **No consideration** — utility bills in Respondent No. 2 s name due to convenience of payment, not sub-tenancy.
6. **Long-standing acquiescence** — landlord aware of arrangement for years; eviction now is mala fide / pretextual.
7. **Vague pleadings** — no specific date of sub-letting; no specific identification of Respondent No. 2; no specific particulars of consideration.
8. **Joint tenancy / partnership original arrangement** — tenancy was originally joint with Respondent No. 2; no fresh sub-letting.

The Drafter pre-empts these by: (a) particularised pleading of exclusive possession + identification + duration; (b) documentary stack at filing (utility bills + society records + neighbour affidavits + photographs); (c) joinder of Respondent No. 2 at petition stage; (d) explicit denial of any consent, oral or written; (e) reliance on Resham Singh / Helper Girdharbhai / Bharat Sales inferential framework; (f) pleading absence of family / partnership / licence relationship between Respondents. The Overseer surfaces residual gaps for the advocate's review.
