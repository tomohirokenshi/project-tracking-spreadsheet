# Project Tracking Spreadsheet
**Spreadsheet:** https://docs.google.com/spreadsheets/d/1V0G2ypi-pR9ef26P9t21bUwNcEN2ffM7/edit?usp=sharing&ouid=102572395607281394456&rtpof=true&sd=true

During my internship, I developed a project tracking spreadsheet to assist the company’s Construction Technical Assistant. This tool was designed to monitor the progress of ongoing projects and ensure tasks stayed on schedule. In the construction industry, where time is critical and schedules are tight, any delays in completing tasks can lead to significant costs. Therefore, adhering to deadlines and completing tasks on time is essential. <br>

The Construction Technical Assistant plays a vital role in this process by providing comprehensive technical analyses and reports on construction projects. They ensure adherence to regulations and standards while supporting strategic decision-making. This spreadsheet was a valuable resource in helping them track project timelines, identify potential delays, and take proactive measures to keep projects running smoothly.

## Formula
The formula is structured with nested IF statements and evaluates different combinations of conditions to determine the output: <br> <br>
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

## Formula Explanation
**Condition 1: AND(ISBLANK($J11), $C$5 > L$10, NOT(L$10 <= $D11), NOT(AND(L$10 >= $D11, L$10 <= $E11))), 3** <br>
Output: 3 (Red) → The task is overdue because it’s past the schedule date (L$10) but doesn’t meet the criteria for being on track.
<br> <br>
**Condition 2: AND($C$5 > L$10, NOT(L$10 > $J11), NOT(L$10 <= $D11), NOT(AND(L$10 >= $D11, L$10 <= $E11))), 3** <br>
Output: 3 (Red) → The task is overdue for similar reasons as Condition 1, but this condition ensures it accounts for tasks with a completion date.
<br> <br>
**Condition 3: AND(ISBLANK($J11), L$10 >= $D11, L$10 <= $E11), 1** <br>
Output: 1 (Green) → The task is on track because it’s within the valid schedule range.
<br> <br>
**Condition 4: AND(L$10 >= $D11, L$10 <= $J11), 1** <br>
Output: 1 (Green) → The task is on track because it was completed on time.
<br> <br>
**Default Condition (Else): 2** <br>
If none of the above conditions are met, the formula outputs 2 (White). <br>
This indicates that the task is not included in the evaluation or doesn’t meet any of the criteria for "on track" or "overdue."

## Reflections
The project allowed me to bridge the gap between theoretical knowledge and practical application. By creating a Gantt chart spreadsheet, I gained hands-on experience with designing tools that address specific needs, such as monitoring project progress and maintaining strict schedules. This reinforced my understanding of logical workflows, time management, and how seemingly small delays can have a significant impact on a project's success.
<br> <br>
Throughout the process, I enhanced my skills in Excel, including advanced commands, and conditional formatting. These tools not only streamlined data processing but also allowed me to deliver a solution that was both efficient and user-friendly.
<br> <br>
Working closely with the Construction Technical Assistant gave me insight into how tools like this directly impact day-to-day operations. Understanding their pain points and incorporating feedback into the spreadsheet design was a crucial part of the process, teaching me the importance of collaboration and adaptability.
<br> <br>
Finally, this project gave me a glimpse into the fast-paced nature of the construction industry, where time is a critical resource. By contributing a tool that helped streamline their operations, I gained a sense of fulfillment and confidence in my ability to deliver practical solutions that make a tangible difference.
