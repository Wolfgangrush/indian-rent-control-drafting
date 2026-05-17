---
name: tenant-written-statement-draft
description: Draft a Tenant's Written Statement in an Eviction Petition / Recovery Suit, under Order VIII of the Code of Civil Procedure 1908 read with the applicable State Rent Control Act tenant-protection provisions, with cross-reference to Damadilal v. Parashram (1976) 4 SCC 645 (statutory tenant has heritable estate; not a mere personal right) and Gian Devi Anand v. Jeevan Kumar (1985) 2 SCC 683 (statutory tenancy is heritable; heirs entitled to continue tenancy on tenant s death). Encodes the THREE-TIER STRUCTURE — (1) Preliminary Objections (jurisdiction, maintainability, limitation, Section 106 TPA notice infirmity, pecuniary jurisdiction); (2) Para-by-para reply to the Petition s allegations; (3) Additional Pleas / Affirmative Defences (statutory tenancy, deposit-protection under Section 8 MRC Act, comparative-hardship, sub-tenant denial, landlord-acquiescence, sham-need, fair-rent already fixed). Encodes ground-specific defences mirror-imaging each eviction ground: NON-PAYMENT → deposit-protection / Section 14(2) DRC protection / Section 20(4) UP protection; BONA-FIDE-NEED → no-other-accommodation + comparative-hardship + sham; SUB-LETTING → no-consideration / family-member / acquiescence; NUISANCE → unsubstantiated / landlord-instigated; DAMAGE → wear-and-tear / landlord neglect. Auto-fires on "draft tenant written statement", "draft WS rent control", "draft written statement eviction", "draft defence eviction petition", and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# Tenant's Written Statement (Rent Control) Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_rent_control_drafting_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Case metadata

```yaml
case_type_line: WRITTEN STATEMENT FILED BY THE RESPONDENT / TENANT
case_short_code: TENANT_WS
role_party_1: Petitioner / Landlord (in Cause Title — same as Eviction Petition)
role_party_2: Respondent / Tenant (the Filer of this Written Statement)
typical_forum: "Same as the Eviction Petition / Recovery Suit — Court of Small Causes / Civil Judge as Rent Controller / Additional Rent Controller / Prescribed Authority (UP) / Rent Court (Tamil Nadu) — Written Statement is filed in the same proceeding."
typical_court_fee: "Nominal court fee on Written Statement per State Court Fees Act (typically Rs. 25-100). Counter-claim component (if any) bears ad valorem fee."
operative_paragraphs:
  - "Cause title — *'IN THE COURT OF [____] AT [____] / R.A.E. NO. [____] OF [____] — Petitioner: [Landlord] / Respondent: [Tenant] — WRITTEN STATEMENT FILED BY THE RESPONDENT'*"
  - "Preliminary objection — jurisdiction — *'The present petition is not maintainable as framed and is liable to be dismissed in limine on the following preliminary grounds: (i) This Hon'ble Court lacks pecuniary / territorial / subject-matter jurisdiction in that [_____]; (ii) The petition is barred by the law of limitation in that the cause of action arose more than [period] prior to the institution of the petition; (iii) The statutory notice under Section [_____] of the [State Act] / Section 106 TPA is defective / not served in accordance with law in that [_____]; (iv) Necessary parties [_____] have not been joined, rendering the petition bad for non-joinder.'*"
  - "Para-by-para reply — *'PARA-WISE REPLY TO THE PETITION — Para 1: The contents of paragraph 1 of the petition relating to title / ownership of the suit premises are denied for want of knowledge, and the Petitioner is put to strict proof thereof. Para 2: The contents of paragraph 2 relating to monthly rent are admitted to the extent that the Respondent is a tenant of the suit premises but the quantum of rent stated as Rs. [____] is excessive and beyond the standard rent of Rs. [____] determinable under Section 7 MRC Act 1999, and a Standard Rent Application bearing No. [____] is pending in this Hon'ble Court [annexed as Annexure ____]. Para 3: [continue para-by-para]…'*"
  - "Additional pleas / affirmative defences — *'WITHOUT PREJUDICE TO THE ABOVE, the Respondent submits the following additional pleas in answer to the petition: (i) Statutory tenancy — The Respondent has held the suit premises as a statutory tenant under the Maharashtra Rent Control Act 1999 since [date], and his rights are protected under the said Act notwithstanding determination of the contractual tenancy. (ii) Deposit-protection — The Respondent has regularly and continuously deposited the monthly rent under Section 8 MRC Act 1999 since [date], in case bearing No. [____] before [____], and is therefore not in default within the meaning of Section 16(1)(a) MRC Act. (iii) Comparative hardship — Greater hardship would be caused to the Respondent by passing the decree than to the Petitioner by refusing it [particulars: school-going children, no alternate accommodation, financial inability, business goodwill at premises]. (iv) Sham need — The Petitioner's alleged bona-fide need is sham and pretextual; the Petitioner owns [_____] other premises at [_____] which are reasonably suitable; the real motive is to re-let at higher rent / to sell vacant.'*"
  - "Prayer — *'In view of the above, it is most respectfully prayed that this Hon'ble Court may be pleased to: (a) dismiss the petition with costs; (b) hold that no decree of eviction can be passed against the Respondent on any of the grounds pleaded; (c) hold that the Respondent is entitled to continue in the suit premises as a tenant under the [State Rent Control Act]; (d) award costs of these proceedings to the Respondent; and (e) pass such further and other orders as this Hon'ble Court may deem fit and proper.'*"
statutory_anchors:
  - "Order VIII CPC (written statement, set-off, counter-claim, denial, etc.)"
  - "Order VI Rule 15 CPC (verification)"
  - "State Rent Control Act tenant-protection provisions — Section 7-11 + Section 16 MRC Act 1999 / Sections 6-9 + Section 14 DRC Act 1958 / Sections 14, 21, 27 KRA 2001 / equivalents"
  - "Section 14(2) DRC Act 1958 (first-default tenant-protection)"
  - "Section 20(4) UP Urban Buildings Act 1972 (first-default tenant-protection)"
  - "Section 8 MRC Act 1999 / Section 27 DRC Act 1958 / equivalents (deposit-protection)"
key_cases:
  - "Damadilal v. Parashram (1976) 4 SCC 645 — Statutory tenancy creates a heritable estate, not merely a personal right; tenant s heirs entitled to continue."
  - "Gian Devi Anand v. Jeevan Kumar (1985) 2 SCC 683 — Statutory tenancy is heritable; on tenant s death, heirs entitled to continue tenancy under the State Rent Act protection."
notice_requirement: "Not applicable — this is a defence pleading, not a notice."
v_dhanapal_chettiar_check: "Where the Petitioner has issued ONLY a State Rent Act notice and relied on Dhanapal Chettiar (1979) 4 SCC 214, the Respondent may challenge the precise compliance with State Act notice ingredients. Where Petitioner has issued ONLY a Section 106 TPA notice without separate State Act notice, the Respondent may plead the notice is inadequate for the State Act ground."
bharatiya_sakshya_check: "Deposit receipts, payment proofs (UPI / NEFT / cheque counterfoils), rent receipts pre-dispute, comparable-rent evidence for standard-rent counter, family-member dependence evidence for sub-letting denial, no-other-accommodation evidence for comparative-hardship — all to be marked as Bharatiya Sakshya Adhiniyam 2023 compliant exhibits. Verification under Order VI Rule 15 CPC."
```

## Statutory framework summary

- **Order VIII Rule 1 CPC** — Defendant shall, within 30 days from service of summons, present a Written Statement of his defence (extendable to 90 days for sufficient cause; further extensions discretionary post Salem Advocate Bar Association SCC).
- **Order VIII Rule 2 CPC** — Defendant must specifically deny every material allegation; matters not specifically denied (except as to damages) are deemed admitted.
- **Order VIII Rule 3 CPC** — Specific denial required for each material allegation.
- **Order VIII Rule 5 CPC** — Specific denial; general / evasive denial deemed admission.
- **Order VIII Rule 6 CPC** — Set-off — Defendant may claim ascertained sum payable by Plaintiff to Defendant against Plaintiff s claim.
- **Order VIII Rule 6A CPC** — Counter-claim — Defendant may set up a counter-claim against Plaintiff up to date of filing WS, treated as a cross-suit for procedural purposes.
- **Order VI Rule 15 CPC** — Verification by the Defendant personally (or person acquainted with facts) signed and dated, distinguishing matters known of own knowledge vs. on information and belief.
- **State Rent Act provisions** — tenant-protection ingredients per eviction ground.

## Three-tier structure

### Tier 1: Preliminary Objections
Threshold defences that, if accepted, lead to dismissal in limine without merits inquiry:

- **Jurisdiction** — pecuniary / territorial / subject-matter
- **Maintainability** — wrong procedural vehicle (e.g., civil suit where Rent Controller exclusively competent)
- **Limitation** — cause of action beyond statutory limitation
- **Statutory notice infirmity** — Section 15 MRC Act / Section 14(1)(a) DRC Act / Section 106 TPA notice defective / not served / wrong amount / wrong cure period
- **Non-joinder / misjoinder** — necessary parties absent OR improper parties included
- **Res judicata** — same issue earlier decided
- **Want of cause of action** — petition discloses no cause

### Tier 2: Para-by-para reply
Order VIII Rule 3-5 CPC requires specific denial of each material allegation. The Drafter responds to EACH numbered paragraph of the petition with:

- "Admitted"
- "Denied"
- "Denied for want of knowledge; Petitioner put to strict proof"
- "Admitted to the extent of [_____]; rest denied"

Vague / evasive denials are deemed admissions under Rule 5; the Drafter takes care to deny specifically.

### Tier 3: Additional pleas / affirmative defences
The "without prejudice to the above" defences — even if Tiers 1 and 2 fail, these stand independently:

- **Statutory tenancy** — Damadilal / Gian Devi Anand framework
- **Deposit-protection** — Section 8 MRC Act / Section 27 DRC Act / equivalent
- **Section 14(2) DRC Act / Section 20(4) UP Act first-default protection**
- **Standard-rent dispute** — pending Standard Rent Application
- **Comparative hardship** — Section 16(2) MRC Act / Section 14(6) DRC Act
- **Acquiescence / waiver** — landlord knew and tacitly consented
- **Sham need / mala fide** — Petitioner's real motive ulterior

## Ground-specific defences (mirror image)

### Against NON-PAYMENT eviction
1. Rent actually paid — annex receipts / bank transfers
2. Tender made — landlord refused — annex tender evidence
3. Deposit under Section 8 MRC Act — annex deposit receipts
4. Section 14(2) DRC Act / Section 20(4) UP Act first-default protection invoked at first hearing
5. Standard-rent dispute pending — landlord s demand exceeds standard rent
6. Adjustment plea — security deposit / advance / amenity-charges set off

### Against BONA-FIDE-NEED eviction
1. No other accommodation pleading is incomplete / false — landlord owns other premises (give particulars)
2. Comparative hardship favours tenant — long tenancy, dependents, business goodwill
3. Sham need — landlord s pattern of prior false petitions / re-letting earlier evictees
4. Family-member not dependent — adult son independent, married daughter separately accommodated
5. Section 25B DRC leave-to-defend affidavit filed with triable issues disclosed
6. Premises not residential — Section 14(1)(e) DRC Act inapplicable

### Against SUB-LETTING eviction
1. Alleged sub-tenant is family member (spouse / child / parent / dependent sibling)
2. Alleged sub-tenant is paying guest / caretaker — no exclusive possession
3. Alleged sub-tenant is business partner / employee — common business use
4. Landlord's oral consent / long acquiescence — waiver
5. No consideration — utility bills in occupant s name out of convenience
6. Inferential framework distinguishable — facts do not establish exclusive possession + consideration

### Against NUISANCE / DAMAGE eviction
1. Incidents not particularised / dates not specified / witnesses not identified
2. Single isolated incident — pattern not made out
3. Landlord-instigated / neighbour-collusion — complaints manufactured
4. Damage attributable to ordinary wear-and-tear / pre-existing condition
5. Damage caused by third parties / visitors — not by tenant or his occupants
6. Damage curable / restoration offered — disproportion of relief
7. Electronic-evidence chain broken — no Section 63 BSA certificate

## Statutory tenancy + heritability framework

**Damadilal v. Parashram (1976) 4 SCC 645** and **Gian Devi Anand v. Jeevan Kumar (1985) 2 SCC 683** establish:

- A statutory tenant under State Rent Act is NOT a mere personal occupant; he has a HERITABLE estate
- On determination of contractual tenancy, the State Rent Act protection vests an interest
- On the statutory tenant s death, heirs entitled to continue the tenancy under the State Rent Act protection
- Statutory tenancy can be defeated only on State Rent Act eviction grounds (not by lapse of contractual tenancy alone)

The Drafter pleads statutory tenancy as a defence to any "expiry of contractual term" or "Section 106 TPA notice" eviction.

## Verification + accompanying affidavit

- Verification under Order VI Rule 15 CPC — signed by Respondent personally + dated + identifying paragraphs known of own knowledge vs. on information and belief.
- Accompanying affidavit in support of preliminary objections + facts within Respondent's knowledge.

## Common opposing-counsel / Court challenges

1. **Evasive / general denials** — Order VIII Rule 5 CPC deems them admissions; Court may strike off.
2. **Tier 1 objections not maintainable on demurrer** — Court may direct trial on merits.
3. **Standard-rent application not actually pending** — pleading must be supported by case number.
4. **Deposit not continuous / regular** — Section 8 MRC Act protection lost.
5. **Section 14(2) DRC Act protection previously exhausted** — one-time only.
6. **Comparative hardship facts unparticularised** — bald averment insufficient.
7. **Statutory tenancy plea inconsistent with original tenancy denial** — alternative pleas to be carefully crafted to avoid mutual destruction.
8. **Verification defective** — signature missing / wrong party / undated.

The Drafter pre-empts these by: (a) specific denials per paragraph + Order VIII Rule 5 CPC discipline; (b) tier-by-tier structure with each tier independently maintainable; (c) supporting documents annexed at filing (deposit receipts, comparable-rent evidence, family-member dependence proof); (d) verification + accompanying affidavit done at filing; (e) inconsistent-pleas managed with "without prejudice" framing. The Overseer surfaces residual gaps for the advocate's review.
