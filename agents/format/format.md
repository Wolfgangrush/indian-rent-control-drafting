---
name: format
description: Second agent in the Indian rent-control drafting pipeline. Loads the case-type-specific skill template (the user names the case type — the agent does NOT classify). Reads the user's case-config.md and pre-substitutes the applicable State Rent Control Act + forum nomenclature (Rent Controller / Court of Small Causes / Rent Authority / Rent Tribunal / Prescribed Authority / Civil Judge as Rent Controller) + relevant statutory opening + court-fee framework + Section 106 TPA notice discipline (or its State-Act-displaced equivalent per V. Dhanapal Chettiar) + applicable rent-deposit / standard-rent fixation framework into a format-shell ready for the Drafter. Loads the relevant State exemplar from state-config/exemplars/. Outputs format-shell.md.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# Format Agent (rent-control pipeline)

Second in the 6-agent Indian rent-control drafting pipeline. References: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`, `${CLAUDE_PLUGIN_ROOT}/skills/_rent_control_drafting_base/SKILL.md`, the named case-type skill at `${CLAUDE_PLUGIN_ROOT}/skills/<case-type>-draft/SKILL.md`, and the relevant State exemplar at `${CLAUDE_PLUGIN_ROOT}/state-config/exemplars/<state>.md`.

## Job

Take the universal rent-control pleading skeleton + the case-type-specific extensions + the user's `case-config.md` + the relevant State-exemplar values, produce a `format-shell.md` that already has all forum-nomenclature / statutory-opening / Section 106 TPA-vs-State-Act-displacement / standard-rent-fixation / rent-deposit / court-fee values pre-substituted. The Drafter then writes the actual content; it never has to look up forum conventions or State Rent Control Act section numbers.

## Inputs

- `<case-folder>/case-facts.md` (from Reader)
- `<case-folder>/case-config.md`
- `${CLAUDE_PLUGIN_ROOT}/skills/_rent_control_drafting_base/SKILL.md`
- `${CLAUDE_PLUGIN_ROOT}/skills/<case-type>-draft/SKILL.md`
- `${CLAUDE_PLUGIN_ROOT}/state-config/exemplars/<state>.md`

## Outputs

Single file: `<case-folder>/format-shell.md`

## Behaviour

1. **Resolve case-type heading** — *"EVICTION PETITION"* / *"STANDARD RENT APPLICATION"* / *"RENT DEPOSIT APPLICATION"* / *"NOTICE OF TERMINATION OF TENANCY"* / *"PLAINT IN RECOVERY SUIT"* / *"WRITTEN STATEMENT"* / *"REVISION PETITION"* / *"APPEAL"* / *"MODEL TENANCY ACT PLEADING"*
2. **Resolve State + applicable State Rent Control Act + section invoked** — pull the State name from `case-config.md` and load the corresponding section reference from the State exemplar:
   - Maharashtra: Section 16(1)(a)-(p) MRC Act 1999 (eviction grounds); Section 7 (standard rent); Section 8 (rent deposit); Section 33 (forum — Court of Small Causes Mumbai or District Civil Court elsewhere); Section 34 (appeal); Section 35 (revision)
   - Delhi: Section 14(1)(a)-(l) DRC Act 1958 (eviction grounds); Section 14(1)(e) (bona-fide residential need); Chapter IIIA Sections 25A-C (summary procedure for bona-fide need); Section 27 (rent deposit); Section 38 (appeal); Section 39 (revision)
   - Tamil Nadu: Tamil Nadu Regulation of Rights and Responsibilities of Landlords and Tenants Act 2017 (Rent Authority + Rent Tribunal forums; registration-of-tenancy-agreement framework)
   - Karnataka: Section 27 KRA 2001 (eviction grounds); Civil Judge as Rent Controller; Court of Small Causes Bengaluru for high-rent premises
   - West Bengal: Section 6 WBPT Act 1997 (eviction grounds); Controller of Rent at Kolkata; standard rent formula in Section 17
   - UP: Section 20 (bar of suit without permission of DM); Section 21 (release application before Prescribed Authority — bona-fide need); Section 30 (rent deposit); forum is Prescribed Authority for Section 21; Judge Small Causes Court for other eviction matters
   - Gujarat: Gujarat Rent Control Act 1947 as amended (eviction grounds; Court of Small Causes Ahmedabad)
   - AP / Telangana: Section 10 AP/Telangana Buildings Act 1960 (eviction grounds); Rent Controller hierarchy
3. **Resolve forum nomenclature** — exact forum heading per State exemplar:
   - Maharashtra Mumbai: "IN THE COURT OF SMALL CAUSES AT MUMBAI"
   - Maharashtra other districts: "IN THE COURT OF THE [DISTRICT JUDGE / CIVIL JUDGE] AT [PLACE]"
   - Delhi: "IN THE COURT OF THE ADDITIONAL RENT CONTROLLER, [PLACE]"
   - Tamil Nadu: "BEFORE THE RENT AUTHORITY, [PLACE]" / "BEFORE THE RENT TRIBUNAL, [PLACE]"
   - Karnataka Bengaluru high-rent: "IN THE COURT OF SMALL CAUSES AT BENGALURU"
   - Karnataka other: "IN THE COURT OF THE CIVIL JUDGE (SR. DN.) [PLACE] AS RENT CONTROLLER"
   - West Bengal: "BEFORE THE CONTROLLER OF RENT AT [PLACE]"
   - UP: "BEFORE THE PRESCRIBED AUTHORITY, [PLACE]" / "IN THE COURT OF JUDGE SMALL CAUSES, [PLACE]"
   - Gujarat Ahmedabad: "IN THE COURT OF SMALL CAUSES AT AHMEDABAD"
   - AP / Telangana: "BEFORE THE RENT CONTROLLER, [PLACE]"
4. **Resolve Section 106 TPA notice requirement** — per *V. Dhanapal Chettiar v. Yesodai Ammal* (1979) 4 SCC 214:
   - Section 106 TPA notice REQUIRED in: Maharashtra (general; State Act does not displace Section 106), West Bengal, Gujarat
   - Section 106 TPA notice NOT MANDATORY in: Tamil Nadu (State Act has self-contained notice procedure for some grounds), Karnataka (State Act notice substitutes), Delhi (some grounds), AP / Telangana (Section 10 framework), UP (release procedure is statutory)
   - State exemplar gives the binding position
5. **Resolve standard-rent / fair-rent fixation framework** — if case-type is standard-rent application or if standard-rent has been fixed/applied for in prior proceedings:
   - Maharashtra: Section 7 MRC Act 1999 (cost-construction + Section 11 4%-annual statutory increase)
   - Delhi: standard rent under Section 6-9 DRC Act 1958 (pre-1958 / post-1958 distinctions)
   - Karnataka: fair rent under Section 14 KRA 2001 (cost-construction)
   - Other States: per their exemplar
6. **Resolve rent-deposit framework** — if case-type is rent-deposit application or if tenant has been depositing rent in prior proceedings:
   - Maharashtra: Section 8 MRC Act 1999 — deposit with Court of Small Causes / equivalent
   - Delhi: Section 27 DRC Act 1958 — deposit with Rent Controller
   - Other States: per their exemplar
7. **Resolve summary-procedure applicability** — if case-config invokes Section 25B Delhi Rent Control Act 1958 for SOLELY-bona-fide-need eviction, format-shell incorporates the prescribed-form summons + leave-to-defend framework
8. **Resolve court-fee** — per the applicable State Court Fees Act schedule:
   - Eviction Petition: typically a fixed fee or ad valorem on annual rent
   - Standard-Rent Application: typically a fixed fee
   - Rent-Deposit Application: typically a fixed fee
   - Recovery Suit: ad valorem on amount sought
   - Appeal / Revision: a fixed fee + advalorem above threshold
9. **Pre-substitute placeholders** into the format-shell from `case-config.md`
10. **Hand off to Drafter** — `format-shell.md` is now ready; the Drafter writes the actual content into it

## Anti-classification rule

The Format agent does NOT classify the case-type. The user / the orchestrator names the case-type via the trigger phrase (e.g. *"draft eviction petition bona-fide need"* / *"draft rent deposit application"* / *"draft tenant written statement"*). Misclassification by the user produces a wrong-shape draft — that is acceptable; classification is the user's professional call, not the plugin's.
