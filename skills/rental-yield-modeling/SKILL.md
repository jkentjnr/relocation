---
name: rental-yield-modeling
description: Estimate gross and net rental yield for a Malta property under long-let and short-let scenarios, with explicit operating-cost and occupancy assumptions.
---

# Rental Yield Modeling

Use this skill to turn a purchase price and an area into a credible income estimate.

## When to use
- Once candidates have a price and locality, to quantify the income side.

## Method
1. **Long-let scenario.**
   - Estimate achievable monthly rent for the property type/area (re-verify with live listings and achieved rents).
   - Gross yield = (annual rent ÷ all-in purchase cost) × 100.
   - Net yield: subtract management (~8–12% if managed), maintenance, insurance, ground rent/condominium fees, and a vacancy allowance.
2. **Short-let (holiday) scenario.**
   - Estimate average nightly rate × realistic occupancy (seasonal — Malta peaks in summer).
   - Subtract the heavier short-let cost stack: MTA-compliant management, cleaning/turnover, furnishing amortisation, utilities, platform fees, higher maintenance, and a larger vacancy/seasonality allowance.
   - **Gate it on licensability** — call the `short-let-licensing-assessment` skill; an unlicensable short-let yield is zero.
3. **Compare** long-let vs short-let net yield for each candidate, and show the gross→net bridge so the number is trusted.

## 2026 reference points (re-verify at runtime)
- Harbour area (Sliema/St Julian's/Gzira) gross yields ~4–6%, compressed by high purchase prices.
- Premium-area rents (reference): 1-bed ≈ €1,100–1,500/mo, 2-bed ≈ €1,500–2,200/mo.
- Cheaper localities can out-yield premium ones on a gross basis despite lower rents.

## Output
Per candidate: achievable rent, gross yield, net yield, and the assumption set, for both long-let and short-let — with short-let flagged valid only if licensable.

## Sources
Pull rents, nightly rates, and occupancy signals from the rental portals and short-let sources in `references/malta-property-sources.md`.

## Caveats
Short-let returns are highly sensitive to occupancy and the 2026 regulatory stack; model conservatively and never present a gross figure as if it were net.
