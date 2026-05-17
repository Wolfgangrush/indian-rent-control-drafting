---
name: standard-rent-fixation-application-draft
description: Draft a Standard Rent / Fair Rent Fixation Application under Section 7 read with Sections 8, 10, and 11 of the Maharashtra Rent Control Act 1999, Sections 6 to 9 of the Delhi Rent Control Act 1958 (standard rent), Section 14 of the Karnataka Rent Act 2001 (fair rent), Sections 17 to 22 of the West Bengal Premises Tenancy Act 1997, and the fair-rent provisions of the Tamil Nadu Regulation of Rights and Responsibilities of Landlords and Tenants Act 2017. Encodes the cost-of-construction methodology (Section 7 MRC Act: percentage return on the cost of construction + land value with depreciation), the market-rent comparable methodology, the statutory-increase methodology (Section 11 MRC Act: 4% annual permitted increase), the permitted-increases discipline (Section 10 MRC Act: amenities, taxes, special increases), the pendency-deposit discipline (tenant must continue agreed rent or provisional rent fixed by Court), and the Section 9 MRC Act mechanism for recovery of excess rent paid above standard rent. Auto-fires on "draft standard rent application", "draft standard rent fixation", "draft fair rent application", "draft rent fixation application", and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# Standard Rent / Fair Rent Fixation Application Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_rent_control_drafting_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Case metadata

```yaml
case_type_line: APPLICATION FOR FIXATION OF STANDARD RENT (or FAIR RENT in Karnataka / Tamil Nadu)
case_short_code: STD_RENT_FIXATION
role_party_1: Applicant (typically Tenant; occasionally Landlord)
role_party_2: Respondent (the counter-party — Landlord if Applicant is Tenant; Tenant if Applicant is Landlord)
typical_forum: "Maharashtra — Court of Small Causes (Mumbai) / Civil Judge designated as Rent Controller (rest of State) under Section 7 MRC Act · Delhi — Rent Controller under Section 9 DRC Act · Karnataka — Court of Small Causes / Civil Judge as Rent Controller · West Bengal — Civil Judge (Junior Division) under Section 17 WBPT Act · Tamil Nadu — Rent Court / Rent Authority under TN Act 2017"
typical_court_fee: "Fixed application fee per State Court Fees Act / Rent Act Rules."
operative_paragraphs:
  - "Facts paragraph — *'It is most respectfully submitted that the Applicant is the lawful tenant / landlord of the premises bearing No. [_____] situate at [_____] (hereinafter \"the suit premises\"), and the present rent payable / claimed in respect of the suit premises is Rs. [_____] per month exclusive / inclusive of permitted increases.'*"
  - "Inadequacy / excessiveness — *'The said rent of Rs. [_____] per month is [excessive and beyond the standard rent / inadequate and below the standard rent] determinable under Section 7 of the Maharashtra Rent Control Act 1999 [or State equivalent], for the reasons set out hereinafter.'*"
  - "Cost-of-construction methodology — *'The suit premises were constructed in or about the year [____] at a cost of construction of approximately Rs. [_____] per square foot of built-up area. The land value at the date of letting was Rs. [_____] per square foot. The total built-up area of the suit premises is [_____] square feet. Computing the standard rent on the cost-of-construction basis under Section 7(1) read with Section 7(2) MRC Act 1999, taking [6% / 8.25%] annual return on the aggregate of land cost and construction cost, less depreciation at [____]% per annum since construction, the standard rent is Rs. [_____] per month.'*"
  - "Comparable-market methodology — *'In the alternative, comparable rents in respect of similar premises in the same locality are: (i) Premises at [_____] — Rs. [_____] per month; (ii) Premises at [_____] — Rs. [_____] per month; (iii) Premises at [_____] — Rs. [_____] per month. The mean comparable rent is Rs. [_____] per month, which corroborates the cost-of-construction figure.'*"
  - "Statutory increases recital — *'The permitted statutory increase under Section 11 of the MRC Act 1999 is 4% per annum from the date of commencement of the Act. Applying the said increase from [date] to date, the standard rent stands at Rs. [_____] per month.'*"
  - "Pendency deposit — *'The Applicant undertakes to continue to deposit the agreed rent of Rs. [_____] / the provisional standard rent as may be fixed by this Hon'ble Court under Section 8 MRC Act 1999, pending final determination of the standard rent.'*"
  - "Prayer — *'It is therefore most respectfully prayed that this Hon'ble Court may be pleased to: (a) fix the standard rent of the suit premises at Rs. [_____] per month with effect from [date]; (b) direct refund / adjustment of any excess rent paid by the Applicant above the standard rent under Section 9 of the MRC Act 1999; (c) fix provisional standard rent pending final determination; (d) award costs of the application; and (e) pass such further and other orders as this Hon'ble Court may deem fit and proper.'*"
statutory_anchors:
  - "Section 7 + Section 8 (procedure) + Section 9 (excess-rent recovery) + Section 10 (permitted increases) + Section 11 (statutory increase) Maharashtra Rent Control Act 1999"
  - "Sections 6 to 9 Delhi Rent Control Act 1958 (standard rent)"
  - "Section 14 Karnataka Rent Act 2001 (fair rent)"
  - "Sections 17 to 22 West Bengal Premises Tenancy Act 1997"
  - "Tamil Nadu Regulation of Rights and Responsibilities of Landlords and Tenants Act 2017 (fair-rent provisions for old tenancies)"
registration_position: "Not applicable — application before Rent Controller / Court of Small Causes; not a registrable instrument."
notice_requirement: "Application filed in prescribed form with court fee; notice to Respondent served by the Court process. No pre-application statutory notice required (distinct from eviction petitions)."
v_dhanapal_chettiar_check: "Not applicable — standard-rent fixation is exclusively under the State Rent Act."
bharatiya_sakshya_check: "Tenancy agreement / rent receipts / cost-of-construction evidence (architect s certificate, contractor s bills, Ready Reckoner extracts), comparable-rents evidence (lease deeds / agreements of comparable premises), depreciation computation (PWD / municipal valuation), all to be marked as Bharatiya Sakshya Adhiniyam 2023 compliant exhibits."
methodology_options: "THREE alternative methodologies: (a) cost-of-construction (Section 7(1) MRC Act); (b) comparable-market (where cost-of-construction data unavailable / unreliable); (c) statutory-increase from a previously-fixed base (Section 11 MRC Act 4% per annum)."
```

## Statutory framework summary

- **Section 7 MRC Act 1999** — Defines "standard rent" as (i) where rent is fixed by the Court, the rent so fixed; (ii) where no such fixation, the rent at which the premises were let on the 1st day of October 1987 (or first letting if later); (iii) where premises let after specified date, the rent which the Court may determine on application by landlord or tenant on the cost-of-construction-plus-fair-return basis.
- **Section 8 MRC Act 1999** — Procedure on application — Court may fix provisional standard rent pending final determination; tenant must continue paying agreed rent or provisional rent.
- **Section 9 MRC Act 1999** — Recovery of excess rent — tenant entitled to recover rent paid above standard rent within prescribed limitation (typically 6 months to 1 year).
- **Section 10 MRC Act 1999** — Permitted increases — landlord may add to standard rent: (i) increase on account of taxes / cesses; (ii) increase for amenities provided; (iii) increase for improvements / additions; (iv) special increase as prescribed.
- **Section 11 MRC Act 1999** — Automatic statutory increase — 4% per annum on standard rent from commencement of the Act / from date of last fixation.
- **Sections 6 to 9 DRC Act 1958** — Delhi standard rent regime — similar cost-of-construction-plus-return basis with prescribed percentages.
- **Section 14 KRA 2001** — Karnataka fair rent — formula-based with reference to construction year, depreciation, and reasonable return.

## Cost-of-construction methodology (Section 7 MRC Act)

The cost-of-construction methodology yields:

**Standard Rent = ((Land Cost + Construction Cost) × Return %) / 12 — Depreciation Adjustment**

Components:

- **Land cost** at date of letting / construction (use sale deed of land OR Ready Reckoner OR registered comparable transactions)
- **Construction cost** at date of construction (use architect s certificate OR Public Works Department schedule of rates OR contractor s bills)
- **Return percentage** — typically 6% to 8.25% per annum (statute / case-law specific)
- **Depreciation** — typically 0.5% to 1% per annum for residential, higher for commercial
- **Built-up area** — verified from sanctioned plan / completion certificate

The Drafter annexes:

- Architect s certificate of cost-of-construction
- Sanctioned plan / completion certificate showing built-up area
- Land cost evidence (sale deed / Ready Reckoner extract)
- Depreciation computation table
- Section 47 BSA expert opinion (where required)

## Comparable-market methodology

Where cost-of-construction data is unavailable / unreliable (very old buildings / no sanctioned plan / no contractor records), the comparable-market methodology yields standard rent by reference to similar premises:

- Similar locality (within 1-2 km radius)
- Similar built-up area (within +/- 20%)
- Similar amenities and condition
- Similar tenure / commercial vs residential
- Recent lease transactions (within last 2-3 years)

The Drafter annexes lease deeds / agreements / society records of comparable premises with verification.

## Statutory-increase methodology (Section 11 MRC Act)

Where a base standard rent is already fixed / agreed, the Section 11 methodology applies automatic 4% per annum compound increase from the commencement of the Act / from date of last fixation. The Drafter computes:

**Current Standard Rent = Base Standard Rent × (1.04)^(years elapsed)**

This methodology is used where landlord seeks confirmation of statutory increase or tenant seeks confirmation that current rent demanded does NOT exceed the Section 11 cap.

## Permitted increases (Section 10 MRC Act)

Beyond the standard rent + Section 11 increase, the landlord may claim additional increases under Section 10:

- **Property tax increase** — pass-through of post-tenancy enhancement
- **Cess / municipal charges** — pass-through
- **Amenities** — lift, generator, security, parking, club access — increase pro-rata to cost
- **Structural improvements** — air-conditioning, modular kitchen, etc. — increase based on cost-plus-return formula
- **Special increase** — prescribed under State Rules

Each permitted increase must be claimed with supporting evidence; tenant may challenge.

## Pendency-deposit discipline

While the application is pending:

- Tenant must continue to pay / deposit the AGREED rent (the rent in the lease deed / receipts), OR
- Court may fix PROVISIONAL standard rent under Section 8 MRC Act, which then becomes the pendency-deposit rate
- Default in pendency deposit attracts Section 11(4) MRC Act / Section 27 DRC Act consequences — striking off defence / summary order

The Drafter pleads the undertaking to deposit on the higher of agreed-rent or provisional-rent until final determination.

## Section 9 MRC Act — recovery of excess rent

Where Court determines standard rent LOWER than agreed rent, tenant is entitled to:

- Refund / adjustment of excess rent paid above standard rent
- Limitation: typically within 6 months to 1 year from determination (verify State Act)
- Excess rent paid before application date may be barred by limitation; from application date onwards refund is mandatory

The Drafter pleads precise quantification of excess from a back-date with limitation calculation.

## Who files

- **Tenant** — typically files where agreed rent is excessive vis-a-vis cost-of-construction / market / Section 11 cap; seeks downward fixation + refund of excess
- **Landlord** — occasionally files where agreed rent is below market / construction cost and landlord seeks upward fixation; less common in practice

## Common opposing-counsel challenges

1. **Cost-of-construction data unreliable** — architect s certificate inflated / contractor s bills fabricated.
2. **Wrong year of construction** — depreciation computation wrong if construction year disputed.
3. **Wrong built-up area** — landlord claims more area than sanctioned / completion certificate.
4. **Comparable premises not truly comparable** — different size, location, amenities.
5. **Section 11 cap exceeded** — landlord s claim of permitted increase exceeds 4% per annum statutory cap.
6. **Amenities not provided / discontinued** — landlord cannot claim amenity-increase for services not actually provided.
7. **Limitation bar on excess refund** — tenant s claim for refund of excess rent paid before prescribed period is time-barred.
8. **Pendency-deposit default** — tenant s defence / application liable to be struck off.

The Drafter pre-empts these by: (a) architect s certificate from credentialed professional; (b) sanctioned plan + completion certificate for built-up area; (c) Ready Reckoner extracts + comparable lease deeds; (d) precise statutory-increase computation table; (e) amenity-by-amenity factual confirmation; (f) limitation-aware quantification of excess refund. The Overseer surfaces residual gaps for the advocate's review.
