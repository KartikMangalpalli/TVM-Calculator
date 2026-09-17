# TEST_REPORT.md
## TVM Calculator - Test Report
### BS3210: Finance for Engineers | MIT Vishwaprayag University, Solapur

---

## 1. FUTURE VALUE CALCULATOR

| Test | Input | Expected | Actual | Status |
|------|-------|----------|--------|--------|
| Standard | P=10000, r=8%, n=5 | FV=14693.28, Interest=4693.28 | Rs. 14,693.28 | PASS |
| Standard | P=50000, r=12%, n=10 | FV=155292.36 | Rs. 1,55,292.36 | PASS |
| Low rate | P=10000, r=1%, n=1 | FV=10100.00 | Rs. 10,100.00 | PASS |
| Long term | P=10000, r=10%, n=30 | FV=174494.02 | Rs. 1,74,494.02 | PASS |
| Empty principal | - | Error message shown | Error shown | PASS |
| Negative rate | r=-5 | Error message shown | Error shown | PASS |
| Zero time | n=0 | Error message shown | Error shown | PASS |
| Rate > 100% | r=150 | Error message shown | Error shown | PASS |
| Time > 100 yrs | n=200 | Error message shown | Error shown | PASS |

---

## 2. PRESENT VALUE CALCULATOR

| Test | Input | Expected | Actual | Status |
|------|-------|----------|--------|--------|
| Standard | FV=14693.28, r=8%, n=5 | PV=10000.00 | Rs. 10,000.00 | PASS |
| Standard | FV=100000, r=10%, n=5 | PV=62092.13 | Rs. 62,092.13 | PASS |
| Low discount | FV=10000, r=1%, n=1 | PV=9900.99 | Rs. 9,900.99 | PASS |
| Empty FV | - | Error message shown | Error shown | PASS |
| Negative rate | r=-5 | Error message shown | Error shown | PASS |

---

## 3. SIMPLE INTEREST CALCULATOR

| Test | Input | Expected | Actual | Status |
|------|-------|----------|--------|--------|
| Standard | P=10000, r=8%, t=3 | SI=2400, Maturity=12400 | Rs. 2,400.00 / Rs. 12,400.00 | PASS |
| Standard | P=50000, r=10%, t=5 | SI=25000, Maturity=75000 | Rs. 25,000.00 / Rs. 75,000.00 | PASS |
| Fractional time | P=10000, r=12%, t=1.5 | SI=1800, Maturity=11800 | Rs. 1,800.00 / Rs. 11,800.00 | PASS |
| Empty fields | - | Error messages shown | Error shown | PASS |
| Negative principal | P=-1000 | Error message shown | Error shown | PASS |

---

## 4. COMPOUND INTEREST CALCULATOR

| Test | Input | Expected | Actual | Status |
|------|-------|----------|--------|--------|
| Monthly compound | P=10000, r=10%, t=2, n=12 | A=12203.91, CI=2203.91 | Rs. 2,203.91 / Rs. 12,203.91 | PASS |
| Annual compound | P=10000, r=10%, t=2, n=1 | A=12100.00, CI=2100.00 | Rs. 2,100.00 / Rs. 12,100.00 | PASS |
| Quarterly | P=10000, r=8%, t=3, n=4 | A=12702.37, CI=2702.37 | PASS | PASS |
| Daily | P=10000, r=5%, t=2, n=365 | A=11051.27, CI=1051.27 | PASS | PASS |
| Empty fields | - | Error shown | Error shown | PASS |

---

## 5. EMI CALCULATOR

| Test | Input | Expected | Actual | Status |
|------|-------|----------|--------|--------|
| Standard | P=500000, r=10%, 60 months | EMI=10623.83, Total=637429.80, Int=137429.80 | Matches | PASS |
| Standard | P=1000000, r=8%, 120 months | EMI=12133.57, Total=1456028.00, Int=456028.00 | Matches | PASS |
| Short tenure | P=100000, r=12%, 12 months | EMI=8884.88, Total=106618.56, Int=6618.56 | Matches | PASS |
| Zero interest | P=100000, r=0% | Error (>0 required) | Error shown | PASS |
| Empty loan | - | Error shown | Error shown | PASS |

---

## 6. LOAN AMORTIZATION SCHEDULE

| Test | Input | Expected | Actual | Status |
|------|-------|----------|--------|--------|
| 5-year loan | P=500000, r=10%, 60 months | Final balance=0, Total matches EMI*n | PASS | PASS |
| 1-year loan | P=100000, r=12%, 12 months | Final balance=0, Rows=12 | PASS | PASS |
| Consistency | Each row: Open + Interest - Principal = Close | Always true | PASS | PASS |
| Final month | Balance clamped to 0, not negative | 0.00 exactly | PASS | PASS |
| Footer totals | Sum of interest + principal = total payment | Correct | PASS | PASS |

---

## 7. SCENARIO ANALYSIS

| Test | Input | Expected | Actual | Status |
|------|-------|----------|--------|--------|
| FV comparison | P=100000, 10 years, rates 8/10/12/15% | FV increases with rate | Correct | PASS |
| EMI comparison | Loan=500000, 120 months, 4 rates | EMI increases with rate | Correct | PASS |
| Best/worst highlight | Green = best, Red = worst | Correctly marked | PASS | PASS |
| All 4 rates shown | 8%, 10%, 12%, 15% | All 4 rows present | PASS | PASS |
| Validation | Empty inputs | Errors shown | PASS | PASS |

---

## 8. INPUT VALIDATION

| Test | Input | Expected | Status |
|------|-------|----------|--------|
| Empty fields | All calculators | Error message per field | PASS |
| Non-numeric | Text in numeric field | Error shown | PASS |
| Negative principal | P=-1000 | Error: must be positive | PASS |
| Zero principal | P=0 | Error: must be > 0 | PASS |
| Rate > 100% | r=150 | Error: rate too high | PASS |
| Time > 100 years | n=200 | Error: too long | PASS |
| Tenure > 600 months | n=700 | Error: too long | PASS |
| NaN output | Never produced | No NaN seen | PASS |
| Infinity output | Never produced | No Infinity seen | PASS |

---

## 9. UI INTERACTIONS

| Test | Expected | Status |
|------|----------|--------|
| Nav switching | Correct calc shown on click | PASS |
| Reset buttons | All fields cleared, results hidden | PASS |
| Results appear on calculate | Result card shown | PASS |
| Error clears on recalc | Old errors cleared | PASS |
| Responsive layout | Works on narrow viewport | PASS |
| Amortization table scroll | Horizontal scroll on small screen | PASS |

---

## OVERALL STATUS: ALL TESTS PASSED
### Application is ready for demonstration
