---
name: revision-appeal-rent-controller-draft
description: Draft a Memorandum of Appeal / Revision Petition against an order of the Rent Controller / Court of Small Causes / Prescribed Authority under Section 34 (appeal) and Section 35 (revision) of the Maharashtra Rent Control Act 1999, Section 38 (appeal) and Section 39 (revision) of the Delhi Rent Control Act 1958, Section 28 of the Karnataka Rent Act 2001, Sections 29 and 30 of the West Bengal Premises Tenancy Act 1997, Section 22 of the UP Urban Buildings Act 1972 (revision before District Judge), Section 10 of the AP / Telangana Buildings Control Act 1960, Section 115 of the Code of Civil Procedure 1908, and Articles 226 / 227 of the Constitution of India. Encodes the appeal-versus-revision distinction (appeal opens questions of fact + law; revision opens jurisdictional error / error apparent on face of record / perversity only), the appellate-forum hierarchy (Appellate Bench of Court of Small Causes in Mumbai; District Judge in Delhi / Karnataka; Appellate Authority constituted under State Act; Rent Tribunal in Tamil Nadu), the revisional-forum hierarchy (High Court under Section 35 MRC Act / Article 227 / Section 115 CPC depending on State Act framework), the typical limitation (30 days appeal; 90 days revision under CPC; reasonable time under Article 227), and the Memorandum format. Auto-fires on "draft revision rent controller", "draft appeal rent controller", "draft revision MRC", "draft appeal rent control", "draft second appeal rent", and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# Revision / Appeal against Rent Controller Order — Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_rent_control_drafting_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Case metadata

```yaml
case_type_line: MEMORANDUM OF APPEAL / REVISION PETITION
case_short_code: REV_APPEAL_RC
role_party_1: Appellant / Petitioner (the party aggrieved by the Rent Controller order — may be Landlord or Tenant)
role_party_2: Respondent (the counter-party — the party in whose favour the Rent Controller order stands)
typical_forum: "APPEAL — Maharashtra (Mumbai): Appellate Bench of the Court of Small Causes · Maharashtra (rest of State): District Judge · Delhi: Rent Control Tribunal (Section 38 DRC Act) · Karnataka: Court of Small Causes (Bengaluru) / District Judge (rest) · West Bengal: District Judge · UP: District Judge (Section 22 release / Section 22 from Civil Judge) · Tamil Nadu: Rent Tribunal (TN Act 2017) · AP/Telangana: Appellate Authority. REVISION — High Court under Section 35 MRC Act / Section 39 DRC Act / Section 115 CPC / Article 227 Constitution (per State Act framework). UP under Section 22(2): revision before District Judge against orders of Prescribed Authority."
typical_court_fee: "Fixed court fee on Memorandum of Appeal / Revision per State Court Fees Act + ad valorem on money component (if any)."
operative_paragraphs:
  - "Cause title — *'IN THE HON BLE [Appellate / Revisional Court] AT [____] — APPEAL / REVISION PETITION (RAE-A / RAE-R) NO. [____] OF [____] — Appellant / Petitioner: [Party] — Respondent: [Party] — MEMORANDUM OF APPEAL / REVISION'*"
  - "Impugned order recital — *'The present Appeal / Revision is preferred against the Judgment and Order dated [____] passed by the Hon'ble Court of [Rent Controller / Court of Small Causes / Prescribed Authority] at [____] in [Case Number], whereby the said Hon'ble Court was pleased to [allow / dismiss / partly allow] the [Eviction Petition / Standard Rent Application / Rent Deposit Application / etc.] and to direct [_____]. A certified copy of the said impugned Judgment and Order is annexed hereto and marked as Annexure A.'*"
  - "Brief facts — *'The brief facts giving rise to the present Appeal / Revision are as follows: (i) [tenancy / property particulars]; (ii) [proceedings before Rent Controller]; (iii) [grounds of contest]; (iv) [evidence led]; (v) [findings of the impugned order]; (vi) [date of receipt of certified copy by Appellant / Petitioner].'*"
  - "Grounds of Appeal (for Appeal) — *'GROUNDS — 1. For that the impugned Judgment is contrary to law and to the weight of evidence on record. 2. For that the learned Trial Court erred in [_____]. 3. For that the learned Trial Court failed to appreciate that [_____]. 4. For that the learned Trial Court mis-construed [the statutory notice / the evidence / the binding precedent in _____]. 5. For that the finding on [issue] is perverse and unsustainable. 6. For that the learned Trial Court overlooked [the documentary evidence at Annexure ____ / the deposition of PW____ / the binding precedent of _____]. 7. For that the application of [Section X of the Act] to the facts of the case is erroneous. 8. For such other grounds as may be permitted to be urged at the time of hearing of this Appeal.'*"
  - "Grounds of Revision (for Revision) — *'GROUNDS — 1. For that the learned Trial Court has acted in excess of jurisdiction / has failed to exercise jurisdiction vested in it by law / has acted with material irregularity in the exercise of its jurisdiction within the meaning of Section 115 CPC / Section 35 MRC Act 1999 / Article 227 of the Constitution. 2. For that there is an error apparent on the face of the record in the impugned order in respect of [_____]. 3. For that the finding on [issue] is perverse and unsupported by any evidence. 4. For that the learned Trial Court overlooked binding precedent of the Hon'ble Supreme Court in [_____ (year) ___ SCC ___] which is directly applicable. 5. For that the impugned order has caused failure of justice / occasioned grave injustice within the meaning of the proviso to Section 115 CPC.'*"
  - "Limitation recital — *'The certified copy of the impugned Judgment and Order was received by the Appellant / Petitioner on [date]. The present Appeal / Revision is presented on [date], within the prescribed period of limitation of [30 days for Appeal under Section 34 MRC Act / 90 days for Revision under Section 115 CPC / reasonable time under Article 227]. The intervening period from the date of impugned order to the date of issue of certified copy ([dates]) is liable to be excluded under Section 12(2) of the Limitation Act 1963.'*"
  - "Interim prayer — *'Pending the hearing and final disposal of the present Appeal / Revision, this Hon'ble Court may be pleased to stay the operation of the impugned Judgment and Order dated [____], more particularly the direction for [eviction / deposit / fixation of standard rent / etc.], failing which the Appellant / Petitioner will suffer grave and irreparable injury.'*"
  - "Prayer — *'It is therefore most respectfully prayed that this Hon'ble Court may be pleased to: (a) call for the records of [Case Number] from the Court of [Rent Controller / Court of Small Causes / Prescribed Authority]; (b) admit the present Appeal / Revision for hearing; (c) set aside / modify the impugned Judgment and Order dated [____] passed by the learned Trial Court; (d) pass such consequential orders as may be just and proper, including [restoring the petition / dismissing the petition / remanding for fresh hearing]; (e) grant interim stay of the impugned Judgment pending hearing; (f) award costs; and (g) pass such further and other orders as this Hon'ble Court may deem fit and proper.'*"
statutory_anchors:
  - "APPEAL — Section 34 Maharashtra Rent Control Act 1999"
  - "APPEAL — Section 38 Delhi Rent Control Act 1958 (Rent Control Tribunal)"
  - "APPEAL — Section 28 Karnataka Rent Act 2001"
  - "APPEAL — Section 29 West Bengal Premises Tenancy Act 1997"
  - "APPEAL — Section 10 AP/Telangana Buildings Control Act 1960"
  - "REVISION — Section 35 Maharashtra Rent Control Act 1999"
  - "REVISION — Section 39 Delhi Rent Control Act 1958"
  - "REVISION — Section 22 UP Urban Buildings Act 1972 (before District Judge)"
  - "REVISION — Section 115 Code of Civil Procedure 1908"
  - "REVISION — Articles 226 and 227 of the Constitution of India"
limitation_position: "Appeal — typically 30 days from receipt of certified copy of impugned order (varies by State Act; verify before drafting). Revision under Section 115 CPC — 90 days. Article 227 — no statutory limitation; reasonable time per facts. Section 12(2) Limitation Act 1963 — period for obtaining certified copy excluded. The Drafter pleads exact dates of order / receipt of certified copy / filing, with explanation of any delay + condonation application under Section 5 Limitation Act 1963 if needed."
notice_requirement: "Not applicable to the filing of Appeal / Revision; notice to Respondent issued by the appellate / revisional Court after admission."
v_dhanapal_chettiar_check: "Not applicable."
bharatiya_sakshya_check: "Certified copy of impugned Judgment + records of Trial Court (paper-book) + relevant excerpts of evidence + binding precedent compilation — all to be marked as Bharatiya Sakshya Adhiniyam 2023 compliant exhibits. Certified copies under Section 76 BSA / Section 78 BSA require no further proof of authenticity."
appeal_vs_revision_distinction: "APPEAL opens questions of FACT + LAW; appellate court can re-appreciate evidence and substitute its findings. REVISION opens jurisdictional error / error apparent on face of record / perversity ONLY; revisional court cannot re-appreciate evidence merely because it would have come to a different conclusion. The Drafter selects the correct vehicle based on the State Act framework — appeal where Section 34 MRC Act / Section 38 DRC Act / equivalent provides; revision where only Section 35 MRC Act / Section 115 CPC / Article 227 available; second-tier challenges typically by revision only."
```

## Statutory framework summary

- **Section 34 MRC Act 1999** — Appeal from every decree or order of the Court of Small Causes / Civil Judge as Rent Controller lies to the Appellate Bench of Court of Small Causes (Mumbai) or District Court (rest of Maharashtra). Limitation 30 days.
- **Section 35 MRC Act 1999** — Revision by the High Court against orders not appealable under Section 34. Grounds — jurisdictional error / illegality / material irregularity.
- **Section 38 DRC Act 1958** — Appeal to Rent Control Tribunal from every order of the Rent Controller (except minor procedural orders). Limitation 30 days.
- **Section 39 DRC Act 1958** — Second appeal to High Court ONLY on substantial question of law from the order of Rent Control Tribunal.
- **Section 22 UP Urban Buildings Act 1972** — Appeal to District Judge from Prescribed Authority s release order; revision to District Judge against orders of Civil Judge under Section 20.
- **Section 115 CPC** — High Court revision where Trial Court has (a) exercised jurisdiction not vested by law, OR (b) failed to exercise jurisdiction so vested, OR (c) acted illegally / with material irregularity in exercise of jurisdiction.
- **Article 227 Constitution** — Power of superintendence of High Court over all subordinate Courts and Tribunals. Wide power but exercised sparingly — not a regular avenue of appeal.

## Appeal vs Revision distinction (critical)

| Feature | APPEAL | REVISION |
|---|---|---|
| Scope | Facts + Law | Jurisdiction / error apparent / perversity ONLY |
| Re-appreciation of evidence | YES — appellate court can substitute findings | NO — revisional court cannot reweigh evidence |
| Grounds | Wide — any error of law / fact / evidence appreciation | Narrow — jurisdictional / patent error / perversity |
| Forum | Appellate Authority constituted by State Act | High Court (typically); District Judge in UP for Prescribed Authority orders |
| Limitation | 30 days (typically) | 90 days under Section 115 CPC; reasonable time under Article 227 |
| Statutory right | Yes — provided by State Act | Discretionary — subject to revisional court s satisfaction |

The Drafter MUST select the correct vehicle based on:

1. **State Act framework** — does the Act provide appeal against the impugned order?
2. **Nature of impugned order** — final order / interlocutory order
3. **Stage** — first-tier challenge (typically appeal where available) / second-tier challenge (typically revision)
4. **Grounds available** — if grounds are factual / evidence-appreciation, must be appeal; if grounds are jurisdictional / patent error, revision suffices

## Forum hierarchy (selected States)

### Maharashtra
- Rent Controller order → Section 34 MRC Act appeal to Appellate Bench of CSC (Mumbai) / District Court (rest of State)
- Appellate Bench / District Court order → Section 35 MRC Act revision to High Court (Bombay)
- High Court revisional order → SLP to Supreme Court under Article 136 Constitution

### Delhi
- Rent Controller order → Section 38 DRC Act appeal to Rent Control Tribunal
- Rent Control Tribunal order → Section 39 DRC Act second appeal to High Court on substantial question of law
- High Court order → SLP to Supreme Court

### UP
- Prescribed Authority release order → Section 22(1) UP Act appeal to District Judge
- Civil Judge order under Section 20 → Section 22(2) UP Act revision to District Judge
- District Judge order → Article 226 / 227 writ petition to High Court (Allahabad / Lucknow)

### Karnataka
- Rent Controller (CSC / Civil Judge) order → Section 28 KRA appeal to Karnataka District Judge
- District Judge appellate order → Section 115 CPC revision / Article 227 to High Court (Karnataka)

### West Bengal
- Rent Controller (Civil Judge) order → Section 29 WBPT Act appeal to District Judge
- District Judge appellate order → Section 30 WBPT Act revision to High Court (Calcutta)

### Tamil Nadu
- Rent Court order → Rent Tribunal appeal (TN Act 2017)
- Rent Tribunal order → High Court (Madras) under Article 227

### AP / Telangana
- Rent Controller order → Section 10 AP Act appeal to Appellate Authority (District Judge / equivalent)
- Appellate Authority order → revision to High Court

## Limitation discipline

- **Appeal under State Rent Act** — typically 30 days from receipt of certified copy (verify exact period in State Act + Rules)
- **Revision under Section 115 CPC** — 90 days from order
- **Article 227 writ** — no statutory limitation; reasonable time judged on facts (delays beyond 6 months typically attract laches)
- **Section 12(2) Limitation Act 1963** — period from date of order to date of receipt of certified copy is excluded
- **Section 5 Limitation Act 1963** — condonation of delay on sufficient cause shown (separate condonation application required if filing beyond limitation)

The Drafter computes:

- Date of impugned order: [____]
- Date of application for certified copy: [____]
- Date of receipt of certified copy: [____]
- Days excluded under Section 12(2): [____]
- Last date for filing: [____]
- Actual date of filing: [____]
- Delay (if any) + condonation: [____]

## Grounds — drafting craft

### Grounds of Appeal (wide)
Each ground typically begins "For that the learned Trial Court erred in [_____]" or "For that the learned Trial Court failed to appreciate that [_____]" — covers:

- Mis-construction of evidence
- Non-appreciation of evidence
- Mis-application of law
- Failure to apply binding precedent
- Perverse finding
- Disregard of admission / pleading
- Inconsistent or contradictory findings
- Error in admission / rejection of evidence
- Error in framing of issues
- Procedural irregularity vitiating the trial

### Grounds of Revision (narrow)
Each ground must demonstrate JURISDICTIONAL infirmity / ERROR APPARENT / PERVERSITY — covers:

- Acted in excess of jurisdiction
- Failed to exercise jurisdiction vested by law
- Acted illegally / with material irregularity in exercise of jurisdiction
- Error apparent on face of record (no need for elaborate argument)
- Finding wholly unsupported by evidence (perversity)
- Binding precedent of Supreme Court / jurisdictional High Court directly applicable but ignored

The Drafter does NOT urge mere evidence-appreciation grounds in revision (these will be rejected as outside revisional scope).

## Interim stay

Standard interim prayer — stay of operation of impugned order pending appeal / revision. Specifically critical where:

- Decree for eviction → stay prevents execution
- Order for deposit → stay defers deposit obligation
- Standard-rent fixation → stay maintains status quo

The Drafter typically files a separate stay application alongside the Memorandum, supported by affidavit of irreparable injury + balance of convenience + prima facie case.

## Common opposing-counsel challenges

1. **Limitation bar** — Memorandum filed beyond limitation; condonation application missing / insufficient.
2. **Wrong vehicle** — appeal filed where only revision lies (or vice versa); Memorandum returned / dismissed.
3. **Wrong forum** — revision filed before District Judge where High Court has jurisdiction; or appeal before High Court where Tribunal / District Judge has jurisdiction.
4. **Grounds vague** — Memorandum grounds bald, no specific findings challenged.
5. **Re-appreciation grounds in revision** — Respondent argues grounds urged go to evidence-appreciation, not jurisdictional infirmity; revision dismissed at admission.
6. **Stay refused** — no balance of convenience / prima facie case / irreparable injury made out.
7. **Certified copy not annexed** — Memorandum incomplete.
8. **Limitation not pleaded with dates** — limitation infirmity argued at admission stage.

The Drafter pre-empts these by: (a) precise computation of limitation with all dates + Section 12(2) exclusion + Section 5 condonation if needed; (b) correct vehicle selection per State Act framework + nature of order; (c) correct forum verification against statutory hierarchy; (d) ground-specific drafting (wide for appeal; narrow for revision); (e) stay application with affidavit of irreparable injury contemporaneously filed; (f) certified copy + paper-book + binding precedent compilation at filing. The Overseer surfaces residual gaps for the advocate's review.
