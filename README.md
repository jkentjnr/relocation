# Malta Relocation & Property Advisory

A [Paperclip](https://github.com/paperclipai) **agent company** — a configured team of AI agents with an org chart, skills, and governance — built to do one job well:

> Research the Malta residential property market and produce an integrated **relocation-and-investment strategy** for a client moving to Malta — covering property selection, the legal ownership route, financing, tax, cross-border business structuring, and the practical move.

It conforms to the `agentcompanies/v1` schema and can be imported into Paperclip and run.

The company is **generic and reusable** — it holds no facts about any particular client. Each engagement is described in a separate **brief** in [`briefs/`](./briefs) (the example brief is `briefs/kent-family-malta.md`), which the agents read as the frame for their work. To run the firm for a new client, supply a new brief.

## The problem this company is built around

In Malta, *living in* a property and *renting it out* are not automatically compatible:

- A property bought by a non-resident under an **Acquisition of Immovable Property (AIP) permit** must be the owner's **residence and cannot be let**, and a non-resident may generally hold **only one** such property.
- Properties in **Special Designated Areas (SDA)** carry **no such restriction** — they can be let, and an owner may hold more than one.
- Any **short-let (holiday) rental** requires a **Malta Tourism Authority licence** under the 2026 regime (Legal Notice 92 of 2026), with real constraints and penalties.

So a naive "buy a nice apartment and put it on Airbnb" plan can be illegal depending on the route. Making that trade-off **explicit and quantified** is the firm's central task — and it shapes every agent's instructions. Where the brief makes a home the priority and income a preference rather than a rule, a standout home that cannot legally be let stays on the table, evaluated as a home-plus-capital-appreciation play against the rentable alternatives.

### The trade-off is status- and time-bound

The route depends on the client's **citizenship/residency status**, which the brief supplies:

- **Third-country nationals** (non-EU citizens, including post-Brexit British): only the AIP-or-SDA routes apply.
- **EU / Maltese citizens:** a primary residence escapes AIP entirely — buy anywhere, no SDA limit — and a third-country-national spouse gains family-member residence rights. After **5 years' continuous residence**, letting on any property unlocks.

When a client's status is changing (e.g. a citizenship application in progress), the firm reasons in **two regimes** (current vs future status), treats timing as a strategic variable, states which regime each recommendation assumes and whether **waiting** changes the answer, and flags any status deadline in the brief as a gating dependency to refer to specialist counsel.

## How the company works

A **hub-and-spoke practice with a synthesis pipeline**: the Managing Partner takes the brief and routes work to three directors; each director's specialists produce focused analyses; the Strategy Editor synthesises everything into one decision-ready memo; the Managing Partner signs off.

## Org chart

```
Managing Partner (CEO)            — intake, routing, final sign-off
├── Director of Market Research   — what to buy and where
│   ├── Market Analyst            — market baseline, what the budget buys
│   ├── Locality Specialist       — town/area comparison, SDA flagging
│   └── Rental Yield Analyst      — long-let & short-let yields
├── Director of Investment Strategy — does it pencil out, after tax
│   ├── Financing Analyst         — mortgages, deposit, cash-at-deed
│   ├── Tax & Residency Advisor   — stamp duty, rental tax, residency
│   ├── International Tax & Structuring Specialist — an Australian company run from Malta
│   └── Portfolio Strategist      — like-for-like ROI model
├── Director of Relocation & Legal — is it legal to own + let, and livable
│   ├── Legal & Conveyancing Specialist — AIP vs SDA, notary, konvenju, deed
│   ├── Livability Specialist     — healthcare, transport, lifestyle
│   └── Settlement & Logistics Specialist — banking, utilities, the move
└── Strategy Editor               — synthesises the final memo
```

**15 agents · 12 custom skills.**

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
| International Tax & Structuring Specialist | Structuring an Australian company run from Malta | Dir. Investment Strategy |
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
- `cross-border-business-structuring` — Australian company operated from Malta (residency, PE, Australia–Malta treaty, non-dom & 6/7ths regimes, exit CGT)
- `investment-roi-modeling` — like-for-like, after-tax ROI comparison
- `property-legal-conveyancing` — AIP vs SDA route, notary, konvenju, deed
- `livability-assessment` — healthcare, connectivity, lifestyle, seasonality
- `relocation-logistics-checklist` — sequenced move playbook
- `investment-strategy-memo` — synthesise the final deliverable

## The deliverable

A single **Malta Relocation & Property Investment Strategy** memo: a recommended shortlist of strategies (locality + property type + ownership route) spanning both dual-purpose (home + income) and standout home-only (home + capital appreciation) options, each costed like-for-like, with a ranked recommendation, a risk register, and a step-by-step action plan from offer to keys-in-hand.

## Repository layout

```
COMPANY.md            generic firm definition (no client facts)
agents/               the 15 agent definitions
skills/               the 12 custom skills (methodology + 2026 reference facts)
references/           shared, non-client-specific reference data
  malta-property-sources.md   Maltese agencies, portals & official data sources
briefs/               engagement-specific prompts (client facts live here)
  kent-family-malta.md        the example engagement brief
deliverables/         generated outputs (strategy memos)
```

The **company definition** (`COMPANY.md`, `agents/`, `skills/`) is reusable and client-agnostic. The **brief** carries who the client is; the firm reads it at runtime. Keep a brief private (git-ignore it) if you don't want client facts committed.

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
