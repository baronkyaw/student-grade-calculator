# Calculator Test Cases

Checked on **3 October 2026** using Python **3.12.14**.

**Result: 24 of 24 scenarios passed.**

The checks execute the actual Python code from `Student_Grade_Calculator.ipynb` with simulated user input. Each check compares independently specified average, grade, status, validation-message counts, and prompt order against the captured result.

Student name: `Baron` in every scenario. Outcomes below use **average / grade / status**. Invalid entries are followed by replacement values for the same score. "Range messages" means the 0-100 warning; "numeric messages" means the valid-number warning.

| ID | Scenario | Score inputs | Expected | Actual | Result |
| --- | --- | --- | --- | --- | --- |
| T01 | Typical A result | 85, 72, 90 | 82.33 / A / Pass | 82.33 / A / Pass | Pass |
| T02 | Typical B result | 75, 75, 75 | 75 / B / Pass | 75 / B / Pass | Pass |
| T03 | Typical C result | 65, 65, 65 | 65 / C / Pass | 65 / C / Pass | Pass |
| T04 | Typical D result | 55, 55, 55 | 55 / D / Pass | 55 / D / Pass | Pass |
| T05 | Typical failing result | 40, 40, 40 | 40 / F / Fail | 40 / F / Fail | Pass |
| T06 | A boundary | 80, 80, 80 | 80 / A / Pass | 80 / A / Pass | Pass |
| T07 | Just below A | 79.99, 79.99, 79.99 | 79.99 / B / Pass | 79.99 / B / Pass | Pass |
| T08 | B boundary | 70, 70, 70 | 70 / B / Pass | 70 / B / Pass | Pass |
| T09 | Just below B | 69.99, 69.99, 69.99 | 69.99 / C / Pass | 69.99 / C / Pass | Pass |
| T10 | C boundary | 60, 60, 60 | 60 / C / Pass | 60 / C / Pass | Pass |
| T11 | Just below C | 59.99, 59.99, 59.99 | 59.99 / D / Pass | 59.99 / D / Pass | Pass |
| T12 | D and pass boundary | 50, 50, 50 | 50 / D / Pass | 50 / D / Pass | Pass |
| T13 | Just below pass | 49.99, 49.99, 49.99 | 49.99 / F / Fail | 49.99 / F / Fail | Pass |
| T14 | Minimum valid scores | 0, 0, 0 | 0 / F / Fail | 0 / F / Fail | Pass |
| T15 | Maximum valid scores | 100, 100, 100 | 100 / A / Pass | 100 / A / Pass | Pass |
| T16 | Decimal scores | 82.5, 74.25, 69.75 | 75.5 / B / Pass | 75.5 / B / Pass | Pass |
| T17 | Score above range | Score 1: 120 then 85; score 2: 72; score 3: 90 | 82.33 / A / Pass; range messages: 1; numeric messages: 0 | 82.33 / A / Pass; range messages: 1; numeric messages: 0 | Pass |
| T18 | Negative score | Score 1: -1 then 80; scores 2 and 3: 80 | 80 / A / Pass; range messages: 1; numeric messages: 0 | 80 / A / Pass; range messages: 1; numeric messages: 0 | Pass |
| T19 | Non-numeric score | Score 1: abc then 60; scores 2 and 3: 60 | 60 / C / Pass; range messages: 0; numeric messages: 1 | 60 / C / Pass; range messages: 0; numeric messages: 1 | Pass |
| T20 | Empty score | Score 1: empty then 50; scores 2 and 3: 50 | 50 / D / Pass; range messages: 0; numeric messages: 1 | 50 / D / Pass; range messages: 0; numeric messages: 1 | Pass |
| T21 | Repeated invalid entries | Score 1: 110, -10, oops, empty, then 80; score 2: 70; score 3: 60 | 70 / B / Pass; range messages: 2; numeric messages: 2 | 70 / B / Pass; range messages: 2; numeric messages: 2 | Pass |
| T22 | Invalid second score | Score 1: 80; score 2: 101 then 70; score 3: 60 | 70 / B / Pass; range messages: 1; numeric messages: 0 | 70 / B / Pass; range messages: 1; numeric messages: 0 | Pass |
| T23 | Invalid third score | Score 1: 80; score 2: 70; score 3: text then 60 | 70 / B / Pass; range messages: 0; numeric messages: 1 | 70 / B / Pass; range messages: 0; numeric messages: 1 | Pass |
| T24 | Unequal scores at pass boundary | 0, 100, 50 | 50 / D / Pass | 50 / D / Pass | Pass |

## Regression check

Before the fix, entering 85, 72, and 90 produced average 82.33 and grade A, but no status line. The corrected code also prints `Status: Pass`. The status print statement now runs after either status has been assigned.

## Coverage

These checks cover the calculator logic and text output. The notebook retains a saved example run. Browser interaction in Jupyter was not automated.
