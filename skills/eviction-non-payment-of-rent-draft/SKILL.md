---
name: eviction-non-payment-of-rent-draft
description: Draft an Eviction Petition on the ground of NON-PAYMENT / DEFAULT OF RENT under Section 16(1)(a) read with Section 15 of the Maharashtra Rent Control Act 1999, Section 14(1)(a) of the Delhi Rent Control Act 1958, Section 20(2)(a) read with Section 20(1) of the UP Urban Buildings (Regulation of Letting, Rent and Eviction) Act 1972, Section 27(2)(a) of the Karnataka Rent Act 2001, Section 6(1)(a) of the West Bengal Premises Tenancy Act 1997, Section 11 of the Tamil Nadu Regulation of Rights and Responsibilities of Landlords and Tenants Act 2017, and Section 10(2)(i) of the Andhra Pradesh / Telangana Buildings (Lease, Rent and Eviction) Control Act 1960. Encodes the Section 15 MRC Act demand-notice discipline (notice of demand for arrears + 90-day cure period in Maharashtra; 30-day cure period under most other State Acts), the strict-compliance-with-statutory-notice requirement (Hiralal Kapur v. Prabhu Choudhury (1988) 2 SCC 172), the Section 11(4) MRC Act interim-deposit obligation on the tenant during pendency, and the dual-notice discipline where Section 106 TPA notice + State Act statutory notice operate together. Auto-fires on "draft eviction petition non-payment", "draft eviction non-payment of rent", "draft eviction default rent", "draft RAE non-payment", and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# Eviction (Non-Payment of Rent) Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_rent_control_drafting_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Case metadata

```yaml
case_type_line: PETITION FOR EVICTION (NON-PAYMENT OF RENT)
case_short_code: EVICTION_NPR
role_party_1: Landlord / Petitioner
role_party_2: Tenant / Respondent
typical_forum: "Maharashtra — Court of Small Causes (Mumbai) / Civil Judge designated as Rent Controller (rest of State) · Delhi — Rent Controller under Section 35 DRC Act · Karnataka — Court of Small Causes (Bengaluru) / Civil Judge as Rent Controller · UP — Prescribed Authority under Section 21 / Civil Judge under Section 20 · West Bengal — Civil Judge (Junior Division) under Section 6 WBPT Act · Tamil Nadu — Rent Court constituted under TN Act 2017 · AP/Telangana — Rent Controller under Section 10"
typical_court_fee: "Fixed court fee on petition (per State Court Fees Act) + ad valorem fee on arrears component where money decree is sought in same petition. In Maharashtra, fixed Rs. 100-300 on eviction relief + ad valorem on arrears."
operative_paragraphs:
  - "Facts paragraph — *'It is most respectfully submitted that the Petitioner is the lawful owner / landlord of the premises bearing No. [_____] situate at [_____] (hereinafter referred to as \"the suit premises\"), and the Respondent has been in occupation of the suit premises as a monthly tenant under the Petitioner at a monthly rent of Rs. [_____] (Rupees [_____] only) exclusive of / inclusive of permitted increases, electricity, and water charges, payable on or before the [___] day of each English calendar month for the month then ended.'*"
  - "Arrears recital — *'The Respondent has committed default in the payment of monthly rent and permitted increases from [date] to [date], aggregating to a sum of Rs. [_____] (Rupees [_____] only), and has neglected and failed to pay the same despite repeated oral and written demands.'*"
  - "Statutory notice — *'The Petitioner, through his / her advocate, caused to be served upon the Respondent a notice dated [_____] under Section 15 of the Maharashtra Rent Control Act 1999 [or State equivalent] read with Section 106 of the Transfer of Property Act 1882, calling upon the Respondent to pay or tender the arrears within the statutory period of [90 / 30] days from the receipt of the said notice, and on failure to do so, to quit, vacate, and deliver vacant possession of the suit premises on the expiry of the tenancy. The said notice was duly served on the Respondent on [date] by registered post acknowledgement due and / or under certificate of posting. A copy of the said notice with proof of service is annexed hereto and marked as Annexure [_____].'*"
  - "Non-compliance — *'The Respondent has neither paid nor tendered the arrears of rent and permitted increases within the statutory period of [90 / 30] days from the receipt of the said notice, nor has the Respondent vacated the suit premises, thereby rendering himself / herself liable to be evicted under Section 16(1)(a) of the Maharashtra Rent Control Act 1999 [or State equivalent].'*"
  - "Interim deposit prayer — *'The Petitioner reserves the right to seek an order under Section 11(4) of the Maharashtra Rent Control Act 1999 [or State equivalent] directing the Respondent to deposit the arrears and continue to deposit the monthly rent during the pendency of the present petition.'*"
  - "Prayer — *'It is therefore most respectfully prayed that this Hon'ble Court may be pleased to: (a) pass a decree for eviction directing the Respondent to quit, vacate, and deliver vacant and peaceful possession of the suit premises to the Petitioner; (b) pass a decree for the recovery of arrears of rent and permitted increases amounting to Rs. [_____] together with interest @ [9%] per annum from the date of the petition until realisation; (c) direct the Respondent to pay mesne profits / damages for use and occupation @ Rs. [_____] per month from the date of the petition until vacant possession is delivered; (d) award costs of the petition; and (e) pass such further and other orders as this Hon'ble Court may deem fit and proper in the facts and circumstances of the case.'*"
statutory_anchors:
  - "Section 15 + Section 16(1)(a) Maharashtra Rent Control Act 1999"
  - "Section 14(1)(a) Delhi Rent Control Act 1958"
  - "Section 20(2)(a) read with Section 20(1) UP Urban Buildings Act 1972"
  - "Section 27(2)(a) Karnataka Rent Act 2001"
  - "Section 6(1)(a) West Bengal Premises Tenancy Act 1997"
  - "Section 11 Tamil Nadu Regulation of Rights and Responsibilities of Landlords and Tenants Act 2017"
  - "Section 10(2)(i) AP/Telangana Buildings Control Act 1960"
notice_requirement: "TWO-TIER NOTICE — (a) Section 106 TPA 1882 (15-day post-2002 amendment) determining tenancy; AND (b) Section 15 MRC Act (or State equivalent) statutory demand notice with 90-day cure period in Maharashtra / 30-day cure period under most other Acts. Failure to serve either notice (where required) is FATAL — Hiralal Kapur v. Prabhu Choudhury (1988) 2 SCC 172. NOTE: V. Dhanapal Chettiar v. Yesodai Ammal (1979) 4 SCC 214 held that where the State Rent Act ground itself constitutes determination of tenancy, separate Section 106 TPA notice is NOT required — but the safer practice in non-payment cases is dual-notice."
interim_deposit_position: "Section 11(4) MRC Act 1999 / Section 27 DRC Act 1958 / Section 21 KRA 2001 / Section 21 WBPT Act 1997 — Court may direct the tenant to deposit arrears + future monthly rent during pendency; non-compliance leads to striking off the defence and decree on admission."
v_dhanapal_chettiar_check: "Where the State Rent Act exhaustively governs the eviction ground, the V. Dhanapal Chettiar (1979) 4 SCC 214 doctrine displaces separate Section 106 TPA notice — but the safer practice is to plead both notices to pre-empt the opposing-counsel challenge."
bharatiya_sakshya_check: "Statutory demand notice + postal AD + UPC receipt to be marked as Bharatiya Sakshya Adhiniyam 2023 Section 63 (electronic record) / Section 67 (proof of execution) compliant exhibits."
```

## Statutory framework summary

- **Section 15 MRC Act 1999** — No suit / petition for eviction on non-payment ground shall lie unless a notice in writing of the demand of the standard rent and permitted increases has been served upon the tenant and the tenant has neglected to pay or tender the arrears within 90 days of the receipt of the notice.
- **Section 16(1)(a) MRC Act 1999** — The Court shall pass a decree for eviction where it is satisfied that the tenant has neither paid nor tendered the standard rent and permitted increases within 90 days of the demand notice under Section 15.
- **Section 14(1)(a) DRC Act 1958** — Eviction lies where the tenant has neither paid nor tendered the whole of the arrears of rent legally recoverable within two months of the date on which a notice of demand for the arrears of rent has been served on him in the manner provided in Section 106 TPA.
- **Section 14(2) DRC Act 1958** — First-default protection — the Court shall NOT pass an order for eviction on this ground if the tenant deposits the rent + interest @ 9% + costs within the time fixed by the Court (the so-called "Section 14(2) protection"). This protection is available ONLY ONCE in the tenant's lifetime in respect of the same premises.
- **Section 20 UP Urban Buildings Act 1972** — Tenant deemed in default on failure to pay rent within one month of notice of demand under Section 106 TPA. Section 20(4) UP protection — deposit at first hearing of rent + damages @ 25% + costs cures the default once.
- **Section 11(4) MRC Act 1999** — Interim deposit pendente lite — Court may direct deposit of admitted rent + continuing monthly rent; default empowers Court to strike off defence.

## Ingredients to be pleaded

1. **Tenancy** — landlord-tenant relationship, premises particulars, monthly rent, due date.
2. **Arrears** — exact period of default, monthly breakup, aggregate amount, mode of pleading (with rent-statement annexure).
3. **Statutory notice** — Section 15 MRC Act / State equivalent notice, date of issue, date of service, mode of service (Registered Post AD + UPC for safety), 90-day / 30-day cure period expiry date.
4. **Non-compliance** — neither payment nor tender within the statutory period; no representation by tenant disputing the demand.
5. **Subsisting default** — at the date of filing, arrears continue.
6. **Reliefs sought** — eviction + arrears recovery + mesne profits + interest + costs.

## Tender vs payment

The statutory notice triggers a TWO-FOLD obligation on the tenant — to PAY OR TENDER. A tender is a valid offer of the entire arrears to the landlord; refusal by the landlord followed by deposit with the Rent Controller / Court (under Section 8 MRC Act / Section 27 DRC Act / Section 21 WBPT Act) protects the tenant. The Drafter pleads the precise dates of the notice, the expiry, and confirms NO deposit was made by the tenant under Section 8 MRC Act / equivalent during the cure period.

## First-default protection (DRC Act / UP Act)

- **Delhi**: Section 14(2) DRC Act — Court SHALL order tenant to deposit arrears + interest @ 9% + costs within fixed time; on compliance, NO order for eviction. Available ONCE.
- **UP**: Section 20(4) UP Act — Deposit at first hearing of rent + 25% damages + costs cures the default ONCE.
- **Maharashtra**: NO equivalent first-default protection under MRC Act 1999 — eviction lies once the 90-day Section 15 cure window expires without payment / tender / deposit.

The Petitioner's Drafter pleads that NO Section 14(2) / Section 20(4) protection is available (e.g. the tenant has previously enjoyed it; OR the State Act does not provide it).

## Interim deposit (Section 11(4) MRC Act / State equivalent)

The Petitioner is entitled to move an application under Section 11(4) MRC Act / Section 27 DRC Act / Section 21 KRA 2001 / Section 21 WBPT Act for an order directing the tenant to deposit:

- Admitted arrears
- Continuing monthly rent during pendency

Non-compliance attracts striking off the defence under Order VIII Rule 10 CPC read with the State Act, leading to a summary decree on admission. This application is typically filed contemporaneously with the eviction petition.

## Common opposing-counsel challenges

1. **Section 15 notice defective** — wrong amount demanded, wrong cure period stated, wrong recipient, defective service.
2. **Tenant deposited under Section 8 MRC Act / equivalent** — landlord refused; deposit with Rent Controller cures the default.
3. **Standard rent dispute pending** — tenant has filed a Standard Rent Application; rent in dispute; landlord's demand is excessive (use of `standard-rent-fixation-application-draft` by tenant).
4. **Section 14(2) DRC Act / Section 20(4) UP Act protection** invoked at first hearing.
5. **Adjustment plea** — security deposit / advance / amenity-charges paid by tenant set off against the arrears.
6. **Landlord's accounts incorrect** — rent has been paid; receipts not issued.
7. **Identity of landlord / privity** — denial that the Petitioner is the landlord (sale of premises / change of ownership / heirship dispute).

The Drafter pre-empts these by: (a) precise statutory-notice drafting + RPAD + UPC + email service stack; (b) confirming no Section 8 / Section 27 deposit by tenant during cure window; (c) confirming Section 14(2) / Section 20(4) protection unavailable; (d) annexing rent-statement reconciled with deposits and refunds; (e) attaching title documents establishing landlord identity. The Overseer surfaces residual gaps for the advocate's review.
