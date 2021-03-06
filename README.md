# Front-end Job Interview Questions

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
  1. Minimize HTTP Requests
  2. Minify Resources
  3. Optimize CSS Delivery
* If you jumped on a project and they used tabs and you used spaces, what would you do?
  I would switch to tabs in order to keep consistency throughout the project. 
* Describe how you would create a simple slideshow page.
* If you could master one technology this year, what would it be?:
  React
* Explain the importance of standards and standards bodies.
* What is Flash of Unstyled Content? How do you avoid FOUC?
* Explain what ARIA and screenreaders are, and how to make a website accessible.
* Explain some of the pros and cons for CSS animations versus JavaScript animations.
* What does CORS stand for and what issue does it address?:
  Cross Orign Resource Sharing and is used to get around the browsers same-origin policy. For security purposes, a browser won't load requests for resources to other domains when those requests are initated by scripts.

#### HTML Questions:

* What does a `doctype` do?
	The doctype declaration should be the very first thing in an HTML document, before the tag. The doctype declaration is not an HTML     tag; it is an instruction to the web browser about what version of the markup language the page is written in. The doctype declaration  refers to a Document Type Definition (DTD)
  
* What's the difference between full standards mode, almost standards mode and quirks mode?
		:quirks mode is a technique used by some web browsers for the sake of maintaining backward compatibility with web pages designed for Internet Explorer 5 and earlier, instead of strictly complying with W3C and IETF standards in standards mode. Standards Mode: the behavior described is same as described by HTML and CSS specifications. Most of the modern browsers uses full standard mode.
  
* What's the difference between HTML and XHTML?
  
	HTML:

	Start tags are not required for every element.
	End tags are not required for every element.
	Only void elements such as br, img, and link may be “self-closed” with />.
	Tags and attributes are case-insensitive.
	Attributes do not need to be quoted.
	Some attributes may be empty (such as checked and disabled).
	Special characters, or entities, do not have to be escaped.
	The document must include an HTML5 DOCTYPE

	XHTML:

	All elements must have a start tag.
	Non-void elements with a start tag must have an end tag (p and li, for example).
	Any element may be “self-closed” using />.
	Tags and attributes are case sensitive, typically lowercase.
	Attribute values must be enclosed in quotes.
	Empty attributes are forbidden (checked must instead be checked="checked" or checked="true").
	Special characters must be escaped using character entities. 
  
* Are there any problems with serving pages as `application/xhtml+xml`?
  : It will more than likely mess up the page for anyone still using older versions of IE.
  
* How do you serve a page with content in multiple languages?
  :By changing the lang attribute on the html element.
  
* What kind of things must you be wary of when design or developing for multilingual sites?
  :Properly localizing content for different audiences based on their location, as well as allowing for a user to easily change their country/language.

* What are `data-` attributes good for?
 	Storing data in HTML for DOM parsing, or other ways of keeping track of information.

* Consider HTML5 as an open web platform. What are the building blocks of HTML5?
	<article>
	<aside>
	<audio>
	<canvas>
	<figcaption>
	<figure>
	<footer>
	<header>
	<hgroup>
	<output>
	<section>
	<video>

* Describe the difference between a `cookie`, `sessionStorage` and `localStorage`.
	Cookie:

	Max size of 4093 bytes
	Can set expiration date
	Sent on every request
	sessionStorage:

	Max size of 2.5MBs+ depending on browser
	Stored in browser and not sent with every request
	If you close a tab using sessionStorage, open a new tab, or exit the browser - you'll lose that specific sessionStorage data.
	localStorage:

	Max size of 2.5MBs+ depending on browser
	Stored in browser and not sent with every request
	Will persist if browser/tabs are closed.

* Describe the difference between `<script>`, `<script async>` and `<script defer>`.

 	A regular <script> tag will block rendering of the page, and the page will not continue to load until the script finishes.

	<script async> will run the script asynchronously, meaning that it will not block rendering, but will run as soon as the script is available. This is usually intended for CDN files, or other such files, which do not change the page structure.

	<script defer> will defer the script to run after the page is done parsing and before an onload event.
  
* Why is it generally a good idea to position CSS `<link>`s between `<head></head>` and JS `<script>`s just before `</body>`? Do you know any exceptions?
	You usually put the <link> tags in between the <head> to prevent Flash of Unstyled Content which gives the user something to look at while the rest of the page is being parsed.

	Since Javascript blocks rendering by default, and the DOM and CSSOM construction can be also be delayed, it is usually best to keep scripts at the bottom of the page.

	Exceptions are if you grab the scripts asynchronously, or at least defer them to the end of the page.
  
* What is progressive rendering?
	With HTML progressive rendering is chunking the HTML into separate bits and loading each block as it's finished. Usually, the backend code loads the HTML at once, but if you flush after finishing one part of the structure, it can be rendered immediately to the page.

* Why you would use a `srcset` attribute in an image tag? Explain the process the browser uses when evaluating the content of this attribute.
	In short, Srcset is a new attribute which allows you to specify different kind of images for different screen-sizes/orientation/display-types. The usage is really simple, you just provide a lot of different images separating them with a comma like this: <img src="image.jpg" alt="image" srcset="<img> <descriptor>, ..., <img_n> <descriptor_n>">.
  
* Have you used different HTML templating languages before?
	Nope

#### CSS Questions:

* What is the difference between classes and IDs in CSS?:
  Unlike the id selector, the class selector is most often used on several elements. This allows you to set a particular style for many HTML elements with the same class. The class selector uses the HTML class attribute, and is defined with a "." id is used when we have to apply CSS property to one attribute only.
  
* What's the difference between "resetting" and "normalizing" CSS? Which would you choose, and why?:
  1. resetting: CSS resets aim to remove all built-in browser styling. Standard elements like h1 - h6, p, strong, em end up looking exactly alike, having no decoration at all. You're then supposed to add all decoration yourself.
  2. normalizing: aims to make built-in browser styling consistent across browsers. Elements like h1 - h6 will appear bold, larger et cetera in a consistent way across browsers. You're then supposed to add only the difference in decoration your design needs.
  
* Describe Floats and how they work.:
  There are left, right and none for float. Each value indicates how an element should float. When float is set, each element will get out of its normal flow and will be shifted to the specified direction, until it gets its container or another floated element.
  
* Describe z-index and how stacking context is formed.
  z-index tells how elements should be stacked in a screen. Stacking context can be formed in several situations, but most famously, by a root element and positioned elements. In each stacking context, z-index will be calculated separately for its children and will stack the children in ascending order.

* Describe BFC(Block Formatting Context) and how it works.
  BFC is a part of rendering a webpage. It's used to determine from which positioning and clearing should be done. The context is created by several ways, but the most famously, by a root element, float, positioned elements.
  
* What are the various clearing techniques and which is appropriate for what context?
  
* Explain CSS sprites, and how you would implement them on a page or site.
CSS sprite is combining multiple images into a merged one image and use CSS to render each of them properly for each element.

It's usually implemented using background: url(...) x-axis y-axis;, or both background-image and background-position.

* What are your favourite image replacement techniques and which do you use when?

* How would you approach fixing browser-specific styling issues?

* How do you serve your pages for feature-constrained browsers?

  * What techniques/processes do you use?
  
* What are the different ways to visually hide content (and make it available only for screen readers)?

* Have you ever used a grid system, and if so, what do you prefer?
Yes, Bootstrap, Materialize, Bulma. I prefer Bootstrap.

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

* What differences =, ==, === :
  = : assigns a variable,
  ==: compares values,
  ===: compares values and types
  
 * const vs. let
  const: cannot be reassigned 
  let: can reassign value as many times as you want
  
* Explain event delegation:
  Event delegation refers to the process of using event propagation (bubbling) to handle events at a higher level in the DOM than the element on which the event originated. It allows us to attach a single event listener for elements that exist now or in the future.
  
* Explain how `this` works in JavaScript
* Explain how prototypal inheritance works
* What do you think of AMD vs CommonJS?
* Explain why the following doesn't work as an IIFE: `function foo(){ }();`.
  * What needs to be changed to properly make it an IIFE?
* What's the difference between a variable that is: `null`, `undefined` or undeclared?
  null: you set the value of the variable to null
  undefined: when you don't set a value, it gives a placeholder of undefined
  * How would you go about checking for any of these states?
* What is a closure, and how/why would you use one?
* Can you describe the main difference between a `forEach` loop and a `.map()` loop and why you would pick one versus the other?
* What's a typical use case for anonymous functions?
* How do you organize your code? (module pattern, classical inheritance?)
* What's the difference between host objects and native objects?
* Difference between: `function Person(){}`, `var person = Person()`, and `var person = new Person()`?
* What's the difference between `.call` and `.apply`?
* Explain `Function.prototype.bind`.
* When would you use `document.write()`?
* What's the difference between feature detection, feature inference, and using the UA string?
* Explain Ajax in as much detail as possible.
* What are the advantages and disadvantages of using Ajax?
* Explain how JSONP works (and how it's not really Ajax).
* Have you ever used JavaScript templating?
  * If so, what libraries have you used?
* Explain "hoisting".
* Describe event bubbling.
* What's the difference between an "attribute" and a "property"?
* Why is extending built-in JavaScript objects not a good idea?
* Difference between document load event and document DOMContentLoaded event?
* What is the difference between `==` and `===`?
* Explain the same-origin policy with regards to JavaScript.
* Make this work:
```javascript
duplicate([1,2,3,4,5]); // [1,2,3,4,5,1,2,3,4,5]
```
* Why is it called a Ternary expression, what does the word "Ternary" indicate?
* What is `"use strict";`? what are the advantages and disadvantages to using it?
* Create a for loop that iterates up to `100` while outputting **"fizz"** at multiples of `3`, **"buzz"** at multiples of `5` and **"fizzbuzz"** at multiples of `3` and `5`
* Why is it, in general, a good idea to leave the global scope of a website as-is and never touch it?
* Why would you use something like the `load` event? Does this event have disadvantages? Do you know any alternatives, and why would you use those?
* Explain what a single page app is and how to make one SEO-friendly.
* What is the extent of your experience with Promises and/or their polyfills?
* What are the pros and cons of using Promises instead of callbacks?
* What are some of the advantages/disadvantages of writing JavaScript code in a language that compiles to JavaScript?
* What tools and techniques do you use debugging JavaScript code?
* What language constructions do you use for iterating over object properties and array items?
* Explain the difference between mutable and immutable objects.
  * What is an example of an immutable object in JavaScript?
  * What are the pros and cons of immutability?
  * How can you achieve immutability in your own code?
* Explain the difference between synchronous and asynchronous functions.
* What is event loop?
  * What is the difference between call stack and task queue?
* Explain the differences on the usage of `foo` between `function foo() {}` and `var foo = function() {}`
* What are the differences between variables created using `let`, `var` or `const`?

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
```

*Question: What will be the output of the code below?*
```javascript
console.log(0.1 + 0.2 == 0.3);
```

*Question: How would you make this work?*
```javascript
add(2, 5); // 7
add(2)(5); // 7
```

*Question: What value is returned from the following statement?*
```javascript
"i'm a lasagna hog".split("").reverse().join("");
```

*Question: What is the value of `window.foo`?*
```javascript
( window.foo || ( window.foo = "bar" ) );
```

*Question: What is the outcome of the two alerts below?*
```javascript
var foo = "Hello";
(function() {
  var bar = " World";
  alert(foo + bar);
})();
alert(foo + bar);
```

*Question: What is the value of `foo.length`?*
```javascript
var foo = [];
foo.push(1);
foo.push(2);
```

*Question: What is the value of `foo.x`?*
```javascript
var foo = {n: 1};
var bar = foo;
foo.x = foo = {n: 2};
```

*Question: What does the following code print?*
```javascript
console.log('one');
setTimeout(function() {
  console.log('two');
}, 0);
console.log('three');
```

*Question: What is the difference between these four promises?*
```javascript
doSomething().then(function () {
  return doSomethingElse();
});

doSomething().then(function () {
  doSomethingElse();
});

doSomething().then(doSomethingElse());

doSomething().then(doSomethingElse);
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
