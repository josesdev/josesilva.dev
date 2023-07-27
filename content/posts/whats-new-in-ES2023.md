---
title: What's new in ES2023
date: 2023-07-27
published: true
tags: ['JavaScript', 'ES2023', 'ES14']
series: false
cover_image: ./images/javascript-2023.png
canonical_url: false
description: 'Check out the new features of the latest version of ECMAScript (ES2023)'
slug: whats-new-in-es2023
author: 'José Silva'
---

ECMAScript 2023 is here! 🚀 These are the features that will become part of the JavaScript programming language:

1. Change Array by copy
2. Array find from last index
3. Symbols as WeakMap keys
4. Hashbang Grammar (`#!`)

# Change Array by copy

Gives new methods to Array.prototype and TypedArray.prototype to perform certain actions in a new copy of the array, that means without mutating the original array.

The `reverse()`, `sort()` and `splice()` methods mutate the array, so using the new `toReversed()`, `toSorted()` and `toSpliced()` you can reverse, sort and splice without mutating the target array.

Another method was added: `with(index, value)` that returns a new array with the element at the given index replaced with the value provided.

## Array.toReversed()

```js
const original = [1, 2, 3, 4, 5];
const newReversed = original.toReversed(); // Doesn't change the original array

original; // [1, 2, 3, 4, 5]
newReversed; // [5, 4, 3, 2, 1]
```

## Array.toSorted()

```js
const original = [1, 4, 2, 5, 3];
const newSorted = original.toSorted(); // Doesn't change the original array

original; // [1, 4, 2, 5, 3]
newSorted; // [1, 2, 3, 4, 5]
```

## Array.toSpliced()

```js
const original = [1, 3, 4, 5];
const newSpliced = original.toSpliced(1, 0, 2); // Doesn't change the original array

original; // [1, 3, 4, 5]
newSpliced; // [1, 2, 3, 4, 5]
```

## Array.with()

```js
const original = [1, 3, 3, 4, 5];
const newCorrected = original.with(1, 2); // Doesn't change the original array

original; // [1, 3, 3, 4, 5]
newCorrected; // [1, 2, 3, 4, 5]
```

`toReversed`, `toSorted`, and `with` will also be added to TypedArrays.

# Array find from last index

Adds new methods to Array.prototype and TypedArray.prototype: `findLast()` and `findLastIndex()` to search an array starting from the end instead of the beginning, that means in the reverse order of `find()` and `findIndex()`. It can be useful when you know that finding an element from last to first will have a better performance or, in case the array is sorted and you care about the order of elements.

So it solves the issues that the workaround `[].reverse().find()` has:

- unnecessary mutation (by reverse).
- unnecessary copy (to avoid mutation)

```js
const isValueOdd = (obj) => obj.value % 2 === 1;
const values = [{ value: 1 }, { value: 2 }, { value: 3 }, { value: 4 }];

values.findLast(isValueOdd); // { value: 3 }
values.findLastIndex(isValueOdd); // 2
```

# Symbols as WeakMap keys

This allows using unique Symbols as keys of a WeakMap that were previously limited to using Objects as keys.

```js
const weakMap = new WeakMap();
const key = Symbol('ref');

weakMap.set(key, 'value');
weakMap.get(key); // 'value'
```

# Hashbang Grammar (#!)

[Hashbang or Shebang comment `#!`](https://en.wikipedia.org/wiki/Shebang_(Unix)) is used at the beginning of a executable script to specify the interpreter for the script to be run on. This standardizes how JavaScript engines handle these comments.

```js
#!/usr/bin/env node

console.log('Hi');
```