# JavaScript & Basic Syntax

JavaScript is an Object-Orientated, loosely typed programming language, this
means it is a programming language that allows us to interact with HTML and data
as though they are individual objects. JavaScript is also a dynamic programming
language, this means it is high-level programming language, which can execute
code in real time as opposed to being compiled first like many Server-Side
programming languages. The syntax in a programming language are the rules about
how to write code, it is the equivalent of the grammar for a spoken language.

### Simple Variable
Below is the most simple syntax to declare a variable in code. We will touch on
more advanced methods to declare variables in the next course. Variables are
core to the syntax without them it would be very hard to write successful code,
this syntax will become habit in time.

```javascript
  var myNewVariable = 42;
```

The variable is started with the shorthand `var` followed by the chosen
identifier and set with an assignment operator of `=` to the value of `42`

### Variable with an Expression

```javascript
  var myExpression = 42 + 6;
```

This variable has a simple operand expression, it simply adding two values with
the use of an arithmetic operator.

### Variable with Operand Expression of Two Variables

```javascript
var priceOne = 42;
var priceTwo = 6;
var totalPrice = priceOne + priceTwo;
```

The first and second variables are provided with literal (static) values, the
third variable `totalPrice` uses an expression to add the two variables together
to create the total.

### Functions

You will be using functions in almost all the coding you do. You will become
very familiar with this syntax in time.

```javascript
function mySpecialFunction(parameterOne, parameterTwo) {
  // here we will place our code statements
}
```

> **Important!**
  Remember all parameters defined in a function like `parameterOne` are
  variables in the scope of the function. See variable scope.

### Calling Functions

For a function to be run it must either be called in code or run as method on an
event or action. To call the function I've declared previously I would simply
call it when I need it to run. This may be in a condition or just at the end of
the code.

```javascript
mySpecialFunction();
```

To call a function simply give the name of the function - remember to check
spelling - withp arentheses at the end and semi-colon to close the statement.
Functions can also call other previously defined functions, this is referred to
as "Nested Functions".

```javascript
function myGlobalFunction (scope) {
  scope = "this variable is in the scope of the first function";
  console.log(scope);

  function changeVariableData () {
    scope = "this function can change the value of the variable";
    console.log(scope);
  }

  changeVariableData();
}

myGlobalFunction();
```

In the function above we can see that we have nest the the function
`changeVariableData` inside the function ​`myGlobalFunction`​. You will also
notice the that our parent variable (`myGlobalFunction`) calls the nested
function before it is closed and outside the `myGlobalFunction` ​ function, the
parent function is called.

When this set of nested functions is called, it will change the value of our
argument (variable) `scope` ​to a string value and then log it to the console
window. Then the function will call the nested function ​`hangeVariableData`​,
which will in turn change the value of our original variable `scope` ​to a new
string value and then proceed to log it to the console window.

Notice that the variable ​`scope`​ has only been declared once as an argument of
the function. This variable has a local scope to the parent function, however
because the second function is nested and is a child of the first function
(`myGlobalFunction`) the variable has a global scope with regards to the child
function. Any functions nested in the parent will have global access to the
variable `scope`.

### Conditional Statements

As mentioned previously, there are a number of conditional statements used in
programming. We will be looking at the most commonly used `if` statement to
provide us with an idea of the basic syntax that is similar to all conditional
statements.

```javascript
if(mySpecialVariable == 4) {
  console.log(mySpecialStatement);
}
```

Conditional statements check to see if specific arguments are met. In the
example above our condition is simply to check to see if the variable -
`mySpecialVariable` - is strictly equal to a value of `4`, if the argument
passed into the if statement is met, we the log the variable value to the console
window.

```javascript
if(myOtherVariable != 4) {
  console.log("It's not equal to 4!");
}
```

In the second example above we are created an argument that is using a logic
operator. The logic operator `!=` is used to check if our variable
`myOtherVariable` is "not equal to" a value of `4`. Should the ​`myOtherVariable`​
not resolve to a value of `4`, it will log to the console window a string that
reads "It’s not equal to 4!".

> **Important!**
  Remember arguments are the variables and values in an expression passed into
  the parentheses of a function or conditional statement.
