---
title: What's new in ES2019
date: 2019-10-28
published: true
tags: ['JavaScript', 'ES2019', 'ES10']
series: false
cover_image: ./images/javascript.jpg
canonical_url: false
description: "Javascript is constantly evolving and receiving updates every year. It is useful to learn as soon as possible to avoid being stumped by syntax and stay productive in any JavaScript codebase."  
---

ECMAScript (ES) is the specification which JavaScript is based. This language is constantly evolving and receiving updates every year. It is useful to learn as soon as possible to avoid being stumped by syntax and stay productive in any JavaScript codebase.

ES2019 is available in the latest version of Chrome, Firefox, Safari, and Node, and are available via compilation with Babel or Typescript.

1. Array.flat()
2. Array.flatMap()
3. String.trimStart()
4. String.trimEnd()
5. Object.fromEntries
6. Optional Catch Binding
7. Symbol.prototype.description
8. Function.prototype.toString()
9. JSON improvements

## Array.flat()
The `flat()` method creates a *new array* flattering all the sub-array elements recursively up to the specified depth.

```js
const a1 = [1, 2, [3, 4], 5];
console.log(a1.flat()); // OUTPUT: [1, 2, 3, 4, 5]
```

By default it only flats one level `flat(1)`, but you can convert any `Array` multi-dimensional to one-dimension using `Infinity`.

```js
const a2 = [1, 2, [[3, [4, 5]], 6], 7];
console.log(a2.flat(Infinity)); // OUTPUT: [1, 2, 3, 4, 5, 6, 7]
```

And, if you have an empty element part of you `Array`, it'll be removed in the new `Array`

```js
const a3 = [1, 2, , 5];
console.log(a3.flat()); // OUTPUT: [1, 2, 5]
```

## Array.flatMap()
It produces a *new array* combining `flat()` and `map()` methods. To remember, ES6 `map()` method of an `Array` returns a new `Array` applying a function to all of its elements. 

Suppose we want to double each element of an array and put the result after each one of these elements:

```js
const b1 = [2, 8, 32];
const b2 = b1.map(el => {
  return [el, el * 2];
});
console.log(b2); // OUTPUT: [[2, 4], [8, 16], [32, 64]]
const b3 = b2.flat();
console.log(b3); // OUTPUT: [2, 4, 8, 16, 32, 64]
```

Using `flatMap()`

```js
const b4 = [2, 8, 32];
const b5 = b4.flatMap(el => {
  return [el, el * 2];
});
console.log(b5); // OUTPUT: [2, 4, 8, 16, 32, 64]
```

## String.trimStart() and String.trimEnd()

`String.trim()` removes the whitespaces from the beggining and the end of a `String` so using `String.trimStart()` will only remove the whitespaces from the beggining of the string while use `String.trimEnd()` will do but with the whitspaces from the end.

```js
const c1 = '      Start here.      ';
const c2 = c1.trimStart();
console.log(c2); // OUTPUT: 'Start here.      ' (with the spaces at the end)
```

```js
const c3 = '      End here.      ';
const c4 = c3.trimEnd();
console.log(c4); // OUTPUT: '      End here.' (with the spaces at the beggining)
```

## Object.fromEntries(iterable)

This method only accepts an `iterable` as argument and it creates an `Object` from a list of key-value pairs e.g. produced by `Object.entries()` (ES2017) which is used to transform an `Object` to an `Array` of [key, value] pairs.

Suppose we want double each value of the properties of an object:

```js
const d1 = {
  prop1: 2,
  prop2: 8,
  prop3: 32
};
const d2 = Object.entries(d1);
console.log(d2); // OUTPUT: [["prop1", 2], ["prop2", 8], ["prop3", 32]]
```

With `map()` we can iterate over each element and apply the function to double each value:

```js
const d3 = d2.map(([key, value]) => [key, value * 2]);
console.log(d3); // OUTPUT: [["prop1", 4], ["prop2", 16], ["prop3", 64]]
```

Now, using `fromEntries()` method we will generate the `Object` with the values changed.

```js
const d4 = Object.fromEntries(d3);
console.log(d4);
/* OUTPUT:
{
  prop1: 4,
  prop1: 16,
  prop1: 64,
}
*/
```

## Optional Catch Binding

It allows to use the `catch()` without the need to specify the parameter (the exception).

```js
try {
  // execute code 
} catch {
  // handle error
}
```

There is no need to add the parameter to the `catch()` (optional)

```js
try {
  // execute code
} catch (err) {
  // handle error
}
```

## Symbol.prototype.description

It allows to provide a description when creating a `Symbol` via the factory function `Symbol()` and access to it via the description property.

```js
const e1 = Symbol('Optional description');
console.log(e1.description); // OUTPUT: 'Optional description'
```

## Function.prototype.toString()

It returns the function exactly as it was defined including withespaces and comments.

Previous ES10

```js
const fn = function /* initial test */ test() {};
fn.toString(); // OUTPUT: 'function test() {}'
```

Now it will be:

```js
const fn = function /* initial test */ test() {};
fn.toString(); // OUTPUT: 'function /* initial test */ test() {}'
```

## JSON improvements

The line separator `\u2028` and paragraph separator `\u2029` symbols now parse correctly instead of resulting in a SyntaxError when using using `JSON.parse()`

### Well-formed JSON.stringify 

Prevent JSON.stringify from returning ill-formed strings (specifically, surrogate code points U+D800 through U+DFFF).
