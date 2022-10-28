---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: Multiple Parson's Problems on One Page
---
<div id="L1-sortableTrash" class="sortable-code"></div> 
<div id="L1-sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="L1-feedbackLink" value="Get Feedback" type="button" /> 
    <input id="L1-newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<script type="text/javascript"> 
(function(){
  var initial = "for i in range (0,3):\n" +
    "	print(&quot;F - In chat&quot;)\n" +
    "    ";
  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "L1-sortable",
    "max_wrong_lines": 10,
    "grader": ParsonsWidget._graders.LineBasedGrader,
    "exec_limit": 2500,
    "can_indent": true,
    "x_indent": 50,
    "lang": "en",
    "show_feedback": true
  });
  parsonsPuzzle.init(initial);
  parsonsPuzzle.shuffleLines();
  $("#L1-newInstanceLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.shuffleLines(); 
  }); 
  $("#L1-feedbackLink").click(function(event){ 
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
