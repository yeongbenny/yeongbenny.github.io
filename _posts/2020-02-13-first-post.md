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

## CSS
CSS is a Cascading Style Sheets that decorates the HTML
and it uses <style>
 
## JavaScript
JavaScript is about all dynamic functions that happen on the web. It can go under the <script> section in html or can get in a separate .js file under a static folder when using Flask.
 
## jQuery
It is a library of JavaScript that could shorten the code. We can either use a link through CDN, or download jQuery file. 

# AJAX
AJAX is a shortened word for Asynchronous JavaScript and XML. This is important as it lets asynchronous communication possible between client and a server. Before AJAX, to change the contents of a website, users had to request another .html and required the entire reload process. By using AJAX, users can request or get data from the server without reloading.

## Web Socket
More advanced version of AJAX. It solves the problem that Server couldn’t start communicating unless they receive a request. Need to study more about this

## Web Server and Framework
Node.js, Flask, Django are all examples of web framework that helps developing, but to finally deploy they need to be integrated with Web Servers such as IIS or Apache. There are two ways data could be sent to the server. GET and POST. 
GET is sending via URL, and POST puts data in a packet body

## Email Code
While working on the email part of our plug-in , I used knowledge from above to build a simple webpage that automatically sends email to a certain user and below is the code.

<pre>
<code>
# importing libraries
from flask import Flask, render_template, request
from flask_mail import Mail, Message

app = Flask(__name__)
mail = Mail(app)  # instantiate the mail class

# configuration of mail
app.config['MAIL_SERVER'] = 'smtp.gmail.com'
app.config['MAIL_PORT'] = 465
app.config['MAIL_USERNAME'] = '*******'
app.config['MAIL_PASSWORD'] = '*******'
app.config['MAIL_USE_TLS'] = False
app.config['MAIL_USE_SSL'] = True
mail = Mail(app)

currentMail = 'zeroship1010@gmail.com'

# message object mapped to a particular URL ‘/’

@app.route("/")
def index():
    return render_template('index.html',currentHTML=currentMail)

@app.route("/email", methods=['POST'])
def email():
    currentMail = request.form['email_receiver']
    msg = Message(
        'another test',
        sender='zzaxex6@gmail.com',
        recipients=[currentMail]
    )
    msg.body = 'Hello Flask message sent from Flask-Mail'
    mail.send(msg)
    document = 'email sent to ' + msg.recipients[0]
    return document


if __name__ == '__main__':
    app.run(debug=True)

<code>
</pre>
* * * 
<pre>
<code>
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
</code>
</pre>

* * *

## Actual Practice on Web

https://code.tutsplus.com/ko/tutorials/creating-a-web-app-from-scratch-using-python-flask-and-mysql--cms-22972

My upcoming plan is to go through all these lectures to realize an actual web application with server and database


