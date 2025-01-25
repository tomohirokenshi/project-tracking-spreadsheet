# Project Tracking Spreadsheet
**Spreadsheet:** https://docs.google.com/spreadsheets/d/1V0G2ypi-pR9ef26P9t21bUwNcEN2ffM7/edit?usp=sharing&ouid=102572395607281394456&rtpof=true&sd=true

During my internship, I developed a project tracking spreadsheet to assist the company’s Construction Technical Assistant. This tool was designed to monitor the progress of ongoing projects and ensure tasks stayed on schedule. In the construction industry, where time is critical and schedules are tight, any delays in completing tasks can lead to significant costs. Therefore, adhering to deadlines and completing tasks on time is essential. <br>

The Construction Technical Assistant plays a vital role in this process by providing comprehensive technical analyses and reports on construction projects. They ensure adherence to regulations and standards while supporting strategic decision-making. This spreadsheet was a valuable resource in helping them track project timelines, identify potential delays, and take proactive measures to keep projects running smoothly.

## Formula
The formula is structured with nested IF statements and evaluates different combinations of conditions to determine the output: <br>
=IF(AND(ISBLANK($J11), $C$5>L$10, NOT(L$10<=$D11), NOT(AND(L$10>=$D11, L$10<=$E11))), 3, IF(AND($C$5>L$10, NOT(L$10>$J11), NOT(L$10<=$D11), NOT(AND(L$10>=$D11, L$10<=$E11))), 3, IF(AND(ISBLANK($J11), L$10>=$D11, L$10<=$E11), 1, IF(AND(L$10>=$D11, L$10<=$J11), 1, 2))))

## Variables
1. **$J11:** The completion date of the task.
2. **$C$5:** The current date or a reference point for the current date.
3. **L$10:** The specific scheduled date is being evaluated. Based on the evaluation, it assigns a value (1, 2, or 3) that corresponds to specific outputs
4. **$D11:** The start date of the task.
5. **$E11:** The due date of the task.

## Outputs
* **1 (Green):** The task is on track and meeting its deadline.
* **2 (White):** The task is not included or doesn’t need evaluation.
* **3 (Red):** The task is overdue.

**Condition 1: AND(ISBLANK($J11), $C$5 > L$10, NOT(L$10 <= $D11), NOT(AND(L$10 >= $D11, L$10 <= $E11))), 3**
Output: 3 (Red) → The task is overdue because it’s past the schedule date (L$10) but doesn’t meet the criteria for being on track.
<br>
**Condition 2: AND($C$5 > L$10, NOT(L$10 > $J11), NOT(L$10 <= $D11), NOT(AND(L$10 >= $D11, L$10 <= $E11))), 3**
Output: 3 (Red) → The task is overdue for similar reasons as Condition 1, but this condition ensures it accounts for tasks with a completion date.
<br>
**Condition 3: AND(ISBLANK($J11), L$10 >= $D11, L$10 <= $E11), 1**
Output: 1 (Green) → The task is on track because it’s within the valid schedule range.
<br>
**Condition 4: AND(L$10 >= $D11, L$10 <= $J11), 1**
Output: 1 (Green) → The task is on track because it was completed on time.
<br>
**Default Condition (Else): 2**
If none of the above conditions are met, the formula outputs 2 (White).
This indicates that the task is not included in the evaluation or doesn’t meet any of the criteria for "on track" or "overdue."
