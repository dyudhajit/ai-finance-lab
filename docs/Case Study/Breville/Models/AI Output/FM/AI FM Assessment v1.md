# AI FM Assessment - v1

## Breville Financial Model (v1)

### AI Model Assessment & Walkthrough

*Perspective: Investment Banking Associate (M&A)*

---

## Executive Summary

This is a first-pass [AI-generated financial model](Breville_Group_FM_v1.xlsx).

If I received this from a first-year analyst after telling them, *"Build me a quick operating model from the annual report,"* I would say the model is approximately **50–55% complete**.

The structure is clean.

The statements link correctly.

The model is readable.

The assumptions are obvious.

However...

This is **not yet an institutional-quality investment banking model.**

The biggest issue is that the AI has produced what looks like a **mathematical model** rather than an **economic model**.

The formulas work.

The business logic often doesn't.

That distinction is one of the biggest lessons every finance professional eventually learns.

---

## Overall Score

| Category | Score |
|----------|------:|
| Structure | 7/10 |
| Formatting | 8/10 |
| Formula Consistency | 8/10 |
| Accounting Accuracy | 7/10 |
| Forecast Methodology | 5/10 |
| Model Flexibility | 5/10 |
| Banking Readiness | 6/10 |

### Overall Rating

**6/10**

A strong AI-generated draft.

Not yet ready for client delivery.

---

## First Impression

Within about thirty seconds, an Investment Banking Associate would notice several positive things.

✅ Three financial statements are present.

✅ Statements are linked together.

✅ Historical and forecast periods are clearly separated.

✅ Ratios are calculated separately.

✅ The model is readable.

✅ Circular references have been avoided.

These are exactly the kinds of things junior analysts often struggle with.

So the AI deserves genuine credit.

---

## What AI Did Well

### 1. Clean Financial Statement Architecture

The model follows the classic investment banking layout.

```
Income Statement
        ↓
Cash Flow Statement
        ↓
Balance Sheet
```

This is exactly how most sell-side models are organised.

Simple.

Logical.

Easy to audit.

---

### 2. Formula Simplicity

Most formulas are easy to understand.

For example:

```text
Revenue (t) = Revenue (t-1) × (1 + Growth Rate)
```

Simple.

Transparent.

Auditable.

That's preferable to unnecessarily complicated nested formulas.

---

### 3. Statement Linking

Cash flows correctly into the Balance Sheet.

Net Income flows into retained earnings.

The Income Statement drives the Cash Flow Statement.

This is the minimum standard expected in investment banking.

---

### 4. Readability

The workbook is easy to navigate.

- No excessive colour coding
- No hidden calculations
- Minimal merged cells
- Reasonable spacing

Good formatting matters more than beginners realise.

---

## Major Weaknesses

This is where an Excel workbook becomes a financial model.

---

### Problem 1 — Revenue Is Growing Mechanically

The forecast assumes:

```text
Next Year Revenue
=
Previous Year Revenue × (1 + Growth Rate)
```

That works mathematically.

It tells us nothing about Breville.

An Associate would immediately ask:

> **Why is revenue growing?**

- New products?
- Pricing?
- US expansion?
- European growth?
- Premium product mix?
- FX tailwinds?

The AI never answers these questions.

Revenue simply grows because a percentage says so.

That's acceptable in first-pass modelling...

but it's not accurate forecasting.

---

### Better Practice

Revenue should ideally be driven by:

- Geographic growth
- Product launches
- Volume assumptions
- Pricing assumptions
- Market share
- Foreign exchange
- Historical management guidance

This makes forecasts defendable.

---

### Problem 2 — Margins Are Static

Operating margins barely change.

Real businesses don't behave like this.

Breville experiences:

- Freight volatility
- Commodity inflation
- FX movements
- Supply chain disruptions
- Operating leverage

A banking model should explain why margins change.

Instead, AI assumes stability - flatline, which is acceptable in a first pass.

However, this removes much of the commercial insight.

---

### Problem 3 — Working Capital Forecast Is Oversimplified

Breville is an inventory-heavy consumer products company.

Working capital ought to be one of its biggest valuation drivers.

The AI forecasts:

- Inventory
- Receivables
- Payables

Professional judgement would need to be excercised for the following forecasts:

- Days Inventory Outstanding (DIO)
- Days Sales Outstanding (DSO)
- Days Payables Outstanding (DPO)

These appropriate choice of these metrics will reflect the true operational reality.

---

### Problem 4 — Capital Expenditure Is Not Operationally Driven

Capex appears to grow smoothly.

A banker immediately asks:

- Is Breville expanding manufacturing?
- Opening distribution centres?
- Investing in automation?
- Upgrading ERP systems?
- Increasing warehouse capacity?

Capex should reflect business strategy.

Not simply historical averages.

---

### Problem 5 — Depreciation Schedule Missing

Depreciation appears disconnected from asset additions.

Professional models generally build a PP&E schedule.

```text
Opening PP&E
+ Capital Expenditure
− Asset Disposals
= Closing PP&E
```

Depreciation is then derived from the asset base.

---

### Problem 6 — Debt Schedule Missing

This is probably the biggest omission.

Institutional models always include a debt roll-forward.

```text
Opening Debt
+ New Borrowings
− Repayments
= Closing Debt
```

Interest expense should be calculated from average debt balances.

Without this schedule, interest becomes an assumption rather than an output.

---

### Problem 7 — Share Count Schedule Missing

A valuation model eventually needs:

- Shares Outstanding
- Diluted Shares
- Employee Options
- Share Buybacks
- EPS
- Diluted EPS

None of these schedules currently exist.

---

### Problem 8 — Missing Supporting Schedules

Several supporting schedules are absent.

- Working Capital
- PP&E
- Debt
- Equity
- Intangibles
- Leases
- Share Capital

These schedules improve transparency and reduce modelling errors.

---

### Problem 9 — No Scenario Analysis

Investment banking models almost always include:

- Base Case
- Bull Case
- Bear Case
- Sensitivity Analysis
- Management Case

The current model contains only a single forecast.

---

## AI Hallucinations to Watch For

One lesson every analyst should learn:

**Never trust AI simply because the formulas calculate.**

Always ask:

> **"Does this make economic sense?"**

Common AI mistakes include:

- Hardcoded assumptions inside formulas
- Growth continuing indefinitely
- Cash increasing despite negative free cash flow
- Debt disappearing unexpectedly
- Unrealistically stable margins
- Circular accounting logic
- Assets growing without investment

Fortunately, this model avoids many catastrophic errors.

Every assumption still requires professional validation.

---

## If I Were Reviewing an Analyst's Work

These would be my review comments.

### Comment 1

Build a proper revenue bridge.

Forecast the business.

What is the concensus growth estimate? Footnote your sources.

---

### Comment 2

Separate assumptions from calculations.

Every key driver should live in one assumptions section.

---

### Comment 3

Build proper supporting schedules.

- Debt
- PP&E
- Working Capital

---

### Comment 4

Replace percentage assumptions with operational drivers wherever possible.

Justify flatlines with a comment.

---

### Comment 5

Double-check your Balance Sheet Check.

Please reconcile:

```text
Assets = Liabilities + Equity
```

The difference should always equal zero.

---

### Comment 6

Add scenario controls.

> "What happens if revenue slows?"

The model should answer that question with one click.

---

## What AI Gets Right

This model demonstrates something important.

Without guidance on data sources and formats, AI is already capable of:

- Extracting (scraping to be more precise) financial data
- Linking statements
- Building financial models
- Forecasting mechanically
- Producing clean Excel structures

That alone can save analysts hours.

---

## What AI Cannot Yet Replace

AI still cannot replace:

- Commercial judgement
- Industry understanding
- Management interpretation
- Forecast rationale
- Business intuition
- Valuation judgement

Those remain fundamentally human skills.

---

## Final Verdict

As an Investment Banker, I would accept this [workbook](Breville_Group_FM_v1.xlsx) as a **starting point**, not a finished deliverable.

It eliminates approximately **50–60% of the repetitive Excel work** traditionally performed by junior analysts.

The remaining **40–50%**—transforming the spreadsheet into an institutional-quality financial model—still requires professional judgement, commercial thinking and rigorous modelling discipline.

The biggest takeaway is not that AI replaces financial modelling.

Rather...

AI changes where analysts spend their time.

Less time building rows.

Less time writing formulas.

More time understanding businesses.

More time validating assumptions.

More time generating investment insight.

---

## AI Model Assessment Summary

> What you're looking at is a first draft generated with AI. The objective wasn't to build a perfect model, but to see how far AI can take us before human judgement becomes essential.

> The AI has correctly structured the three financial statements, linked them together, and projected the business into the future. That's already a meaningful productivity gain. Tasks that might take a junior analyst several hours can now be completed in minutes.

> But here's the key lesson: a spreadsheet that calculates is not necessarily a financial model that explains a business.

> Notice how revenue is forecast using a simple growth assumption. That's mathematically correct, but an investment banker wants to understand *why* revenue is growing. Is it pricing? Product launches? Geographic expansion? FX? Consumer demand? Those are business questions—not spreadsheet questions.

> The same applies to margins, working capital and capital expenditure. AI has extrapolated historical trends, but it doesn't yet understand management strategy or operational realities. That's where human analysis creates value.

> Think of AI as your first-year analyst. It can assemble the framework quickly, perform repetitive tasks consistently and eliminate much of the manual work. But every assumption still needs to be challenged.

> Our role as finance professionals is no longer just building models. It's reviewing them, improving them, stress-testing them and ensuring every number reflects the economics of the business rather than simply extending historical trends.

> That's exactly the philosophy behind the AI Finance Lab. We use AI to automate the mechanics so we can spend more time on judgement, valuation and investment insight.