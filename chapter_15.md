# JQuery Extras, AJAX and Goodies

## No Conflict

Depending on your project, you might find that there is a problem with other
Javascript libraries using the `$` symbol. If you have two libraries both using
`$` symbols for functions or pro grammatical dynamics then certain scripts could
stop working. jQuery has seen this coming. Instead of using the `$` one can
actually just use the word `jQuery` instead.

```javascript
jQuery(document).ready(function(){
  jQuery("h2").next();
});
```

You can create your own alternative for the `$` sign and store it inside a
variable.

```javascript
var dm = $.noConflict();

dm(document).ready(function(){
  dm("button").click(function(){
    dm("p").hide(1000);
  });
});
```

## AJAX

AJAX stands for Asynchronous Javascript and XML. AJAX allows the loading data in
the background and displaying it on the webpage without reloading the entire
page or refreshing it. It's quite useful and you see it every single day. Gmail
uses it, so does Facebook with your News Feed, Youtube, Portfolio sites, blogs.
We can do AJAX calls in both JavaScript and JQuery, each is a different method
but the end results are the same.

* [JavaScript AJAX](https://developer.mozilla.org/en-US/docs/AJAX/Getting_Started)
* [JQuery AJAX]​(http://api.jquery.com/jquery.ajax/)

These two links above will get you on the right track using AJAX. Happy Coding!

## Goodies

There are hundreds, if not thousands of JavaScript and jQuery plugins/libraries
available to aid yourdevelopment. Below is a list of some popular libraries:

* [Typeahead.js](http://twitter.github.io/typeahead.js/)
* [Windows.js](http://nick-jonas.github.io/windows/)
* [ScrollPath.js](http://joelb.me/scrollpath/)
* [ArcText.js](http://tympanus.net/codrops/2012/01/24/arctext-js-curving-text-with-css3-andjquery/)
* [Lettering.js](http://letteringjs.com/)
* [Gridster.js](http://gridster.net/)
* [CountDownTimer.js](https://www.npmjs.com/package/countdowntimer)
* [SocialShare.js](https://github.com/ritz078/socialShare.js)
* [AnimatedModal.js](http://joaopereirawd.github.io/animatedModal.js/)
* [Sortable.js](https://github.com/RubaXa/Sortable)
* [jQueryTween.js](http://thednp.github.io/jQueryTween/)
* [Lightcase.js](http://cornel.bopp-art.com/lightcase/)
* [Vivus.js](http://maxwellito.github.io/vivus/)
* [Wysiwyg.js](ttp://wysiwygjs.github.io/)
* [3D Responsive Scroll](https://github.com/nickavignone/responsive_3dfoldscroll)

## References

* W3schools.com, (2016). JavaScript Tutorial. [online] Available at:
  http://www.w3schools.com/js/default.asp [Accessed 15 Feb. 2016].
* jquery.org, j. (2016). jQuery. [online] Jquery.com. Available at:
  http://jquery.com/ [Accessed 15 Feb. 2016].
* Mozilla Developer Network, (2016). JavaScript Tutorial. [online] Available at:
  https://developer.mozilla.org/en­US/docs/Web/JavaScript/Reference
  [Accessed 20 Feb. 2016].
* McFarland, David Sawyer, and David Sawyer McFarland. Javascript & Jquery.
  Sebastopol, Calif.: O'Reilly, 2011. Print.
  Pehlivanian, Ara, and Don Nguyen. Jump Start Javascript. Collingwood, Vic.
  SitePoint Pty. Ltd., 2013. Print.
