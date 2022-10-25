# Hoisting
JavaScript Hoisting refers to the process whereby the interpreter appears to move the declaration of functions, variables or classes to the top of their scope, prior to execution of the code, thereby allowing functions to be safely used in code before they are declared.  

# Scope
The scope is the current context of execution in which values and expressions are "visible" or can be referenced. If a variable or expression is not in the current scope, it will not be available for use. Scopes can also be layered in a hierarchy, so that child scopes have access to parent scopes, but not vice versa.  
## Types of scopes
* Global scope
* Module scope
* Function scope
* Block scope (for `let` and `const`)

# Strict
JavaScript's strict mode is a way to opt in to a restricted variant of JavaScript, thereby implicitly opting-out of "sloppy mode". It is invoked by writing `"use strict";` at the top of a script and has siffernt semantics from normal JavaScript.
## Differences from normal JavaScript
* Eliminates some JavaScript silent errors by changing them to throw errors.
* Fixes mistakes that make it difficult for JavaScript engines to perform optimizations: strict mode code can sometimes be made to run faster than identical code that's not strict mode.
* Prohibits some syntax likely to be defined in future versions of ECMAScript.

# DOM
A web page is a document that can be either displayed in the browser window or as the HTML source. In both cases, it is the same document but the Document Object Model (DOM) representation allows it to be manipulated.  
The DOM is not part of the JavaScript language, but is instead a Web API used to build websites. The core DOM defines the entities describing any document and the objects within it. This is expanded upon as needed by other APIs that add new features and capabilities to the DOM. The DOM is not a programming language, but without it, the JavaScript language wouldn't have any model or notion of web pages.  

# Bibliography
* [MDN - Introduction to DOM](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction)
* [MDN - Hoisting](https://developer.mozilla.org/en-US/docs/Glossary/Hoisting)
* [MDN - Strict mode](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Strict_mode)
* [MDN - Scope](https://developer.mozilla.org/en-US/docs/Glossary/Scope)