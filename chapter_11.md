# Setting Up JQuery

JQuery is a cross platform Javascript library designed to simplify the client
side scripting of HTML.

#### What does that mean?
The jQuery library assists developers in writing JavaScript code, it contains
many common functions and methods used in JavaScript development. This provides
JavaScript developers and designers a toolkit to quickly and easily get common
functionality running on a system or website.

The jQuery library makes the following common development tasks simpler:

* HTML/DOM Manipulation
* CSS Manipulation
* HTML Event Methods
* Effects and Animation
* AJAX
* Utilities

We must include JQuery on our website or system in order to access the
predefined functions and methods that will make our development work simpler.
Including a JavaScript library on a simple website is very easy. First we need
to download the JQuery library and store it in a folder in our website. We must
then create a link to the library in the appropriate HTML code, so that the site
or system can identify the library. Alternatively we can create a link that
points to a CDN (Content Distribution Network). A CDN is merely a server that
stores common libraries and files that can be openly accessed by websites. Once
again if we apply the appropriate HTML code to link the file, we can include the
library in our site. To link a script file we will need to add the following
HTML code to our website. This can be either added to `<head>` section of our
website or before the closing `</body>`tag of our website.

```html
<!DOCTYPE html>
<head>
  <!­­ local file ­­>
  <script src="javascriptfolder/jquery.js"></script>
  <!­­ CDN hosted file ­­>
  <script src="http://ajax.googleapis.com/ajax/libs/jquery/1.11.1/jquery.min.js"></script>
</head>
<body>
  <!­­ local file ­­>
  <script src="javascriptfolder/jquery.js"></script>
  <!­­ CDN hosted file ­­>
  <script src="http://ajax.googleapis.com/ajax/libs/jquery/1.11.1/jquery.min.js"></script>
</body>
</html>
