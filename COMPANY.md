---
name: Malta Relocation & Property Advisory
description: A boutique advisory firm that researches the Malta residential property market and produces an integrated relocation-and-investment strategy for clients relocating to Malta — covering property selection, the legal ownership route, financing, tax, cross-border business structuring, and the practical move. Engagement-specific facts (client identity, budget, objectives, nationality and citizenship status, any business to structure) are supplied separately as an engagement brief.
slug: malta-relocation-advisory
schema: agentcompanies/v1
version: 1.1.0
license: MIT
authors:
  - name: J. Kent
goals:
  - Research the Malta residential property market across localities, price trends, and property types, and surface the options that fit the client's stated objectives and budget
  - Make the structural tension between living in a property and renting it out under Maltese law (AIP permits vs Special Designated Areas, short-let licensing) explicit, so the client can choose knowingly between a dual-purpose property and the best possible home even where letting is not permitted
  - Reason across the client's citizenship and residency status (third-country national vs EU/Maltese citizen, and the five-year-residence threshold), because that status determines the acquisition route and can change the optimal timing
  - Model the full economics of each shortlisted strategy — acquisition costs, financing, taxes, gross and net rental yield where applicable, and total cost of ownership (including the capital-appreciation case for a home-only option) — on a like-for-like basis
  - Where the client operates a foreign business, advise on structuring and running it from Malta (corporate tax residency, permanent-establishment risk, the relevant double-tax treaty, the Maltese non-dom and company regimes, and the home country's exit-tax traps)
  - Cover the non-property side of relocation (tax residency, legal conveyancing, healthcare, schooling, banking, and logistics) so the property decision is made inside the real-world context of moving to Malta
  - Deliver a single, decision-ready investment-and-relocation strategy memo with a recommended shortlist, ranked rationale, risks, and a step-by-step action plan
metadata:
  engagement_inputs: The firm is generic and reusable. The specific engagement — client identity, budget, objectives and priority, nationality and citizenship/residency status, and any business to structure — is supplied separately as an engagement brief (see the briefs/ directory). Agents must read the active brief as the frame for the work; this COMPANY.md contains no client-specific facts.
  reference_data_basis: 2026 (Malta Budget 2026, AIP rules under Chapter 246, MTA short-let regime under Legal Notice 92 of 2026, Australia–Malta DTA 1984 for cross-border structuring). All figures are reference points captured at build time and MUST be re-verified against current sources at runtime.
---

# Malta Relocation & Property Advisory

Malta Relocation & Property Advisory is a boutique firm that helps a relocating client choose, finance, and legally structure a Maltese property — as a home, an income-producing asset, or both — and then plans the move (and, where relevant, the client's business) around it.

## Engagement inputs (kept separate from the firm)

This company is **generic and reusable**. It holds no facts about any particular client. Each engagement is described in a separate **brief** (see the `briefs/` directory), which states the client's identity, budget, objectives and their priority, nationality and citizenship/residency status, and any business to structure. **Every agent reads the active brief as the frame for its work.** To run the firm for a new client, supply a new brief; nothing in the company definition needs to change.

## Why this firm exists: the core trade-off

In Malta, *living in* a property and *renting it out* are not automatically compatible. A property bought by a non-resident under an **Acquisition of Immovable Property (AIP) permit** must be used as the owner's residence and **cannot be rented out**, and such a buyer may generally hold only one such property. Properties in **Special Designated Areas (SDA)** carry no such restriction — they can be rented, and an owner may hold more than one. On top of that, any short-let (holiday) rental now requires a **Malta Tourism Authority licence** under the 2026 regime. A naive "buy a nice apartment and rent it on Airbnb" plan can be illegal depending on the route taken.

The firm's central job is to make this trade-off **explicit and quantified** so the client can decide knowingly: where a property can be both a home and an income source, show the combined case; where the best home cannot be let, present it honestly as a home-plus-capital-appreciation play alongside the rentable alternatives.

**This trade-off is also time- and status-bound.** It bites hardest for **third-country nationals** (for whom only AIP or SDA routes exist). For an **EU or Maltese citizen**, the AIP constraint largely dissolves for a primary residence (no permit, bought anywhere, not limited to the SDA list), and after **five years' continuous residence** letting on any property unlocks. So whenever a client's citizenship or residency status is in flux, the firm reasons in **two regimes** (current vs future status), treats the status timeline as a strategic variable, and flags any deadline that gates it — drawing the specific facts from the engagement brief.

## How work flows

The firm runs as a **hub-and-spoke practice with a synthesis pipeline**:

1. **Managing Partner (CEO)** reads the engagement brief, confirms the mandate, and routes work to the three directors. Holds final sign-off.
2. **Three directors** each own a domain and delegate to their specialists:
   - **Director of Market Research** — what to buy and where (market data, localities, rental yields).
   - **Director of Investment Strategy** — whether it pencils out (financing, tax & residency, cross-border business structuring, ROI modelling).
   - **Director of Relocation & Legal** — whether it is legal and livable (conveyancing & permits, livability, settlement logistics).
3. **Specialists** produce focused analyses using their skills.
4. **Strategy Editor** synthesises every contribution into one decision-ready memo and returns it to the Managing Partner for sign-off.

## Org chart

```
Managing Partner (CEO)
├── Director of Market Research
│   ├── Market Analyst
│   ├── Locality Specialist
│   └── Rental Yield Analyst
├── Director of Investment Strategy
│   ├── Financing Analyst
│   ├── Tax & Residency Advisor
│   ├── International Tax & Structuring Specialist
│   └── Portfolio Strategist
├── Director of Relocation & Legal
│   ├── Legal & Conveyancing Specialist
│   ├── Livability Specialist
│   └── Settlement & Logistics Specialist
└── Strategy Editor
```

## Shared references

Reusable, non-client-specific reference material lives in the `references/` directory — e.g. the directory of Maltese real-estate agencies and property portals (`references/malta-property-sources.md`) that the Market Research team uses to source live listings and prices.

## The deliverable

A single **Malta Relocation & Property Investment Strategy** memo: a recommended shortlist of property strategies (locality + property type + ownership route) spanning both dual-purpose (home + income) options and best-home (home + capital appreciation) options, each costed and stress-tested, with a ranked recommendation, a dedicated section on structuring the client's business from Malta where relevant, an honest risk register, and a step-by-step action plan from offer to keys-in-hand.
