---
title: What's new in ES2019
date: 2019-10-28
published: true
tags: ['JavaScript', 'ES2019', 'ES10']
series: false
cover_image: ./images/javascript.jpg
canonical_url: false
description: "Javascript is constantly evolving and receiving updates every year. It is useful to learn as soon as possible to avoid being stumped by syntax and stay productive in any JavaScript codebase."  
slug: whats-new-in-es2019
author: 'José Silva'
---

ECMAScript (ES) is the specification on which JavaScript is based. This language is constantly evolving and receiving updates every year. It is useful to keep up to avoid being stumped by syntax and stay productive in any JavaScript codebase.

ES2019 is available in the latest version of Chrome, Firefox, Safari, and Node. It is also available in older platforms via compilation with Babel or Typescript. Remember to always check [Can I Use](https://caniuse.com) website to make sure the new feature you want to use is available in your target platforms.

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
The `flat()` method returns a *new array* flattering all the sub-array elements recursively up to the specified depth.

```js
const a1 = [1, 2, [3, 4], 5];
a1.flat(); // [1, 2, 3, 4, 5]
```

By default it only flats one level `flat(1)`, but you can convert any `Array` multi-dimensional to one-dimension using `Infinity`.

```js
const a2 = [1, 2, [[3, [4, 5]], 6], 7];
a2.flat(Infinity); // [1, 2, 3, 4, 5, 6, 7]
```

And, if you have an empty element as part of you `Array`, it'll be removed in the new `Array`

```js
const a3 = [1, 2, , 5];
a3.flat(); // [1, 2, 5]
```

## Array.flatMap()
It returns a *new array* combining `flat()` and `map()` methods. Remember: ES6 `map()` method of an `Array` returns a new `Array` applying a function to each of its elements. 

Suppose we want to double each element of an array and put the result after each one of these elements:

```js
const b1 = [2, 8, 32];
const b2 = b1.map(el => {
  return [el, el * 2];
});
b2; // [[2, 4], [8, 16], [32, 64]]
const b3 = b2.flat();
b3; // [2, 4, 8, 16, 32, 64]
```

Using `flatMap()`

```js
const b4 = [2, 8, 32];
const b5 = b4.flatMap(el => {
  return [el, el * 2];
});
b5; // [2, 4, 8, 16, 32, 64]
```

## String.trimStart() and String.trimEnd()

`String.trim()` removes the whitespaces from the beginning and the end of a `String` so using `String.trimStart()` will only remove the whitespaces from the beginning of the string while use `String.trimEnd()` will do but with the whitespaces from the end.

```js
const c1 = '      Start here.      ';
const c2 = c1.trimStart();
c2; // 'Start here.      ' (with the spaces at the end)
```

```js
const c3 = '      End here.      ';
const c4 = c3.trimEnd();
c4; // '      End here.' (with the spaces at the beggining)
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
d2; // [["prop1", 2], ["prop2", 8], ["prop3", 32]]
```

With `map()` we can iterate over each element and apply the function to double each value:

```js
const d3 = d2.map(([key, value]) => [key, value * 2]);
d3; // [["prop1", 4], ["prop2", 16], ["prop3", 64]]
```

Now, using `fromEntries()` method we will generate the `Object` with the values changed.

```js
const d4 = Object.fromEntries(d3);
d4;
/*
{
  prop1: 4,
  prop2: 16,
  prop3: 64,
}
*/
```

## Optional Catch Binding

It allows to use the `catch()` clause without the need to specify the parameter (the exception).

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
e1.description; // 'Optional description'
```

## Function.prototype.toString()

It returns the function exactly as it was defined including withespaces and comments.

Previous ES10

```js
const fn = function /* initial test */ test() {};
fn.toString(); // 'function test() {}'
```

Now it will be:

```js
const fn = function /* initial test */ test() {};
fn.toString(); // 'function /* initial test */ test() {}'
```

## JSON improvements

The line separator `\u2028` and paragraph separator `\u2029` symbols now parse correctly instead of resulting in a SyntaxError when using using `JSON.parse()`

### Well-formed JSON.stringify 

Prevent JSON.stringify from returning ill-formed strings (specifically, surrogate code points U+D800 through U+DFFF).
