
10. Building A System With Logic in JavaScript
Let’s determine our logic first. We will need to ask a number of questions before we
begin to get an idea of what the this little system must do as well as the process and
order it will do it in.
1. How would we describe this process in basic spoken language? (e.g. english)
I’m becoming very forgetful, and I would like a tool that will let me know if today is my birthday at
the click of a button.
2. What does our simple system need to do?
It needs to do a check to see if today is my birthday and let me know, when I click on a button.
3. What are the different parts of the process?
We need to know what today’s date is. We need to know when my birthday is. We need a button
that will execute the function to compare today’s date with my birthday to check if today is my
birthday. Thereafter we need to show what the results are.
4. When the user engages with the system should something happen?
When the user clicks the “check my birthday” button, we check to see if today is the user’s birthday.
5. What will be final outcome of the logic process?
That we have either confirmed or denied that today is the user’s birthday.
You can see that point 1 and 2 are basically the same, however in larger more complex systems,
asking similar questions from different perspectives can reveal small details that may be
overlooked. It is good practise to ask many questions and to soundboard your thoughts with your
team or your friend/girlfriend/yourself if working alone. Now that we know what we must build and
how it must work, we can begin writing the logic (code) of the application. Let’s look at the logic, we
need to know today’s date & my birthdate, let’s define the basic variables.
var todaysDate;
var birthdayDate;
Client-Side Scripting: JavaScript and JQuery | Evening Course | 2016 © Friends of Design - Academy of Digital Arts
36Client-Side Scripting: JavaScript and JQuery | Class Notes
Now let’s assign some static values to the date variables. We will deal with dynamic
variables and dynamic data in the next course.
var todaysDate = “August 25”;
var birthdayDate = “January 15”;
Again let’s look to the logic to see what will be next. Or logic tells us we need a button to
call the function. We will now create some HTML for the basic UI elements the user will
engage with. We are going to make a simple button object and a paragraph, each with an id and
class as needed.
<button id=button>Check my Birthday</button>
<p id=”results” class=”results”></p>
As you can see the paragraph is empty. It will be the wrapper/container object that receives the
message text to inform the user of what has occurred. If we again look at the logic we can see we
will need a place to display the message, but also need to send a specific message based on
whether it’s my birthday or not. For this we will define two
variables one for each message type.
var messageBirthday = “Hey look at that, it’s my birthday!”;
var messageNotBirthday = “Aww, it’s not your birthday, sorry...”;
We now have the assigned the values for the dates, messages and the basic HTML in place. Now we
need to make the code react to the user and do a check to see if the dates correspond. In this case
according to our dates we can anticipate that the dates will not match, thus we will be
testing with “ ​
false ​
” in mind. That is to say, we expect a result that is not my birthday.
function checkDates() {
// conditional statement
if (todaysDate == birthdayDate) {
// our code will go here
}
}
The basic “if” statement in place to begin the check, but once again we must look to the logic to see
what must happen based on which condition is met - true or false.
Client-Side Scripting: JavaScript and JQuery | Evening Course | 2016 © Friends of Design - Academy of Digital Arts
37Client-Side Scripting: JavaScript and JQuery | Class Notes
According to our logic the user must receive a message let’s them know whether it’s my birthday or
not. So we will need to show our messages we created previously to the user.
To do this we need to interact with the HTML objects we created. We need to use JavaScript to
identify them and then based on what happens interact with them, by passing data to them or
calling an function or both. But how do we do this?
document.getElementById(‘elementId’);
The line code above will ask our document (webpage) to identify the object with an id of “results”.
Once we have identified it we can work with it. So let’s identify our basic HTML objects and store
them in variables for later.
var showResults = document.getElementById(‘results’);
var checkMyBirthday = document.getElementById(“button”);
Now we need need to put the correct message in our results container based on the condition. We
will need to adjust our “if” statement to become an ”if else” statement to switch between the
messages.
function checkDates() {
// conditional statement
if (todaysDate == birthdayDate) {
// first action here
} else {
// second action here
}
}
We have adjusted our “ ​
if ​
” statement, declared all the variables we need, now we need to complete
our function.
function checkDates() {
// conditional statement
if (todaysDate == birthdayDate) {
Client-Side Scripting: JavaScript and JQuery | Evening Course | 2016 © Friends of Design - Academy of Digital Arts
38Client-Side Scripting: JavaScript and JQuery | Class Notes
// if the dates are the same put messageBirthday into our
results container.
showResults.innerHTML = messageBirthday;
} else {
// if the dates are not the same put messageNotBirthday into our
results container.
showResults.innerHTML = messageBirthday;
}
}
Important!
“.innerHTML = x;” ​
is a javscript method which allows us to change html content inside an html
tag.
We have completed the “ ​
checkDates ​
” function it will run and compare the values of the variables
we defined as our dates to see if they correspond and then send the message which is most
appropriate to the results container. However our logic says that this must happen on a button
click. We have already defined our button in a variable. We need only link the functions to the
button.
checkMyBirthday.addEventListener(‘click’, function () {
checkDates();
}, false);
At this point we have created a click function using an “ ​
addEventListener ​
”, the event listener will
wait till a specific event occurs before it is run. In this case it waits for the click. Inside the click
function we execute our “ ​
checkDates ​
” function we already created. The whole code should look
like the following.
<script type=”text/javascript”>
var todaysDate = “August 25”;
var myBirthday = “August 25”;
var showResults = document.getElementById(‘results’);
var checkMyBirthday = document.getElementById(“button”);
var messageBirthday = “Hey look at that, it’s my birthday!”;
var messageNotBirthday = “Aww, it’s not your birthday, sorry...”;
function checkDates() {
Client-Side Scripting: JavaScript and JQuery | Evening Course | 2016 © Friends of Design - Academy of Digital Arts
39Client-Side Scripting: JavaScript and JQuery | Class Notes
if (todaysDate == myBirthday) {
showResults.innerHTML = messageBirthday;
} else {
showResults.innerHTML = messageNotBirthday;
}
}
checkMyBirthday.addEventListener(‘click’, function () {
checkDates();
}, false);
</script>
And the HTML like this:
<button id=”button”>Check My Birthday</button>
<p id=”results” class=”results”></p>
Using only basic parts of JavaScript, we have built a basic system using some logic to guide us.
