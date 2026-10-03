# Student Grade Calculator

A beginner Python project by **Thu Kha Pyeit Sone Kyaw (Baron)** that calculates a student's average from three test scores, assigns a letter grade, and displays pass/fail status.

## What it does

- Accepts a student name and three equally weighted scores.
- Accepts integer or decimal scores from 0 to 100.
- Rejects scores outside that range and prompts again.
- Handles non-numeric and empty score input without ending the program.
- Displays the average rounded to two decimal places, the letter grade, and pass/fail status.

## Grading rules

| Average | Grade | Status |
| --- | --- | --- |
| 80 to 100 | A | Pass |
| 70 to below 80 | B | Pass |
| 60 to below 70 | C | Pass |
| 50 to below 60 | D | Pass |
| Below 50 | F | Fail |

The grade and pass/fail status are based on the **unrounded** average. Only the displayed average is rounded. These are the grading rules defined for this project.

## How to run

You need Python 3 and Jupyter Notebook or JupyterLab. The calculator itself uses only built-in Python functions.

1. Download the repository files into one folder.
2. Open a terminal in that folder and run `jupyter notebook`, or open the notebook through your existing Jupyter installation.
3. Open `Student_Grade_Calculator.ipynb`.
4. Select the Python code cell and press **Shift + Enter**.
5. Enter the student name and three scores when prompted.

For Jupyter installation instructions, see the [official Jupyter installation guide](https://jupyter.org/install).

## Example run

```text
Student Grade Calculator
Enter student name: Baron
Enter score 1: 85
Enter score 2: 72
Enter score 3: 90

----- Result -----
Student: Baron
Average: 82.33
Grade: A
Status: Pass
```

## Testing

The notebook's actual Python code was checked with **24 input scenarios**, including each grade boundary, minimum and maximum scores, decimal scores, invalid values, and repeated invalid entries. All 24 checks passed after the status-display fix.

See [TEST_CASES.md](TEST_CASES.md) for expected and actual results. The checks used simulated user input to execute the Python code and capture its output.

A regression check confirmed that passing students previously had no status line. Moving the status print statement outside the `else` block makes both Pass and Fail visible.

## What I practiced

- Functions and loops for repeated input validation
- Conditional statements for grading
- `try` / `except ValueError` for invalid numeric input
- Checking boundary values and comparing expected and actual output
- Finding and correcting an indentation bug

## Current scope

The calculator processes one student and three equally weighted scores per run. It displays results in Jupyter; it does not store a student database.

## Files

| File | Purpose |
| --- | --- |
| `Student_Grade_Calculator.ipynb` | Calculator code and a saved example output |
| `README.md` | Project overview and run instructions |
| `TEST_CASES.md` | Input scenarios with expected and actual results |
