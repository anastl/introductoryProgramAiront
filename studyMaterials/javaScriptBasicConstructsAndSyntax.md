# JavaScript  

It’s a scripting language that enables you to create dynamically updating content, control multimedia, etc. JavaScript is a lightweight and dynamic interpreted language, used to create client-side dynamic pages. It is an open-source and cross-platform language. It allows implicit type conversion.  

## Comments
* // Single line comment
* /* Multiple  
lines comment */  

## How to add it to a page?
Both internal and external Javascript can go inside the ``<head>`` or the ``<body>`` tag.   
### Internal JavaScript  
```
<script>  
    // JavaScript code goes here  
</script>
```

### External JavaScript
``<script src="index.js" type="text/javascript" defer > </script>``  

## Variable declaration
* const: to declare constant variables, block scoped
* let: to declare non-constant variables, block scoped
* var: also allows to declare non-constant variables but allows multiple declarations and it’s not scoped. Deprecated.  

### Naming convention
#### Functions and variables
* isProperty for booleans
* getSomething for returning functions
* doSomething for non-returning functions
* they are always camel-cased and start with a letter  

## JavaScript Operators
### Arithmetic
* \+
* \*
* \-
* /
* %
### Assignment
* =
* +=
* -=
* /=
* *=
* %=  

## JavaScript Data Types  
### Primitives
* String 
    * Let name = “Ana”
* Integer ( and BigInt )
    * Let age = 21
* Boolean
    * isWoman = true
* Undefined
    * Set by JavaScript
* Null
    * Set by the programmer
* Symbol  

### Non-primitives
* Arrays
    * const ages = [ 19, 21, 23, 25, 28, 30, 31 ]
* Objects
    * const person = { name: ‘Ana’, age: 21, isWoman: true }
* Sets and WeakSets
* Maps and WeakMaps  

## Equality and comparisons  
* Strict equals ( === )
    * Compares values AND type 
    * Only on primitive types
* Loose equals ( == )
    * Only on primitive types
* Object.is() === true if:
    * both undefined
    * both null
    * both true or both false
    * both strings of the same length with the same characters in the same order
    * both the same object (meaning both values reference the same object in memory)
    * both BigInts with the same numeric value
    * both symbols that reference the same symbol value
    * both numbers and
    * both +0
    * both -0
    * both NaN
    * or both non-zero, not NaN, and have the same value

# Bibliography
* [ Developer Mozilla](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/What_is_JavaScript)  
* [ Developer Mozilla - is it still part of your lifetime ](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/is)  