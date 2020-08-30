---
title: Scope III: Closures
tags: javascript, scope, closure, iife, lexical scope
module: 2
---

## Learning Goals

* Describe and speak to lexical scoping in JavaScript
* Understand and implement closures

## Vocab

- `lexical scope` also known as static scope
- `closure` a function that has a reference to its outer/lexical environment


## Lexical Scope

Though we haven't put a name to it until now, our conversations around scope and the scope chain are directly related to what we call **lexical scoping**.

Lexical scoping means that our scope is **statically** bound, and therefore perfectly predictable upon authoring our code. You can see lexical scope by looking directly at code, as it reads:

```js
function eatSnack() {
  var hunger = 25;

  getHangry();

  function getHangry() {
    console.log('I am sooooooo HANGRY!');
  }
}

eatSnack();
```

In our example above, the lexical scope for our `getHangry` function is the scope (and any variables) that are contained within `eatSnack`.

All inner functions (since functions create new scope) are statically (lexically) bound during the Creation Phase to the parent context in which the inner function was physically defined in the source/program code.

## Closures 

[Closures](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures) are expressions (usually functions) which can work with variables set within a certain context. In other words, a closure is formed when a function is defined inside of another function (one function nested inside of another function). This allows the inner function to access to the outer function's variables via the scope chain. 

Let's build on a definition together. At the most basic level, **a closure is when an inner function is defined inside of another function**.

This is syntactically and factually correct, but it doesn't tell us much about what's significant here. So a more thorough definition might be:  **a closure is when an inner function has access to its outer function's variables**.

Let's look at an example:  
 
```js
function greet() { 
  var firstName = 'Alan'; // a local variable created by greet()  
  function displayName() { // displayName() an inner function
    console.log(firstName); // access variable declared in parent fn
  } 
  displayName();     
} 

greet(); 
```
<section class="call-to-action">
### Turn and talk

With a partner, walk through the code execution above.
</section>

<section class="answer">
There's nothing really new here that we don't already know about how scope (specifically the scope chain) works:

1.  When we get to the console log for `firstName`, the JS interpreter first looks in its current scope (within `displayName`) for a `firstName` variable that it can grab the value from.
2. It doesn't find it, so it traverses up the scope chain to the parent scope (`greet`) and again looks for a `firstName` variable to reference.
3. It finds it here, with a value of `Alan`, so the log will say `Alan`.
</section>

Now let's modify this example a bit. Instead of invoking `displayName` right away within our `greet` function, we'll return it:

```js
function greet() { 
  var firstName = 'Alan'; // a local variable created by greet()  
  function displayName() { // displayName() an inner function
    console.log(firstName); // access variable declared in parent fn
  } 
  return displayName;     
} 

var createGreeting = greet(); // createGreeting is now a function that can be invoked
createGreeting(); // will run the displayName function and log 'Alan'
```

Now when we invoke `greet`, we get a function back (`displayName`). In many languages, as soon as `greet` is finished running, our `firstName` variable would be completely removed from memory.

In JavaScript this isn't the case. Because there is an inner function here `displayName` -- JavaScript is smart enough to know that this function can still be called (we're going to invoke it with `createGreeting()`) and therefore it still needs access to the `firstName` variable. 

So when we run this code, we'll still get `Alan` to log to our console. In other languages, they would see this `displayName` function in isolation, and when it was invoked, it would say "I don't have a `firstName` variable to reference - it's undefined".

This is why "What is a closure" has become such a big question in JavaScript interviews -- lots of people coming from other languages are really surprised by this different behavior.

So our newer, better definition of a closure could now be: **When an inner function has access to the outer function's variables and can remember the environment in which it was created.** (So not only does our inner function have access to the outer function's variables, but it also remembers their values, even if the outer function has finished executing!)

## Closures for Protecting Variables

This still might not seem like an incredibly useful feature of JavaScript, but there are some more practical use-cases for closures. Before we move on, What we want to point out about this example, in order to better understand closures, is that:

* `firstName` is not available anywhere outside of the `greet` function. We would say that the `greet` function "closes over" this variable
* the inner function, `displayName` can reference (or even modify) the `firstName` variable because it is inside the scope of the outer function `greet`

So one use-case for closures is to **protect variables from any sort of outside manipulation**. Other languages often have some really nice way of implementing private or protected variables, but JavaScript doesn't. So if this is something we want to achieve, we would use a closure.

Take the following example:

```js
function analyzeGrades() {
  // We keep these variables private inside this closure
  let privateGrades = [93, 95, 88, 0, 55, 91];
  
  return {
    changeGrades() {
      privateGrades = privateGrades.map(grade => {
        return grade + 5;
      });
    },
    
    viewGrades() {
      return privateGrades;
    }
  }
};
  
console.log(privateGrades) // undefined
console.log(analyzeGrades) // fn definition
console.log(analyzeGrades()) // object with changeGrades method

let instructor = analyzeGrades();
instructor.changeGrades(); // undefined (we are not returning anything from that method, but it is running)
instructor.viewGrades(); // [98, 100, 93...]
```

<section class="call-to-action">
### Practice

Add a new function `addGrade` to this closure, such that we can update our
`privateGrades` variable, adding a new grade to the array.
</section>

Our most thorough definition of a closure is now **when an inner function has access to the outer function's variables and can remember the environment in which it was created. The outer function's variables are protected by the closure and can only be manipulated by code defined within that function.**

In the previous example, you'll notice we could still technically change those grades and snoop on them if we wanted to. This is why we say JavaScript doesn't have a true fashion for creating private variables. We can kind of imply that you shouldn't be fussing with something by hiding it in a function and not exposing that variable declaration outside of it - but we can still gain access to that value. So closures aren't really going to help if you have truly sensitive data that nobody should be able to see.

<section class="call-to-action">
### Practice

Use the closure pattern to create a "private" counter. The counter variable should be protected by an outter function. The outter function should return an object of methods that allow a user to `incrementCounter`, `decrementCounter` and `getCounterValue`. 
</section>

<section class="checks-for-understanding">
### Checks for Understanding 

- What is lexical scope?
- What is a closure and how can it be helpful?
</section>
