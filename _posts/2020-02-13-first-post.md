---
title: "Welcome to Jekyll!"
date: 2020-02-13 19:21:28 -0400
categories: jekyll update
---

My task during People Space Bad Print’s project was to create a frontend plugin that works on top of OctoPrint. 
Our plugin’s final purpose is to execute video analysis via communication through the machine learning server and manufacture the JSON result into a visualize gauge model to show the status of a 3d printer in real time. 
We chose to add other options such as giving direct email notice when spaghetti happens and a ‘STOP’ button that can actually stop the 3d printer remotely. 

In order to create all these functions, knowledge about WEB was crucial. Creating plugin, materializing UI, communication with server all required WEB skills, but the problem was that I have very shallow understanding about this.
Furthermore, this project was about creating a plugin on other people’s work (Octoprint, theSpaghettiDetective), which made it even more difficult to get started with for a person like me.
Hence, I spent quite a long time studying these, and this article is going to be about the final summarization about the WEB i studied during the past few weeks. 

### WEB Study Summarization

1. HTML
2. CSS
3. JAVASCRIPT
4. JQUERY 
5. AJAX
6. Web Socket
7. Web Server (GET, POST)
8. email code
9. Actual Practice on Web

## HTML
HTML is a markup language that consists of the basis of a webpage. It has a certain format 
this is the example of the index.html page that I created while practicing. Under <script> goes JavaScript grammer.

<!doctype html>
<html>

<head>
Current E-mail : {{currentHTML}}
</head>

<body>

<script>
function button1_click(){
alert("you pressed button");
}
</script>

 <h1>Email System</h1>

 <h1>{{ content }}</h1>

   <dt>Email_Receiver:</dt>


<form action="/email" method="post">

   <dd>
    <input type="text" name=email_receiver value="" />
   </dd>
<input type = "submit" value = "apply">

</form>

</body>

</html>
