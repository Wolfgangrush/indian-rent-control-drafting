---
name: rent-deposit-application-draft
description: Draft a Rent Deposit Application under Section 8 of the Maharashtra Rent Control Act 1999, Section 27 of the Delhi Rent Control Act 1958, Section 21 of the Karnataka Rent Act 2001, Section 21 of the West Bengal Premises Tenancy Act 1997, Section 30 of the UP Urban Buildings Act 1972, and Section 9 of the AP / Telangana Buildings Control Act 1960. Encodes the trigger conditions (landlord refusal to accept rent / landlord dispute / multiple-claimant uncertainty / landlord absence / refusal of rent receipt), the reason-for-deposit pleading discipline, the procedure (deposit with the Rent Controller / Court of Small Causes / equivalent + intimation to landlord), the without-prejudice withdrawal mechanism (landlord may withdraw without surrender of rights), and the continuous-and-regular-deposit protection against non-payment eviction. Auto-fires on "draft rent deposit application", "draft rent deposit", "draft application deposit rent controller", "draft rent escrow application", and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# Rent Deposit Application Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_rent_control_drafting_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Case metadata

```yaml
case_type_line: APPLICATION FOR DEPOSIT OF RENT
case_short_code: RENT_DEPOSIT
role_party_1: Applicant / Tenant
role_party_2: Respondent / Landlord (or multiple Respondents where rival claimants)
typical_forum: "Maharashtra — Court of Small Causes (Mumbai) / Civil Judge as Rent Controller (rest of State) under Section 8 MRC Act · Delhi — Rent Controller under Section 27 DRC Act · Karnataka — Court of Small Causes / Civil Judge as Rent Controller under Section 21 KRA · West Bengal — Civil Judge (Junior Division) under Section 21 WBPT Act · UP — Munsif / Civil Judge under Section 30 UP Act · AP/Telangana — Rent Controller under Section 9"
typical_court_fee: "Fixed application fee per State Court Fees Act / Rent Act Rules — typically nominal (Rs. 25-100)."
operative_paragraphs:
  - "Tenancy recital — *'It is most respectfully submitted that the Applicant is the lawful tenant of the premises bearing No. [_____] situate at [_____] (hereinafter \"the suit premises\"), under the Respondent / Landlord at a monthly rent of Rs. [_____] payable on or before the [___] day of each English calendar month for the month then ended.'*"
  - "Reason for deposit — *'The Applicant has been ready and willing to pay the said monthly rent regularly, but has been unable to do so for the following reasons: (i) [Landlord has refused to accept the rent when tendered on dates ___, ___, ___, evidenced by witness affidavits and / or postal returns of money orders annexed as Annexure _____]; OR (ii) [Landlord has refused to issue rent receipts notwithstanding payment, putting the Applicant at risk of eviction on alleged non-payment]; OR (iii) [Landlord has expired / is absent / cannot be traced, and the heirs / legal representatives are disputing among themselves the identity of the proper recipient of rent]; OR (iv) [There is a bona fide dispute as to the identity of the landlord on account of (sale / partition / dispute among co-owners)].'*"
  - "Tender particulars — *'The Applicant tendered the rent for the month of [_____] amounting to Rs. [_____] to the Respondent on [date] by [mode — cash with witness / cheque / money order / demand draft / NEFT to last-known account / etc.], which tender was refused / returned / not accepted by the Respondent. Documentary evidence of the said tender and refusal is annexed hereto and marked as Annexure [_____].'*"
  - "Deposit prayer — *'The Applicant tenders herewith the monthly rent for the month(s) of [_____] amounting to Rs. [_____] for deposit with this Hon'ble Court under Section 8 of the Maharashtra Rent Control Act 1999 [or State equivalent], and undertakes to continue depositing the monthly rent regularly on or before the [___] day of each succeeding month during the pendency of any dispute between the Applicant and the Respondent.'*"
  - "Notice prayer — *'The Applicant prays that notice of this application and of every deposit made hereunder may be issued to the Respondent at the address [_____] by registered post acknowledgement due, to enable the Respondent to withdraw the deposit without prejudice to the rights of either party.'*"
  - "Prayer — *'It is therefore most respectfully prayed that this Hon'ble Court may be pleased to: (a) accept the deposit of Rs. [_____] tendered herewith as deposit of rent under Section 8 of the Maharashtra Rent Control Act 1999 [or State equivalent]; (b) issue notice to the Respondent of the deposit; (c) permit the Applicant to continue depositing the monthly rent regularly during the pendency of the dispute; (d) declare that such deposits constitute valid discharge of the Applicant s liability to pay rent; and (e) pass such further and other orders as this Hon'ble Court may deem fit and proper.'*"
statutory_anchors:
  - "Section 8 Maharashtra Rent Control Act 1999"
  - "Section 27 Delhi Rent Control Act 1958"
  - "Section 21 Karnataka Rent Act 2001"
  - "Section 21 West Bengal Premises Tenancy Act 1997"
  - "Section 30 UP Urban Buildings Act 1972"
  - "Section 9 AP/Telangana Buildings Control Act 1960"
registration_position: "Not applicable."
notice_requirement: "Statutory notice / intimation of every deposit issued by Court to Respondent under State Act Rules + Applicant s independent intimation by registered post AD."
v_dhanapal_chettiar_check: "Not applicable — rent-deposit mechanism is exclusively under the State Rent Act."
bharatiya_sakshya_check: "Tender evidence (witness affidavits, money-order receipts, returned cheques, NEFT transaction records, email / WhatsApp screenshots of refusal), tenancy agreement / past rent receipts, landlord-refusal correspondence — all to be marked as Bharatiya Sakshya Adhiniyam 2023 compliant exhibits. Electronic records (NEFT / UPI / email) require Section 63 BSA certificate."
protection_position: "Continuous and regular deposit under Section 8 MRC Act protects tenant against eviction on the ground of non-payment of rent under Section 16(1)(a) MRC Act / Section 14(1)(a) DRC Act / equivalent. Deposit must be REGULAR (within statutory due dates) and CONTINUOUS (every month without break) — irregular / sporadic deposits do NOT afford protection."
```

## Statutory framework summary

- **Section 8 MRC Act 1999** — Where landlord does not accept rent lawfully tendered or where bona fide doubt arises as to the person to whom rent is payable, the tenant may deposit such rent with the Court / Rent Controller in the prescribed manner. The Court shall give notice of the deposit to the landlord, who may withdraw the deposited rent without prejudice to his rights to contest. Regular deposit constitutes valid discharge of liability.
- **Section 27 DRC Act 1958** — Identical structure — Delhi Rent Controller accepts deposit on grounds of refusal / dispute / absence; landlord may withdraw without prejudice.
- **Section 21 KRA 2001** — Karnataka equivalent.
- **Section 21 WBPT Act 1997** — West Bengal equivalent; with prescribed forms under the WBPT Rules.
- **Section 30 UP Urban Buildings Act 1972** — UP equivalent; deposit before Munsif having jurisdiction.

## Trigger conditions (grounds for deposit)

The Application MUST plead one or more of the following triggers:

1. **Landlord refusal to accept** — tenant tendered rent on prescribed dates, landlord refused (witness corroboration / postal return of money order / returned cheque / refusal endorsement)
2. **Landlord refusal to issue receipt** — tenant pays but landlord refuses receipt, exposing tenant to false non-payment eviction
3. **Landlord absent / cannot be traced** — landlord shifted / abroad / deceased / heirs not identifiable
4. **Multiple-claimant dispute** — co-owners disputing inter se / sale of premises with conflicting claims / heirship contest — tenant unsure of correct recipient
5. **Landlord-disputed status of premises** — landlord disputes the tenancy itself / status is uncertain pending litigation

Each ground must be supported by specific factual pleading with documentary evidence.

## Documentary evidence stack (mandatory)

- **Tender evidence** — witness affidavits (where tendered in cash with witness), returned money orders (Indian Postal Service receipt with return endorsement "refused"), returned cheques (with bank memo "refused / not presented"), NEFT/UPI transaction records (with bank statement showing reversal / non-acceptance)
- **Refusal correspondence** — emails, WhatsApp messages, letters from landlord refusing to accept / disputing the rent
- **Tenancy agreement / past rent receipts** — establishing the tenancy and pre-dispute rent acceptance pattern
- **Landlord-absence evidence** — postal returns marked "addressee not available", death certificates, multiple-claimant correspondence
- **Section 63 BSA certificate** — for all electronic-evidence exhibits

## Procedure (Section 8 MRC Act / State equivalent)

1. Application in prescribed form with court-fee + first deposit amount (cash / demand draft in favour of Court)
2. Court accepts deposit and registers the application
3. Court issues notice of deposit to landlord at address furnished by tenant
4. Landlord may:
   - Withdraw the deposit "without prejudice" (no surrender of rights to contest tenancy / rent quantum / eviction grounds)
   - File objections challenging the validity of deposit / the tenant s tendered amount / the tenant s ground for deposit
   - Ignore the notice (deposit continues to accrue with Court)
5. Tenant must continue depositing every month on or before the prescribed due date
6. Default in continuous deposit defeats the protection

## Without-prejudice withdrawal mechanism

The landlord may withdraw the deposited amount at any time WITHOUT prejudice to:

- His right to contest the validity of the deposit
- His right to claim higher rent / standard rent / permitted increases
- His right to seek eviction on any ground
- His right to argue that the deposit is short / partial / not in compliance

The Drafter pleads the without-prejudice protection so that the landlord does not face the false dilemma of "accept = compromise position" vs "refuse = lose money".

## Regular-and-continuous-deposit protection

The Section 8 MRC Act / Section 27 DRC Act / equivalent protection against non-payment eviction is available ONLY where:

- Deposits are REGULAR — within the statutory due date each month (typically end of the month for which rent is due)
- Deposits are CONTINUOUS — every month without break
- Deposits are for the FULL admitted rent (not partial)
- Deposits include all permitted increases / amenity charges where lawfully due

Sporadic / partial / delayed deposits do NOT afford protection. The Drafter pleads the tenant s commitment to regular continuous deposit and counsels the tenant on calendar discipline.

## Distinct from rent-control deposit pendente lite

Note the distinction:

- **Rent Deposit Application (this skill)** — pre-emptive deposit by tenant to protect against future non-payment eviction; tenant-initiated; based on landlord refusal / dispute
- **Section 11(4) MRC Act deposit pendente lite** — Court-ordered deposit during pendency of eviction petition; landlord-initiated application; based on Court's direction during pending eviction proceedings

The two mechanisms operate at different stages and serve different functions; the Drafter selects the correct one based on the procedural posture.

## Common opposing-counsel challenges

1. **No valid tender** — landlord pleads tender was not made, or was made at improper time / place / mode.
2. **Tendered amount short** — landlord pleads deposit is partial / does not include permitted increases / amenity charges / cesses.
3. **No bona fide dispute** — landlord pleads no genuine refusal / dispute; the deposit application is pretextual.
4. **Deposit delayed / irregular** — landlord pleads break in continuity; protection lost.
5. **Premises sold / landlord changed** — fresh deposit application required under new landlord s name.
6. **Heirship dispute fabricated** — landlord pleads heirship dispute is fictitious; identity of recipient was clear.

The Drafter pre-empts these by: (a) precise tender particulars with witness / postal / electronic evidence; (b) full-amount deposit including admitted permitted increases; (c) regular calendar reminders to tenant for continuous deposit; (d) documentary support for refusal / dispute trigger; (e) updating application when landlord changes (sale / partition / heirship resolution). The Overseer surfaces residual gaps for the advocate's review.
