# Manipulating the DOM with JQuery

There are few methods just like `.click()` or `.mouseover()` or `.hide()` that
jQuery uses to manipulate specific elements in the DOM. The first component is
Get Content. There are 3 jQuery methods available for this:

* `text()`: can set or return textual content of a selected element
* `html()`: can set or return the content of a selected element
  (including HTML markup)
* `val()`: sets or returns the value of form fields.

```javascript
$("button").click(function(){
  alert("Text: " + $("#p1").text());
  // alert is a javascript function for making a browser popup window
});
```

The code may look complicated but it's quite simple. When a user clicks on any
button the browser will alert the user, it will prepend the text `Text:` and
append whatever text is located in the element which has an ID of `p1`. If we
use the same code but replace `text()` with `html()` - it will return the actual
html markup within the element `p1`.

```javascript
$("button").click(function(){
  alert("HTML: " + $("#p1").html());
});
```

Finally, we can use the `val()` on a similar piece of code to find out what the
value of an input field might be. In this example we assume that there is an
input field with the ID of `test`.

```javascript
$("button").click(function(){
  alert("Value: " + $("#p1").val());
});
```

We can grab attribute values from elements in DOM quite easily using the
following method.

```javascript
$("button").click(function(){
  alert($("a#contact").attr("href");
});
```

This code will pull the value of the href attribute from a HTML `<a>` tag with
the ID of `contact`. These "Get Content" methods can be useful, but aren't very
functional, ideally we need to be able to change the content within the selected
DOM element. We use "SET Content" methods to do this.

## Setting Contents

To set the contents of DOM objects or HTML elements. The same methods will apply
however we work with them differently.

* `text()`
* `html()`
* `val()`

```javascript
$("button").click(function(){
  alert("HTML: " + $("#p1").html());
});
```

This is the jQuery code to "Get Content". Find all the HTML `<button>` elements,
when a user clicks, inform the browser to alert the user with the following
content - a string with value `HTML:` and then to identify the HTML markup in an
element with the ID of `p1`.

To "Set Content" of the text in an HTML element, we can do the following:

```javascript
$("button").click(function(){
  $(".intro").text("Welcome to my Campaign");
});
```

Or set the HTML markup inside another HTML element, we can use the `.html()`
method.

```javascript
$("button").click(function(){
  $(".intro").html("<p>Welcome to my Campaign</p>");
});
```

Below we are setting the value attribute of an HTML form field element.

```javascript
$("button").click(function(){
  $(".intro").val("Batman");
});
```

However we can also set other attribute values using the `.attr()` method:

```javascript
$("button").click(function(){
  $(".intro").attr("href", "http://www.google.com");
});
```

As you can see we've added two parameters, the attribute name and the value.
Finally, you can set multiple attributes, but you must include them in the
parentheses.

```javascript
$("button").click(function(){
  $(".intro").attr({
    "href": "http://www.google.com",
    "title": "Google"
  });
});
```

## Add Content

There are four basic methods available for adding HTML content to a DOM element.

* `append()`: Will place content at the end of selected elements
* `prepend()`: Will place content at the beginning of a selected element
* `after()`: Inserts content after the selected element
* `before()`: inserts content before the selected element

```javascript
$("div").append("<p>Hello, World</p>");
```

We can also remove or empty HTML elements with the DOM, using the following
methods.

* `remove()`: removes the selected element and its child/nested elements
* `empty()`: removes the child elements from the selected element.

```javascript
$("div").remove();
```

Would remove that `div` element out of the DOM.

```javascript
$("div").empty();
```

Would remove everything within that `div` element. You can go a step further and
target specific elements within a selector. This works as a parameter with in
the remove method.

```javascript
$("div").remove("p");
```

## CSS Classes

As much as jQuery can manipulate HTML elements, it can also manipulate CSS. It
contains 4 methods:

* `addClass()`: Can add one or multiple classes to the selected elements
* `removeClass()`: Removes one or more classes from the selected elements
* `toggleClass()`: Toggles between adding/removing classes from selected elements
* `css()`: sets or returns the style attribute

Just like any other jQuery method we can use this with a function, or just by
itself. Consider the following:

```javascript
$("button").click(function() {
  $("h1, h2, h3").addClass("red");
});

$("button").click(function() {
  $("h1, h2, h3").addClass("red", "heading");
});
```

This will append two classes to all the `h1, h2, h3`. You can even have multiple
elements being assigned classes.

```javascript
$("button").click(function(){
  $("h1, h2, h3").addClass("red", "heading");
  $("p").addClass("pink");
});
```

As would imagine, the removeClass() and toggleClass() work much the same:

```javascript
$("button").click(function(){
  $("h1,h2,h3").removeClass("red", "heading");
});

$("button").click(function(){
  $("h1, h2, h3").toggleClass("heading");
});
```

The toggle class will remove or add the class `heading` on click. The CSS method
can be used to get and set css properties, we will focus on set as its the most
useful and appropriate for now.

```javascript
$("p").css("background-­color", "#000000");
```

This will find all `<p>` tags and apply a background colour of black. Remember
that this won't be executed or written in your stylesheet. It will be added to
the HTML element as an inline style attribute as shown below.

```html
<p style="background­-color: #000000;"></p>
```
