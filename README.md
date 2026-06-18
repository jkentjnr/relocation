# Malta Relocation & Property Advisory

A [Paperclip](https://github.com/paperclipai) **agent company** — a configured team of AI agents with an org chart, skills, and governance — built to do one job well:

> Research the Malta residential property market and produce an integrated **relocation-and-investment strategy** for a couple moving to Malta who want **both a primary home and rental income**, within a budget of **up to €700,000**.

It conforms to the `agentcompanies/v1` schema and can be imported into Paperclip and run.

## The problem this company is built around

In Malta, *living in* a property and *renting it out* are not automatically compatible:

- A property bought by a non-resident under an **Acquisition of Immovable Property (AIP) permit** must be the owner's **residence and cannot be let**, and a non-resident may generally hold **only one** such property.
- Properties in **Special Designated Areas (SDA)** carry **no such restriction** — they can be let, and an owner may hold more than one.
- Any **short-let (holiday) rental** requires a **Malta Tourism Authority licence** under the 2026 regime (Legal Notice 92 of 2026), with real constraints and penalties.

So a naive "buy a nice apartment and put it on Airbnb" plan can be illegal depending on the route. Resolving that into a legal, economically sound structure is the firm's central task — and it shapes every agent's instructions.

## How the company works

A **hub-and-spoke practice with a synthesis pipeline**: the Managing Partner takes the brief and routes work to three directors; each director's specialists produce focused analyses; the Strategy Editor synthesises everything into one decision-ready memo; the Managing Partner signs off.

## Org chart

```
Managing Partner (CEO)            — intake, routing, final sign-off
├── Director of Market Research   — what to buy and where
│   ├── Market Analyst            — market baseline, what €700k buys
│   ├── Locality Specialist       — town/area comparison, SDA flagging
│   └── Rental Yield Analyst      — long-let & short-let yields
├── Director of Investment Strategy — does it pencil out, after tax
│   ├── Financing Analyst         — mortgages, deposit, cash-at-deed
│   ├── Tax & Residency Advisor   — stamp duty, rental tax, residency
│   └── Portfolio Strategist      — like-for-like ROI model
├── Director of Relocation & Legal — is it legal to own + let, and livable
│   ├── Legal & Conveyancing Specialist — AIP vs SDA, notary, konvenju, deed
│   ├── Livability Specialist     — healthcare, transport, lifestyle
│   └── Settlement & Logistics Specialist — banking, utilities, the move
└── Strategy Editor               — synthesises the final memo
```

**14 agents · 11 custom skills.**

## Agents

| Agent | Role | Reports to |
|---|---|---|
| Managing Partner | Intake, routing, sign-off | — |
| Director of Market Research | Owns "what & where" | Managing Partner |
| Market Analyst | Price baseline & budget mapping | Dir. Market Research |
| Locality Specialist | Area comparison, SDA flagging | Dir. Market Research |
| Rental Yield Analyst | Long-/short-let yield + licensing | Dir. Market Research |
| Director of Investment Strategy | Owns the financial case | Managing Partner |
| Financing Analyst | Mortgage & cash-at-deed | Dir. Investment Strategy |
| Tax & Residency Advisor | Stamp duty, rental tax, residency | Dir. Investment Strategy |
| Portfolio Strategist | Like-for-like ROI model | Dir. Investment Strategy |
| Director of Relocation & Legal | Owns feasibility & livability | Managing Partner |
| Legal & Conveyancing Specialist | AIP/SDA route & conveyancing | Dir. Relocation & Legal |
| Livability Specialist | Day-to-day living quality | Dir. Relocation & Legal |
| Settlement & Logistics Specialist | The practical move | Dir. Relocation & Legal |
| Strategy Editor | Synthesises the final memo | Managing Partner |

## Skills

Custom skills in `skills/`, each grounded in 2026 Malta reference facts (to be re-verified at runtime):

- `malta-property-market-analysis` — market baseline & what a budget buys
- `locality-comparison` — score and shortlist towns/areas, flag SDA
- `rental-yield-modeling` — gross/net long-let & short-let yields
- `short-let-licensing-assessment` — MTA Holiday Furnished Premises licensability (LN 92/2026)
- `mortgage-financing-analysis` — LTV, deposit, rate, cash-at-deed
- `malta-tax-residency-assessment` — stamp duty, rental tax, residency
- `investment-roi-modeling` — like-for-like, after-tax ROI comparison
- `property-legal-conveyancing` — AIP vs SDA route, notary, konvenju, deed
- `livability-assessment` — healthcare, connectivity, lifestyle, seasonality
- `relocation-logistics-checklist` — sequenced move playbook
- `investment-strategy-memo` — synthesise the final deliverable

## The deliverable

A single **Malta Relocation & Property Investment Strategy** memo: a recommended shortlist of strategies (locality + property type + ownership route), each costed like-for-like, with a ranked recommendation, a risk register, and a step-by-step action plan from offer to keys-in-hand.

## Importing into Paperclip

From the repository root (this folder is the company package):

```bash
npx paperclipai company import --from .
```

Or point at the GitHub URL:

```bash
npx paperclipai company import --from https://github.com/jkentjnr/relocation
```

## Disclaimer

This company produces **research-grade decision support, not professional financial, tax, or legal advice**. All Malta figures, rates, thresholds, permit fees, and regulations are reference points captured in 2026 and **must be re-verified against current sources** and confirmed with qualified Maltese professionals (a notary/advocate, a tax practitioner, and a licensed bank) before committing any money.

## License

MIT — see [LICENSE](./LICENSE).
