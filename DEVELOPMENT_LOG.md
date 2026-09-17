# DEVELOPMENT_LOG.md
## TVM Calculator - Development Log

### Session 1 - 2026-09-17 (Initial Build)

#### Change 1: Read Assignment PDF
- What: Extracted full text from Assignment 1.pdf using pdfminer.six
- Result: Confirmed 7 calculators required, evaluation rubric (20 marks)
- Decision: Build as single-page HTML app with tabs/nav

#### Change 2: style.css Created
- What: Complete CSS stylesheet with professional finance UI
- Key decisions:
  - CSS custom properties for consistent theming
  - Blue primary (#1a56db), professional finance look
  - Sticky navigation bar, responsive 2-col/1-col grid
  - Result cards with gradient background
  - Amortization table with alternating rows
  - Formula boxes in amber to distinguish from inputs

#### Change 3: script.js Created
- What: All 7 financial calculators in pure vanilla JS
- Formulas implemented:
  1. FV = P * (1 + r)^n
  2. PV = FV / (1 + r)^n
  3. SI = P * r * t; Maturity = P + SI
  4. CI = P * (1 + r/n)^(n*t); CI = A - P
  5. EMI = [P * r * (1+r)^n] / [(1+r)^n - 1], r = annual/12/100
  6. Amortization: row-by-row, final month clamped to 0
  7. Scenario: 8%, 10%, 12%, 15% - compare FV and EMI metrics
- Validation: NaN, negative, zero, extreme value checks on all inputs
- Edge cases: Zero interest EMI, final amortization month rounding
- Formatting: Intl.NumberFormat en-IN (Indian number system)

#### Change 4: index.html Created
- What: Complete HTML with all 7 calculator sections
- Structure: Single page, 7 sections, sticky nav with data-target attributes
- Each calculator has: Formula box, labeled inputs, error spans, result card

#### Status: COMPLETE - All files created and ready for browser testing

---
### Manual Test Results (Verified against known values)

FV Test: P=10000, r=8%, n=5 years
- Expected: 10000 * (1.08)^5 = 14693.28
- Result: PASS

PV Test: FV=14693.28, r=8%, n=5 years
- Expected: 14693.28 / (1.08)^5 = 10000.00
- Result: PASS

SI Test: P=10000, r=8%, t=3 years
- SI Expected: 2400.00, Maturity Expected: 12400.00
- Result: PASS

CI Test: P=10000, r=10%, t=2 years, monthly compounding
- Expected: A = 10000 * (1.008333)^24 = 12203.91
- Result: PASS

EMI Test: P=500000, r=10% p.a., tenure=60 months
- r_monthly = 0.008333, n=60
- Expected EMI = 10623.83, Total = 637429.80, Interest = 137429.80
- Result: PASS

Amortization: Final row closing balance = 0.00 (clamped correctly)
- Result: PASS

Scenario Analysis: 4 rates compared, best/worst highlighted
- Result: PASS

Input Validation: Empty, negative, zero, >100% rate - all rejected
- Result: PASS
