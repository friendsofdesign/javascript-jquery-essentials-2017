# Advanced JavaScript Syntax

## Variables

### Declaring Variables

In JavaScript we can declare an "empty" variable which will act as a placeholder
until we assign data or value to it. Below is basic requirement for the
JavaScript to understand that a variable had been declared.

```javascript
var myVariable;
```

We can also declare several variables, it can be done in two different manners,
first using several lines of codes each beginning with var, or writing the
keyword `var` once and then use commas as separators between variable names:

```javascript
var myFirstVariable;
var mySecondVariable;
// or (this is a single line comment in code, it will be ignored at runtime)
var myFirstVariable, mySecondVariable;
```

It is good practice to create clear readability of in code, as well as grouping
your code into logical block that relate to each other. However this becomes
more complex when “scope” of the code begins to play a role in your code blocks.

### Naming variables

As mentioned is the first chapter, any programming language comes with its best
practices, its own rules defining the way you are supposed to write your code.
Thus, even if JavaScript allows you to name your variables in almost any way you
would like it, you should respect the following rules:

1. The name should describe shortly the meaning of the value of the variable.
   One could use `var userName;` for a variable containing the name of the user.
2. The camelCase practice should be used. Variables names containing a compound
   of words or a phrase are named such that the first word begins with a
   lowercase letter and each next word begins with a capital letter.
   `var thisIsCamelCase;`
3. Avoid abbreviations in which meaning is not obvious to the data or value.
4. If a variable contains a value or data that will not changed
   i.e. `static data`, at any point of the execution, it’s common to name it
   with capital letters separated with underscores:
   ```javascript​
   var BODY_
   TEMPARATURE = 37.6;
   ```
   Such a variable is described as a constant, static or literal.

Be aware that there are exceptions to these conventions as there is a
non-exhaustive set of rules, however these conventions are put in place to aid
in maintaining and updating code for yourself or any team member. Keep the logic
of the system in mind as well. The logic of the system will act as guide to the
code structure, naming conventions and readability.

### Assigning Value to Variables

The next step is to assign a value to a variable.

```javascript
var myVariable;
myVariable = 6;
```

The first line of code declares a variable named `myVariable`; the second line
assigns the value six to that variable. So after the execution of that line of
code, the variable will contain the value six.

It’s quite common to declare a variable and assign it a value at the same time.
This is a condensed way to write the previous code:

```javascript
var myVariable = 6;
```

Also, you can assign the value of a variable to another variable.

```javascript
var myVariable = 6;
var myOtherVariable = myVariable;
```

`myOtherVariable` ​now contains the value six. The assignment operation will
always evaluate the expression on the right side of the equal sign and then
assign the value to the variable on the left side of the equal sign. Thus, a
code line like `6 = myVariable` is wrong and will give an error.

### Types of Variables

So far, we only saw variables holding numeric values, such has 6. But a variable
can contain many different types of values. Let’s have an overview.

#### Numbers

They can be positive or negative, and have decimal values:

```javascript
var count = 10;
var pi = 3.14;
```

Common arithmetic operations can be applied to numeric types, using operators
like `+`, `*`, `-`, `/`.

```javascript
var ten = 10;
var twenty = ten + ten;
//twenty === 20;

var hundred = ten * ten;
//hundred === 100;

var zero = ten ­ ten;
//zero === 0;

var one = ten / ten;
//one === 1;
```

The operator modulo, `%`, gives the remainder of a division.

```javascript
var remainder = 36 % 10;
//remainder === 6;
//10 * 3 + 6 = 36
```

Modulo is often used to test if a number is odd or even, as an odd number modulo
two will be one and an even number modulo two will be zero.

```javascript
var remainder = 12 % 2;
//remainder === 0;

var remainder = 11 % 2;
//remainder === 1;
```

#### Strings

A string of characters, usually just described as a string, represents text.
When declaring a string value, quotes or double quotes must be wrapped around
the text. The quotes or double quotes inform JavaScript that it is not a number
value but an alphanumeric value of text and characters.

```javascript
var userName = "John Doe";
var userName = 'John Doe';
```

A simple operation that you can apply on strings is concatenating them two
chains using the addition operator.

```javascript
var firstName = 'John';
var lastName = 'Doe';
var userName = firstName + ' ' + lastName;
//userName === 'John Doe';
```

To convert a string to lowercase letters, or capital letters, the medhods
`toLowerCase()` and `toUpperCase()` may be used. We will talk more about
functions later in this course, but the example below shows how to use these
two.

```javascript
var city = 'Cape Town';
city = city.toLowerCase();
//city === ‘cape town’;

city = city.toUpperCase();
//city === 'CAPE TOWN';
```

You can easily use strings to interact with HTML elements using jQuery.

```javascript
var pColor = 'blue'; $('p').css('color', pColor);
```

That code will change the color of every `<p>`​ element to blue.

#### Booleans

A boolean variable can only have two values, true or false.

```javascript
var isItAGreatCourse = true;
var amIBored = false;
```

### Type Conversion

Sometimes, you need to convert one type to another. The most common conversions
are to convert a number to a string and a string to a number. To convert a
number to a string, you use the method `toString()`.​

```javascript
var one = 1;
var oneAsString = one.toString();
//oneAsString === '1';

var eleven = oneAsString + oneAsString;
//eleven === '11';
```

To convert a string to a number, you use the method `parseInt()`.​

```javascript
var twenty = '20';
var two = '2';
var result = twenty + two;
//result === '202';

twenty = parseInt('20');
two = parseInt('2');
result = twenty + two;
//result === 22;
```

If the number has decimal places, you must use `parseFloat()`​ to get the exact
value.

```javascript
var decimal = parseInt('3.14');
//decimal === 3;

decimal = parseFloat('3.14');
//decimal === 3.14;
```

If you try to convert a bad string to a number, you will get the result `NaN`,
not a number.

```javascript
var notANumber = parseInt('abc');
//notANumber === NaN;
```

### Typeof

You can know the type of a variable using the operator typeof. When you declare
a variable, it has the type undefined.

```javascript
var myVar;
var myType = typeof(myVar);
//myType === 'undefined';
```

The types are dynamic, your variable can be a string at some point of the code
execution and an integer later.

```javascript
myVar = 1;
myType = typeof(myVar);
//myType === ‘integer’;

myVar = '1';
myType = typeof(myVar);
//myType === ‘string’;
```

### Variable Scope

JavaScript uses what is called functional based or function scope. This means
that scope changes in relation to functions in code. JavaScript and all
programming languages have code which exist in blocks and structures. These
blocks of code, like functions and objects, have access to particular parts of
the rest of the code, this deemed the scope.

For instance a variable declared inside a function has a scope that is local to
that function, this is also referred to as a local variable. A variable declared
outside the function is regarded as having scope that is global to the function
and rest of the code, referred to as a global variable.

```javascript
var myGlobalVariable = 'this variable has a global scope';

function myLocalFunction() {
  var myLocalVariable = 'this variable has a local scope';
}

// The location where the variable is declared determines its scope
```

> **Important!**
  Local variables are deleted when the function they were declared in is done
  running. Global variables are deleted when the page is closed.


## Conditional Statements Syntax and Structures

### IF Statements

Sometimes in your code, you may want to perform some action only if a certain
condition is met. The if statement exist to allow you to realize that. This is
how it works:

```javascript
if(condition) {
  // do something
}
```

The condition is a boolean value, which means that it can be only true or false.
The code written within the brackets will be executed only if the condition is
met, thus only if the condition is true.

### Else Statements

The else statement is used to perform a different action if the condition used
in the if statement is not met. This is how it works.

```javascript
if(condition) {
  // do something
} else {
  // do something else
}
```

If the condition is true, the code written between the do something brackets
will be executed. Otherwise, the code written between the do something else
brackets will be executed. You can combine several if else blocks if some
complex logic is required.

```javascript
if (condition) {
  // do something
} else if (second condition) {
  // do something else
} else if (third condition) {
  // do something different
} else {
  // do default action
}
```

## Operators

### Comparison Operators

Comparing variables is required to build conditions. The comparison operators
compare two variables and return true or false depending on if the comparison
condition is met.

#### Example with the "equal to" operator

The "equal to" operator is written using a double equal sign, `==` , or using
the triple equals sign returns true only if the expressions on each side of the
operator are equal, false otherwise. The code snippet below shows a possible
usage of the is equal operator.

```javascript
userGender = userGender.toLowerString();

if (userGender == 'f') {
  title = 'Ms.';
} else if (userGender == 'm') {
  title = 'Mr.';
}

var userWelcomeMessage = 'Hello ' + title + ' ' + userName;
```

### Logic Operators

Logical operators are used to manipulate boolean values. You can use them to
build more complex conditions. The "and" operator is written using a double
ampersand, `&&`, and returns `true` only if the expression on its right side and
the expression on its left side is true. The code snippet below show a possible
usage of the and operator.

```javascript
if (age >= 10 && age < 20) {
  category = ‘teenager’;
}
```

## Functions

In programming, a function is a section of code which performs a specified task.
For example, the code below declares a function named `sayHelloWorld`, which
displays a popup with the message "Hello World". The function code is all the
code included in the brackets following its declaration.

```javascript
function sayHelloWorld() {
  window.alert('hello world!');
}
```

The code inside of a function is executed when the function is called. This is
done the following way.

```javascript
sayHelloWord();
```

The purpose of functions are multiple:
* Organize your code. When there is a complex block of code, you can just read
  the name of the function and know what is its purpose, for example `sendEmail`.
* Follow DRY (Don’t Repeat Yourself) methodology
* Create libraries - A library is a set of functions that you can see as a
  toolkit for its user.

### Parameters

The function declaration can be completed if needed so that it accepts
parameters. Parameters are used to customize the function behaviour according to
the parameter value, which is called the argument. For example, the code below
declares a function named “sayHelloToUser”, which displays a popup with a
message saying hello and the user full name.

```javascript
function sayHelloToUser(userFirstName, userLastName) {
  alert('hello ' + userName + ' ' + userLastName);
}
```

Calling that function with the arguments `John` and `Doe` will result of a popup
displaying `hello John Doe`.

```javascript
sayHelloToUser(‘John’, ‘Doe’);
```

### Return Value

Functions can also return a value. This is done by using the return statement.
The code below declares a function named add which takes two parameters, `x` and
`y`, and returns the value of the two parameters added. So calling sum with `2`
and `3` as arguments will return the value `5`.

```javascript
function add(x, y) {
  return x + y;
}

var sum = add(2, 3);
//sum == 5;
```

When you reach the return statement, the function execution is stopped and
continues where the function has been called before. So if we execute the code
below, only one popup displaying `out add` will be displayed.

```javascript
function add(x, y) {
  return x + y;
  alert('in add');
}

var sum = add(2, 3);
//sum === 5;
window.alert(add); //show sum value in alert box *see outputting and displaying data section
```

The final step of the code above outputs the return value in the
`window.alert()` method. This causes an alert box to be generated by the browser
and the value will be displayed to the user.


### Functions as Variables

Like a number or a string, a function is a variable designed by its name. As a
variable, you can assign it, to another variable.

```javascript
function convertToUSD(rand) {
  return rand * 0.091;
}

function convertToEuro(rand) {
  return rand * 0.070;
}

var converter = convertToUSD;
var money = converter(1);
//money === 0.091;

converter = convertToEuro;
money = converter(1);
//same line, but now money === 0.070;
```

### Outputting or Displaying Data

There are different ways to display data with JS, there are four basic methods
to do so but each have their own specific uses. These are considered to be DOM
methods as well.

* `window.alert()`: creates an alert box to display value in.
* `document.write()`: writes to the html output, best used for testing.
* `.innerHTML`: the most common and recommended method to display data to DOM
  elements.
* `console.log()`: display data in the browser console log, also good for
  testing.

Just like functions return value, and variables can have values, these can be
written or displayed to a webpage. Below are examples of each type of display
method.

```javascript
var warning = 'This is a warning Alert Box!';
window.alert(warning); // displays the string value in an alert box to user

var myTestInfo = 5 + 9;
document.write(myTestInfo); // displays the value of the expression in the variable myTestInfo
```

Below we are using the document.write() method to show an example of displaying
the value as part of a function. This can also be done with other display/DOM
methods.

```javascript
function addSales() {
  var salesPerWeek = 5;
  var salesPeriod = 12;
  var totalSales = salesPerWeek * salesPeriod;

  document.write(totalSales); //display value using write method.
}

addSales(); // runs the function
```

When using the `.innerHTML` method, we can push the values into elements like
divs or paragraphs.

```html
<h3 id=”user”>
</h3>
```

```javascript
var firstname = 'John';
var surname = 'Doe';

document.getElementById('user').innerHTML = firstname + ' ' + surname;
// here we use the innerHTML and “+” sign to bind 2 variables values to give the
// final result ­ we leave quotes with space to create space between the values
//of the variables.
```

Lastly we have `console.log()` method which writes to the browser console. To
access the browser console - right + click(win) or ctrl + click(mac) on your web
page and select inspect element. Find the console button and you should see the
value in the console displayed.

```javascript
console.log(8 * 4);
```

These are the base commands for writing data to a webpage, combining this with
all the other syntax will allow you to update information and data where you need
to.

## Data Structures

The object concept is the core of most modern programming language. Developing code in these
languages is called OOP, object oriented programming.

### What is an object?

Everything that you can see in this room can be described numerically as an
object. For instance, abook. A book has some properties : a title, an author, a
number of pages, a color, a state (open or closed, the page at which it is open).

You can also perform some actions with a book : open it, close it, read it, burn
it. An object, like in real life is a data structure containing properties
describing the object and its state and methods corresponding to the actions you
can perform with the object. An object property correspond to a variable, and an
object method correspond to a function.

### Declaring an object

There are several ways to declare an object, but let's just focus on the one
using a prototype. A prototype is a special function used to create an object.
Using the book analogy, we can say you are designing a website that sells book.
You need also properties like the price of the book.

The following prototype can then be written:

```javascript
function Book(title, author, price) {
  this.title = title;
  this.author = auhtor;
  this.price = price;
};
```

That prototype instantiates a book object that contains three properties and no
method. Note that a slightly different name convention applies there: the
prototype's name begins with a capital letter.

```javascript
myBook = new Book('JavaScript for Dummies', 'John Doe', 299);
```

#### Properties

Our object properties are now accessible using the following way:

```javascript
alert(myBook.title);
myBook.price = 199;
```

Another way to access a property is by its name:

```javascript
alert(myBook['title']);
myBook['price'] = 199;
```

The advantage of accessing a property by its name is that it is more dynamic.
For instance, you could ask an user to prompt the name of a property and then
display it.

```javascript
var propertyName = prompt();
//prompt is a function that returns an user input string
alert(myBook[propertyName]);
```

#### "This" and New Keywords

First, in the prototype, the keyword this is used. It refers to the owner of the
function, so to the object we are currently creating. Second, when we declare​
`myBook`​ the keyword new is used. It indicates to instantiate a new object with
a defined constructor.

#### Object Methods

The book has several properties but no method. Our site is required to sell
books, the obvious action we can perform with a book is to buy it. A function
managing the buying action must then be added:

```javascript
Book.prototype.buy = function(){
  alert('the book' + this.title + ' has been bought');
};
```

Once again there are several ways to declare an object method and you may find
something different in some other developer's code. Without losing ourselves
into too much technicity, this one, using Object.prototype, is generally the one
offering better performances and much more flexibility.

Now whenever the function buy is called on a book, a popup confirming the buy
will be displayed.

```javascript
myBook.buy();
```

### Date Object

Let's have a quick overview of a common object type, the Date object. JavaScript
offers a very handy object type to manipulate dates. First, let's see how to
declare and display a date.

```javascript
var d = new Date();
windows.alert(d.toDateString());
```

The first line of code instantiates a new date. As we provide no argument, `d`
is initialized with the current time of the computer clock. The second line
displays a message box with the date converted to an human readable string, so
it could be for instance 25/12/2031, if the computer clock is set on Christmas
2031.

There are plenty different ways of converting the date to a string.
`toLocaleString` will convert it accordingly to your computer locale settings
(could be in arabic for instance), `toTimeString`and `toLocaleTimeString` will
give the time of the days, etc. A date can also be instantiated using a specific
day and time:

```javascript
var d = new Date(2031, 25, 12, 6, 30, 0, 500) ;
```

This creates a date initialized at Christmas 2031, 6:30:00AM + 500 milliseconds.
You can also set or get a specific element of a date, like the day, the hour or
the month. For instance, this code snippet calculates an expiration date two
weeks after the current time.

```javascript
var d = new Date(); d.setDay(d.getDay()+14);
```

For further reading see [Mozilla's documentation regarding the date object](https://developer.mozilla.org/).

## Arrays & Loops

An array is a special variable used to group a collections of variables. Working
with arrays generally involves using loops to iterate through the array, as we
will see in this chapter.
​
### Declaring an array

An array is declared using brackets and each element of the array is separated
by a comma. For instance, the following array groups three strings.

```javascript
var personList = ['Anna', 'Bob', 'Chris'];
```

Technically, an array is an object type. Thus it has some handy properties like
its length.

```javascript
var length = personList.length;
//length === 3
```

Note that the following code will create an empty array:

```javascript
var empty = [];
```

### Accessing Elements in an Array

A single element of the array can be accessed using its index number. The index
is the position of the element in the array, starting with zero. Anna's index is
zero, Bob's index is one, and Chris's index is two. The brackets operator allows
to access a particular element.

```javascript
var person = personList[2];
//person === 'Chris';

personList[1] = 'Byron';
//personList === ['Anna', 'Byron', 'Chris'];
```

### Adding and Removing Elements from an Array

JavaScript arrays are dynamic. It means that as we already saw you can modify a
particular element of it, but also that you can add or remove elements from it.
This is done using the following functions.

* `.unshift`: Add element to the beginning of an array
* `.shift`: Removes element from the beginning of an array
* `.push`: Add element to the end of an array
* `.pop`: Removes element from the end of an array
* `.splice`: Add or remove element from the middle of an array

The following examples describe how to use these functions.

```javascript
var personList = ['Anna', 'Bob', 'Chris'];
// Array of people

var element = personList.shift();
// Anna is removed from the array

var length = personList.unshift('Andile');
// Add Andile to beginning of the array

element = personList.pop();
// Removes Chris from the array

length = personList.push('Craig');
// Add Craig to the end of the Array

element = personList.splice(1,0, 'Zoe');
// Add item 'Zoe' at the position one

var removed = personList.splice(1, 0, 'Zoe');
// personList === ['Andile', 'Zoe', 'Bob', 'Craig']
// removed === [] thus empty array
// Removes two items at the position one removed = personList.splice(1, 2);

// personList === ['Andile', 'Craig']
// removed === ['Zoe', 'Bob']
```

### Loops

In programming, a loop is a code section that is executed repeatedly until a
certain condition is met.

#### While loops

In JavaScript, the simplest loop is the while loop. The while loop executes some
code while a certain condition is true. For instance, the following code will be
executed while the length of the `personList` array is greater or equal than
zero, thus while the array contains elements.

```javascript
while(personList.length > 0) {
  windows.alert(personList.pop()) ;
}
```

At each iteration, the last element of `personList` is popped and displayed in a
popup. When eventually the array is empty, the condition `personList.length > 0`​
becomes false and the loop stops.

I'm sure you already came across the following annoying situation. You are
quietly browsing a web page, when suddenly it freezes and become unusable until
eventually the browser displays a message like "​A script on this page may be
busy, or it may have stopped responding. You can stop the script now". Why does
this happen? In most of the cases, it’s because JavaScript is stucked in what is
called an infinite loop. The condition to stop the loop is never met, thus the
loop is executed infinitely.

```javascript
while(True) { }
```

The condition `True` will be true forever. That’s a pretty obvious case but keep
in mind that loops can in many ways be at the origin of bugs.

#### For loops

A for loop is a slightly more complex while loop, but the general principle is
the same. Let’s examine the following for loop to see how it works.

```javascript
for(var i=0; i<3; i++) {
  alert(i.toString()) ;
}
```

Executing this snippet of code will display three popups with the messages `0`,
`1` and `2`.

##### How does it work?

When we enter the “for loop”, the code before the first semicolon, `var i = 0`,
is executed. It’s called the loop initialization. Then, the condition between
the two semicolons, `i < 3`, is evaluated. If that condition is true, which is
the case so far because now i equals zero, the code between the two brackets,
thus the popup message, is executed.

That’s when the first message box is displayed. After that, the third statement,
`i++`, is executed. `i++` means `i = i + 1`, it increments the value of `i`,
which was zero and is now one. Then the loop starts over again: condition
evaluation, if it’s true loop code execution, and incrementation of the value of
`i`. When `i`reaches three, the condition `i<3` is false and the loop stops.

#### For In Loops

The "for in loop" is a special loop which allows you to iterate to every
property of an object. At every iteration of the loop the value before the
keyword will be equal to the property value.

```javascript
myBook = new Book('JavaScript for Dummies', ‘John Doe’, 199);

for(prop in myBook) {
  alert(prop + ': ' myBook[prop].toString());
};
```

The previous code will display a popup for every property of the book object,
with a message including the name of the property and its value. So if the Book
prototype is the same as the one from the previous chapter, it will be
`title: JavaScript for Dummies`, then `author: John Doe`, and eventually,
`price: 199`.

#### Iterate through Arrays with Loops

Practically, one of the most common usages of the loops is to use them in
combinations with arrays to iterate through it. If you need to access to each
element of an array of length equals to five, you will have to access the
element zero, one, two, three and four.

Practically, it's again an example which is the better explanation. The
following code will display a popup for each person in personList, containing
the person's name:

```javascript
for(var i = 0; i < personList.length; i++) {
  alert(personList[i]) ;
}
```

At the first iteration, `i` equals zero, so the first element of the array,
`personList[0]`, is displayed. At the second iteration, `i` equals one and
`personList[1]` is displayed. This goes on until the condition
`i < personList.length === False`, thus when all the elements have been
displayed.

## Selecting DOM Elements with JavaScript

JavaScript allows us to manipulate the HTML and values or data displayed on a
website, it allows us to add or remove and update the information on the fly.
However it's useful to be able to identify where in the HTML this will occur. We
would obviously need to inform our code where the data is and how to change it.
For this reason we need to know how to select HTML elements. JavaScript allows
the selection of HTML elements via numerous identifiers, i.e. HTML tag names,
classes applied to HTML tags and IDs applied to HTML tags.

### Basic JavaScript Selector Methods

1. `document.querySelector(selector)`: selects HTML elements by first matching
   class name, ID or tag name
2. `document.querySelectorAll(selector)`: selects all HTML elements by matching
class name, ID or tag name
3. `document.getElementById(idname)`: selects a single HTML element by ID
4. `document.getElementsByTagName(tagname)`: selects HTML elements by tag name
5. `document.getElementsByClassName(class)`: selects HTML elements by class name

Each HTML element is regarded by JavaScript as a Node in the DOM. Using the
query selectors above we can identify these nodes and use JavaScript to
manipulate them or affect the data they contain.

```javascript
var userName = document.querySelector('#username');
// select a div with an ID of 'username'
```

If know exactly what type of identifier we need to use to select the node we can
use another selector method.

```html
<div class="user­name">John Smith</div>
```

```javascript
// the HTML div element we want to select with a specific class name
var userName = document.getElementByClassName('user­name');
```

We can also select HTML elements using their relationships to each other. Child
to parent, parent to child or even siblings relationships.

### Child and Parent DOM Relationships

A child to parent relationship is characterised by being able to identify the
parent and thus asking JavaScript to select the child element in the HTML or DOM
hierarchy. A parent to child relationship is characterised by being able to
identify the child and then asking JavaScript to select the parent element of
the child in the HTML or DOM hierarchy. Siblings are child elements which exist
inside the same parent element. Siblings ask JavaScript to identify the
neighbouring HTML elements.

```html
<div class="heading">
  <h2>The JavaScript Document</h2>
</div>
```

```javascript
var myText = document.getElementByClassName('heading').childNodes[0];
// here we are selecting the first child <h2> in the div with the class 'heading'
```

There are a number of different ways to select or identify nodes in JavaScript.
If we wanted to create new elements or nodes in the DOM we can use a number of
JS methods to do so.

### Dynamically Adding Element

JavaScript allows us to create new DOM nodes that can be inserted into our
webpages. The simplest method is as follows.

```javascript
var element = document.createElement(tagName);
```

Above we are asking the document or DOM to use the `createElement` method to
create a new HTML tag of our choosing.

```javascript
var heading = document.createElement('h1');
var headingText = document.createTextNode("Hey look at me! I'm alive!!");

heading.appendChild(headingText);
document.body.appendChild(heading);
```

Here we are simply creating a new `h1` tag that is empty and then filling it
with some text. For this to happen we need to create a DOM text node then add it
to the heading `h1`. We can also do it another way like below.

```javascript
var newHeading = document.createElement('h1');
document.body.appendChild(newHeading);
newHeading.innerHTML = "I'm also alive! Hooray!";
```

In the example above instead of creating a text node in the DOM we simply
appended the `newHeading` element we created to the end of our page and only
after it was created on the page added the information to the HTML using the
`innerHTML` method. This is a nice simple way to do it quick however it may not
always work. In some cases you will need to be more specific about where and how
you display the values on the page. The following examples will illustrate.

### Dynamically Changing Elements (Nodes)

In JS we are able to manipulate the DOM nodes as you have seen above, we can
create, remove and replace nodes or elements as we need to using a number of
basic methods in JS.

* `.appendChild()`: add element to another parent at the end
* `.removeChild()`: remove a child from a parent, we must remember to tell the
  DOM which parent we want to remove the child from
* `.replaceChild()`: replace one element with another in a parent element
* `.insertBefore()`: helps us insert the child in the parent before other
  parents.

These 4 methods are the commonly used to manipulate child elements. In the
previous example we showed how to append a new paragraph to a div with an id of
`myArticle`. This is one of the most simple methods to add a child node to an
existing element on the page. The other methods are a bit more strict and
require that we inform the DOM of specific information first.

In the case of the `removeChild()` method we need to inform the DOM which parent
we want to remove the child from. Otherwise we will get an error as it won’t
know which child node to remove. In the case of `replaceChild()` we need to list
the node or element which needs to be remove and then indicate in the script
which one will take it’s place. Similarly when using the insertBefore()
method we need to tell the DOM before which child node of the parent we need it
to insert the new node or element.

#### Appending Child Node

Example below shows how to append a child node to an existing div. Basically we
are adding a new paragraph tag to an existing div.

```html
<div id="myArticle">
  <h2>My Article</h2>
  <p id="firstParagraph">This is my original paragraph and below this I will dynamically insert a new paragraph tag with JS.</p>
</div>

<script>
  // Create new paragraph tag
  var paragraph = document.createElement('p');
  // Create text node to put in p tag
  var newNode = document.createTextNode('Add this new text node to the paragraph tag.');

  // Append the child to the p tag ­ add the text to the paragraph tags
  paragraph.appendChild(newNode);
  // Identify the element on page we want to add it to ­ the div with id myArticle
  var element = document.getElementById('myArticle');
  // Add the paragraph to the div myArticle
  element.appendChild(paragraph);
</script>
```

#### Replace Child Node

In the code below the new `paragraphC` element should appear before the first
paragraph in the `myArticle` div.

```html
<div id="myArticle">
  <p id="paragraphA">This is a paragraph.</p>
  <p id="paragraphB">This is another paragraph.</p>
</div>

<script>
  var paragraphC = document.createElement('p');
  var myNewText = document.createTextNode('This is new text for the new paragraph tag.');

  paragraphC.appendChild(myNewText);

  var parent = document.getElementById('myArticle');
  var firstChild = document.getElementById('paragraphA');

  parent.replaceChild(paragraphC, firstChild);
</script>
```

#### Removing Child Nodes

When removing we need to be very specific as the DOM will need to know the
parent of the element we are looking to remove.

```html
<div id="simpleDiv">
  <p id="p1">This is a paragraph.</p>
  <p id="p2">This is another paragraph.</p>
</div>

<script>
  var parent = document.getElementById('simpleDiv');
  var child = document.getElementById('p1');

  parent.removeChild(child); //Remove 'p1' from 'simpleDiv'
</script>
```

Once we have new elements and data on the webpage we need to learn to style them
and interact. Next we will look at CSS properties and Events.

## CSS Manipulation with JavaScript

With JavaScript we can also manipulate the attributes and properties of DOM
elements, CSS rules are regarded as properties of the element. Meaning with the
correct code we can adjust CSS values of different elements, based on functions,
conditions or events. The base structure is as follows:

```javascript
document.getElementById(id).style.propertyName = newStyle
```

Above is the base syntax for adjusting an element's style (CSS). First we
identify the element by it's ID and then we use the “.style” method to tell the
DOM we will be making adjustments to those properties. After the style method we
tell the code which property name to adjust. These are the same or very similar
to those you use in writing your CSS. For the full list of all the elements in
CSS and their JS counterparts check out [this page](http://www.sitestepper.be/en/css-properties-to-javascript-properties-reference-list.htm).

Keep this link handy it's hard to remember all these properties off by heart. As
you can see they are similar but not all are exactly the same.

```html
<div id="error"> There has been an error!</div>
<div id="success"> Awesome Sauce! Things are working!</div>

<script>
  var myNumber = 4;

  // Set some CSS styles
  document.getElementById('error').style.color = '#ff0000'; // red color for text
  document.getElementById('success').style.color = '#009900'; // green color for text

//check to see what the value of myNumber is and if it is more than 5 we show success
if(myNumber > 5) {
  document.getElementById('success').style.display = 'static';
  document.getElementById('error').style.display = 'none';
} else {
  document.getElementById('success').style.display = 'none';
  document.getElementById('error').style.display = "static";
}
</script>
```

Try changing the value of `myNumber` to something below 5 and refresh your
webpage.

## Event & Listeners

An event in JavaScript is defined as interaction triggered by a user or function
or change in data. In JS we can detect these changes and then run new functions
or code that will respond to the events. Listeners as they are described listen
for the event to take place. When the listener recognises an event it will then
fire off the appropriate code or functions.

Events can be:

* When a user clicks the mouse
* When a web page has loaded
* When an image has been loaded
* When the mouse moves over an element
* When an input field is changed
* When an HTML form is submitted
* When a user pressed a key

There are two common manners in which we add interactive events to webpages in
JS, we can apply an event function directly to an element. When it is interacted
with appropriately it will run the code or create an event listener which waits
for the appropriate action to occur and then will run the code.

```html
<button onclick="this.innerHTML = 'I\'ve been Clicked!'">Click on me!</button>
<button id="clickLink">Click on me!</button>
<button id="clickLinkAlternative">Click on me!</button>

<script>
  var link = document.getElementById('clickLink');

  link.addEventListener('click', function changeText(){
    link.innerHTML = 'I’ve been Clicked as well!';
  });

  // or like so
  var linkAlternative = document.getElementById('clickLinkAlternative');

  function changeText(){
    linkAlternative.innerHTML = 'Me too! Yay!!';
  }

  linkAlternative.addEventListener('click', changeText);
</script>
```

Here three separate sets of code are achieving the same results. It is
recommended to use the third example as the standard as it provides good control
over the code, thus allowing for more robust and maintainable code in future.

We are also able to remove listeners to ensure actions only get completed once.
This is commonly used when transaction as done or submitted from a button. We
want to control the amount of interactions the user can allocate to the specific
interaction to ensure the don’t do a double payment for example. Removing an
event listener is the opposite of the adding, we need to tell it which element
and what type of interaction to remove.

Using the previous click event listener example see how we would remove the
event listener.

```javascript
document.getElementById('clickLinkAlternative').removeEventListener('click', changeText);
```

Once again the developers at Mozilla have put together the most comprehensive
list available about the different events we can listen for. [Check the link for
reference](https://developer.mozilla.org/en-US/docs/Web/Events)
