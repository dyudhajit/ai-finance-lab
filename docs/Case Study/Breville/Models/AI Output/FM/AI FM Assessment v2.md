# AI FM Assessment - v2

## Breville Group Financial Model (AI v2 - Built on YahooFinance Data)

### AI model assessment & improvement walkthrough

*Perspective: Investment Banking Associate (M&A)*

---

## Executive Summary

Compared with the original AI-generated model, this [second version](Breville_Group_FM_v2.xlsx) built on YahooFinance Data represents a **substantial improvement in financial modelling architecture**.

The model has evolved from a relatively basic three-statement forecast into a much more structured [**integrated operating model with dedicated supporting schedules**](Breville_Group_FM_v2.xlsx).

The most significant improvement is that the AI has moved beyond isolated assumptions and begun modelling the relationships between operating performance, assets, financing, and equity.

This version now includes:

* operating working capital schedules,
* PP&E and depreciation roll-forwards,
* intangible asset and amortisation schedules,
* debt schedules,
* equity reconciliation,
* share count schedules, and
* ratio analysis.

From an investment banking perspective, this moves the model from **approximately 6/10 to 8.5/10**.

The architecture is now recognisably institutional.

However, this assessment is important for another reason.

AI has become surprisingly good at **building the structure of a financial model**, but it still struggles with **accounting integrity, financial integration, and commercial forecasting logic**.

Many of the remaining weaknesses are not spreadsheet formatting issues.

They are exactly the kinds of problems that require **analyst judgement**.

---

## What changed between AI v1 and AI v2?

One important point is that the improvement in [the AI v2 model](Breville_Group_FM_v2.xlsx) did **not** happen in isolation.

The biggest difference is that AI v2 was supplied with **structured historical financial data extracted directly from Yahoo Finance using the AI Finance Dashboard**.

Instead of asking the model to generate a financial model from a general prompt, the workflow was:

* extract historical financial statements,
* clean and standardise the data,
* structure the inputs consistently,
* and then ask the AI to build an integrated operating model from that dataset.

This matters because AI performs dramatically better when it receives **well-structured financial data** rather than fragmented or manually copied information.

In other words, the quality of the model improved because the quality of the inputs improved.

This is an important lesson for anyone using AI in finance: **better data pipelines often create bigger improvements than better prompts**.

The AI Finance Dashboard was designed specifically for this purpose — to provide AI with clean, structured financial statement data that can be used for modelling, valuation, and analytical workflows.

However, as the rest of this assessment demonstrates, better data improves the **architecture** of the model. It does not eliminate the need for **analyst validation**.


---

## Overall score

| Category             |  Score |
| -------------------- | -----: |
| Model structure      | 9.5/10 |
| Integration          | 9.0/10 |
| Formula quality      | 7.5/10 |
| Accounting integrity | 8.5/10 |
| Forecast methodology | 7.5/10 |
| Banking readiness    | 8.5/10 |

### Overall rating

**8.0/10**

A strong AI-assisted analyst-quality financial model.

It demonstrates significant progress from the original version, although several important areas still require analyst intervention before the model could be considered transaction-ready.

---

## What AI improved from v1

### 1. Proper supporting schedules

This is the single biggest improvement.

The original model relied heavily on direct assumptions embedded within the financial statements.

This version builds dedicated schedules for:

* working capital,
* PP&E,
* intangible assets,
* debt,
* equity, and
* shares outstanding.

This is much closer to how professional investment banking models are constructed.

Supporting schedules improve:

* transparency,
* auditability,
* flexibility,
* and valuation readiness.

The AI has clearly learned a more institutional modelling structure.

---

### 2. PP&E roll-forward

The depreciation schedule is a major upgrade.

The model now follows a proper asset roll-forward:

Beginning PP&E

* Capital expenditure

− Depreciation

= Ending PP&E

This is fundamentally correct modelling practice.

Depreciation is now linked to the asset base rather than being treated as an isolated assumption.

That is a meaningful improvement in model quality.

---

### 3. Intangible asset schedule

The addition of a separate amortisation schedule is another important improvement.

Many AI-generated models incorrectly combine depreciation and amortisation.

Separating them creates a cleaner operating model and provides a better foundation for acquisition analysis and valuation work.

---

### 4. Debt schedule

The debt schedule is significantly more sophisticated than the original version.

It now includes:

* opening balances,
* repayments,
* and ending balances.

Interest can be linked to debt balances rather than being manually forecast.

This is an essential institutional modelling feature.

---

### 5. Equity roll-forward

The retained earnings schedule now follows a proper reconciliation:

Beginning retained earnings

* Net income

− Dividends

= Ending retained earnings

This improves balance sheet logic and allows dividend policy to flow through equity correctly.

---

### 6. Share count schedule

The addition of basic and diluted share schedules is particularly useful.

This enables:

* EPS forecasting,
* diluted EPS,
* valuation per share,
* and dilution analysis.

Many beginner financial models omit this entirely.

---

### 7. Working capital schedule

The model now attempts a **days-based working capital forecast**.

Using DSO, DIO, and DPO is directionally correct and substantially more sophisticated than simple percentage-of-revenue assumptions.

This represents a clear step toward professional operating forecasting.

---

## Where AI still needs analyst intervention

The improvements are real, but the remaining issues are concentrated in areas where **financial reasoning matters more than spreadsheet mechanics**.

---

### Issue 1 — Revenue forecasting remains mechanical

Revenue is still forecast primarily through a growth assumption.

For a business such as Breville, a stronger model would separate:

* geographic growth,
* pricing,
* volume,
* product mix,
* and FX effects.

The AI can generate a revenue forecast.

It does not yet generate a **commercial revenue model**.

---

### Issue 2 — Margin forecasting lacks operational drivers

Gross margin and operating expenses are largely assumption-driven.

This creates a relatively smooth forecast profile.

Real consumer product businesses experience:

* freight volatility,
* commodity inflation,
* marketing investment cycles,
* operating leverage,
* and inventory normalisation.

The model captures accounting structure, but not operational behaviour.

---

### Issue 3 — Debt repayment assumptions are arbitrary

The long-term debt schedule assumes a fixed percentage repayment.

Professional models typically link debt reduction to:

* mandatory amortisation,
* refinancing,
* excess cash flow,
* and management capital allocation.

This is a key area where analyst judgement is required for making the appropriate corrections.

---

### Issue 4 — Cash management is incomplete

Cash accumulates independently rather than interacting dynamically with financing decisions.

A more advanced model would include a financing sweep that allocates excess cash to debt repayment or other capital allocation priorities.

---

### Issue 5 — Interest calculation is simplified

Interest should ideally be calculated using average debt balances.

The current approach is functional, but it is not yet consistent with standard investment banking modelling practice.

---

### Issue 6 — The balance sheet challenge

This is the most important limitation.

One of the primary tests of an integrated financial model is whether the **Balance Sheet balances**.

Every professional model should include a visibly highlighted balance sheet check:

Assets − Liabilities − Equity = 0

This is also one of the areas where AI-generated models most commonly fail.

AI is very good at:

* creating schedules,
* writing formulas,
* and linking worksheets.

It is much less reliable at maintaining **full accounting consistency across a complex integrated model**.

A model can appear sophisticated and still fail to balance because of subtle issues such as:

* retained earnings reconciliation,
* working capital timing,
* debt schedule integration,
* PP&E roll-forwards,
* cash flow sign conventions,
* and financing interactions.

This is one of the clearest examples of where **analyst intervention remains essential**.

---

### Issue 7 — Circularity management

The model currently avoids circular references, which keeps it relatively stable.

However, interest, cash, and debt are not yet fully integrated.

A slightly more advanced version would incorporate controlled circularity and financing iteration.

---

### Issue 8 — Scenario analysis

The model is now structurally ready for scenario analysis.

Adding Base, Bull, and Bear cases with scenario switches for revenue growth, margins, CapEx, and working capital would substantially improve decision usefulness.

---

## Technical assessment

### Model flow

Model flow

The model follows an integrated financial modelling architecture in which the financial statements and supporting schedules interact continuously rather than in a simple linear sequence.
```

Assumptions & Operating Drivers
              │
              ▼
      Revenue & Cost Forecast
              │
              ▼
       Income Statement
              │
      ┌───────┼────────┐
      │       │        │
      ▼       ▼        ▼
 Working    PP&E   Intangible
 Capital  Schedule  Schedule
(AR/AP)  (CapEx)  (Amortisation)
      │       │        │
      └───────┼────────┘
              │
              ▼
   Operating & Investing Cash Flow
          Adjustments
              │
              ▼
       Cash Flow Statement
              │
      ┌───────┼────────┐
      │       │        │
      ▼       ▼        ▼
    Debt   Equity   Ending
  Schedule Schedule  Cash
      │       │        │
      └───────┼────────┘
              │
              ▼
       Balance Sheet
              │
              ▼
 Ratios, Valuation & Sensitivities

```

This structure reflects how a professional investment banking model actually operates. The Income Statement drives the supporting schedules, the schedules determine cash flow and ending balance sheet positions, and the financing schedules (debt and equity) influence both the Cash Flow Statement and future Income Statement items such as interest expense and earnings per share.

The key insight is that the supporting schedules are the analytical engine of the model. They translate operational assumptions into accounting outcomes, allowing the three financial statements to remain fully integrated and internally consistent.

---

### Formula discipline

Overall formula quality has improved materially.

Links are transparent.

Assumptions are identifiable.

The workbook is relatively easy to audit.

The remaining weaknesses are primarily **financial integration and forecast methodology**, rather than spreadsheet organisation.

---

## What I would still question

If this model were used in a client discussion, I would still expect questions such as:

* Why is revenue growing 6%?
* Why is gross margin stable?
* Why are debt repayments fixed?
* What drives inventory?
* What happens in a recession?
* How does management allocate capital?

The model is increasingly capable of producing financial statements.

It is not yet capable of explaining **business behaviour**.

That distinction is critical.

---

## Final verdict

[This second-pass model](Breville_Group_FM_v2.xlsx) is a **genuinely impressive improvement from the original AI-generated model**.

The AI has demonstrated a meaningful understanding of:

* three-statement integration,
* supporting schedules,
* depreciation and amortisation,
* equity accounting,
* share dilution,
* and debt roll-forwards.

These are the building blocks of institutional financial modelling.

However, the most important takeaway is that the model still requires **analyst intervention in the areas that matter most**.

The next step is not simply adding more formulas.

The next step is ensuring:

* accounting integrity,
* balance sheet consistency,
* financing logic,
* and commercially realistic forecasting.

AI is becoming increasingly good at building financial model architecture.

Analysts remain responsible for building financial model truth.

That is the difference between a sophisticated spreadsheet and a decision-ready operating model.

---

## AI v2 assessment summary

> AI v2 is a significant upgrade from AI v1. The model has evolved from a basic three-statement forecast into a structured integrated operating model with dedicated supporting schedules.

> The most important improvement is architectural. Revenue now flows through working capital, PP&E, intangible assets, debt, and equity schedules before feeding the Balance Sheet and valuation outputs. That is much closer to the structure used in professional investment banking models.

> The model demonstrates that AI can now build a surprisingly large portion of an institutional financial model. It can create roll-forward schedules, link statements, and organise financial relationships in a recognisable way.

> However, this version also highlights the current limits of AI in financial modelling. Revenue is still mechanically forecast, margins lack operational drivers, debt assumptions are simplified, and the model’s accounting integrity still requires careful analyst verification.

> Think of AI v2 as a very strong first draft. It has dramatically improved the structure of the model, but the final stage — reconciliation, integration, and commercial judgement — is still where analysts add the most value.

> In the next post, I’ll walk through the corrected version of this model and show exactly where the AI broke, how the balance sheet was repaired, and why those corrections matter in a real investment banking environment.
