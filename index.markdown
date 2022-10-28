Skip to content
Search or jump to…
Pull requests
Issues
Marketplace
Explore
 
@MrVanD 
courtneylee0610
/
pygame_parsons
Public
forked from codio-content/hosting-parsons-on-github-template
Code
Pull requests
Actions
Projects
Security
Insights
pygame_parsons/index.markdown
@courtneylee0610
courtneylee0610 Removed examples
Latest commit 7552ee0 yesterday
 History
 3 contributors
@edeitrick@ksimuk@courtneylee0610
63 lines (56 sloc)  2.12 KB

---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: Multiple Parson's Problems on One Page
---
# PyGame Zero Parsons Puzzles

Re-arrange the code into the correct order to achieve each task.

## Colliding Objects
Create a program that:
1. Checks to see if the tank1 bullet is touching tank2
    2. If it is, changes location of tank2 to a random place on the screen
    3. Set the bullet from tank1 to inactive
    4. Increase the score of tank1 by 1 point

<div id="CollideRect-sortableTrash" class="sortable-code"></div> 
<div id="CollideRect-sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="CollideRect-feedbackLink" value="Get Feedback" type="button" /> 
    <input id="CollideRect-newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<script type="text/javascript"> 
(function(){
  var initial = "if tank1_bullet.colliderect(tank2):\n" +
    "	tank2.pos = (random.randint(50, 250), random.randint(50, HEIGHT - 50))\n" +
    "	tank1_bullet.isActive = False         \n" +
    "	tank1.score += 1\n" +
    "tank1_bullet.isActive = True #distractor\n" +
    "tank2.score += 1 #distractor\n" +
    "tank1.pos = (random.randint(50, 250), random.randint(50, HEIGHT - 50)) #distractor\n" +
    "if tank1_bullet.colliderect(tank1): #distractor";
  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "CollideRect-sortable",
    "max_wrong_lines": 10,
    "grader": ParsonsWidget._graders.LineBasedGrader,
    "exec_limit": 2500,
    "can_indent": true,
    "x_indent": 50,
    "lang": "en",
    "show_feedback": true,
    "trashId": "CollideRect-sortableTrash"
  });
  parsonsPuzzle.init(initial);
  parsonsPuzzle.shuffleLines();
  $("#CollideRect-newInstanceLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.shuffleLines(); 
  }); 
  $("#CollideRect-feedbackLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.getFeedback(); 
  }); 
})(); 
</script>
      
### Example Next Link
[Next](./parsons/example1.html)
      

Footer
© 2022 GitHub, Inc.
Footer navigation
Terms
Privacy
Security
Status
Docs
Contact GitHub
Pricing
API
Training
Blog
About
pygame_parsons/index.markdown at master · courtneylee0610/pygame_parsons
