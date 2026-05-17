---
name: eviction-nuisance-damage-draft
description: Draft an Eviction Petition on the ground of NUISANCE / ANNOYANCE / DAMAGE / IMPAIRMENT to the premises under Section 16(1)(c) (nuisance / annoyance) and Section 16(1)(d) (damage / impairment of the value or utility of the premises) of the Maharashtra Rent Control Act 1999, Section 14(1)(j) (damage) and Section 14(1)(k) (illegal / immoral use) of the Delhi Rent Control Act 1958, Section 27(2)(d) and Section 27(2)(e) of the Karnataka Rent Act 2001, Section 6(1)(b) and Section 6(1)(o) of the West Bengal Premises Tenancy Act 1997, and Section 10(2)(iii) of the AP / Telangana Buildings Control Act 1960. Encodes the specific-incident discipline (dates, particulars, witnesses), the documentary-proof stack (police complaints, neighbour affidavits, photographic evidence, pre-tenancy condition record, cost-of-repair estimate), and the distinction between nuisance (acts disturbing neighbours / landlord / occupants) and damage (acts impairing the structural / aesthetic / utility value of the premises). Auto-fires on "draft eviction nuisance", "draft eviction damage", "draft eviction nuisance damage", "draft eviction annoyance", and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# Eviction (Nuisance / Damage) Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_rent_control_drafting_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Case metadata

```yaml
case_type_line: PETITION FOR EVICTION (NUISANCE / DAMAGE)
case_short_code: EVICTION_NUISANCE_DAMAGE
role_party_1: Landlord / Petitioner
role_party_2: Tenant / Respondent
typical_forum: "Maharashtra — Court of Small Causes / Civil Judge as Rent Controller · Delhi — Additional Rent Controller · Karnataka — Court of Small Causes / Civil Judge as Rent Controller · West Bengal — Civil Judge (Junior Division) · UP — Civil Judge under Section 20 · AP/Telangana — Rent Controller"
typical_court_fee: "Fixed court fee on eviction relief per State Court Fees Act + ad valorem on damages quantified."
operative_paragraphs:
  - "Facts paragraph — *'It is most respectfully submitted that the Petitioner is the lawful owner / landlord of the premises bearing No. [_____] situate at [_____] (hereinafter \"the suit premises\"), and the Respondent has been in occupation of the suit premises as a monthly tenant under the Petitioner at a monthly rent of Rs. [_____].'*"
  - "Nuisance incidents — *'The Respondent has, since [date], been guilty of conduct which is a nuisance and / or annoyance to the adjoining / neighbouring occupants and / or to the Petitioner. The specific incidents include, inter alia: (i) on [date], the Respondent [describe conduct — loud music / abusive behaviour / unlawful gathering / blocking common areas / etc.]; (ii) on [date], [further incident]; (iii) on [date], [further incident]. Several neighbours / co-occupants have submitted written complaints to the Petitioner and / or to the local police station, copies of which are annexed hereto and marked as Annexures [_____].'*"
  - "Damage incidents — *'The Respondent has caused damage to the suit premises and / or has impaired the value and utility thereof by: (i) unauthorised demolition / alteration of [describe structure]; (ii) removal of [fixtures / fittings]; (iii) [other specific damage]. A report of a qualified structural engineer / architect dated [_____] estimating the cost of restoration at Rs. [_____] is annexed hereto and marked as Annexure [_____]. Photographs of the pre-tenancy condition and the present damaged condition are also annexed.'*"
  - "Statutory notice — *'The Petitioner caused to be served upon the Respondent a notice dated [_____] under Section 16(1)(c) and / or Section 16(1)(d) of the Maharashtra Rent Control Act 1999 [or State equivalent] terminating the tenancy and calling upon the Respondent to quit and deliver vacant possession.'*"
  - "Prayer — *'It is therefore most respectfully prayed that this Hon'ble Court may be pleased to: (a) pass a decree for eviction directing the Respondent to quit, vacate, and deliver vacant and peaceful possession of the suit premises to the Petitioner; (b) pass a decree for damages in the sum of Rs. [_____] together with interest @ [9%] per annum; (c) award mesne profits from the date of the petition until vacant possession; (d) award costs; and (e) pass such further and other orders as this Hon'ble Court may deem fit and proper.'*"
statutory_anchors:
  - "Section 16(1)(c) Maharashtra Rent Control Act 1999 (nuisance / annoyance)"
  - "Section 16(1)(d) Maharashtra Rent Control Act 1999 (damage / impairment)"
  - "Section 14(1)(j) Delhi Rent Control Act 1958 (damage)"
  - "Section 14(1)(k) Delhi Rent Control Act 1958 (illegal / immoral use)"
  - "Section 27(2)(d) Karnataka Rent Act 2001 (nuisance)"
  - "Section 27(2)(e) Karnataka Rent Act 2001 (damage)"
  - "Section 6(1)(b) West Bengal Premises Tenancy Act 1997"
  - "Section 6(1)(o) West Bengal Premises Tenancy Act 1997"
  - "Section 10(2)(iii) AP/Telangana Buildings Control Act 1960"
notice_requirement: "Statutory notice under the State Rent Act terminating tenancy on the nuisance / damage ground, with specific particulars of incidents. Where the State Act exhaustively governs, separate Section 106 TPA notice is dispensed with under Dhanapal Chettiar (1979) 4 SCC 214 — safer practice is dual-notice."
v_dhanapal_chettiar_check: "Nuisance / damage is exclusively a State Rent Act ground."
bharatiya_sakshya_check: "Police complaint receipts (under Section 173 BNSS), neighbour affidavits (Section 24 BSA), photographs / video recordings (Section 63 BSA — electronic record certificate), pre-tenancy condition record, cost-of-repair report by qualified expert (Section 47 BSA — opinion of expert) — all to be marked as Bharatiya Sakshya Adhiniyam 2023 compliant exhibits."
```

## Statutory framework summary

- **Section 16(1)(c) MRC Act 1999** — Tenant has been guilty of conduct which is a nuisance or annoyance to the adjoining or neighbouring occupiers.
- **Section 16(1)(d) MRC Act 1999** — Tenant has done, or permitted to be done, any act which is destructive or permanently injurious to the premises.
- **Section 14(1)(j) DRC Act 1958** — Tenant has, whether before or after the commencement of the Act, caused or permitted to be caused substantial damage to the premises.
- **Section 14(1)(k) DRC Act 1958** — Tenant has, notwithstanding previous notice, used or dealt with the premises in a manner contrary to any condition imposed on the landlord by the Government or the Delhi Development Authority or the Municipal Corporation of Delhi while giving him a lease of the land on which the premises are situate.
- **Section 27(2)(d) KRA 2001** — Nuisance ground equivalent.
- **Section 27(2)(e) KRA 2001** — Damage ground equivalent.

## Distinction — nuisance vs damage vs illegal use

| Ground | Trigger | Affected Party | Proof |
|---|---|---|---|
| Nuisance / Annoyance | Conduct of tenant or occupants | Neighbours / co-occupants / landlord | Police complaints, neighbour affidavits, society complaints |
| Damage / Impairment | Acts to the physical premises | The premises themselves | Pre-tenancy condition record + present condition + expert report on cost-of-repair |
| Illegal / Immoral Use | Use of premises contrary to lawful purpose | Public interest / lease covenant | FIR / police charge-sheet, lease violation evidence |

The Drafter selects the precise sub-ground; combining grounds in one petition is permitted but each ground must be pleaded with its own particulars.

## Ingredients to be pleaded

1. **Landlord-tenant relationship** — title, tenancy, rent, premises particulars.
2. **Specific incidents** — dates, conduct, witnesses, geographical / structural reference within premises.
3. **Pattern / persistence** — single isolated incident is rarely sufficient; pattern of conduct strengthens the petition.
4. **Notice / warning** — prior warnings by landlord (oral / written) showing tenant's persistence despite knowledge.
5. **Affected third parties** — neighbours / occupants whose complaints document the nuisance.
6. **Damage quantification** — pre-tenancy condition record (inventory at lease commencement / photographs), present damaged condition, expert cost-of-repair report.
7. **Statutory notice** — State Rent Act notice terminating tenancy on the nuisance / damage ground.

## Documentary evidence stack (mandatory)

For nuisance / annoyance:

- **Police complaints** — FIRs / NCRs / Daily Diary entries / Section 154 BNSS register copies
- **Neighbour affidavits** — sworn statements of immediate neighbours / co-occupants identifying the nuisance with specifics
- **Society / RWA complaints** — for flats in Co-operative Housing Society / Apartment Owners Association
- **Audio / video recordings** — Section 63 BSA electronic-record certificate compulsory; chain-of-custody pleaded
- **Local-authority notices** — Municipal Corporation / Pollution Control Board notices for noise / waste / illegal use

For damage / impairment:

- **Pre-tenancy condition record** — lease deed schedule, inventory, photographs at handover
- **Present condition** — photographs / videography with date-stamp + Section 63 BSA certificate
- **Expert report** — qualified Architect / Structural Engineer / Civil Engineer report estimating cost of repair / restoration, with credentials and methodology
- **Bills / quotations** — repair quotations from contractors

For illegal / immoral use:

- **FIR / charge-sheet** — under BNS / NDPS Act / Immoral Traffic (Prevention) Act 1956 / Excise Act / etc.
- **Local-authority sealing / closure orders** — Municipal Corporation / Police / Excise authorities

## Mesne-profits + damages combo

The petition typically claims:

- **Eviction decree** — vacant possession
- **Mesne profits** — for period from petition until possession at prevailing market rate (Ready Reckoner / comparable-rents methodology)
- **Damages for repair** — quantified by expert report

The court-fee is paid on the damages component ad valorem.

## Common opposing-counsel challenges

1. **Vague pleadings** — incidents not dated / particularised / witnesses not identified.
2. **Single isolated incident** — pattern not established.
3. **No prior warning** — landlord did not document warning; tenant pleads ignorance / lack of opportunity to remedy.
4. **Neighbour-collusion / landlord-instigated complaints** — tenant pleads complaints are manufactured at landlord's instance.
5. **Damage attributable to wear-and-tear / pre-existing** — tenant pleads damage existed before tenancy or arose from normal use.
6. **Landlord's own neglect** — failure to maintain common areas / structural maintenance; damage flowed from landlord's neglect not tenant's act.
7. **Damage curable / restoration possible** — tenant offers restoration; pleads disproportion between damage and eviction relief.
8. **Identity of perpetrator** — acts by visitors / sub-occupants / third parties; tenant denies own conduct.
9. **Pre-tenancy condition record absent** — landlord cannot prove damaged vs original state.
10. **Electronic-evidence chain broken** — Section 63 BSA certificate absent; video / photograph inadmissible.

The Drafter pre-empts these by: (a) particularised incident-by-incident pleading with dates + witnesses; (b) neighbour affidavits attached at filing; (c) Section 63 BSA certificate annexed to every electronic exhibit; (d) expert report from credentialed professional; (e) pre-tenancy inventory / photographs from lease commencement; (f) documented prior warnings (letters, society notices, police complaints). The Overseer surfaces residual gaps for the advocate's review.
