12. JQuery Syntax
JQuery syntax is fairly similar to JavaScript syntax seeing as it is a library of JavaScript, however
there are a couple noticeable differences. JQuery requires the use of “$” symbol, to indicate to the
website that we want to use the JQuery library functions and methods. This ensures that the
website will know which file to look in for the appropriate code we are calling.
Client-Side Scripting: JavaScript and JQuery | Evening Course | 2016 © Friends of Design - Academy of Digital Arts
41Client-Side Scripting: JavaScript and JQuery | Class Notes
We can write jQuery on an HTML page, much like we write embedded CSS. We need to use a
<script> tag for this process and write any jQuery with in that <script> tag.
<script>
$(selector).method();
</script>
Anything in “$(brackets)” is known as the selector. The selector queries or finds HTML elements, like
classes, id’s and tags, the.”.action();” lastly we have what is known as the jQuery method or action -
in other words, what should be performed on the element selected.
It should be noted that if you are targeting a <p> or a css .class they must be written with “”, the
angle brackets must be removed from the <p> and the css class must be written as if you had
written it in a stylesheet.
Selecting a HTML elements by Tag name
$(“p”).method();
Selecting a HTML elements by Class name
$(“.container”).method();
Selecting a HTML elements by ID name
$(“#myId”).method();
The only time you don’t need quotes around a selector is when the selector is part of the jQuery
function, like a variable. Its also worth noting that you can add your jQuery in a separate file.
Rather than embedded in your HTML file - create a functions.js file in a folder named js in the root
of your website and link it to your document. ​
(Please note, the name of the can be anything you feel is
appropriate to call it i.e. menu-actions.js or menu-functions.js, etc.)
<script src=”js/functions.js”></script>
Document Ready Function
The document ready function is a special function in jQuery that holds on to executing the jQuery
code until the entire DOM is loaded.
$(document).ready(function(){
//my code goes here
Client-Side Scripting: JavaScript and JQuery | Evening Course | 2016 © Friends of Design - Academy of Digital Arts
42Client-Side Scripting: JavaScript and JQuery | Class Notes
});
The Document ready function prevents any jQuery from running before the entire document is
finished loading or is “ready”. It is considered good practice to do this and you can run as many
functions as you like with in this code block - the code block is anything or rather the code that gets
executed when jQuery calls the functions and is always contained within the parentheses.
A shorthand for the document.ready function can be written as follows.
$(function(){
//my code goes here
});
jQuery Selectors
Examine the following block of code.
$(document).ready(function(){
$(“button”).click(function(){
$(“p”).hide();
});
});
Breaking it down line for line we can decipher exactly what the code block is attempting to do.
$(document).ready(function(){
The first line as we know, tells jQuery to load only when the rest of DOM (HTML and CSS) has
loaded.
$(“button”).click(function(){
The second line looks quite similar to the first except it exists within the Document Ready Function.
When the document is ready, begin jQuery, then find all HTML elements called <button>, when that
button is clicked we would like to execute a function that will find all <p> tags and hide them. Close
instruction, close instruction” We can use simple syntax that will be pretty familiar to you with CSS.
$(“button”).click(function(){
Client-Side Scripting: JavaScript and JQuery | Evening Course | 2016 © Friends of Design - Academy of Digital Arts
43Client-Side Scripting: JavaScript and JQuery | Class Notes
Is looking for all the HTML <button> elements.
$(“.sidebar”).click(function(){
Is looking for an element with the class of “sidebar”.
$(“#tweet”).click(function(){
Is looking for an element with the ID of ”tweet”. There are a variety of Query selectors that can be
used.
● $(“*”) - finds all elements like the universal selector in CSS.
● $(this) - will selects the current HTML element interacted with, either by the code or by the
user.
$(document).ready(function(){
$(“button”).click(function(){
$(“this”).hide();
});
});
● $(“p.intro”) - Will select any paragraph with the class of “intro”.
● $(“[href]”) - this will select all elements with an href attribute.
jQuery Events
An event is used when a visitor can respond to action, like a click or double click, or maybe a key
down action performed by the user, even scrolling can be identified and thus call a function when
the event of scrolling takes place. One of the most basic events is the “ready” event.
$(document).ready(function(){
// my code goes here
});
Once the document is “ready” or rather done loading, we can call a function inside the “ready”
event. Apart from the “ready” event we can ask JQuery to listen for events that occur from the
user's interactions. Clicking on a link for example.
$(“a”).click();
Client-Side Scripting: JavaScript and JQuery | Evening Course | 2016 © Friends of Design - Academy of Digital Arts
44Client-Side Scripting: JavaScript and JQuery | Class Notes
This means that we can do something when the user clicks on any HTML <a> tag element. Once we
have identified an event has taken place, we can add functions to event to be executed when the
event occurs. The code below shows a “document ready” event, which will listen for a user’s click
event. If the user clicks a HTML <a> tag element, we execute code which will make the something
occur on the website or in the system.
$(document).ready(function(){
$(“a”).click(function(){
//something needs to happen!
});
});
Below is added code to be executed when the user clicks on a HTML <a> tag element. The code
below will cause the link that is clicked to be hidden using the JQuery “.hide()” method.
$(document).ready(function(){
$(“a”).click(function(){
$(this).hide();
});
});
JQuery Effects
They are simple effects that can manipulate DOM elements. Commonly used effects are:
● hide
● show
● toggle
● slide
● fade
● animate
Let us take a look at this example - you would right it with an event within a document ready
function, I will write it by itself and then with all the code necessary to get it to work:
$(“p”).hide();
Client-Side Scripting: JavaScript and JQuery | Evening Course | 2016 © Friends of Design - Academy of Digital Arts
45Client-Side Scripting: JavaScript and JQuery | Class Notes
Will hide all p’s - but if we had that inside of our document ready function as soon as the page
loaded, all the <p> HTML tags would disappear. We could instead have this function occur in a user
event like a click function.
$(“button.goaway”).click(function(){
$(“p”).hide();
});
When a user clicks on the button with the class of “ ​
goaway ​
”, all <p> HTML elements must
disappear. With effects or methods we can also have what are known as “ ​
parameters ​
” These are
simple additions to effects that provide more detailed information.
$(button.goaway).click(function(){
$(“p”).hide(“slow”)
// or we could have $(“p”).hide(1000);
});
The speed parameter in this case can use a keyword - either slow or fast, or you can give it a
number in milliseconds - in this case 1 second. There is another very useful method - known as
“ ​
.toggle() ​
” - switch or toggle between states, like on or off. Toggle will hide/show and element
depending on the event.
The code below will toggle the visibility of the all the HTML “<p>” tag elements on the page.‘
$(document).ready(function(){
$(“button.toggle”).click(function(){
$(“p”).toggle();
});
}):
Fade
The fade method is just another form of animation that will fade an element. There are 4 fade
methods:
fadeIn();
fadeOut();
fadeToggle();
Client-Side Scripting: JavaScript and JQuery | Evening Course | 2016 © Friends of Design - Academy of Digital Arts
46Client-Side Scripting: JavaScript and JQuery | Class Notes
fadeTo();
$(“button”).click(function(){
$(“div”).fadeIn();
});
The fade method also supports the speed parameter. You can try these examples out to get more
familiar with them.
Slide
The slide method is just another form of animation that will slide an element either up or down or
you can toggle it. There are 3 fade methods:
fadeDown();
fadeUp();
fadeToggle();
$(“button”).click(function(){
$(“div”).slideDown();
});
The slide method also supports the speed parameter. You can try these examples out to get more
familiar with them.
Animate
You can use the animate() method for creating custom animations
$(“button”).click(function(){
$(“div”).animate({left: ‘250px’}, 1000);
});
The code states that a click event on any of the HTML “<button>” tag elements any of the HTML
“<div>” tag element on the page will animate to the left by 250px - the parameters must go in the
parentheses and you can add speed parameter i.e. slow, fast or milliseconds (500ms).
$(“button”).click(function(){
$(“div”).animate({
left: ‘250px’,
opacity: ‘0.5’,
height: ‘150px’,
Client-Side Scripting: JavaScript and JQuery | Evening Course | 2016 © Friends of Design - Academy of Digital Arts
47Client-Side Scripting: JavaScript and JQuery | Class Notes
width: ‘150px’
});
});
Note, that the values are in single quotes and are separated by commas. Please also note that if for
instance you wanted to animate “ ​
margin­left ​
”, you need to camelCase so “ ​
margin­left ​
” would
become “ ​
marginLeft ​
”.
.Stop() Method
The stop method is used to stop an animation before it is finished. You can read up about it on
your own especially if you plan on writing jQuery animation plugins.
Callbacks
Callbacks are functions that can be executed within other functions to instantiate the next
appropriate functionality in code at the appropriate time. Callback methods can be used as a
parameter in functions.
$(document).ready(function(){
$(“.button”).click(function(){
$(“p”).hide(“slow”,function(){
alert(“The paragraph was hidden”);
});
});
});
This means that everything will be executed line by line and once it’s done, the browser will alert
the user that it was successful by displaying the message “The paragraph was hidden”.
Chaining
Up until now we’ve been writing jQuery commands, statement by statement. with chaining we can
use the dot-syntax to chain multiple methods together. The “.” simply keeps the string together.
$(“#p1”).css(“color”,”red”).slideUp(2000).slideDown(2000);
JQuery is not a strict-typed language - because it is essentially JavaScript - thus you can employ
linebreaks to make it more readable, the above line of code can be written like as below.
Client-Side Scripting: JavaScript and JQuery | Evening Course | 2016 © Friends of Design - Academy of Digital Arts
48Client-Side Scripting: JavaScript and JQuery | Class Notes
$(“#p1”).css(“color”,”red”)
.slideUp(2000)
.slideDown(2000);
