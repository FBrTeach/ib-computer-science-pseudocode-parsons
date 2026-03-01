---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: Multiple Parson's Problems on One Page
---
<style>
  table {
    border-collapse: collapse;
    margin-bottom: 20px;
  }
  th, td {
    border: 1px solid black !important;
    padding: 8px;
    text-align: center;
  }
</style>

# 2025 May Question 13c
A team of four high-school students decided to create a computer program for younger students to help them learn to count and recognize whole numbers from 1 to 25.

A table partially completed with numbers from 1 to 25 is given to a younger student. The table consists of five rows and five columns (see **Figure 2**). The younger student must enter the remaining numbers. Each number from 1 to 25 should be entered only once.

**Figure 2: Example table partially filled with numbers**

| | | | | |
| :---: | :---: | :---: | :---: | :---: |
| | 24 | 1 | | |
| | | 7 | 14 | |
| 4 | 6 | | | 22 |
| 10 | | | 21 | 3 |
| 11 | | 25 | | 9 |

In the program, the table is stored as a static two-dimensional array.

**Figure 3: Two examples of data**

<div style="display: flex; gap: 40px; flex-wrap: wrap;">

<div style="flex: 1; min-width: 300px;">

**Figure 3a:** The two-dimensional array is correctly completed because each of the numbers from 1 to 25 appears only once.

| | [0] | [1] | [2] | [3] | [4] |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **[0]** | 2 | 24 | 1 | 8 | 15 |
| **[1]** | 23 | 5 | 7 | 14 | 16 |
| **[2]** | 4 | 6 | 13 | 20 | 22 |
| **[3]** | 10 | 12 | 19 | 21 | 3 |
| **[4]** | 11 | 18 | 25 | 17 | 9 |

</div>

<div style="flex: 1; min-width: 300px;">

**Figure 3b:** The two-dimensional array is not correctly completed because the number 17 is missing and the number 12 appears twice.

| | [0] | [1] | [2] | [3] | [4] |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **[0]** | **12** | 24 | 1 | 8 | 15 |
| **[1]** | 23 | 5 | 7 | 14 | 16 |
| **[2]** | 4 | 6 | 13 | 20 | 22 |
| **[3]** | 10 | **12** | 19 | 21 | 3 |
| **[4]** | 11 | 18 | 25 | 2 | 9 |

</div>

</div>

<br>

The sub-program `isCorrectlyCompleted(MAT)` accepts the two-dimensional array `MAT` and outputs an appropriate message to indicate if it has been correctly filled.

For example:

If `MAT` is the two-dimensional array shown in **Figure 3a**, then `isCorrectlyCompleted(MAT)` should output that the table has been correctly completed.

If `MAT` is the two-dimensional array shown in **Figure 3b** then `isCorrectlyCompleted(MAT)` should output that the table has **not** been correctly completed.

---

The description of the algorithm for the `isCorrectlyCompleted(MAT)` sub-program is as follows:
* Initialize a one-dimensional array, `FLAGS`, with zero (0) values.
* Visit all elements of the `MAT` array.
    * Use the number stored in the `MAT` array to match up the index in the `FLAGS` array.
    * Assign one (1) to the `FLAGS` array at that index.
* Inspect elements of the `FLAGS` array.
    * If all the elements in the `FLAGS` array are one (1), output a message saying that the table has been completed correctly; otherwise, output a message saying that the table has not been completed correctly.

For example, the `FLAGS` array for the `MAT` array shown in **Figure 3a** is:

| [0] | [1] | [2] | [3] | [4] | [5] | [6] | [7] | [8] | [9] | [10] | [11] | [12] | [13] | [14] | [15] | [16] | [17] | [18] | [19] | [20] | [21] | [22] | [23] | [24] |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 |

And the `FLAGS` array for the `MAT` array shown in **Figure 3b** is:

| [0] | [1] | [2] | [3] | [4] | [5] | [6] | [7] | [8] | [9] | [10] | [11] | [12] | [13] | [14] | [15] | [16] | [17] | [18] | [19] | [20] | [21] | [22] | [23] | [24] |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 | **0** | 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 |
<div id="q13c-sortableTrash" class="sortable-code"></div> 
<div id="q13c-sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="q13c-feedbackLink" value="Get Feedback" type="button" /> 
    <input id="q13c-newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<script type="text/javascript"> 
(function(){
  var initial = "isCorrectlyCompleted(MAT)\n" +
    "    // Initializing the FLAGS array\n" +
    "    loop K from 0 to 24\n" +
    "        FLAGS[K] = 0\n" +
    "    end loop\n" +
    "\n" +
    "    // Mapping MAT values to FLAGS indices\n" +
    "    loop R from 0 to 4\n" +
    "        loop C from 0 to 4\n" +
    "            INDEX = MAT[R][C] - 1\n" +
    "            FLAGS[INDEX] = 1\n" +
    "        end loop\n" +
    "    end loop\n" +
    "\n" +
    "    // Inspecting the FLAGS array\n" +
    "    F = true\n" +
    "    loop K from 0 to 24\n" +
    "        if FLAGS[K] = 0 then\n" +
    "            F = false\n" +
    "        end if\n" +
    "    end loop\n" +
    "\n" +
    "    if F then\n" +
    "        output('the table has been correctly completed')\n" +
    "    else\n" +
    "        output('the table has not been correctly completed')\n" +
    "    end if\n" +
    "end isCorrectlyCompleted";

  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "q13c-sortable",
    "trashId": "q13c-sortableTrash",
    "max_wrong_lines": 10,
    "grader": ParsonsWidget._graders.LineBasedGrader,
    "exec_limit": 2500,
    "can_indent": true,
    "x_indent": 50,
    "lang": "en",
    "show_feedback": true,
    "python3": true
  });
  
  parsonsPuzzle.init(initial);
  parsonsPuzzle.shuffleLines();
  
  jQuery("#q13c-newInstanceLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.shuffleLines(); 
  }); 
  jQuery("#q13c-feedbackLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.getFeedback(); 
  }); 
})(); 
</script>

### Implementation Notes

When you host multiple Parson's problems on a single markdown page, you need to add a unique prefix. You can easily do this in the Codio generator by typing a unique prefix into the "Prefix" textbox and pressing Enter/Return. Then you can simply copy-paste like normal.

If want each problem to be it's own page, you can use relative path links at the bottom of each of your markdown pages as seen below. If you want students to be able to return to previous problems in this format, consider adding previous links or link to a table of contents like page.

### Example Next Link
[Next](./parsons/example1.html)
