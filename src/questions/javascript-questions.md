---
title: JavaScript Questions
layout: layouts/page.njk
permalink: /questions/javascript-questions/index.html
---

# Explain event delegation.

In JavaScript and DOM, and triggered event will not only captured in its own scope but bubble up to parent elements and keep going up.

For example

```html
<div id="parent">
  <div id="child">click me</div>
</div>

<script>
  const p = document.getElementById("parent");
  const c = document.getElementById("child");
  p.addEventListener("click", (e) => {
    console.log("catched in parent");
  });
  c.addEventListener("click", (e) => {
    console.log("catched in child");
  });
</script>
```

Once we click the `click me`. It will log `catched in parent` and `catched in child`.

# Explain how `this` works in JavaScript. Can you give an example of one of the ways that working with `this` has changed in ES6?

`this` refers to the current instance scope. We can ues `this` to access instance's values.

```js
function MyObj() {
  this.value = "Hello world";
}

const a = new MyObj();

console.log(a); // will log MyFunc { value: "Hello world" }
```

In ES6, `arrow function` is introduced. In this function scope, `this` will always refer to the `window`, not the instance.

# Explain how prototypal inheritance works.

In short, it's one object pointing to the other object to inherit all of its properties.

```js
const a = function () {
  console.log("a");
};

// if we use a.classMethod instead, in the following temp.classMethod, it will throw an error.
a.prototype.classMethod = function () {
  console.log("class method");
};

const temp = new a();

temp.classMethod();
```

# What's the difference between a variable that is: `null`, `undefined` or undeclared? How would you go about checking for any of these states?

```js
const a = null; // null
var b; // undefined
c; // undeclared

const isUndefined = (v) => v === undefined;
const isNull = (v) => !isUndefined(v) && v === null;
// there is no way to detect undeclared since it will throw as soon as compiler runs the code, however we can handle that if we wish for no runtime error.
```

# What is a closure, and how/why would you use one?

It means encapsulating a variable inside a function. Usually it is used for not leaking internal variables.

```js
const a = () => {
  let value = 0;
  const b = () => {
    value = value + 1;
    return value;
  };
  return b;
};

const b = a();

console.log(b()); // 1
console.log(b()); // 2
console.log(b()); // 3
```

# What language constructions do you use for iterating over object properties and array items?

```js
// for obj
Object.keys(obj).forEach((k) => obj[k]);

// for array
arr.forEach((v) => v);
```

# Can you describe the main difference between the `Array.forEach()` loop and `Array.map()` methods and why you would pick one versus the other?

`Array.forEach()` simply iterate through an array without any modification to the original data.
`Array.map()` iterate and modify the copy of array value. Upon completion, it will return an copy of modified array.

# What's a typical use case for anonymous functions?

When you don't care to give a function a name.

# What's the difference between host objects and native objects?

`Native Objects` comes with ECMAScript itself, regardless its running environment. Like `Date`, `Math`, `parseInt` and so on.
`Host Objects` comes with the platform which JS is running on. For example, `window`, `location`, `XMLHttpRequest`.

# Explain the difference between: `function Person(){}`, `var person = Person()`, and `var person = new Person()`?

`function Person(){}` is a function declaration.
`var person = Person()` means executing a function and assigning a value to a variable.
`var person = new Person()` means creating an instance and assigning a value to a variable.

# Explain the differences on the usage of `foo` between `function foo() {}` and `var foo = function() {}`

There is no difference between them as both of them are named functions.

# Can you explain what `Function.call` and `Function.apply` do? What's the notable difference between the two?

Both of them execute the function. The first argument receives the `this`. The only difference is the second argument. `call` takes more arguments as arguments, however `apply` only takes arguments as an array.

```js
const func = (...args) => console.log(args);

func.call(null, 1, 2, 3);
func.apply(null, [1, 2, 3]);
```

# Explain `Function.prototype.bind`.

It makes `this` point to another instance.

# What's the difference between feature detection, feature inference, and using the UA string?

`feature detection` is simply using JS to detect if one API is available. For example `if (navigator.geolocation) {/* then do something* /}`
`feature inference` simply inference the existence of one API and assume the other API also exist.
`UA string` stands for user agent string. It labels the version of browser so developers can tell if it supports a specific feature.

# Explain "hoisting".

JavaScript will put the function or `var` declarations in memory before execution. One caveat is that JS only puts declaration ahead of execution not including initialization so the following example will be `undefined`. For example:

```js
// function hoisting
a();

function a() {
  console.log("hello");
}
// undefined example
console.log(b); // undefined
var b = 1;
```

# Describe event bubbling.

In DOM, triggered events will be bubbled up to its parents even if it is captured.

```html
<div id="parent">
  <div id="child">click me</div>
</div>

<script>
  const p = document.getElementById("parent");
  const c = document.getElementById("child");
  p.addEventListener("click", (e) => {
    console.log("catched in parent");
  });
  c.addEventListener("click", (e) => {
    console.log("catched in child");
  });
</script>
```

# Describe event capturing.

If one element's event is triggered, we can use `addEventListener` or `foobarElementInstance.onClick` to capture that event.

# What's the difference between an "attribute" and a "property"?

In HTML the `class`, `href`, `id` are called attributes, however in JS they are called properties. The terminology differs from the context.

# What are the pros and cons of extending built-in JavaScript objects?

The pro is you can access the modified object no matter where they are during runtime of your application. The con is you might make 3rd-party libraries break because inconsist behaviours of built-in objects. Normally it is considered as bad practice.

# What is the difference between `==` and `===`?

`==` compares by value.
`===` compares by reference.

# Explain the same-origin policy with regards to JavaScript.

From JavaScript aspect, under that policy, the browser restricts requests can only be made when requests are sent to the same origin server, unless the target server allows requests from different sources.

# Why is it called a Ternary operator, what does the word "Ternary" indicate?

`?:` is a ternary operator. Ternary takes 3 arguments.

# What is strict mode? What are some of the advantages/disadvantages of using it?

pros

1. unmute silent errors
2. by fixing mistakes, js knows better how to optmize perforamnce.
3. forbit the potential reserved keywords for future ECMAScript versions.
   cons
4. Some people don't like the strict mode because it affects how they write the code.
5. Some libraries not using strict mode makes compiler work in hybrid mode.

# What are some of the advantages/disadvantages of writing JavaScript code in a language that compiles to JavaScript?

pros

1. Potential better syntaxes or language structures.

cons

1. adding another layer of complexity.
2. another tool to learn

# What tools and techniques do you use debugging JavaScript code?

`Devtool` or `console.log`

# Explain the difference between mutable and immutable objects. What is an example of an immutable object in JavaScript? What are the pros and cons of immutability? How can you achieve immutability in your own code?

You can acheive immutability with `const` or `Object.freeze` if you want to make every property immutable in an object.

```js
const a = 0;
const b = Object.freeze({
  foo: "foo",
});
```

pros

1. developers won't accidentally mutate the state of a variable.

cons

1. it takes more computation resource to do immutability as every mutation will create an new value.

# Explain the difference between synchronous and asynchronous functions.

`synchronous` means running the process in a **blocking** mode which means the program can only run next task after completing the current one.
`asynchronous` means running the process in a **non-blocking** mode which means the program can run multiple tasks in parallel.

# What is event loop? What is the difference between call stack and task queue?

Event loop consists of these parts

1. `call stack` - is a stack that whenever a function is called, the local variables and arguments will be pushed into the stack. Once the function completes running, it will get pop up.
2. `heap` - Objects that are held in the memory.
3. `task queue` - also known as `message queue`. Once the runtime receives a function call, the handler of that function will be enqueued. The runtime will process tasks from the oldest, and once it starts processing, the handler will be called and dequeued.

The difference between `call stack` and `task queue` is `call stack` is the context of current and previous processing state when `task queue` is a task scheduler.

# What are the differences between variables created using `let`, `var` or `const`?

`var` mutable, global scope, hoisted in global scope.

`let` mutable, block scope, hoisted in block scope.

`const` immutable, block scope, hoisted in block scope.

# What are the differences between ES6 class and ES5 function constructors?

ES6 class syntax sugar helps developers with OOP background to have an easier way to construct data while ES5 function constructor remains more closely to its true identity -- prototype chain.

# Can you offer a use case for the new arrow `=>` function syntax? How does this new syntax differ from other functions?

```js
const greeting = (v) => console.log(`hello ${v}`);
greeting("foo");
```

The difference is `this` doesn't bind to arrow function. It always binds to the innermost function scope or global object.

# What advantage is there for using the arrow syntax for a method in a constructor?

`this` will always be binded to the nearest function scope.

# What is the definition of a higher-order function?

Functions can be arguments and get returend as an result.

# Can you give an example for destructuring an object or an array?

```js
// obj
const { a, b, ...rest } = { a: "apple", b: "banana", c: "cello", d: "dentist" };
// arr
const [head, neck, ...tail] = [1, 2, 3, 4, 5];
```

# Can you give an example of generating a string with ES6 Template Literals?

```js
const a = "foo";
const b = "bar";
console.log(`hello ${a}${b}`);
```

# Can you give an example of a curry function and why this syntax offers an advantage?

```js
const add = (a) => (b) => a + b;
const add3 = add(3);
const add5 = add(5);
add3(10); // 13
add5(10); // 15
```

1. curry function is already a factory pattern.
2. delay the actual invocation/execution time. Only runs when all the neccesary data are received as arugments.

# What are the benefits of using `spread syntax` and how is it different from `rest syntax`?

`spread syntax` is mostly used for composing object

```js
const obj = { a: "apple", b: "banana", c: "cello", d: "dentist" };
const obj2 = { ...obj, e: "elephant" };
```

`spread syntax` is used while assigning variables.
`rest syntax` is used while deconstructing variables.

# How can you share code between files?

Use module import/export like `import` and `export`.

# Why you might want to create static class members?

When you want to share the member among all instances. For example a counter

```js
class Foo {
  static counter = 0;

  constructor() {
    Foo.counter++;
    console.log(`Foo ${Foo.counter} is constructed`);
  }
}

new Foo(); // Foo 1 is constructed
new Foo(); // Foo 2 is constructed
```

# What is the difference between `while` and `do-while` loops in JavaScript?

`while` will check the condition first and then execute the command while `do-while` does things in reversed order.

# What is a promise? Where and how would you use promise?

`Promise` is used in async programming. Mostly in sending or reciving requests. In ES6 I would use it with `async` to avoid promise hell:

```js
const func = async () => {
  const user = await fetch("/user/123");
  const friend = await fetch(`/friend/${user.firendId}`);
  // ...
};
```

# Make this work:

```javascript
const duplicate = (v) => [...v, ...v];

duplicate([1, 2, 3, 4, 5]); // [1,2,3,4,5,1,2,3,4,5]
```

# Create a for loop that iterates up to `100` while outputting **"fizz"** at multiples of `3`, **"buzz"** at multiples of `5` and **"fizzbuzz"** at multiples of `3` and `5`

```js
for (let i = 0; i < 100; i++) {
  if (i % 5 === 0 && i % 3) console.log("fizzbuzz");
  else if (i % 5 === 0) console.log("buzz");
  else if (i % 3 === 0) console.log("fizz");
}
```

# What will be returned by each of these?

```javascript
console.log("hello" || "world"); // hello
console.log("foo" && "bar"); // bar
```

# Write an immediately invoked function expression (IIFE)

```js
(() => "")();
```
