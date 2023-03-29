# Arrow Functions

## Learning Goals

- Review declaring a function using a function expression
- Declare a function using arrow syntax
- Describe situations where arrow functions are used

## Introduction

We've learned that there are multiple ways to write a function. There's the
classic way, _function declaration_. Then there are anonymous functions, which
can be expanded to named _function expressions_ and _immediately-invoked
function expressions_. There's also one more way we haven't covered yet -
**arrow functions**.

This style of function syntax expands on the function expression, providing a
more concise way to write them. In this lesson, we will learn about the **arrow
function** syntax and when to use it.

## Arrow Function Syntax

First, let's review the function expression syntax:

```js
const crossbow = function () {
  return "Bullseye!";
};
```

We declare a variable, then assign it an anonymous function expression using the
`function` keyword.

The arrow function syntax is similar, but it provides a shorthand way to declare
functions by utilizing an arrow `=>` instead of the `function` keyword:

```js
const crossbow () => {
  return "Bullseye!"
}
```

All we did was drop the `function` keyword and add an arrow `=>` between the
parameter list `()` and the function body `{}`, but it looks much more concise.
In fact, we can make this even shorter!

## Single Expression Arrow Functions

In cases where the function body consists of only one line of code, we can
define the whole function in a single line.

```js
const crossbow = () => "Bullseye!";
```

There are a couple of things to be aware of in the code above: first, note that
if the function body consists of a single expression, we no longer need to wrap
it in curly braces. Second, **when there are no braces, arrow functions have an
_implicit_ return**, i.e., they _automatically_ return the result of the
expression! **This is the only situation in which a JavaScript function doesn't
require _explicit return_ with the `return` keyword.**

Let's look at a mathematical function to see that more clearly.

```js
const multiplyByTwo = (x) => 2 * x;

multiplyByTwo(2); // => 4
```

We didn't have to explicitly tell the arrow function to return the result of
`2 * x`. It was implicitly returned due to being written in a single line
without `{}` braces.

**Implicit returns only applies to arrow functions with single line
expressions.** If we need to do more work than return a single expression, we'll
need `{}` to wrap the multiple lines of code, **and** we'll have to declare a
`return`. That sweet no-`return` syntax is only available if your function body
is one expression long.

```js
const multiplyByTwo = (x) => {
  console.log(`Multiplying ${x} by 2`);
  return 2 * x;
};

multiplyByTwo(2); // => 4
```

## The Single Parameter Specialty

Its compactness is the highlight of the arrow function syntax - and guess what,
we can go _even shorter_.

If your arrow function has only _one_ parameter, the `()` around it becomes
optional:

```js
const multiplyByTwo = (x) => 2 * x;
// is the same as
const multiplyByTwo = (x) => 2 * x;
```

This doesn't just apply for single line expressions, full-bodied arrow functions
can utilize this feature as well.

```js
const multiplyByTwo = (x) => {
  console.log(`Multiplying ${x} by 2`);
  return 2 * x;
};

multiplyByTwo(2); // => 4
```

## Conclusion

In the past two lessons, we've seen two different styles for declaring
functions: function expressions and arrow functions. Neither is "better" than
the standard function declaration we've been using. Arrow functions excel when a
simple change or operation needs to be used repeatedly. But they're certainly
used to write long, complex functions too! As you continue through the course,
you'll see all three methods used to write functions, and develop a feel for
when to use each.

## Resources

- [MDN: Arrow Functions][arrow functions]

[arrow functions]:
  https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions
