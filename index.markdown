<div id="sortableTrash" class="sortable-code"></div> 
<div id="sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="feedbackLink" value="Get Feedback" type="button" /> 
    <input id="newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<script type="text/javascript"> 
(function(){
  var initial = "print(&quot;Welcome to the \&quot;Have a Great Day!\&quot; Program&quot;)\n" +
    "import datetime\n" +
    "year = int(input(&quot;What year (####) were you born? &quot;))\n" +
    "month = int(input(&quot;What month were you born (1-12)? &quot;))\n" +
    "day = int(input(&quot;What day were you born (1-31)? &quot;))\n" +
    "myDate = datetime.datetime(year, month, day)\n" +
    "today = datetime.datetime.today()\n" +
    "if myDate.month == today.month and myDate.day == today.day:\n" +
    "	print(&quot;HAPPY BIRTHDAY and have a GREAT DAY!&quot;)\n" +
    "else:\n" +
    "	print(&quot;Have a great day!&quot;)";
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
