---
name: landlord-recovery-suit-draft
description: Draft a Landlord's Suit for Recovery of Arrears of Rent and Mesne Profits under Order VII of the Code of Civil Procedure 1908, read with Article 52 of the Schedule to the Limitation Act 1963 (three-year limitation from the date arrears became due), Section 9 CPC (general civil-court jurisdiction), and the applicable State Court Fees Act (ad valorem on the amount sought). DISTINCT from an Eviction Petition — this is a money suit for ARREARS and MESNE PROFITS where (a) the tenant has already vacated and only money relief remains, OR (b) landlord chooses to confine relief to money decree while preserving / not invoking the eviction jurisdiction, OR (c) the suit combines eviction + arrears recovery in one composite suit (subject to State Rent Act bar). Encodes the limitation discipline under Article 52 Limitation Act, the Section 18 Limitation Act acknowledgement extension, the mesne-profits computation methodology (comparable-rents / Ready Reckoner basis from date of unauthorised possession), and the pecuniary-jurisdiction selection (Civil Judge Junior / Senior Division / Court of Small Causes). Auto-fires on "draft landlord recovery suit", "draft recovery suit rent arrears", "draft suit for arrears", "draft money suit rent", "draft mesne profits suit", and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# Landlord's Suit for Recovery of Arrears + Mesne Profits Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_rent_control_drafting_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Case metadata

```yaml
case_type_line: SUIT FOR RECOVERY OF ARREARS OF RENT AND MESNE PROFITS
case_short_code: RECOVERY_SUIT
role_party_1: Landlord / Plaintiff
role_party_2: Tenant / Ex-Tenant / Defendant
typical_forum: "Civil Judge (Junior Division) for suits up to State pecuniary limit (typically Rs. 10 lakh / Rs. 20 lakh — varies by State) · Civil Judge (Senior Division) for suits above Junior Division limit · Court of Small Causes (Mumbai / Bengaluru / Chennai / Kolkata) for tenancy-related money suits where State Rent Act vests jurisdiction · District Court in States where rent-related suits lie with District Court"
typical_court_fee: "AD VALOREM on the entire amount claimed (arrears + mesne profits + interest), per the applicable State Court Fees Act. Provisional valuation of mesne profits for ongoing periods to be quantified under Order VII Rule 2 CPC; final valuation at decree."
operative_paragraphs:
  - "Tenancy / occupation recital — *'It is most respectfully submitted that the Plaintiff is the lawful owner / landlord of the premises bearing No. [_____] situate at [_____] (hereinafter \"the suit premises\"), and the Defendant has been in occupation of the suit premises as a monthly tenant under the Plaintiff at a monthly rent of Rs. [_____] (Rupees [_____] only) payable on or before the [___] day of each English calendar month for the month then ended.'*"
  - "Arrears recital — *'The Defendant has committed default in the payment of monthly rent for the period from [date] to [date], aggregating to a sum of Rs. [_____] (Rupees [_____] only), particulars whereof are set forth in the Statement of Account annexed hereto and marked as Annexure [_____]. Despite repeated oral and written demands by the Plaintiff, the Defendant has failed and neglected to pay or tender the said arrears.'*"
  - "Termination / vacation recital (where applicable) — *'The tenancy of the Defendant stood determined by efflux of time / by notice dated [_____] under Section 106 TPA 1882 / by surrender on [date]. Pursuant thereto, the Defendant vacated and delivered possession of the suit premises to the Plaintiff on [date].'* OR *'The Defendant continues in occupation of the suit premises as a statutory tenant / occupier, against whom the Plaintiff confines the present relief to arrears recovery without prejudice to any separate eviction proceeding.'*"
  - "Mesne profits recital — *'In addition to the said arrears, the Defendant is liable to pay mesne profits / damages for use and occupation of the suit premises at the prevailing market rate of Rs. [_____] per month for the period from [date — when tenancy determined or when continuing in wrongful possession] until vacation / until decree. The prevailing market rate is established by reference to comparable lease deeds in respect of similar premises in the same locality, particulars whereof are annexed at Annexure [_____], and the Ready Reckoner / Stamp Valuation rate for the locality.'*"
  - "Acknowledgement (where applicable, to extend limitation) — *'The Defendant, by his letter / email / WhatsApp message dated [_____] (annexed as Annexure _____), expressly acknowledged the liability for the arrears of rent within the meaning of Section 18 of the Limitation Act 1963, thereby providing a fresh period of limitation from the date of the said acknowledgement.'*"
  - "Cause of action — *'The cause of action for the present suit arose on [date — when arrears first became due] and continued to accrue with each subsequent month s default; the latest accrual being on [date]. The cause of action is within limitation under Article 52 of the Schedule to the Limitation Act 1963 [augmented by Section 18 acknowledgement where applicable].'*"
  - "Prayer — *'It is therefore most respectfully prayed that this Hon'ble Court may be pleased to: (a) pass a money decree in favour of the Plaintiff and against the Defendant for Rs. [_____] being the arrears of rent for the period [_____] to [_____]; (b) pass a money decree for Rs. [_____] being mesne profits / damages for use and occupation up to the date of suit; (c) award future mesne profits at Rs. [_____] per month from the date of suit until vacation of the suit premises; (d) award interest @ [9%] per annum from the date of suit until realisation; (e) award costs of the suit; and (f) pass such further and other orders as this Hon'ble Court may deem fit and proper.'*"
statutory_anchors:
  - "Order VII CPC (plaint) read with Order I CPC (parties) and Order II CPC (frame of suit)"
  - "Article 52 Schedule to the Limitation Act 1963 (three-year limitation for rent arrears)"
  - "Section 18 Limitation Act 1963 (effect of acknowledgement in writing)"
  - "Section 9 CPC (general jurisdiction)"
  - "Applicable State Court Fees Act (ad valorem)"
  - "Order XX Rule 12 CPC (decree for possession + mesne profits)"
limitation_position: "Article 52 Limitation Act 1963 — three years from the date arrears became due. Each monthly default accrues a fresh cause of action; arrears more than 3 years old before suit are barred unless extended by Section 18 acknowledgement / Section 19 part-payment. The Drafter computes per-month arrears within limitation and pleads acknowledgement / part-payment evidence."
forum_selection: "Pecuniary jurisdiction — total claim (arrears + mesne profits to date of suit + future mesne profits provisionally valued) determines Court. For composite eviction + arrears suit, State Rent Act may bar civil court jurisdiction even on the money component, requiring the entire suit before Rent Controller / Court of Small Causes."
notice_requirement: "Pre-suit notice not statutorily required for a pure money suit (unlike eviction where State Act notice is required). However, the Drafter typically issues a demand notice before filing, both for limitation-extension purposes (Section 18 acknowledgement response) and to demonstrate the Plaintiff s good-faith demand."
bharatiya_sakshya_check: "Statement of Account (rent ledger), tenancy agreement, prior rent receipts establishing pattern, bank statements showing rent credits / non-credits, demand notice + RPAD acknowledgement, comparable-rent evidence for mesne profits computation, acknowledgement evidence (letter / email / WhatsApp with Section 63 BSA certificate) — all to be marked as Bharatiya Sakshya Adhiniyam 2023 compliant exhibits."
```

## Statutory framework summary

- **Order VII CPC (Rules 1-11)** — Form of plaint: cause-title, parties, jurisdiction averment, facts constituting cause of action, relief sought, valuation for court-fee, verification.
- **Article 52 Limitation Act 1963** — For money payable for rent: three years from when the arrears became due.
- **Section 18 Limitation Act 1963** — Where, before the expiration of the prescribed period, an acknowledgement of liability in respect of any property or right has been made in writing signed by the party against whom such property or right is claimed, a fresh period of limitation shall be computed from the time when the acknowledgement was so signed.
- **Section 19 Limitation Act 1963** — Effect of part-payment of rent: where part-payment is made before expiration of limitation, fresh limitation runs from date of payment.
- **Section 9 CPC** — Civil court has jurisdiction to try all suits of a civil nature except those expressly or impliedly barred.
- **Order XX Rule 12 CPC** — Decree for recovery of immovable property with mesne profits — Court may pass decree (a) for possession; (b) for past mesne profits to date of institution; (c) for inquiry into future mesne profits.

## Distinct from Eviction Petition

| Feature | Eviction Petition | Recovery Suit |
|---|---|---|
| Primary relief | Vacant possession | Money decree |
| Forum | Rent Controller / Court of Small Causes / Civil Judge as RC | Civil Judge (per pecuniary jurisdiction) / CSC for tenancy-money |
| Statutory notice | State Rent Act notice required | Not statutorily required (advisable for limitation) |
| Limitation | Per State Rent Act / no specific period | Article 52 — 3 years per month default |
| Court fee | Typically fixed | Ad valorem on entire claim |
| Procedural law | State Rent Act + CPC where not inconsistent | CPC primarily |
| Tenant in possession | Tenant in possession is typical | Tenant typically vacated (else combined suit) |

The Drafter selects the procedural vehicle based on:
- Tenant in possession or vacated?
- Eviction relief required or money only?
- State Rent Act bar on civil court jurisdiction?
- Pecuniary jurisdiction of available forum?

## Combinable composite suit

In States where the State Rent Act does NOT bar civil court jurisdiction on the money component, the Plaintiff may file a COMPOSITE SUIT combining:

- Eviction relief under the State Rent Act
- Arrears recovery as money decree
- Mesne profits up to and beyond date of suit
- Damages for impairment / nuisance
- Interest under Section 34 CPC

In Maharashtra (Mumbai), the Court of Small Causes hears both eviction and tenancy-money suits, simplifying the composite-suit choice.

In Delhi, the Rent Controller s jurisdiction is exclusive for eviction; the money decree component is also typically passed by the Rent Controller alongside the eviction order — the Plaintiff need not file a separate civil suit.

## Mesne profits computation

Mesne profits under Section 2(12) CPC are the profits which the person in wrongful possession of property actually received or might with ordinary diligence have received from such property, together with interest, but not including profits due to improvements made by him.

Computation methodology:

1. **Comparable lease rents** — recent (last 1-2 years) lease deeds / agreements of similar premises in same locality
2. **Ready Reckoner / Stamp Valuation rate** — Stamp Authority published rental values
3. **Brokerage market rate** — affidavits / certificates from registered real-estate professionals
4. **Pre-suit period** — mesne profits from date of tenancy determination until date of suit
5. **Post-suit period** — future mesne profits — Court may direct inquiry under Order XX Rule 12(1)(c) CPC

The Drafter pleads provisional quantum for past mesne profits and prays for future mesne profits inquiry; court-fee paid on past component, future component reserved.

## Article 52 limitation discipline

Each monthly default accrues a fresh cause of action; the 3-year clock runs separately for each month. Practical consequence:

- For suit filed on [Date], arrears for [Date minus 3 years] onwards are within limitation
- Arrears more than 3 years before suit are barred UNLESS extended by Section 18 acknowledgement or Section 19 part-payment

The Drafter:

- Computes per-month arrears table with limitation flag
- Drops time-barred amounts (or pleads them with Section 18 / 19 extension argument)
- Annexes acknowledgement evidence (letter, email, WhatsApp message, payment receipt) where available
- For each acknowledgement, computes fresh 3-year period from acknowledgement date

## Section 18 acknowledgement framework

A valid Section 18 Limitation Act acknowledgement requires:

- Writing — letter, email, WhatsApp, court filing, partial-payment receipt
- Signed (or e-signed / authenticated under IT Act) by the Defendant or his agent
- Made before expiration of original limitation
- Acknowledges existence of liability (need not state amount precisely)

The Drafter scrutinises all communications post-arrears for acknowledgement signals — *"I will pay next month"*, *"please give me time"*, *"the amount is correct, kindly accept by month-end"* — these typically qualify under Section 18 case-law.

## Interest under Section 34 CPC

Interest is awardable in three components:

1. **Pre-suit interest** — at the contractual rate (where lease deed prescribes) OR at customary commercial rate (typically 9-12% p.a.)
2. **Pendente lite interest** — from date of suit to date of decree at rate fixed by Court (typically 6-9% p.a.)
3. **Future interest** — from date of decree to date of realisation (typically 6% p.a. unless Court directs otherwise)

The Drafter prays for each component separately with the proposed rate.

## Common opposing-counsel challenges

1. **Limitation bar** — arrears claimed beyond 3 years; no valid Section 18 acknowledgement.
2. **No tenancy / wrong landlord** — Defendant denies tenancy or denies privity with Plaintiff.
3. **Adjustment / set-off** — security deposit / advance / amenity-charges paid by Defendant set off against claim.
4. **Excess rent / standard rent dispute** — Defendant pleads agreed rent exceeded standard rent; counter-claim for refund.
5. **Mesne profits excessive** — Defendant pleads market rate is lower; comparable lease deeds unreliable.
6. **Pre-suit deposit / tender** — Defendant pleads rent was tendered / deposited under Section 8 MRC Act / equivalent; no actual default.
7. **Jurisdiction / forum** — pecuniary jurisdiction wrong; State Rent Act bars civil court; forum selection challenged.
8. **Cause of action defective** — vague pleadings, no specific per-month breakup, no acknowledgement signature verified.

The Drafter pre-empts these by: (a) Statement of Account with per-month breakup + limitation flag; (b) tenancy agreement / past receipts establishing privity + rent agreed; (c) RPAD-served demand notice; (d) acknowledgement evidence with Section 63 BSA certificate; (e) comparable-rents evidence + Ready Reckoner extract for mesne profits; (f) pecuniary-jurisdiction verification against State Court Fees Act + State Rent Act bar analysis. The Overseer surfaces residual gaps for the advocate's review.
