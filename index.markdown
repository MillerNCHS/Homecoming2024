<div id="sortableTrash" class="sortable-code"></div> 
<div id="sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="feedbackLink" value="Get Feedback" type="button" /> 
    <input id="newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<script type="text/javascript"> 
(function(){
  var initial = "color = input(&quot;What color are you wearing today?&quot;).lower()\n" +
    "if (color == &quot;red&quot;):\n" +
    "	print(&quot;You are a freshman.&quot;)\n" +
    "elif (color == &quot;purple&quot;):\n" +
    "	print(&quot;You are a sophomore.&quot;)\n" +
    "elif (color == &quot;orange&quot;):\n" +
    "	print(&quot;You are a junior.&quot;)\n" +
    "else:\n" +
    "	print(&quot;You are a senior.&quot;)";
  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "sortable",
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
  $("#newInstanceLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.shuffleLines(); 
  }); 
  $("#feedbackLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.getFeedback(); 
  }); 
})(); 
</script>
