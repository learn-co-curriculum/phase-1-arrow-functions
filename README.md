# Arrow Function Shorthand


## Introduction

The original style for declaring functions in JavaScript is the _function
declaration_.

```js
function foo() {
  return 'bar';
}
```

But JavaScript has two other ways to write functions: the _function expression_
and the _arrow function_. None of these is more correct or better than others.

## Learning Goals

- Declare a function using a function expression
- Declare a function using an arrow function
- Describe situations where arrow functions come in handy

## Declare a Function Using a Function Expression

Thus far we've only ever used a _function declaration_:

```js
function foo() {
  return 'bar';
}
```

A function can also be written:

```js
let foo = function() {
  return 'bar';
}
```

The `function() {...}` to the right of the assignment operator (`=`) is called
a _function expression_. The best way to understand what a function expression
is is by analogy.

```js
let sum = 1 + 1
```

EVALUATE the expression `1 + 1`, RETURNING `2` and ASSIGN it to the variable `sum`

```js
let difference = 10 - 1;
```

EVALUATE the expression `10 - 1`, RETURNING `9` and ASSIGN it to the variable
`difference`.

```js
let foo = function() {
  return 'bar';
}
```

EVALUATE the expression `function() { return 'bar' }`, RETURNING a thing that
can be called and ASSIGN it to the variable `foo`. The function expression
(again, the thing to the right of `=`) is known as "an anonymous
function." It doesn't have a name associated with it like you see in a
_function declaration_.

However, when we assign an anonymous function to a name (that is, a variable),
we have name that points to a callable thing. We could call this anonymous
function by invoking `foo()`. That anonymous function is now, for all
reasonable purposes, named `foo`.

There are a few subtle differences between _function declarations_ and
_function expressions_, but they are very minute. Neither is really better than
the other. JavaScript supports variety. Neither is better or more preferred
than the other.

Try thinking about the following code. Will this work? Does it work? Try to
explain to yourself what's happening using the words "anonymous function" and
"`call`." If you need help, see IIFE in the Resources section below.

```js
(function() { console.log("Hello world") })()
```

## Declare a Function Using An Arrow Function

Around 2015, developers got tired of typing `f-u-n-c-t-i-o-n` over and over.
They lobbied the ECMAScript body for a way to write functions in a very short
way. Here is the result, the "Arrow Function."

```js
let add = (parameter1, parameter2) => parameter1 + parameter2
add(2,3) //=> 5
```

Yes, this works! Really! This builds on the syntax of the _function expression_
just covered. The arrow syntax just lets you cut out a some typing.

`add` is the name to which the following _anonymous function_ is assigned, same
as in the previous section:

```js
(parameter1, parameter2) => parameter1 + parameter2
```

This is a very short function! It adds `parameter1` and `parameter2`.  Without
any braces, arrow functions **automatically** return the result of the last
expression.

Functions like this are very common in JavaScript's iterator methods that we'll
cover in a future lesson.

As one final gift to programmers' fingers, if your arrow function has only
_one_ parameter, JavaScript will let you drop the `()` around the parameter:

```js
let twoAdder = x => x + 2;
```

If we need to do more work than return a mere single expression, we'll need
`{}` to wrap the multiple lines of code **and** we'll have to declare a
`return`.

```js
let sum = (parameter1, parameter2) => {
  console.log(`Adding ${parameter1}`);
  console.log(`Adding ${parameter2}`);
  return parameter1 + parameter2;
}
sum(1,2) //=> 3
```

## Describe Situations Where Arrow Functions Come In Handy

As a preview of advanced iteration in JavaScipt, we'll show the `.map()`
function iterates through one `Array`, passes each element to a function that's
passed in as an argument, takes that functions return value, and stacks it into
a new array.

```js
const nums = [1,2,3];
const squares = nums.map(x => x ** 2); //=> [2,4,6]
const doubles = nums.map(x => x * 2); //=> [1,4,9]
```

If all this math stuff seems a bit too, textbook-y, realize that a similar
pattern could be done with DOM elements:

```js
finishedItems = overdueTodoItems.map( item => item.className = "complete" );
header.innerText = `You finished ${finishedItems.length} items!`;
```

Or billing software:

```js
lapsedUserAccounts.map( u => sendBillTo(u.address) );
```

In a subsequent lesson, we'll show the power of arrow functions with other
iterator methods.

## Conclusion

In this lesson you saw two different styles for declaring functions: function
expressions and arrow functions. Neither is "better" than the standard function
declaration we've been using. Arrow functions excel when a simple change or
opration needs to be used repeatedly. But they're certainly used to write long,
full functions too!

## Resources

- [MDN: Arrow functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)
- [IIFE](https://developer.mozilla.org/en-US/docs/Glossary/IIFE)