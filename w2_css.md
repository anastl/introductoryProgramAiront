# CSS
Cascading Style Sheets (CSS) is a stylesheet language used to describe the presentation of a document written in HTML or XML. It describes how elements should be rendered on screen, on paper, in speech, or on other media. CSS is what you use to selectively style HTML elements.  

## Importing external rulesets
```
<head>
    <link href=”<url || path>” rel="stylesheet" />
    …
</head>
```  

## CSS rulesets
They are what create a CSS stylesheet and are comprised by:
* Selector: The element(s) to style.
    * Type selectors ( div )
    * Class selectors ( .className )
    * Id selectors ( not recommended )
    * Attribute selectors ( [attr=value] )
    * Pseudo-classes and pseudo-elements ( :hover, ::first-line )
    * Combinators 
    * Grouping selectors ( , )
* Declaration: It specifies which of the element's properties you want to style. 
* Properties: These are ways in which you can style an HTML element. 
* Property value  

## CSS syntax
* Apart from the selector, each ruleset must be wrapped in curly braces. ({})
* Within each declaration, you must use a colon (:) to separate the property from its value or values.
* Within each ruleset, you must use a semicolon (;) to separate each declaration from the next one.  

## The Box Model
When laying out a document, the browser's rendering engine represents each element as a rectangular box according to the standard CSS basic box model. CSS determines the size, position, and properties (color, background, border size, etc.) of these boxes. The box model describes how these elements work together to create a box as displayed by CSS.  
Every box is composed of four parts (or areas), defined by their respective edges: the **content** edge, **padding** edge, **border** edge, and **margin** edge.

### Block boxes
* The box will break onto a new line.
* The width and height properties are respected.
* Padding, margin and border will cause other elements to be pushed away from the box.
* The box will extend in the inline direction to fill the space available in its container. In most cases, the box will become as wide as its container, filling up 100% of the space available.  

### Inline boxes
* The box will not break onto a new line.
* The width and height properties will not apply.
* Vertical padding, margins, and borders will apply but will not cause other inline boxes to move away from the box.
* Horizontal padding, margins, and borders will apply and will cause other inline boxes to move away from the box.

## Specificity
The specificity algorithm calculates the weight of a CSS selector to determine which rule from competing CSS declarations gets applied to an element.  

### How is it calculated?
The weight is determined by the number of selectors of each weight category in the selector matching the element (or pseudo-element). If there are two or more declarations providing different property values for the same element, the declaration value in the style block having the matching selector with the greatest algorithmic weight gets applied.  
The algorithm is a three column value of three categories or weights:  
`ID - CLASS - TYPE`  
The three columns are created by counting the number of selector components for each selector weight category in the selectors that match the element. Once the specificity values of the relevant selectors are determined, the number of selector components in each column are compared, from left to right.  

### Selector weight category
* ID column: Includes only ID selectors, such as `#example`. For each ID in a matching selector, add 1-0-0 to the weight value.
* CLASS column

    * Includes class selectors, such as `.myClass`, 
    * attribute selectors like `[type="radio"]` and `[lang|="fr"]`, 
    * and pseudo-classes, such as `:hover`, `:nth-of-type(3n)`, and `:required`. 
    * For each class, attribute selector, or pseudo-class in a matching selector, add 0-1-0 to the weight value.
* TYPE column:
    * Includes type selectors, such as `p`, `h1`, and `td`, 
    * and pseudo-elements like `::before`, `::placeholder`, and all other selectors with double-colon notation. 
    * For each type or pseudo-element in a matching selector, add 0-0-1 to the weight value.
* No value: The universal selector (`*`) and the pseudo-class `:where()` and its parameters aren't counted when calculating the weight so their value is 0-0-0, but they do match elements. These selectors do not impact the specificity weight value.
* Combinators, such as `+`, `>`, `~`, `" "` (space), and `||`, may make a selector more specific in what is selected but they don't add any value to the specificity weight.
* The negation pseudo-class, `:not()`, itself has no weight. Neither do the `:is()` or the `:has()` pseudo-classes. The parameters in these selectors, however, do. The values of both come from the parameter in the list of parameters that has the highest specificity.  

### The !important keyword
CSS declarations marked as important override any other declarations within the same cascade layer and origin. When conflicting declarations from the same origin and cascade layer with the !important flag are applied to the same element, the declaration with a greater specificity is applied.  

# Bilbiography
* [MDN - Cascading Stylesheets](https://developer.mozilla.org/en-US/docs/Web/CSS)
* [MDN - CSS basics](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/CSS_basics)
* [MDN - CSS selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors)
* [MDN - Introduction to the CSS box model](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Box_Model/Introduction_to_the_CSS_box_model)
* [MDN - The box model](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/The_box_model)
* [MDN - CSS box model](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Box_Model)
* [MDN - Specificity](https://developer.mozilla.org/en-US/docs/Web/CSS/Specificity)