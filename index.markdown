---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: Multiple Parson's Problems on One Page
---
# 2025 May Question 13c

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
  
  $("#q13c-newInstanceLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.shuffleLines(); 
  }); 
  $("#q13c-feedbackLink").click(function(event){ 
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
