---
name: model-tenancy-act-2021-framework-draft
description: Draft pleadings under the Model Tenancy Act 2021 (the Central Government model law adopted by Andhra Pradesh and partially overlapping with Tamil Nadu, with UP and other States in the process of adoption). Encodes the MTA 2021 architecture — Section 4 (compulsory written tenancy agreement and registration with Rent Authority within 2 months of execution), Section 5 (Rent Authority — administrative + standard-rent fixation + security-deposit disputes), Section 6 (Rent Court — eviction + damages + recovery), Section 7 (Rent Tribunal — appeals from Rent Court), Section 24 (security-deposit cap — 2 months for residential / 6 months for non-residential), Section 32 (eviction grounds — exhaustive list mirroring State Rent Acts plus modernised grounds), Section 35 (eviction procedure — fast-track with 60-day disposal target), Section 41 (appellate procedure). Encodes the forum-selection discipline (Rent Authority vs Rent Court vs Rent Tribunal per dispute type), the tenancy-date-based selection rule (post-MTA-adoption tenancies governed by MTA; pre-adoption tenancies typically retain State Rent Act protection), and the adoption-status verification step (Drafter MUST verify State has adopted MTA before invoking — verify in state-config exemplar). Auto-fires on "draft model tenancy act pleading", "draft MTA 2021", "draft tenancy under model act", "draft eviction MTA", "draft rent authority application", and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# Model Tenancy Act 2021 Framework — Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_rent_control_drafting_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Case metadata

```yaml
case_type_line: APPLICATION / PETITION UNDER THE MODEL TENANCY ACT 2021
case_short_code: MTA_2021_PLEADING
role_party_1: Applicant / Petitioner (Landlord OR Tenant depending on pleading)
role_party_2: Respondent (counter-party)
typical_forum: "Rent Authority — Section 5 MTA (administrative + standard-rent fixation + security-deposit + minor disputes) · Rent Court — Section 6 MTA (eviction petitions + damages + recovery of arrears) · Rent Tribunal — Section 7 MTA (appeals from Rent Court orders + revisional jurisdiction). Each State that adopts MTA constitutes its own Rent Authority / Court / Tribunal — verify state-specific notification before filing."
typical_court_fee: "Per State Rules framed under MTA adoption notification — typically nominal for Rent Authority applications; ad valorem for Rent Court money-claims."
operative_paragraphs:
  - "Cause title — *'BEFORE THE HON BLE [Rent Authority / Rent Court / Rent Tribunal] AT [____] — CASE NO. [____] OF [____] — Applicant: [Party] — Respondent: [Party] — APPLICATION / PETITION UNDER THE MODEL TENANCY ACT 2021 AS ADOPTED IN THE STATE OF [____]'*"
  - "Adoption + jurisdiction recital — *'It is most respectfully submitted that the State of [____] has adopted the Model Tenancy Act 2021 vide Notification dated [____] / Act No. [____] of [____], with effect from [____], and the present matter is governed by the said Act read with the Rules framed thereunder.'*"
  - "Tenancy recital — *'The premises bearing No. [____] situate at [____] (hereinafter \"the tenancy premises\") were let by the Petitioner / Landlord to the Respondent / Tenant by a written tenancy agreement dated [____] (annexed as Annexure A) at a monthly rent of Rs. [____] for a term of [____] months / years, with a security deposit of Rs. [____] equivalent to [____] months rent (within the Section 24 MTA cap of 2 months for residential / 6 months for non-residential). The said tenancy agreement was duly registered with the Rent Authority at [____] on [____] within the 2-month period prescribed under Section 4 MTA, bearing Registration Number [____].'*"
  - "Cause of action — *'The cause of action for the present petition arose on [____] when [eviction ground occurred / standard-rent dispute crystallised / security-deposit was wrongfully withheld / etc.]. The relevant facts are: (i) [____]; (ii) [____]; (iii) [____].'*"
  - "Forum jurisdiction recital — *'This Hon'ble [Rent Authority / Rent Court / Rent Tribunal] has jurisdiction under Section [5 / 6 / 7] of the Model Tenancy Act 2021 to entertain and decide the present matter, the premises being situate within the territorial jurisdiction of this Hon'ble Forum and the subject-matter falling within the powers conferred under the said Section.'*"
  - "Statutory ground — *'The Petitioner relies on Section 32(1)([____]) of the Model Tenancy Act 2021 [for eviction matters] / Section 24(2) [for security-deposit disputes] / Section [____] [for the specific relief sought]. The ingredients of the said ground are made out as follows: (i) [____]; (ii) [____]; (iii) [____].'*"
  - "Prayer — *'It is therefore most respectfully prayed that this Hon'ble [Rent Authority / Rent Court / Rent Tribunal] may be pleased to: (a) [grant the specific relief — eviction / standard rent fixation / security deposit refund / etc.]; (b) award damages / mesne profits / interest as applicable; (c) award costs; and (d) pass such further and other orders as this Hon'ble Forum may deem fit and proper.'*"
statutory_anchors:
  - "Model Tenancy Act 2021 (Central model law)"
  - "Section 4 MTA — Compulsory written tenancy agreement + registration with Rent Authority within 2 months"
  - "Section 5 MTA — Rent Authority (administrative + standard-rent + security-deposit disputes + minor disputes)"
  - "Section 6 MTA — Rent Court (eviction + damages + recovery)"
  - "Section 7 MTA — Rent Tribunal (appeals + revisional jurisdiction)"
  - "Section 24 MTA — Security-deposit cap (2 months residential / 6 months non-residential)"
  - "Section 32 MTA — Eviction grounds (exhaustive)"
  - "Section 35 MTA — Eviction procedure (fast-track; 60-day disposal target)"
  - "Section 41 MTA — Appellate procedure"
  - "Relevant State adoption notification / State Act / State Rules framed under MTA"
adoption_status_note: "MTA 2021 is a CENTRAL MODEL LAW under the Concurrent List subject (Entry 7 Concurrent List — contracts). It does NOT operate of its own force; each State must adopt by notification. ADOPTION STATUS AS AT 2026-05-17 — Andhra Pradesh (notified, in force) · Tamil Nadu (TN 2017 Act predates and overlaps; adoption with modifications) · Uttar Pradesh (in process — verify before filing) · Other States: not adopted. The Drafter MUST verify the State has adopted MTA before invoking; for non-adopting States, the relevant State Rent Control Act (Maharashtra Rent Control Act 1999 / Delhi Rent Control Act 1958 / Karnataka Rent Act 2001 / West Bengal Premises Tenancy Act 1997 / etc.) governs."
notice_requirement: "Per MTA Rules — notice between Landlord and Tenant required for material breaches; notice before approaching Rent Court for eviction; notice by Tenant before security-deposit recovery claim. Modern fast-track design — most pre-litigation notices have shorter cure periods (15-30 days)."
v_dhanapal_chettiar_check: "Not applicable — MTA exhaustively governs tenancy under its scope; Section 106 TPA notice displaced where MTA-registered tenancy exists. Pre-MTA tenancies continue under State Rent Act or general law."
bharatiya_sakshya_check: "Written tenancy agreement (mandatory under Section 4 MTA), Rent Authority registration certificate, rent receipts / payment records (typically digital — UPI / bank transfer / Rent Authority portal records), security-deposit receipts, communications between Landlord and Tenant — all to be marked as Bharatiya Sakshya Adhiniyam 2023 compliant exhibits. MTA design favours digital records; Section 63 BSA certificate to be prepared for each electronic exhibit."
forum_distinction: "RENT AUTHORITY (administrative) — registration of tenancy, standard rent fixation, security-deposit disputes, minor disputes, factual disputes capable of summary determination. RENT COURT (judicial) — eviction petitions, damages, arrears recovery, complex contested matters. RENT TRIBUNAL (appellate) — appeals from Rent Court orders, revisional jurisdiction. Drafter selects correct forum based on the relief sought; misfiled matters returned for filing before correct forum."
```

## Statutory framework summary

- **Section 1 MTA 2021** — Short title; State adoption mechanism; commencement on State notification.
- **Section 2 MTA 2021** — Definitions — "landlord", "tenant", "premises", "rent", "rent authority", "rent court", "rent tribunal", "security deposit", "tenancy agreement", "written agreement".
- **Section 3 MTA 2021** — Application — to premises let on or after the commencement of the Act in the State; not retrospective; pre-existing tenancies governed by erstwhile law unless parties opt-in to MTA.
- **Section 4 MTA 2021** — Tenancy agreement to be in writing + signed by both parties + registered with Rent Authority within 2 months of execution. Failure to register makes the agreement inadmissible in evidence for any purpose other than collateral purpose.
- **Section 5 MTA 2021** — Rent Authority — appointed by State Government; quasi-judicial; powers to register tenancy agreements, fix standard rent, resolve security-deposit disputes, refer parties to Rent Court for major disputes.
- **Section 6 MTA 2021** — Rent Court — constituted by State Government; judicial court (typically Civil Judge designated); exclusive jurisdiction over eviction + damages + recovery + breach of tenancy.
- **Section 7 MTA 2021** — Rent Tribunal — appellate forum from Rent Court orders; typically District Judge or specialised tribunal.
- **Section 24 MTA 2021** — Security deposit shall not exceed:
  - TWO months rent for residential premises
  - SIX months rent for non-residential premises
  - Excess collected = refundable forthwith
  - Security deposit to be returned within ONE month of tenant vacating, subject to lawful deductions for damages / dues
- **Section 32 MTA 2021** — Eviction grounds (exhaustive):
  - (a) Failure to pay rent for arrears period
  - (b) Sub-letting without landlord s consent
  - (c) Breach of essential term of tenancy
  - (d) Use of premises for purpose other than tenancy use
  - (e) Causing damage / nuisance
  - (f) Bona fide need of landlord (for self / family member)
  - (g) Premises required for repair / reconstruction
  - (h) Premises required for demolition under municipal / development authority order
  - (i) Other grounds prescribed under State adoption Rules
- **Section 35 MTA 2021** — Eviction procedure:
  - Summary procedure with pleading + reply timelines
  - 60-DAY DISPOSAL TARGET from filing
  - Digital filing where State has framed Rules
  - Limited adjournments
- **Section 41 MTA 2021** — Appellate procedure:
  - Appeal to Rent Tribunal within 30 days
  - Tribunal s decision typically final; further challenge by writ petition under Article 226 / 227

## State adoption status (as at 2026-05-17)

| State | Adoption Status | Effective Date | Notes |
|---|---|---|---|
| Andhra Pradesh | NOTIFIED + IN FORCE | 2021 onwards | First mover; Rent Authority constituted |
| Tamil Nadu | OVERLAPPING — TN Act 2017 + MTA adoption with modifications | TN Act 2017 predates | Verify which Act applies to specific tenancy |
| Uttar Pradesh | IN PROCESS | Pending | Continue under UP Urban Buildings Act 1972 until notified |
| Maharashtra | NOT ADOPTED | N/A | Maharashtra Rent Control Act 1999 governs |
| Delhi | NOT ADOPTED | N/A | Delhi Rent Control Act 1958 governs |
| Karnataka | NOT ADOPTED | N/A | Karnataka Rent Act 2001 governs |
| West Bengal | NOT ADOPTED | N/A | West Bengal Premises Tenancy Act 1997 governs |
| Other States | NOT ADOPTED | N/A | State-specific Rent Act governs |

**Drafter MUST verify current adoption status before filing — refer to state-config exemplar in the plugin or to the State Government Gazette.**

## Tenancy-date-based selection rule

| Tenancy Commencement | Premises in MTA-adopted State | Premises in non-MTA State |
|---|---|---|
| Pre-MTA adoption | Erstwhile State Rent Act / General law (TPA) | State Rent Act / General law (TPA) |
| Post-MTA adoption | Model Tenancy Act 2021 | State Rent Act / General law (TPA) |
| Mutually opted-in (post-adoption) | Model Tenancy Act 2021 (per opt-in clause) | NOT APPLICABLE |

Pre-MTA tenancies continue under their original legal regime unless parties mutually opt-in to MTA. Post-MTA tenancies in adopting States are governed by MTA by operation of Section 3.

## Compulsory written tenancy agreement (Section 4 MTA)

Every tenancy under MTA MUST be in writing. The written agreement MUST contain:

- Identities of Landlord and Tenant (with KYC)
- Premises particulars (address, area, type)
- Rent amount + due date + escalation
- Security deposit (within Section 24 cap)
- Term of tenancy
- Tenancy purpose (residential / non-residential / mixed)
- Rights and obligations of each party
- Maintenance and repair responsibilities
- Termination grounds
- Notice periods

The written agreement MUST be registered with the Rent Authority within 2 months of execution. Registration is online in most adopting States — the Rent Authority issues a Tenancy Registration Number which is the proof of valid MTA tenancy.

## Security-deposit discipline (Section 24 MTA)

- Maximum 2 months rent for RESIDENTIAL premises
- Maximum 6 months rent for NON-RESIDENTIAL premises
- Excess collected is refundable forthwith
- Deposit to be returned within 1 month of tenant vacating
- Lawful deductions only — for unpaid rent / damages / utility dues
- Wrongful withholding of deposit = grounds for Tenant's application to Rent Authority

## Forum-selection discipline

The Drafter selects the correct forum based on the relief sought:

| Relief Sought | Correct Forum | Section |
|---|---|---|
| Registration of tenancy agreement | Rent Authority | Section 4 + Section 5 |
| Standard-rent fixation | Rent Authority | Section 5 |
| Security-deposit refund | Rent Authority | Section 5 + Section 24 |
| Minor factual disputes capable of summary determination | Rent Authority | Section 5 |
| EVICTION on Section 32 grounds | Rent Court | Section 6 + Section 32 + Section 35 |
| Damages for breach of tenancy | Rent Court | Section 6 |
| Recovery of arrears | Rent Court | Section 6 |
| APPEAL from Rent Court order | Rent Tribunal | Section 7 + Section 41 |
| Revisional / review of Tribunal order | High Court under Article 226 / 227 | Constitutional |

Misfiled matters are returned for filing before the correct forum, costing time. The Drafter verifies forum competence at petition-drafting stage.

## MTA-specific advantages (drafting talking-points)

When the Drafter is invoked by Landlord OR Tenant in an MTA-adopting State, the modernised features are pleaded as advantages:

- **Compulsory written agreement** — removes disputes about tenancy terms
- **Registration with Rent Authority** — public record of tenancy
- **Digital filing + digital payment trail** — evidence simpler to lead
- **60-day eviction disposal target** — much faster than State Rent Acts
- **Capped security deposit** — protects Tenant
- **One-month return of deposit** — clear timeline for Landlord and Tenant
- **Tribunal appellate structure** — appellate timelines fixed
- **Standardised eviction grounds** — fewer pleading ambiguities

## Common opposing-counsel challenges

1. **State has not adopted MTA** — Respondent challenges jurisdiction; petition returned for filing under State Rent Act.
2. **Tenancy agreement not in writing / not registered with Rent Authority** — agreement inadmissible under Section 4 proviso; tenant denies tenancy terms.
3. **Tenancy commenced before MTA adoption** — MTA does not apply; State Rent Act / general law governs.
4. **Wrong forum** — eviction filed before Rent Authority instead of Rent Court (or vice versa); petition returned.
5. **Security-deposit cap exceeded** — Landlord's claim to forfeit deposit beyond Section 24 cap denied.
6. **60-day disposal target relied on by Landlord but adjournments granted** — Tenant pleads no prejudice; status quo continues.
7. **Section 32 ground not made out** — exhaustive list; Landlord cannot import grounds from other State Rent Acts.
8. **Adoption State Rules not framed yet** — for States that have adopted but not framed Rules, procedural ambiguities remain.

The Drafter pre-empts these by: (a) verifying State adoption status + Rules framed before filing; (b) annexing registered tenancy agreement + Rent Authority registration certificate; (c) verifying tenancy-date is post-adoption; (d) selecting correct forum per relief sought; (e) computing security-deposit cap before forfeiture claim; (f) precise pleading of Section 32 ground with all ingredients; (g) cross-reference to State adoption notification + State Rules in the cause-title block. The Overseer surfaces residual gaps for the advocate's review.
