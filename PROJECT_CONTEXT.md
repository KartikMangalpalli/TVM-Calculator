# PROJECT_CONTEXT.md
## TVM Calculator — MIT Vishwaprayag University, Solapur
### BS3210: Finance for Engineers, Designers and Professionals
### Assignment 1: Time Value of Money (TVM) Calculator Application

---

## Assignment Objective
Develop a working HTML-based web application that enables users to perform the following financial calculations:
1. Future Value (FV)
2. Present Value (PV)
3. Simple Interest
4. Compound Interest
5. EMI Calculation
6. Loan Amortization Schedule
7. Scenario Analysis based on different interest rates

## Technology
- HTML5, CSS3, Vanilla JavaScript ONLY
- No frameworks, no backend, no database
- Single-page application (index.html + style.css + script.js)

## File Structure
```
TVM-Calculator/
+-- index.html          - Main HTML structure and navigation
+-- style.css           - All styling (professional, clean, responsive)
+-- script.js           - All financial logic and UI interactions
+-- PROJECT_CONTEXT.md  - This file (project memory)
+-- DEVELOPMENT_LOG.md  - Development history
+-- TEST_REPORT.md      - Test cases and results
```

## Financial Formulas Used

### 1. Future Value
FV = P x (1 + r)^n
- P = Principal Amount, r = Annual Interest Rate (decimal), n = Time Period in Years

### 2. Present Value
PV = FV / (1 + r)^n
- FV = Future Value, r = Discount Rate (decimal), n = Time Period in Years

### 3. Simple Interest
SI = P x r x t
Maturity Value = P + SI
- P = Principal, r = Rate (decimal), t = Time (years)

### 4. Compound Interest
A = P x (1 + r/n)^(nxt)
CI = A - P
- P = Principal, r = Annual Rate (decimal), n = Compounding freq/year, t = Time (years)

### 5. EMI
EMI = [P x r x (1 + r)^n] / [(1 + r)^n - 1]
- P = Loan Amount, r = Monthly rate = Annual Rate / 12 / 100, n = Tenure in months
- Total Payment = EMI x n
- Total Interest = Total Payment - P

### 6. Loan Amortization Schedule
- Interest = Opening Balance x Monthly Rate
- Principal Repaid = EMI - Interest
- Closing Balance = Opening Balance - Principal Repaid
- Final month: closing balance clamped to 0

### 7. Scenario Analysis
Compare FV, PV, EMI, Total Interest across 4 rates: 8%, 10%, 12%, 15%

## Implemented Features
- [x] Future Value Calculator
- [x] Present Value Calculator
- [x] Simple Interest Calculator
- [x] Compound Interest Calculator
- [x] EMI Calculator
- [x] Loan Amortization Schedule
- [x] Scenario Analysis (8%, 10%, 12%, 15%)
- [x] Input Validation (all calculators)
- [x] Reset buttons
- [x] Responsive design
- [x] Navigation between calculators
- [x] Error messages

## NEXT SESSION
Current state: Complete
Last completed task: Full application build
Remaining tasks: None
Next action: Open index.html in browser
