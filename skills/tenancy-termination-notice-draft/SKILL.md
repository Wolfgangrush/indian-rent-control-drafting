---
name: tenancy-termination-notice-draft
description: Draft a Tenancy Termination Notice under Section 106 of the Transfer of Property Act 1882 (15-day notice post the 2002 Amendment for monthly tenancies) read with Section 111 TPA 1882 (modes of determination of lease), with the State Rent Control Act statutory-notice overlay where applicable. NOT a court pleading — this is a pre-litigation notice on advocate's letterhead, addressed to the tenant, terminating the tenancy and demanding vacant possession. Encodes the V. Dhanapal Chettiar v. Yesodai Ammal (1979) 4 SCC 214 doctrine (State Rent Act displacement of Section 106 TPA notice where State Act exhaustively governs the eviction ground), the dual-notice safer practice in eviction-on-non-payment cases, the mode-of-service stack (registered post acknowledgement due + under certificate of posting + speed post + email + WhatsApp + personal + affixture), the 15-day computation discipline (from end of receipt of notice, not from issue), and the demand-for-vacant-possession with consequence-of-legal-action warning. Auto-fires on "draft tenancy termination notice", "draft section 106 notice", "draft termination notice", "draft quit notice", "draft eviction notice", and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# Tenancy Termination Notice Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_rent_control_drafting_base/SKILL.md` (adapted — this is a NOTICE document, not a court pleading; cause-title / verification / synopsis sections do NOT apply; output is a single-page memo on advocate's letterhead)
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Notice metadata

```yaml
notice_type_line: NOTICE OF TERMINATION OF TENANCY
notice_short_code: TERMINATION_NOTICE
role_party_1: Landlord (through advocate as Notice-Sender)
role_party_2: Tenant (Notice-Recipient / Notice-Addressee)
typical_format: "Single-page (or 2-3 page) memo on Sender-Advocate s letterhead — NOT a court pleading. Format: Date — Notice Reference Number — Sender block — Addressee block — Subject line — Numbered paragraphs (Tenancy recital → Cause of termination → Statutory provisions → Termination clause → Demand for vacant possession → Consequence of non-compliance → Without prejudice clause) — Signature of Advocate."
notice_structure:
  - "1. Notice header — *'NOTICE — Without Prejudice'* + Notice Reference Number + Date"
  - "2. Sender block — Advocate s name + chambers address + Bar Council enrolment + counsel-of-record-for-Landlord recital"
  - "3. Addressee block — Tenant's full name + address (suit premises address)"
  - "4. Subject line — *'Subject: Termination of Tenancy in respect of premises bearing No. [_____] situate at [_____]'*"
  - "5. Tenancy recital — particulars of the tenancy (date of commencement / mode of letting / monthly rent / due date)"
  - "6. Cause of termination — the eviction ground OR end of contractual tenancy OR change of landlord OR transfer of premises"
  - "7. Statutory provisions — Section 106 TPA 1882 + State Rent Act provision (where applicable) + relevant ingredients pleaded"
  - "8. Termination clause — *'My client hereby terminates the tenancy with effect from [date — last day of the month following the 15-day period from receipt of this Notice]'*"
  - "9. Demand for vacant possession — *'You are hereby called upon to quit, vacate, and deliver vacant peaceful possession of the suit premises to my client on or before [date]'*"
  - "10. Consequence of non-compliance — *'In the event of your failure to comply with this Notice within the stipulated period, my client shall be constrained to initiate appropriate legal proceedings for eviction against you, including a petition / suit before the [forum], at your sole risk as to costs and consequences'*"
  - "11. Without-prejudice clause — *'This Notice is without prejudice to all rights and remedies available to my client at law and in equity'*"
  - "12. Signature block — Advocate s signature + name + enrolment number + chambers seal"
statutory_anchors:
  - "Section 106 Transfer of Property Act 1882 (15-day notice for monthly tenancies post the 2002 Amendment)"
  - "Section 111 Transfer of Property Act 1882 (modes of determination of lease)"
  - "State Rent Control Act statutory-notice provisions (Section 15 MRC Act 1999 / equivalents) where the notice is on a non-payment / sub-letting / nuisance / damage / bona-fide-need ground"
key_case: "V. Dhanapal Chettiar v. Yesodai Ammal (1979) 4 SCC 214 — Where the State Rent Control Act exhaustively governs the eviction ground and the State Act itself constitutes determination of tenancy, a separate Section 106 TPA notice is NOT required. However, the safer practice for the Drafter is dual-notice (both Section 106 TPA and the State Rent Act notice) — pre-empts the opposing-counsel challenge."
mode_of_service: "Registered Post Acknowledgement Due (RPAD) [PRIMARY] + Under Certificate of Posting (UPC) [BACKUP] + Speed Post [BACKUP] + Email to last known email address + WhatsApp to last known mobile number + Personal service through process server + Affixture at suit premises in presence of two witnesses (panchnama signed) [WHERE OTHER MODES UNFEASIBLE]. The Drafter advises Landlord to use AT LEAST RPAD + UPC + Email stack — courts give effect to receipt presumed on RPAD return."
bharatiya_sakshya_check: "Notice + RPAD acknowledgement + UPC receipt + Speed Post receipt + email send report + WhatsApp delivery receipt — all to be marked as Bharatiya Sakshya Adhiniyam 2023 compliant exhibits when subsequently led in evidence at the eviction petition. Electronic-mode service requires Section 63 BSA certificate."
```

## Statutory framework summary

- **Section 106 TPA 1882 (post-2002 Amendment)** — Lease of immovable property for agricultural or manufacturing purposes is deemed to be from year-to-year, terminable on six months notice; lease for any other purpose is deemed from month-to-month, terminable on FIFTEEN days notice (pre-2002, this was 15 days; the 2002 Amendment retained 15 days but clarified computation).
- **Section 111 TPA 1882** — A lease of immovable property determines: (a) by efflux of time; (b) where a conditional limitation is fulfilled; (c) where the interests of lessor and lessee become vested in the same person; (d) by express surrender; (e) by implied surrender; (f) by forfeiture; (g) on the expiration of a notice to determine the lease.
- **State Rent Control Act notice provisions** — Section 15 MRC Act 1999 (demand for arrears + 90 days), Section 14(1)(a) DRC Act 1958 (2 months for arrears), and equivalents under other State Acts — these prescribe the specific cure period for the relevant eviction ground.

## V. Dhanapal Chettiar doctrine

The Supreme Court in **V. Dhanapal Chettiar v. Yesodai Ammal (1979) 4 SCC 214** held:

- Where the State Rent Control Act exhaustively governs the eviction grounds and the State Act provisions themselves constitute determination of tenancy, a separate Section 106 TPA notice is NOT a pre-condition to instituting eviction proceedings.
- The State Rent Act notice (Section 15 MRC Act / Section 14 DRC Act / equivalents) suffices on its own merits.
- The Section 106 TPA notice is redundant in such cases.

**Safer-practice rule for the Drafter:** Despite Dhanapal Chettiar, the prudent Drafter issues a DUAL NOTICE covering BOTH (i) Section 106 TPA determination AND (ii) the State Rent Act statutory ground — this pre-empts the opposing-counsel challenge that the relevant notice was inadequate.

## Notice components — narrative structure

### Tenancy recital
- Date of commencement of tenancy
- Mode of letting (oral / written, registered / unregistered lease deed)
- Monthly rent amount + due date
- Premises particulars (address, area, type — residential / non-residential)
- Identity of Landlord (with reference to title) and Tenant

### Cause of termination
The notice MUST identify the cause clearly:

1. **End of contractual term** — fixed-term lease expiring; notice not strictly required but customary
2. **Termination at will under Section 106 TPA** — month-to-month tenancy, no fault, landlord exercising statutory right (where State Rent Act permits)
3. **Eviction ground under State Rent Act** — non-payment / sub-letting / nuisance / damage / bona-fide-need / unauthorised construction / etc.
4. **Determination by forfeiture under Section 111 TPA** — breach of covenant, landlord re-entering
5. **Change of landlord** — sale / partition / heirship — fresh notice from new landlord

The cause-of-termination paragraph must plead all necessary ingredients for the specific eviction ground (where applicable).

### Statutory provisions
The notice cites:

- Section 106 TPA 1882 — determination of tenancy
- State Rent Act provision — eviction ground (where applicable)
- Section 111 TPA 1882 — modes of determination (where relevant)

### 15-day computation
The 15-day period under Section 106 TPA runs from the END of the rent-month following receipt of the notice — i.e., the tenancy ends on the LAST DAY of the month following the month in which the notice expires. Practical computation:

- Notice issued: [Date 1]
- Notice received: [Date 1 + delivery period]
- 15-day period expires: [Date of receipt + 15 days]
- Tenancy determined w.e.f.: [End of the month following expiry of 15-day period]
- Vacant possession demanded: [Tenancy determination date]

The Drafter computes these dates precisely and pleads them in the notice.

### Demand for vacant possession
The notice demands:
- Vacant, peaceful possession by the determination date
- Surrender of keys + clearance of dues (electricity, water, society maintenance, property tax)
- Removal of tenant s belongings

### Consequence of non-compliance
The notice warns:
- Institution of eviction petition / suit before the appropriate forum
- Claim for mesne profits / damages at market rate from tenancy determination date
- Recovery of arrears (where applicable) with interest
- Costs of the proceeding

### Without-prejudice clause
Standard end-clause preserves the Landlord's rights to additional grounds, additional remedies, and to issue further notices.

## Mode of service — best practice stack

| Mode | Purpose | Evidence |
|---|---|---|
| Registered Post AD | PRIMARY — statutory presumption of receipt | Postal acknowledgement card OR return-cover with endorsement |
| Under Certificate of Posting | BACKUP — proof of dispatch | UPC receipt |
| Speed Post | BACKUP — tracking with delivery report | Speed Post slip + Indian Post tracking screenshot |
| Email | Modern complement — datable proof | Sent items screenshot + Section 63 BSA certificate |
| WhatsApp | Modern complement — delivery / read confirmation | Screenshot of delivery / read ticks + Section 63 BSA certificate |
| Personal service | Where Tenant is locally available | Process server affidavit |
| Affixture at premises | Where other modes unfeasible | Panchnama signed by two witnesses |

The Drafter advises Landlord to use AT LEAST the RPAD + UPC + Email stack; courts consistently give effect to RPAD return endorsement "refused" / "not claimed" as constructive receipt.

## Output format

This is NOT a court pleading. Output is a single-page (or 2-3 page) memo on Sender-Advocate s letterhead:

- Top: Advocate s letterhead (chambers name, address, phone, email, Bar Council enrolment)
- Notice Reference Number + Date (top right)
- Title: "NOTICE — Without Prejudice"
- Sender block (advocate as counsel for landlord)
- Addressee block (tenant)
- Subject line
- Numbered paragraphs as per Notice structure above
- Signature block: Advocate s manuscript signature + name + enrolment number + chambers seal

The Drafter does NOT generate cause-titles, verification, or court-pleading structures for this output.

## Common opposing-counsel challenges (when subsequently led in evidence)

1. **Notice not served / not received** — landlord must produce RPAD acknowledgement / postal endorsement / Section 63 BSA-compliant email proof.
2. **Notice ambiguous** — wrong premises address, wrong rent amount, wrong cure period, wrong determination date.
3. **Notice issued by wrong person** — advocate without vakalat / Power of Attorney / instructions on record.
4. **Notice cited wrong statutory provision** — e.g. Section 14(1)(a) cited where Section 14(1)(b) was the actual ground.
5. **Notice premature / belated** — issued before cause arose / issued after limitation expired.
6. **Notice insufficient under State Rent Act** — Section 15 MRC Act notice did not specify exact arrears amount / did not provide 90-day cure period correctly.
7. **Mode of service not statutorily compliant** — affixture without panchnama / email without Section 63 BSA certificate.

The Drafter pre-empts these by: (a) precise tenancy + cause + statute + dates pleading; (b) multi-mode service stack at first instance; (c) vakalat on record before issuing notice; (d) Section 63 BSA certificate prepared contemporaneously with electronic-mode service; (e) panchnama with two witnesses where affixture used; (f) cure-period computation verified against governing State Act. The Overseer surfaces residual gaps for the advocate's review.
