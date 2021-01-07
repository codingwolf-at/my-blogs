# Var, Let and Const - What should I use?

A few weeks ago when I first started learning Javascript, just like any other beginner I looked for "hello world" javascript tutorials on the internet to start with. And the first thing that I noticed was that some people were using `var` to declare the variables and some were using `let` and `const`.

And to understand why is it so, I had to understand a few more terms that are __variable scope__, __variable hoisting__ and __EMCAScript standard__.
Now if you already know the meaning of these terms, I say you already know what I am going to talk about in this blog post. But if you are a beginner and don't know what these terms exactly mean in the context of JavaScript language then keep on reading this blog is for you.

![GIF](https://media.giphy.com/media/SWonAz0ZVuYhXuhPrC/giphy.gif)

## ECMAScript, what does this mean?

JavaScript was first introduced in __1995__ exclusively for Netscape Navigator. If you don't know Netscape Navigator was a proprietary web browser and was dominant in terms of usage share in the __1990s__, but around __2003__ its use had almost disappeared. 

But after JavaScript started gaining popularity and almost every new modern browser started using it a standard document was written to describe the way JavaScript should work. This is called __ECMAScript__ standard or only __ES__ in its short form. 

In __2015__, the __6th edition__ of ECMAScript (__ES6__) was introduced and one of the main addition was the concept of `let` and `const`. That means before __ES6__, `var` was the only way of declaring variables. 

__Note__ that the terms ECMAScript and JavaScript can be used interchangeably. 

Now before diving deep into this discussion there are two more terms you need to be cleared about.

## What is Variable Scope?

If you declare a variable in your JavaScript program then the part of code where this variable is accessible is called the scope of the variable. 

There are two types of variable scope.

### Global Scope

When a variable is declared at the top of the program or outside of a function, the variable is said to be a global scope variable. A global scope variable can be accessed from anywhere in the program.

Look at the following example.

```javascript
let userName = "Atul";

function greetUser() {
    console.log("Hello", username);
}

greetUser();    // prints: "Hello Atul"
```

Here, you can see we declared `userName` on the top of the program and outside the function body. So `userName` is a global scope variable, and we accessed its value inside the `greetUser()` function body which worked because global scope variables can be accessed from anywhere in the program.

### Local/Function Scope

When a variable is declared inside a function definition, then the variable is only accessible inside the function body. If we try to access the variable from outside the function body we will get a `ReferenceError`.

Look at this example below.

```javascript
function myFunction() {
    let userName = "codingWolf";
}

myFunction();   // prints: "codingWolf"

console.log(userName);  // ReferenceError: username is not defined
```

Here we declared `userName` inside the function body. When we tried to access the variable within the function body upon invoking it we got ourselves an output, but when we tried to access the variable outside the function body we encountered the `ReferenceError`. 

This is all about variable scope.
## What is Variable Hoisting?
