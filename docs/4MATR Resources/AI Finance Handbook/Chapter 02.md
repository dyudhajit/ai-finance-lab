# Chapter 2

## The AI-First Engineering Mindset

AI makes it much easier to write code.

It does not make it easier to build the right features.

That distinction matters.

A model can generate a working Python function in seconds. It can also generate a plausible-looking financial model with incorrect assumptions, broken links, inconsistent definitions, or outputs that cannot be reconciled.

The bottleneck therefore moves.

Previously, much of the work was writing code.

With AI, more of the work becomes:

- defining the problem
- specifying the expected behaviour
- providing the right context
- reviewing the output
- testing the result
- integrating it into the wider system

This is the AI-first engineering mindset.

It is not "let AI build everything."

It is:

> Use AI to reduce the cost of implementation while increasing the importance of specification, review, and verification.

---

## Learning Objectives

By the end of this chapter, you should be able to:

- distinguish AI-assisted development from AI-directed development
- break a financial problem into explicit requirements
- provide AI with useful context
- review AI-generated code systematically
- use tests and reconciliations to validate outputs
- recognise why plausible AI output is not evidence of correctness
- apply financial modelling discipline to software development

---

## Engineering Principles

### Principle 1: Specify Before You Generate

Do not start with:

> "Build me a financial dashboard."

Start by defining:

- the user
- the objective
- the inputs
- the outputs
- the calculations
- the data sources
- the constraints
- the expected behaviour when data is missing

The quality of the implementation is constrained by the quality of the specification.

---

### Principle 2: AI Generates; You Decide

AI can propose:

- code
- architecture
- formulas
- tests
- documentation
- debugging approaches

It cannot be the final authority on whether those outputs are correct.

That responsibility remains with the engineer.

In financial modelling, this is familiar.

A formula that produces a number is not necessarily a correct formula.

The same applies to code.

Code that runs is not necessarily correct code.

---

### Principle 3: Review Outputs at the Right Level

Do not review AI output only line by line.

Review it at three levels.

#### Level 1 — Syntax

Does the code run?

#### Level 2 — Logic

Does it do what it is supposed to do?

#### Level 3 — System

Does it behave correctly within the wider application?

A function can pass Level 1 and fail Levels 2 and 3.

---

### Principle 4: Make Errors Observable

A good system makes mistakes obvious.

A bad system produces plausible numbers.

This is particularly important in finance.

Consider a revenue forecast:

```
Revenue = Revenue Prior Year × (1 + Growth)
```

The formula is simple.

But a system also needs to answer:

- What happens if prior-year revenue is missing?
- What if growth is None?
- What if revenue is negative?
- What if the API returns a different currency?
- What if the historical period is incorrectly identified?
- What if the company reports revenue under a different taxonomy?

The formula is only part of the problem.

---

## The Financial Modelling Analogy

The easiest way for a finance professional to understand AI-assisted engineering is to think about financial modelling.

A good financial model has:

- clear assumptions
- defined inputs
- logical calculations
- structured schedules
- linked outputs
- checks
- review mechanisms

Software should be treated similarly.

|Financial Model      |    Software System |
|---------------------|--------------------|
|Assumptions          |    Requirements    |
|Inputs               |    Data            |
|Formulas             |    Functions       |       
|Schedules            |    Modules         |
|Outputs              |    Interfaces      |
|Balance checks       |    Tests           |
|Model review         |    Code review     |
|Version history      |    Git             |

The terminology changes.

The discipline does not.

---

## From Prompting to Specification

A common beginner workflow is:
```
Ask AI
  ↓
Copy code
  ↓
Run code
  ↓
Fix error
  ↓
Ask AI again
```
This works for small experiments.

It becomes inefficient as the project grows.

A better workflow is:
```
Define requirement
  ↓
Define constraints
  ↓
Provide context
  ↓
Ask AI for implementation
  ↓
Review implementation
  ↓
Test
  ↓
Integrate
  ↓
Document
```

> The difference is that the second workflow treats AI as part of an engineering process rather than as a substitute for one.

---

## Context Is an Engineering Input

AI output depends heavily on context.

Consider these two prompts.

**Prompt A**
```
Build a DCF.
```
**Prompt B**
```
Build a DCF module for a Streamlit finance application.

Inputs:
- UFCF by forecast year
- WACC
- terminal growth rate
- forecast period

Requirements:
- calculate PV of forecast UFCF
- calculate terminal value using Gordon Growth
- discount terminal value
- calculate enterprise value
- expose intermediate calculations
- validate that WACC > terminal growth
- return a structured result
- do not embed Streamlit UI code in the calculation module
```

The second prompt is better because the problem has been specified.

> The important improvement is not clever wording. It is information.

---

## Context Engineering

In an AI-assisted development environment, context becomes a form of engineering input.

Useful context includes:

- repository structure
- relevant files
- data schemas
- existing functions
- coding conventions
- business requirements
- expected outputs
- known constraints
- examples
- tests
- error messages

**Poor context produces generic solutions.**

> Good context allows the AI to work within the required framework.

---

### Give AI the Smallest Useful Problem

Large prompts often produce large, difficult-to-review outputs.

Instead of saying:
```
"Build the entire public comparables platform."
```

Break the problem down.

**Step 1**
```
Define the company data structure.
```
**Step 2**
```
Build the market-cap calculation.
```
**Step 3**
```
Build enterprise value.
```
**Step 4**
```
Calculate valuation multiples.
```
**Step 5**
```
Add peer aggregation.
```
**Step 6**
```
Build the table.
```
**Step 7**
```
Add validation.
```
**Step 8**
```
Connect the UI.
```
Each step creates a smaller unit that can be reviewed independently.

This is not only easier for AI to build.

It is easier for humans to audit.

---

### Architecture Before Code

AI is particularly good at producing code before the architecture has been resolved.

**This creates a common failure mode:**
```
Prompt
  ↓
Code
  ↓
Another prompt
  ↓
More code
  ↓
Another prompt
  ↓
More code
  ↓
Large tangled application
```
The application may work.

It becomes increasingly difficult to understand or modify.

**The alternative is:**
```
Requirement
    ↓
Architecture
    ↓
Interfaces
    ↓
Modules
    ↓
Implementation
```
For the AI Finance Dashboard, for example, we chose to distinguish the logic into:
```
Data Layer
    ↓
Analytics Layer
    ↓
Application Layer
    ↓
Presentation Layer
```
> A data retrieval function should not also decide how a Streamlit table is formatted.

> A valuation calculation should not depend on a button being clicked.

> A UI component should not contain the definition of enterprise value.

**Separation makes the system easier to test and change.**

---

## The Three-Statement Model as an Engineering Lesson

Financial models provide a useful example of why architecture matters.

Consider a three-statement model:
```
Income Statement
       ↓
Cash Flow Statement
       ↓
Balance Sheet
```
But the actual system contains (potential) circular relationships.

For example:
```
Debt
 ↓
Interest Expense
 ↓
Pre-Tax Income
 ↓
Net Income
 ↓
Cash Flow
 ↓
Cash
 ↓
Debt
```
A model therefore needs an explicit architecture for these dependencies.

The same principle applies to software.

> If dependencies are implicit, systems become difficult to debug.

> If dependencies are explicit, errors become easier to isolate.

---

## AI Can Produce Plausible Errors

This is one of the most important concepts in AI-assisted engineering.

AI-generated errors are often syntactically valid.

Consider:
```
enterprise_value = market_cap + total_debt - cash
```
The code is valid.

The formula is also often valid.

But suppose the source data defines debt as:
```
Total Debt = Short-Term Borrowings + Long-Term Borrowings
```
while the API field being used contains only long-term debt.

The code runs.

The result is wrong.

**This is a financial error, not a programming error.**

> AI cannot reliably detect this without sufficient context.

---

## The Model Review Mindset

The same distinction appears in financial modelling.

A model can:

- calculate correctly
- balance mechanically
- look professional

and still contain a conceptual error.

Examples include:

- using EBITDA instead of EBIT for a specific metric
- treating capex as depreciation
- using the wrong working-capital definition
- double-counting debt
- using inconsistent historical periods
- applying an inappropriate growth assumption

The engineering equivalent is:

- wrong data source
- wrong field
- wrong type
- wrong dependency
- wrong business rule
- wrong abstraction

The lesson is simple:

**Technical correctness does not guarantee financial correctness.**

---

### Build Checks Into the System

> Financial models use checks. Financial Software should too.

For example:
```
assert wacc > terminal_growth
```
A valuation engine might check:
```
WACC > Terminal Growth
```
A financial statement system might check:
```
Assets = Liabilities + Equity
```
A market-data pipeline might check:
```
Market Capitalization >= 0
```
A share-price input might check:
```
Price > 0
```
**Checks convert silent errors into visible failures.**

---

### Prefer Explicit Failures to Silent Substitutions

A dangerous pattern is:
```
revenue = data.get("revenue", 0)
```
This prevents the application from crashing.

But if revenue is actually missing, the system has silently converted:

Missing data

into:
```
Zero revenue
```
That can be much worse.

In financial analysis, a missing value and a zero value are not equivalent.

Prefer explicit handling:
```
if revenue is None:
    raise ValueError("Revenue data is unavailable")
```
or, where appropriate:
```
revenue = None
```
and handle the missing value at the presentation or analysis layer.

**The correct approach depends on the business requirement.**

> The important point is to make the distinction explicit.

---

## AI as a Junior Analyst

A useful mental model is to treat an AI coding assistant like a very fast junior analyst.

It can:

- produce a first draft
- investigate an error
- explain unfamiliar code
- suggest alternatives
- write repetitive code
- generate tests
- document functions

But you would not give a junior analyst unrestricted authority over an entire financial assignment.

You would:

- define the task
- provide context
- review the work
- test the calculations
- challenge assumptions
- integrate the output

Use the same discipline with AI.

---

## The AI Development Loop

The AI development workflow used throughout this handbook is:

```
1. Specify
      ↓
2. Contextualise
      ↓
3. Generate
      ↓
4. Inspect
      ↓
5. Test
      ↓
6. Refine
      ↓
7. Integrate
```

Each stage has a purpose.

**1. Specify**

What exactly needs to happen?

**2. Contextualise**

What does AI need to know about the existing system?

**3. Generate**

What implementation should AI propose?

**4. Inspect**

Does the implementation make sense?

**5. Test**

Does it behave correctly?

**6. Refine**

What needs to change?

**7. Integrate**

Does it fit the rest of the application?

> Skipping steps is possible. It is rarely appropriate.

---

### When AI Should Not Write the Code

AI does not need to generate everything.

For small, obvious functions, writing the code yourself may be faster.

For example:

```
def calculate_growth(current, prior):
    return current / prior - 1
```

There is little value in spending several prompts generating this function.

AI becomes more useful when the task involves:

- unfamiliar libraries
- repetitive implementation
- complex transformations
- boilerplate
- debugging
- test generation
- refactoring
- documentation

> The objective is not maximum AI usage. It is maximum useful output per unit of human attention.

---

## AI and Financial Models

The same principle applies when using AI to build financial models.

AI can generate:

- formulas
- schedules
- assumptions
- Python calculations
- Excel logic
- data extraction scripts

But the finance professional must determine:

- whether the accounting treatment is correct
- whether the forecast methodology is appropriate
- whether the data is comparable
- whether the valuation methodology is appropriate
- whether the model reconciles

This distinction became particularly clear in AI-generated financial modelling exercises.

An AI system can produce a model that looks sophisticated.

It may contain:

- three statements
- working-capital schedules
- debt schedules
- depreciation schedules
- valuation outputs

**Yet individual components may still be conceptually wrong.**

> The correct response is to introduce a proper review framework.

---

### Review the Model in Layers

When reviewing AI-generated financial software, use four layers.

#### Layer 1 — Data

Ask:

- Where did the data come from?
- Is the period correct?
- Is the unit correct?
- Is the currency correct?
- Is the definition correct?

#### Layer 2 — Calculation

Ask:

- Is the formula correct?
- Are signs correct?
- Are units consistent?
- Are assumptions applied correctly?

#### Layer 3 — Integration

Ask:

- Does the output flow correctly into dependent calculations?
- Are there duplicated calculations?
- Are definitions consistent across modules?

#### Layer 4 — Presentation

Ask:

- Is the result understandable?
- Are units labelled?
- Are periods clear?
- Are negative values formatted correctly?
- Does the presentation distinguish historical and forecast data?

Presentation is the last layer, not the first.

---

### Do Not Confuse Complexity With Quality

AI makes it easy to produce large amounts of code.

More code does not necessarily mean a better system.

A good system should be:

- understandable
- modular
- testable
- maintainable
- appropriately simple

If a calculation can be expressed clearly in ten lines, it does not need fifty.

The same principle applies to financial models.

A model with twelve unnecessary schedules is not more institutional-grade than a model with six well-designed schedules.

Complexity should correspond to a real requirement.

---

### Version Control Is Part of the Engineering Process

When working with AI, changes can happen quickly.

That makes version control more important, not less.

A sensible workflow is:
```
Working version
      ↓
Test
      ↓
Commit
      ↓
Next change
      ↓
Test
      ↓
Commit
```
Each meaningful change should have a recoverable state.

This becomes particularly important when AI proposes a large refactor.

If the refactor breaks something, you should be able to identify and reverse it.

> Git is therefore not an administrative tool. It is part of the development process.

---

### Keep the Human in the Critical Path

The objective of AI-assisted development is:
```
Human
  ↓
Specification
  ↓
AI
  ↓
Implementation
  ↓
Human Review
  ↓
Testing
  ↓
Production
```
The human remains responsible for the system.

**AI changes how quickly implementation happens.**

> It does not transfer accountability.

---

## Practical AI Prompt Structure

**A useful engineering prompt can be structured as:**
```
CONTEXT

What is the existing system?


OBJECTIVE

What needs to change?


CONSTRAINTS

What must not change?


INPUTS

What data or files are relevant?


EXPECTED OUTPUT

What should the function/system return?


VALIDATION

How should correctness be checked?
```
**For example:**
```
Context:
The application contains a valuation module
that calculates enterprise value.

Objective:
Add a DCF valuation function.

Inputs:
- UFCF
- WACC
- terminal growth
- forecast period

Constraints:
- Do not modify the existing comps module.
- Keep calculations independent of Streamlit.

Expected output:
Return enterprise value and intermediate
valuation components.

Validation:
Raise an error when WACC <= terminal growth.
```

---

### A Note on Prompt Length

> Longer prompts are not automatically better.

The objective is relevant context.

Do not provide the AI with:

- irrelevant files
- unnecessary history
- unrelated code
- contradictory requirements

> A useful prompt contains enough information to make the task unambiguous. No more.

---

## The AI Engineering Standard

Throughout this handbook, we use a simple standard:

> If you cannot explain what the system is supposed to do, you are not ready to ask AI to build it.

And:

> If you cannot test whether the output is correct, you are not ready to trust it.

These two rules eliminate a large proportion of poor AI-assisted development.

---

### AI-First Does Not Mean AI-Only

The term "AI-first" can be misleading.

It does not mean:

- never write code yourself
- automate everything
- accept generated code without review
- replace architecture with prompting
- replace financial judgment with AI

It means considering AI as part of the default development workflow.

When starting a task, ask:

> Can AI accelerate this?

Then ask:

> What remains my responsibility?

This second question is more important.

---

### Implementation Exercise

Take a simple finance calculation:
```
Enterprise Value
=
Equity Value
+
Debt
+
Preferred Stock
+
Minority Interest
-
Cash
```
Write a specification for an implementation.

Define:

**Inputs**

What values are required?

**Definitions**

What exactly does "debt" include?

**Output**

What should the function return?

**Validation**

What conditions should cause an error?

**Edge Cases**

What happens if:

- cash is missing?
- debt is negative?
- preferred stock is unavailable?
- minority interest is unavailable?

Only after defining these should you ask AI to write the function.

---

### AI Prompt Walkthrough

A practical prompt might be:
```
You are helping implement a financial analytics
module.

Context:
This module calculates enterprise value for a
public company analytics application.

Formula:

EV =
Equity Value
+ Total Debt
+ Preferred Stock
+ Minority Interest
- Cash

Requirements:
1. Accept each component as an explicit argument.
2. Do not substitute missing values with zero
   unless explicitly specified.
3. Validate numeric inputs.
4. Return the calculated enterprise value.
5. Include a docstring explaining the formula.
6. Keep the function independent of the UI.

Before writing code, identify any ambiguity
in the financial definition.
```
Notice what this prompt does.

**It does not ask AI to "build enterprise value."**

> It defines the problem. It also asks AI to identify ambiguity before implementation.

That is often useful in financial work because terminology is not always standardised across data providers.

---

### Production Tips
**1. Keep Requirements Close to the Code**

If a calculation has important business rules, document them.

Do not rely on the original AI prompt surviving indefinitely.

**2. Test Financial Logic Separately**

A valuation calculation should be testable without launching the dashboard.

**3. Expose Intermediate Values**

For financial calculations, intermediate outputs are often useful for review.

For example:

- PV of Forecast Cash Flows
- Terminal Value
- PV of Terminal Value
- Enterprise Value

A single final number is harder to audit.

**4. Keep Definitions Consistent**

If one module defines EBITDA one way and another module defines it differently, the system becomes unreliable.

Create common definitions where appropriate.

**5. Treat External Data as Untrusted**

APIs can return:

- missing values
- stale values
- unexpected types
- changed fields
- inconsistent periods

Validate external data before using it.

---

### Common Mistakes
**Mistake 1: Starting With a Huge Prompt**

Large requests create large outputs that are difficult to review.

Better: break the system into components.

**Mistake 2: Accepting Code Because It Runs**

A successful execution proves very little.

Better: test expected behaviour.

**Mistake 3: Asking AI to Make Architectural Decisions Without Constraints**

AI will fill gaps with assumptions.

Better: define architectural boundaries first.

**Mistake 4: Mixing UI and Financial Logic**

For example:
```
def calculate_ev():
    ...
    st.metric(...)
```
This makes the calculation difficult to reuse and test.

Prefer:
```
def calculate_ev(...):
    ...
    return ev
```
and keep presentation elsewhere.

**Mistake 5: Hiding Missing Data**

Do not silently turn missing financial information into zero.

**Mistake 6: Refactoring Without Tests**

AI can make a clean-looking refactor that changes behaviour.

Run tests before and after.

**Mistake 7: Using AI to Avoid Understanding**

If AI writes a function that you cannot explain, you have increased your dependency on the system rather than improved your capability.

Ask AI to explain unfamiliar code.

Then verify the explanation.

---

### Exercises

#### Exercise 1 — Convert a Prompt Into a Specification

Take:

"Build a public comps dashboard."

Rewrite it as a specification containing:

- objective
- users
- inputs
- outputs
- calculations
- constraints
- validation

#### Exercise 2 — Find the Financial Error

Consider:
```
net_debt = total_debt - cash
enterprise_value = market_cap + net_debt
```
List at least five reasons why the result could still be wrong even if the code executes successfully.

Consider:

- data definitions
- currency
- period
- missing values
- debt classification
- cash classification

#### Exercise 3 — Review AI Output

Ask an AI assistant to generate a function calculating:

- Revenue Growth
- EBITDA Margin
- Net Debt / EBITDA
- EV / EBITDA

Review the output for:

- Syntax
- Financial logic
- Edge cases
- Data assumptions
- Integration

Document every issue you find.

#### Exercise 4 — Build a Test Before the Function

Write expected test cases for:
```
calculate_growth()
```
Include:

- positive growth
- negative growth
- zero prior-year revenue
- missing revenue
- negative revenue

Then ask AI to implement the function against those requirements.

---

## Chapter Summary

AI changes how financial software is created.

It does not remove the underlying engineering problems.

The important skills therefore shift toward:

- specification
- architecture
- context
- review
- testing
- validation

Finance professionals already have a useful mental model for this.

Financial modelling requires assumptions, structured calculations, checks, and review.

AI-assisted software should be approached in the same way.

The central workflow is:
```
Specify
   ↓
Contextualise
   ↓
Generate
   ↓
Inspect
   ↓
Test
   ↓
Refine
   ↓
Integrate
```
> AI is useful throughout this process.

**It is not responsible for the process. The engineer is.**

---

## Next Chapter

### Chapter 3 

#### How to Work With AI Like an Engineer

Chapter 2 established the mindset.

Chapter 3 turns it into a working method.

We will examine how to structure AI-assisted development sessions, provide repository context, break down tasks, manage iterations, review generated changes, and maintain control as the codebase grows.