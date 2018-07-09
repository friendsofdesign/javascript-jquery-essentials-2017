# Traversing the DOM with JQuery

With JQuery we can move through different HTML elements using the traversing
methods, as we know HTML is used for structure, this structure has a hierarchy
and is systematically in relation to other elements. Just like in JavaScript we
can identify the child or parent (descendents or ancestors) of HTML elements
from elements we are already know exist.

* *Ancestor:* is a parent, grandparent or great-grandparent
* *Descendant:* is a child, grandchild or great-grandchild
* *Siblings:* share the same parent.

An example of a basic HTML `<div>` with an unordered list and two list items in
the unordered list.

```html
<div class="parent">
  <ul class="child">
    <li class="granchild"><span>Hello</span></li>
    <li class="granchild"><strong>Goodbye</strong></li>
  </ul>
</div>
```

The `<div>` element is the parent of the `<ul>` element, and an ancestor of all
of it's children. The `<ul>` is the parent of both the `<li>`, but a child of
the `<div>`. The `<li>` is the parent of the `<span>` element, but child of the
`<ul>` and descendant of the `<div>`. Both the `<li>` are siblings.

###Ancestors

We can traverse parents using:

* `parent()`
* `parents()`
* `parentsUntil()`

The parent method will rerun the direct parent of the selected element. It goes
up by one level.

```html
<body>
  <section class="container">
    <div>
      <p>Hello</p>
    </div>
  </section>

  <script>
  $(document).ready(function(){
    $("p").parent();
  });
  </script>
</body>
```

The `parents()` method will find its way all the way up the DOM tree to the last
ancestor or root element which is the `<html>` element.

```javascript
$(document).ready(function(){
  $("p").parents();
});
```

Finally, the `parentsUntil()` method will rerun all ancestor elements between
two arguments or parameters.

```javascript
$(document).ready(function(){
  $("p").parents("body");
});
```

This will return the div and section elements as parents.


## Descendants

Just as we can traverse up, we can also traverse down. We can use the
`children()` and `find()` methods . The `children()` method returns all direct
children of the selected element. The `parent()` method it is only capable of
traversing down by one level.

```javascript
$(document).ready(function(){
  $("section").children();
});
```

You can use the `find()` method to find all descendants to the very last.

```javascript
$(document).ready(function(){
  $("section").find("*");
});
```

Use the Asterisk (`*`) operator to find all. Or we could find specific children

```javascript
$(document).ready(function(){
  $("section").find("div");
});
```

Will return every `<div>` tag that is a child of the `<section>`.

## Siblings

As you would have guessed, we can go up and down and even sideways through the
DOM, in this case we are talking about siblings. I will go through the most
common methods here as there are quite a few:

The `siblings()` method will return all sibling elements of the `<p>`.

```javascript
$(document).ready(function(){
  $("p").siblings();
});
```

The most useful is the next() method:

```javascript
$(document).ready(function(){
  $("h2").next();
});
```

Will find the next sibling element of the `<h2>`. As you expect so will `prev()`.
There are also `nextAll()` method, `prevAll()`, `nextUntil()` and `prevUntil()`​
all work off the same concepts we have already discussed.
