---
name: _rent_control_drafting_base
description: Universal Indian rent-control / landlord-tenant pleading skeleton. Shared base for all 11 case-type drafting skills. Holds the standard structure (Cause Title with forum + matter type + parties -> Statutory Opening invoking the applicable State Rent Control Act provisions -> Prelude with tenancy origin, last paid rent, statutory notice trajectory, standing -> FACTS with rent-history chronology and eviction-ground-specific factual matrix -> GROUNDS -> PRAYER -> Verification under Order VI Rule 15 CPC -> Counsel block -> Index -> Synopsis -> List of Annexures -> Accompanying Applications). NOT invoked directly — extended by every case-type skill in this plugin.
allowed-tools: Read
---

# `_rent_control_drafting_base` — universal Indian rent-control pleading skeleton

This base skill defines the **structural shape** of any Indian rent-control / landlord-tenant pleading drafted by the plugin. Case-type skills extend this base with case-type-specific statutory openings, ground-specific factual matrices, and prayer-clause framing.

## Universal skeleton

```
1. CAUSE TITLE
   IN THE [FORUM — Court of Small Causes at [Place] / Rent Controller,
   [Place] / Court of the Civil Judge as Rent Controller, [Place] /
   Rent Authority, [Place] / Rent Tribunal, [Place] / Prescribed
   Authority, [Place] / High Court of [State] at [Place]]

   {{matter_type}} No. ___ of {{year}}
   (e.g. EVICTION PETITION / STANDARD RENT APPLICATION /
    RENT DEPOSIT APPLICATION / RENT CONTROL APPEAL / REVISION
    PETITION / NOTICE OF TERMINATION / RECOVERY SUIT /
    WRITTEN STATEMENT)

   IN THE MATTER OF:
   [Landlord/Petitioner full description — name, age, parentage,
    occupation, full address with PIN]
   ...Landlord / Petitioner / Applicant / Plaintiff / Appellant /
      Revisionist / Respondent (as the case may be)

   VERSUS

   [Tenant/Respondent full description as above]
   ...Tenant / Respondent / Defendant / Respondent in Appeal /
      Respondent in Revision (as the case may be)

2. STATUTORY OPENING
   Petition / Application / Suit / Appeal / Revision / Notice
   filed under [the applicable section of the applicable State
   Rent Control Act / TPA 1882 / CPC 1908 / Constitution Article].
   For an Eviction Petition: typically under Section 16(1)(__) of
   the Maharashtra Rent Control Act 1999 / Section 14(1)(__) of
   the Delhi Rent Control Act 1958 / Section 21(1)(__) of the UP
   Urban Buildings Act 1972 / Section 27(2)(__) of the Karnataka
   Rent Act 2001 / Section 6 of the West Bengal Premises Tenancy
   Act 1997 / the corresponding Tamil Nadu 2017 Act section.

3. PRELUDE
   The Petitioner / Applicant / Plaintiff / Appellant / Revisionist
   most respectfully submits as follows:

4. FACTS (numbered paragraphs)
   Para 1 — Tenancy origin
     Tenancy commenced on [Tenancy-Commencement-Date] in respect
     of the premises bearing [Premises-Description], situated at
     [Address], within the jurisdiction of this Hon'ble Court.
     The tenancy was created by [oral agreement / written
     tenancy agreement dated ___ / a registered lease deed
     dated ___]. The premises were let out for [residential /
     non-residential / mixed] purpose at a monthly rent of
     [Monthly-Rent-Placeholder], exclusive of municipal taxes
     and statutory deductions.

   Para 2 — Standing of the Petitioner
     The Petitioner is the [absolute owner / co-owner with
     authority of the other co-owners / lessor by virtue of
     registered lease deed dated ___ / legal heir of the
     deceased landlord under Section ___ Hindu Succession Act
     1956 / authorised attorney under registered Power of
     Attorney dated ___] of the suit premises and is competent
     to institute the present petition.

   Para 3 — Rent payment history
     The Tenant paid rent regularly until [Last-Paid-Rent-Date],
     after which [the Tenant defaulted in payment of rent from
     ___ till date / the Tenant has been paying rent under
     protest pending standard-rent fixation in Application
     No. ___ / the Tenant has been depositing rent in this
     Hon'ble Court / before the Rent Controller in Deposit
     Application No. ___ since ___].

   Para 4-N — Ground-specific factual matrix
     (Each eviction ground / each application type has its own
      Para 4-N matrix — bona-fide need recitals / nuisance
      and damage particulars / sub-letting particulars / arrears
      computation / standard-rent computation / etc. The
      case-type skill specifies the relevant paragraphs.)

   Para N+1 — Section 106 TPA notice (where required)
     A statutory notice under Section 106 of the Transfer of
     Property Act 1882, terminating the tenancy with effect
     from [Notice-Expiry-Date], was issued to the Tenant on
     [Notice-Date] by registered post acknowledgement due. The
     Tenant [received the notice on ___ / refused service /
     replied vide letter dated ___ denying the contents]. The
     notice and the postal acknowledgement are annexed and
     marked as Annexure [__]. (Where the State Rent Control Act
     dispenses with the Section 106 TPA notice per V. Dhanapal
     Chettiar v. Yesodai Ammal (1979) 4 SCC 214, this paragraph
     is omitted and the corresponding State Act notice paragraph
     is inserted.)

   Para N+2 — Cause of action
     The cause of action for the present petition arose on
     [Cause-of-Action-Date] when [the Tenant defaulted in payment
     of rent / the Tenant sub-let the premises / the Petitioner's
     bona-fide need crystallised / the nuisance complained of
     occurred / the Section 106 TPA notice expired without
     compliance], and is continuing.

   Para N+3 — Jurisdiction
     This Hon'ble Court / Rent Controller / Court of Small Causes
     has territorial jurisdiction by reason of the situs of the
     suit premises within [Jurisdiction-Locality], and pecuniary
     jurisdiction by reason of the [annual rent / Premises value]
     being within the prescribed limits.

   Para N+4 — Limitation
     The present petition is filed within the period prescribed
     by [the State Rent Control Act / Article ___ of the
     Limitation Act 1963], the cause of action having arisen on
     [Cause-of-Action-Date].

   Para N+5 — Court Fee
     The petition is filed on Court Fee of Rs. ___ paid under
     [the applicable State Court Fees Act schedule entry].

5. GROUNDS (numbered Roman or Arabic, one ground per paragraph)
   I. {{ground_1}} — e.g. "That the Tenant has been in arrears
       of rent for a continuous period of [N] months from
       [start-date] to [end-date], which arrears were not
       cleared within the period prescribed under Section 15
       of the Maharashtra Rent Control Act 1999 read with the
       statutory notice dated [Notice-Date]"
   II. {{ground_2}} — e.g. "That the suit premises are required
        bona-fide by the Petitioner / Landlord for his own
        occupation / for the occupation of [family member] who
        is dependent upon him, as more particularly pleaded in
        Para [__] above, and the Petitioner has no other
        reasonably suitable residential accommodation"
   III. {{ground_3}} — e.g. "That per Ragavendra Kumar v. Firm
         Prem Machinary (2000) 1 SCC 679, the landlord is the
         best judge of his own requirement and the Tenant
         cannot dictate which of the Petitioner's premises he
         should occupy"
   (Additional grounds as the case-type requires.)

6. PRAYER
   In the premises aforesaid, the Petitioner / Applicant /
   Plaintiff / Appellant most respectfully prays that this
   Hon'ble Court / Rent Controller / Court of Small Causes be
   pleased to:

   (a) Pass an order of eviction against the Tenant in respect
       of the suit premises more particularly described in
       Schedule A hereto, and to direct the Tenant to deliver
       vacant and peaceful possession thereof to the Petitioner;
   (b) Direct the Tenant to pay the arrears of rent of Rs. ___
       together with interest at the rate of __% per annum from
       the date of default till realisation;
   (c) Direct the Tenant to pay mesne profits at the rate of
       Rs. ___ per month from the date of termination of
       tenancy till delivery of vacant possession;
   (d) Award costs of the petition; and
   (e) Pass such further or other order(s) as this Hon'ble
       Court may deem fit and proper in the facts and
       circumstances of the case.

7. VERIFICATION BLOCK
   I, [Deponent], the Petitioner above-named, do hereby verify
   that the contents of paragraphs ___ to ___ are true to my
   personal knowledge, and the contents of paragraphs ___ to
   ___ are true to my information received and believed by me
   to be true.

   Verified at [Place] on this __ day of [Month, Year].

                                          [Signature of Deponent]

8. COUNSEL BLOCK
   [Petitioner / Applicant / Plaintiff / Appellant]
   Through

   [Advocate's Name]
   Advocate for the Petitioner
   Enrolment No. ___
   Address for service: ___
   Mobile: ___    Email: ___

9. INDEX
   | Sl. No. | Description | Page Nos. |
   |---------|-------------|-----------|
   | 1       | Synopsis    | __ - __   |
   | 2       | List of Annexures | __ - __ |
   | 3       | Memo of Petition with Verification | __ - __ |
   | 4       | Annexure A — [description] | __ - __ |
   | 5       | Annexure B — [description] | __ - __ |
   | ...     | ...         | ...       |
   | N       | Accompanying Application(s) | __ - __ |
   | N+1     | Vakalatnama | __        |

10. SYNOPSIS
    A 1-2 page concise narrative of the tenancy origin, the
    grounds of eviction relied upon, the statutory notice
    trajectory, the rent-payment history, the prior proceedings
    (if any), and the relief sought. Drafted in the third
    person, neutral tone.

11. LIST OF ANNEXURES
    Annexure A — Tenancy agreement / oral-tenancy proof
    Annexure B — Rent receipts / counterfoils
    Annexure C — Section 106 TPA notice + postal acknowledgement
    Annexure D — Tenant's reply (if any)
    Annexure E — Title documents of the Petitioner
    Annexure F — Bank statement showing non-payment of rent
                 (for non-payment cases)
    Annexure G — Affidavit on bona-fide need
                 (for bona-fide need cases)
    Annexure H — Sub-tenancy evidence (rent receipts to
                 sub-tenant / photograph of board / utility
                 bills in sub-tenant's name) — for sub-letting
                 cases
    Annexure I — Damage report / photographs (for nuisance /
                 damage cases)
    Annexure J — Police complaint copies (for nuisance cases)
    Annexure K — Standard-rent application order (where
                 applicable)
    Annexure L — Rent-deposit receipts (where applicable)
    (Annexures vary per case-type.)

12. ACCOMPANYING APPLICATIONS
    - Application under Section 11(4) Maharashtra Rent Control
      Act 1999 / equivalent for interim direction to deposit
      rent during pendency
    - Application for ad-interim injunction restraining the
      Tenant from creating any third-party interest pending
      hearing
    - Application for striking out defence under Section 25B(4)
      Delhi Rent Control Act 1958 (in summary procedure cases)
    - Application for production / discovery of documents
    - Application for amendment of pleadings
    - Vakalatnama / Memo of Appearance
```

## Statute references the plugin handles

- Transfer of Property Act 1882 (Sections 105-117 [general law of lease]; Section 106 [termination notice]; Section 111 [determination]; Sections 114 / 114A [relief against forfeiture])
- Maharashtra Rent Control Act 1999 (Sections 7 [standard rent], 8 [rent deposit], 11 [statutory increase + interim direction to deposit], 15 [non-payment ground], 16 [grounds for eviction], 22 [transfer / assignment], 33 [forum — Court of Small Causes / District Court], 34 [appeal], 35 [revision], 56 [pagdi system])
- Delhi Rent Control Act 1958 (Sections 14 [grounds incl. (a) non-payment, (e) bona-fide residential need, (h) sub-letting], 14A [residential premises required by Central Government employees], 14B-D [special categories], 25A-C [Chapter IIIA summary procedure for bona-fide need], 27 [rent deposit])
- Tamil Nadu Regulation of Rights and Responsibilities of Landlords and Tenants Act 2017 (registration of tenancy agreements; Rent Authority + Rent Tribunal forums; Model-Tenancy-Act adopter framework)
- Karnataka Rent Act 2001 (Section 27 [eviction grounds]; Civil Judge as Rent Controller)
- West Bengal Premises Tenancy Act 1997 (Section 6 [grounds]; Controller of Rent at Kolkata; standard-rent formula)
- Uttar Pradesh Urban Buildings (Regulation of Letting, Rent and Eviction) Act 1972 (Section 20 [bar of suit without permission of District Magistrate where applicable], 21 [release application before Prescribed Authority — the UP-distinctive bona-fide need ground], 30 [rent deposit])
- Gujarat Rent Control Act 1947 (as amended)
- Andhra Pradesh / Telangana Buildings (Lease, Rent and Eviction) Control Act 1960 (Rent Controller hierarchy; eviction grounds in Section 10)
- Model Tenancy Act 2021 (Central model law; adoption by States is opt-in; Andhra Pradesh and Tamil Nadu (with modifications) and Uttar Pradesh have notified or are in the process)
- Code of Civil Procedure 1908 (Order VI Rule 15 [verification]; Order VII Rule 1 [plaints]; Order VIII Rule 1 [written statements]; Section 9 [civil court jurisdiction]; Section 115 [revision])
- Limitation Act 1963 (Articles 51, 52, 61)
- Bharatiya Sakshya Adhiniyam 2023 (Section 132 [advocate-client privilege]; Section 63 [electronic record certificate])
- Bharatiya Nagarik Suraksha Sanhita 2023 (for execution-side cross-references where eviction decree warrants police aid)
- Indian Stamp Act 1899 (for stamp on plaints / petitions / tenancy agreements)
- Court Fees Act 1870 / applicable State Court Fees Act (for ad valorem court fee on plaints / petitions)
- Constitution of India (Article 226 / 227 for High Court revisional jurisdiction over Rent Controller orders)
