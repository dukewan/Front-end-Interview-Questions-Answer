# Front-end Job Interview Questions with Answers

This file contains a number of front-end interview questions that can be used when vetting potential candidates. It is by no means recommended to use every single question here on the same candidate (that would take hours). Choosing a few items from this list should help you vet the intended skills you require.

**Note:** Keep in mind that many of these questions are open-ended and could lead to interesting discussions that tell you more about the person's capabilities than a straight answer would.

## Table of Contents

  1. [General Questions](#general-questions)
  1. [HTML Questions](#html-questions)
  1. [CSS Questions](#css-questions)
  1. [JS Questions](#js-questions)
  1. [Testing Questions](#testing-questions)
  1. [Performance Questions](#performance-questions)
  1. [Network Questions](#network-questions)
  1. [Coding Questions](#coding-questions)
  1. [Fun Questions](#fun-questions)

## Getting Involved

  1. [Contributors](#contributors)
  1. [How to Contribute](https://github.com/h5bp/Front-end-Developer-Interview-Questions/blob/master/CONTRIBUTING.md)
  1. [License](https://github.com/h5bp/Front-end-Developer-Interview-Questions/blob/master/LICENSE.md)

#### General Questions:

* What did you learn yesterday/this week?
* What excites or interests you about coding?
* What is a recent technical challenge you experienced and how did you solve it?
* What UI, Security, Performance, SEO, Maintainability or Technology considerations do you make while building a web application or site?
* Talk about your preferred development environment.
* Which version control systems are you familiar with?
* Can you describe your workflow when you create a web page?
* If you have 5 different stylesheets, how would you best integrate them into the site?
* Can you describe the difference between progressive enhancement and graceful degradation?
* How would you optimize a website's assets/resources?
* How many resources will a browser download from a given domain at a time?
  * What are the exceptions?
* Name 3 ways to decrease page load (perceived or actual load time).
* If you jumped on a project and they used tabs and you used spaces, what would you do?
* Describe how you would create a simple slideshow page.
* If you could master one technology this year, what would it be?
* Explain the importance of standards and standards bodies.
* What is Flash of Unstyled Content? How do you avoid FOUC?
* Explain what ARIA and screenreaders are, and how to make a website accessible.
* Explain some of the pros and cons for CSS animations versus JavaScript animations.
* What does CORS stand for and what issue does it address?

#### HTML Questions:

* What does a `doctype` do?
> + DOCTYPE, document type declaration, associated our webpage document with a DTD. For HTML1 to HTML4.
> + In HTML5, the doctype is only for triggering the standard mode of browser.
> + [#ref](https://en.wikipedia.org/wiki/Document_type_declaration)

* What's the difference between full standards mode, almost standards mode and quirks mode?
> + Full standards mode: follow the HTML and CSS specifications
> + Almost standards mode: only a few quirks implemented
> + Quirks mode: Follow the behavior for Navigator 4 and Internet Explorer 5.
> + [#ref](https://developer.mozilla.org/en-US/docs/Quirks_Mode_and_Standards_Mode)

* What's the difference between HTML and XHTML?
> + XHTML are HTML4 applications of XML
> + All elements in XHTML should be closed. `<br/>`
> + HTML: attribute minimization `<option selected>`, element minimization `<tbody>` can be inferred
> + XHTML: case sensitive
> + XHTML: no `document.write()` JavaScript function
> + [#ref](https://en.wikipedia.org/wiki/XHTML)

* Are there any problems with serving pages as `application/xhtml+xml`?
> + Internet Explorer 8 and earlier will ask user to save the pages instead of display the webpage.
> + [#ref](https://en.wikipedia.org/wiki/XHTML)

* How do you serve a page with content in multiple languages?
> + Host translated webpages in server.
> + Recognize the browser's language request.
> + Serve the corresponding webpage.
> + [#ref](http://www.pro-tekconsulting.com/blog/how-do-you-serve-a-page-with-content-in-multiple-languages/)

* What kind of things must you be wary of when design or developing for multilingual sites?
> + How will users to be directed to their native language? Allow user to switch? Redirect according to IP? Language based url or domain?
> + How to handle text in image?
> + Restrict word/sentence length.
> + Formatting Dates. Different culture have different formats.
> + [#ref](https://www.quora.com/What-kind-of-things-one-should-be-wary-of-when-designing-or-developing-for-multilingual-sites)

* What are `data-` attributes good for?
> + `data-` attributes allow us to store extra data on standard, semantic HTML elements without other hacks such as non-standard attributes, extra properties on DOM.
> + JS access of `data-columns`:
>
```javascript
var article = document.getElementById('electriccars');
article.dataset.columns 
```
> + [#ref](https://developer.mozilla.org/en-US/docs/Learn/HTML/Howto/Use_data_attributes)

* Consider HTML5 as an open web platform. What are the building blocks of HTML5?
> + more semantic markups `<section>` `<header>` `<nav>`
> + video and audio
> + canvas and SVG
> + geolocation API
> + Web Worker API
> + new data storage `session storage` `Indexed DB` `Web SQL`
> + [#ref](https://www.quora.com/Design-Consider-HTML5-as-an-open-web-platform-What-are-the-building-blocks-of-HTML5)

* Describe the difference between a `cookie`, `sessionStorage` and `localStorage`.
> + They are all stored at client side.
> + localStorage: stores data without expiration date, gets cleared only through JS or clearing browser data.
> + sessionStorage: similar to localStorage but expires when the browser is closed (not tab)
> + cookie: stores data that should be sent back to server with subsequent requests. Has expiration duration, can be set by both server and client.
> + [#ref](https://www.quora.com/What-is-the-difference-between-sessionstorage-localstorage-and-Cookies) 

* Describe the difference between `<script>`, `<script async>` and `<script defer>`.
> + `<script>`: external and inline scripts are fetched and executed immediately, before the browser continues to parse the page.
> + `<script async>`: indicate the browser should, if possible, execute the script asynchronously. No effect on inline scripts.
> + `<script defer>`: indicate the browser that the script should be executed after the document has been parsed, but before firing DOMContentLoaded. Should only be used on external scripts.
> + [#ref](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script)

* Why is it generally a good idea to position CSS `<link>`s between `<head></head>` and JS `<script>`s just before `</body>`? Do you know any exceptions?
> + This allows the browser to load CSS files first and let the user feel the page was loaded faster than it really was. It provides a better user experience. If the `<script>` tags are put just before `</body>`, they won't block the rendering of browser.
> + [#ref](http://uxmovement.com/content/why-you-should-place-style-sheets-before-scripts/)
> + Exceptions: when the HTML content and styles are generated by JS files?

* What is progressive rendering?
> + Render content for display as quickly as possible. Examples:
> + Lazy loading of images: use JS to load an image when it comes to viewport instead of loading all images at page load. 
> + Prioritizing visible content: include only the minimum css/content/scripts necessary for quickly display and then load resources and content using JS.
> + [#ref](http://stackoverflow.com/questions/33651166/what-is-progressive-rendering)

* Have you used different HTML templating languages before?
> + Mustache: use `{{}}`
> 
```javascript
//<script id="template" type="x-tmpl-mustache">
// <p>Use the <strong>{{power}}</strong>, {{name}}!</p>
//</script>
//Grab the inline template
var template = document.getElementById('template').innerHTML;
//Parse it (optional, only necessary if template is to be used again)
Mustache.parse(template);
//Render the data into the template
var rendered = Mustache.render(template, {name: "Luke", power: "force"});
//Overwrite the contents of #target with the rendered HTML
document.getElementById('target').innerHTML = rendered;
```
> + HandleBars: 
> 
```javascript
//<script id="template" type="text/x-handlebars-template">
//  <p>Use the <strong>{{power}}</strong>, {{name}}!</p>
//</script>
//Grab the inline template
var template = document.getElementById('template').innerHTML;
//Compile the template
var compiled_template = Handlebars.compile(template);
//Render the data into the template
var rendered = compiled_template({name: "Luke", power: "force"});
//Overwrite the contents of #target with the renderer HTML
document.getElementById('target').innerHTML = rendered;
```
> + [#ref](https://www.sitepoint.com/overview-javascript-templating-engines/)

#### CSS Questions:

* What is the difference between classes and IDs in CSS?
> + ID: unique, each element can only have one ID, each page can only have one element with this ID.
> + class: no unique, each element can have multiple classes, each page can have multiple elements with this class.
> + ID has higher specificity than class.
> + [#ref1](https://css-tricks.com/the-difference-between-id-and-class/)
> + [#ref2](https://developer.mozilla.org/en-US/docs/Web/CSS/Specificity)

* What's the difference between "resetting" and "normalizing" CSS? Which would you choose, and why?
> + Resetting: remove all built-in browser styling. All elements look exactly alike.
> + Normalizing: aims to make built-in browser styling consistent across browsers. You only need to add difference in decoration.
> + I will choose Normalizing. Since it enables me to write CSS faster and fewer.
> + [#ref](http://stackoverflow.com/questions/6887336/what-is-the-difference-between-normalize-css-and-reset-css/6896881#6896881)

* Describe Floats and how they work.
> + When an element is floated, it will be taken out from the normal flow and shifted to the left or right until it hits the edge of its containing box or another floated element.
> + [#ref](https://developer.mozilla.org/en-US/docs/Web/CSS/float)

* Describe z-index and how stacking context is formed.
> + z-index: imaginary z-axis relative to the user who is assumed to be facing the viewport or the webpage
> + stacking context: positioning and assigning a z-index value to a HTML element creates a stacking context(as does assigning non-full opacity)
> + [#ref](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Positioning/Understanding_z_index/The_stacking_context)

* Describe BFC(Block Formatting Context) and how it works.
> + Block Formatting Context: a part of a visual CSS rendering of a Web page. It is the region in which the layout of block boxes occurs and in which floats interact with others.
> + [#ref](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Block_formatting_context)

* What are the various clearing techniques and which is appropriate for what context?
* Explain CSS sprites, and how you would implement them on a page or site.
* What are your favourite image replacement techniques and which do you use when?
* How would you approach fixing browser-specific styling issues?
* How do you serve your pages for feature-constrained browsers?
  * What techniques/processes do you use?
* What are the different ways to visually hide content (and make it available only for screen readers)?
* Have you ever used a grid system, and if so, what do you prefer?
* Have you used or implemented media queries or mobile specific layouts/CSS?
* Are you familiar with styling SVG?
* How do you optimize your webpages for print?
* What are some of the "gotchas" for writing efficient CSS?
* What are the advantages/disadvantages of using CSS preprocessors?
  * Describe what you like and dislike about the CSS preprocessors you have used.
* How would you implement a web design comp that uses non-standard fonts?
* Explain how a browser determines what elements match a CSS selector.
* Describe pseudo-elements and discuss what they are used for.
* Explain your understanding of the box model and how you would tell the browser in CSS to render your layout in different box models.
* What does ```* { box-sizing: border-box; }``` do? What are its advantages?
* List as many values for the display property that you can remember.
* What's the difference between inline and inline-block?
* What's the difference between a relative, fixed, absolute and statically positioned element?
* The 'C' in CSS stands for Cascading.  How is priority determined in assigning styles (a few examples)?  How can you use this system to your advantage?
* What existing CSS frameworks have you used locally, or in production? How would you change/improve them?
* Have you played around with the new CSS Flexbox or Grid specs?
* How is responsive design different from adaptive design?
* Have you ever worked with retina graphics? If so, when and what techniques did you use?
* Is there any reason you'd want to use `translate()` instead of *absolute positioning*, or vice-versa? And why?

#### JS Questions:

* Explain event delegation
> + Event delegation: allows us to add a single event listener, to a parent element, that will fire for all descendants matching a selector, whether those descendants exist now or are added in the future.
> + [#ref](https://learn.jquery.com/events/event-delegation/)

* Explain how `this` works in JavaScript
> + Only consider strict mode below:
> + Global Context: refers to the global object (window)
> + Function Context: depends on how the function is called.
>   + call and apply: this can be bound to a particular object in the call
>   + bind: this is permanently bound to the first argument of bind
> + Arrow functions: this is set lexically, it's set to the enclosing execution context's this (what it was when it was created)
> + As an object method: When a function is called as a method of an object, its this is set to the object the method is called on.
> + As a constructor: When a function is used as a constructor (with the new keyword), its this is bound to the new object being constructed.
> + As a DOM event handler: When a function is used as an event handler, its this is set to the element the event fired from.
> + [#ref](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this)

* Explain how prototypal inheritance works
> + JavaScript objects are dynamic "bags" of properties. JavaScript objects have a link to a prototype object. When trying to access a property of an object, the property will not only be sought on the object but on the prototype of the object, the prototype of the prototype, and so on until either a property with a matching name is found or the end of the prototype chain is reached.
> + [#ref](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain)

* What do you think of AMD vs CommonJS?
> + CommonJS is aimed at helping server side development.
> + AMD is better for browser use, supports for asynchronous module loading. Define a set of dependencies.
> + [#ref](https://auth0.com/blog/javascript-module-systems-showdown/)

* Explain why the following doesn't work as an IIFE: `function foo(){ }();`.
  + What needs to be changed to properly make it an IIFE?
  
  > + This situation will treat `function` as a declaration statement instead of expression.
  > + IIFE(Immediately-invoked function expressions)
  > + `(function () { … })();`
  > + `(function () { … }()); `
  > + `!function () { … }();`
  > + `+function () { … }();`, etc
  > + In contexts where an expression is expected, wrapping in parentheses is not necessary: `var f = function () { … }();`
  > + [#ref](https://en.wikipedia.org/wiki/Immediately-invoked_function_expression)
  
* What's the difference between a variable that is: undeclared, `undefined` or `null`?
  * How would you go about checking for any of these states?
  
  > + `undeclared` variables don’t even exist. A variable is undeclared when it does not use the var keyword. It gets created on the global object. In ECMAScript 5 strict mode, assigning to an undeclared variable throws an error.
  > + `undefined` variables exist, but don’t have anything assigned to them. `variable === undefined` `typeof variable === 'undefined'`
  > + `null` variables exist and have null assigned to them. `variable === null`
  > + [#ref1](http://lucybain.com/blog/2014/null-undefined-undeclared/)
  > + [#ref2](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/var)
  
* What is a closure, and how/why would you use one?
> Closures are inner functions inside of an outer function. They have their own local scope and has access to outer function's scope, parameters. And they also have access to global variable.
> Why: to deal with scope issues. Because ES5 JavaScript is Function-level scope instead of block-level scope.
> How: Number counter example.
> + [#ref1](https://medium.com/@rlynjb/js-interview-question-what-is-a-closure-and-how-why-would-you-use-one-b6fd45ea95f6#.75gj2utgt)
> + [#ref2](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures)


* What's a typical use case for anonymous functions?
> Anonymous functions are function expressions rather than function declaration which are statements. Function expressions are more flexible, we can assign function to variables, object properties, pass them as as arguments to other functions and even write a simple one line code enclosed in any anonymous function.
> + [#ref](https://medium.com/@rlynjb/js-interview-question-what-s-a-typical-use-case-for-anonymous-functions-54cf547b2a0e#.3wzipi5hr)

* How do you organize your code? (module pattern, classical inheritance?)
* What's the difference between host objects and native objects?
> + [#ref](http://stackoverflow.com/questions/7614317/what-is-the-difference-between-native-objects-and-host-objects)

* Difference between: `function Person(){}`, `var person = Person()`, and `var person = new Person()`?
> + [#ref](https://www.quora.com/In-Javascript-what-is-the-difference-between-function-Person-var-person-Person-var-person-new-Person)

* What's the difference between `.call` and `.apply`?
> + The difference is that apply lets you invoke the function with arguments as an array; call requires the parameters be listed explicitly. A useful mnemonic is "A for array and C for comma."
> + [#ref](http://stackoverflow.com/questions/1986896/what-is-the-difference-between-call-and-apply)

* Explain `Function.prototype.bind`.
> + Calling f.bind(someObject) creates a new function with the same body and scope as f, but where `this` occurs in the original function, in the new function it is permanently bound to the first argument of bind, regardless of how the function is being used.
> + [#ref](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this)

* When would you use `document.write()`?
> + [#ref](http://lucybain.com/blog/2015/js-document-write/)

* What's the difference between feature detection, feature inference, and using the UA string?
> + [#ref](http://stackoverflow.com/questions/20104930/whats-the-difference-between-feature-detection-feature-inference-and-using-th/20105161#20105161)

* Explain Ajax in as much detail as possible.
> + [#ref](http://stackoverflow.com/questions/22963610/ajax-explained-in-detail)

* What are the advantages and disadvantages of using Ajax?
> + [#ref](http://www.jscripters.com/ajax-disadvantages-and-advantages/)

* Explain how JSONP works (and how it's not really Ajax).
> + [#ref](http://lucybain.com/blog/2015/how-does-jsonp-work/)

* Have you ever used JavaScript templating?
  * If so, what libraries have you used?

* Explain "hoisting".
> + [#ref](http://lucybain.com/blog/2014/hoisting/)

* Describe event bubbling.
> + [#ref](http://lucybain.com/blog/2014/event-bubbling/)

* What's the difference between an "attribute" and a "property"?
> + DOM property and HTML attribute.
> + [#ref](What's the difference between an "attribute" and a "property"?)

* Why is extending built-in JavaScript objects not a good idea?
> + [#ref](http://lucybain.com/blog/2014/js-extending-built-in-objects/) 

* Difference between document load event and document DOMContentLoaded event?
> + [#ref](http://stackoverflow.com/questions/2414750/difference-between-domcontentloaded-and-load-events)

* What is the difference between `==` and `===`?
> + [#ref](http://stackoverflow.com/questions/359494/which-equals-operator-vs-should-be-used-in-javascript-comparisons)

* Explain the same-origin policy with regards to JavaScript.
> + [#ref](http://lucybain.com/blog/2014/same-origin-policy/)

* Make this work:
* 
```javascript
duplicate([1,2,3,4,5]); // [1,2,3,4,5,1,2,3,4,5]
```
> ```javascript
> function duplicate (a) { 
>   return a.concat(a);
> }
> ```

* Why is it called a Ternary expression, what does the word "Ternary" indicate?
> + [#ref](http://lucybain.com/blog/2014/js-ternary/)

* What is `"use strict";`? what are the advantages and disadvantages to using it?
> + [#ref](http://lucybain.com/blog/2014/js-use-strict/)

* Create a for loop that iterates up to `100` while outputting **"fizz"** at multiples of `3`, **"buzz"** at multiples of `5` and **"fizzbuzz"** at multiples of `3` and `5`
> ```javascript
> for (let i = 1; i <= 100; i++) {
      console.log(i)
      let m1 = i % 3
      let m2 = i % 5
      if (m1 === 0 && m2 === 0) {
        console.log('fizzbuzz')
      } else if (m1 === 0) {
        console.log('fizz')
      } else if (m2 === 0) {
        console.log('buzz')
      }
> }
> ```

* Why is it, in general, a good idea to leave the global scope of a website as-is and never touch it?
> + [#ref](http://lucybain.com/blog/2014/js-dont-touch-global-scope/)

* Why would you use something like the `load` event? Does this event have disadvantages? Do you know any alternatives, and why would you use those?
* Explain what a single page app is and how to make one SEO-friendly.
> + [#ref](https://kruschecompany.com/blog/post/seo-tips-and-tricks-for-single-page-web-applications)

* What is the extent of your experience with Promises and/or their polyfills?
> + need improve
> + [#ref](http://andrewyan.logdown.com/posts/643979-front-end-job-interview-questions)

* What are the pros and cons of using Promises instead of callbacks?
> + [#ref](https://www.quora.com/Are-there-any-advantages-to-using-callbacks-instead-of-promises)

* What are some of the advantages/disadvantages of writing JavaScript code in a language that compiles to JavaScript?
> + [#ref](http://workmonkey.com/front-end/advantagesdisadvantages-writing-javascript-code-language-compiles-javascript)

* What tools and techniques do you use debugging JavaScript code?
> VSCode
> Vue Dev Tool
> log

* What language constructions do you use for iterating over object properties and array items?
> Object: `let ... in ...`
> Array: `let ... of ...`

* Explain the difference between mutable and immutable objects.
  * What is an example of an immutable object in JavaScript?
  * What are the pros and cons of immutability?
  * How can you achieve immutability in your own code?
> + [#ref](https://wecodetheweb.com/2016/02/12/immutable-javascript-using-es6-and-beyond/)
  
* Explain the difference between synchronous and asynchronous functions.
> + [#ref](http://stackoverflow.com/questions/748175/asynchronous-vs-synchronous-execution-what-does-it-really-mean)

* What is event loop?
  * What is the difference between call stack and task queue?
> + [#ref](http://stackoverflow.com/questions/33874419/difference-between-call-stack-and-task-queue)

* Explain the differences on the usage of `foo` between `function foo() {}` and `var foo = function() {}`
> + [#ref](http://markdaggett.com/blog/2013/02/15/functions-explained/)

#### Testing Questions:

* What are some advantages/disadvantages to testing your code?
* What tools would you use to test your code's functionality?
* What is the difference between a unit test and a functional/integration test?
* What is the purpose of a code style linting tool?

#### Performance Questions:

* What tools would you use to find a performance bug in your code?
* What are some ways you may improve your website's scrolling performance?
* Explain the difference between layout, painting and compositing.

#### Network Questions:

* Traditionally, why has it been better to serve site assets from multiple domains?
* Do your best to describe the process from the time you type in a website's URL to it finishing loading on your screen.
* What are the differences between Long-Polling, Websockets and Server-Sent Events?
* Explain the following request and response headers:
  * Diff. between Expires, Date, Age and If-Modified-...
  * Do Not Track
  * Cache-Control
  * Transfer-Encoding
  * ETag
  * X-Frame-Options
* What are HTTP methods? List all HTTP methods that you know, and explain them.

#### Coding Questions:

*Question: What is the value of `foo`?*

```javascript
var foo = 10 + '20';
// '1020'
```


*Question: How would you make this work?*

```javascript
add(2, 5); // 7
add(2)(5); // 7
// answer
function add (a) {
  return function (b) {
    return a + b
  }
}
```

*Question: What value is returned from the following statement?*

```javascript
"i'm a lasagna hog".split("").reverse().join("");
// "i'm a lasagna hog".split("") => ["i", "'", "m", " ", "a", " ", "l", "a", "s", "a", "g", "n", "a", " ", "h", "o", "g"]
// "goh angasal a m'i"
```

*Question: What is the value of `window.foo`?*

```javascript
( window.foo || ( window.foo = "bar" ) );
// 'bar'
```

*Question: What is the outcome of the two alerts below?*

```javascript
var foo = "Hello";
(function() {
  var bar = " World";
  alert(foo + bar);
  // Hello World
})();
alert(foo + bar);
// Uncaught ReferenceError: bar is not defined
```

*Question: What is the value of `foo.length`?*

```javascript
var foo = [];
foo.push(1);
foo.push(2);
// 2
```

*Question: What is the value of `foo.x`?*

```javascript
var foo = {n: 1};
var bar = foo;
foo.x = foo = {n: 2};
// undefined
```

*Question: What does the following code print?*

```javascript
console.log('one');
setTimeout(function() {
  console.log('two');
}, 0);
console.log('three');
// one, three, two
```

#### Fun Questions:

* What's a cool project that you've recently worked on?
* What are some things you like about the developer tools you use?
* Who inspires you in the front-end community?
* Do you have any pet projects? What kind?
* What's your favorite feature of Internet Explorer?
* How do you like your coffee?


#### Contributors:

This document started in 2009 as a collaboration of [@paul_irish](https://twitter.com/paul_irish) [@bentruyman](https://twitter.com/bentruyman) [@cowboy](https://twitter.com/cowboy) [@ajpiano](https://twitter.com/ajpiano)  [@SlexAxton](https://twitter.com/slexaxton) [@boazsender](https://twitter.com/boazsender) [@miketaylr](https://twitter.com/miketaylr) [@vladikoff](https://twitter.com/vladikoff) [@gf3](https://twitter.com/gf3) [@jon_neal](https://twitter.com/jon_neal) [@sambreed](https://twitter.com/sambreed) and [@iansym](https://twitter.com/iansym).

It has since received contributions from over [100 developers](https://github.com/h5bp/Front-end-Developer-Interview-Questions/graphs/contributors).



