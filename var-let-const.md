# Var, Let and Const - What should I use?

A few weeks ago when I first started learning Javascript, just like any other beginner I looked for "hello world" javascript tutorials on the internet to start with. And the first thing that I noticed was that some people were using `var` to declare the variables and some were using `let` and `const`.

And to understand why is it so, I had to understand a few more terms that are __variable scope__, __variable hoisting__ and __EMCAScript standard__.
Now if you already know the meaning of these terms, I say you already know what I am going to talk about in this blog post. But if you are a beginner and don't know what these terms exactly mean in the context of JavaScript language then keep on reading this blog is for you.

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

To understand the concept of Hoisting better, first, let's understand the basic difference between __variable declaration__ and __variable initialization__.

Look at the example below.

```javascript
var color;  // variable declaration
color = "red";  // variable initialization

var shape = "square";   // variable declaration plus initialization
```

Look at the first line this is how we declare a variable, right? Using either `var`, `let` or `const`. And like the second line, when we assign a value to the variable it is said to be initialized. In the last line, we see that these two steps can be combined into one. But here is the catch, the JavaScript engine treats the last line as two separate statements just like the above two lines.

Now, let's look at another code example.

```javascript
var brand;
var model = "Model X";
    
console.log(brand);    // prints: "undefined"
console.log(model);    // prints: "Model X"
```

Here we observe that if we don't initialize the variable ourselves, the JavaScript engine initializes it by default by `undefined`. Just like it did to `brand` in our code.

Now let's see what happens when we try to access a variable before its declaration plus initialization.

```javascript
console.log(text);    // prints: "undefined"
var text;
```

Do you see what happened here? Don't you think we should encounter a `ReferenceError` because we tried to `console.log()` a variable that isn't declared yet? Instead, we got `undefined` in output that we usually get when the JavaScript initializes a variable itself upon its declaration. 

Well turns out this all what  __hoisting__ is, that no matter where variables are declared within a particular scope, all variable declarations are moved to the top of their scope (global or local). This is called __hoisting__, as the variable declarations are hoisted to the top of the scope. 

__Note__ that hoisting only moves the declaration, the assignments are left in place.