# [U.S Solar Equipment Importer] – Technical Specification 

**Created by:** [Victoria Zheng]  
**Updated by:** [Victoria Zheng]  
**Date Created:** [4/15/26]  
**Date Updated:** [2/15/26]  
**Version:** [0.0]
**LLM Used:** [None]

**Role:** Financial Analyst / Treasury Analyst  
**Audience:** CFO or Director of Treasury  

**Purpose:** Provide a professional, quantitative specification outlining the analytical structure for evaluating FX hedging alternatives.

---

## 1. Problem Statement

Our company, a U.S.-based solar equipment importer, expects to receive €4,500,000 in 12 months, exposing us to transaction exposure from potential EUR/USD exchange rate fluctuations. This specification outlines the analytical framework for quantifying, comparing, and evaluating alternative hedging strategies—including forward contracts, money-market hedges, and currency options—to determine the optimal approach for protecting the USD value of this receivable while balancing cash flow certainty, cost efficiency, and strategic flexibility. The analysis will support a data-driven recommendation to corporate treasury leadership for mitigating downside currency risk.


## 2. Inputs (Known Variables)


| Variable | Description | Unit | Example | Source |
|-----------|-------------|------|----------|--------|
| `FC_AMT` | Foreign-currency receivable | EUR | 1,200,000 | Company data |
| `S₀` | Current EURUSD spot rate | USD/EUR | $1.18 | Market data |
| `F₀` | 1-year EURUSD forward rate | USD/EUR | 1.0890 | Provided |
| `r_USD` | USD 1-year interest rate | % | 3.68% | Market data |
| `r_EUR` | EUR 1-year interest rate | % | 4% | Market data |
| `t` | Time to maturity | Years | 1 | Derived |
| `K_put` | EUR Put strike | USD/EUR | 1.24 | Analyst choice |
| `K_call` | EUR Call strike | USD/EUR | 0.02 | Analyst choice |
| `Premium_put` | Put premium | USD per contract | 0.017 | Scenario |
| `Premium_call` | Call premium | USD per contract | 0.022 | Scenario |

---

## 3. Assumptions & Constraints

- The forward rate provided represents a 1-year maturity.  
- Transaction and credit costs are excluded.  
- Option premiums are paid upfront in USD.  
- Exchange rates expressed as USD per EUR.
- Interest rates assumed based on market data at the time of search

---

## 4. Calculation Flow

Step 1: Define Base Parameters
- Record receivable amount (€4,500,000), time horizon (12 months), spot rate, forward rate (1.0875 USD/EUR), and option terms (strike, premium).
- Gather USD and EUR interest rates for money-market calculations.

Step 2: Establish Unhedged Baseline
- Project USD proceeds across multiple future spot rate scenarios.
- This serves as the benchmark for comparing all hedged strategies.

Step 3: Model Forward Contract Hedge
- Lock in forward rate for full receivable amount.
- Calculate fixed USD proceeds (outcome invariant to exchange rate movements).

Step 4: Formulate Recommendation
- Select strategy aligned with objectives
- Document alternatives and key limitations.

---

## 5. Outputs


| Output | Description | Format | Purpose |
|---------|--------------|---------|----------|
| `USD_forward` | USD proceeds from forward hedge | Numeric | Certainty benchmark |
| `USD_mm` | USD proceeds from money market hedge | Numeric | Cross-check against forward |
| `USD_put` | USD proceeds from EUR put hedge | Table | Sensitivity & protection |
| `USD_call` | USD proceeds from EUR call hedge | Table | Optional upside case |
| `Chart_1` | Hedge outcomes vs. S_T | Line chart | Visual comparison |
| `Summary` | Written conclusion | 1–2 paragraphs | Executive-ready takeaway |


---

## 6. Sensitivity Plan

> Define Exposure by identifing currency pairs, amounts, and dates (receivables/payables). 
> Vary EURUSD spot at maturity \(S_T\) from 0.95×S₀ to 1.05×S₀ in increments of 0.01.  
> Run Simulations for each value, compute USD proceeds under all hedge strategies.
> Define Exposure: Identify currency pairs, amounts, and dates (receivables/payables).
> Present results as a comparison table and line chart.

---

## 7. Limitations & Next Steps

- dynamic volatility is excluded.
- Counterparty default risk on forward and option contracts is excluded.
- Bid-ask spreads, banking fees, and margin requirements are excluded.
- All tax implications are excluded.

- Next Steps are to run scenario simulations and generate comparative outputs for CFO recommendation.
