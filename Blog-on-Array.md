## What is an Array?
An array is a datatype for storing multiple pieces of data in one single variable. These multiple data values can be different in terms of the datatype, that is JavaScript allows you to store both string and numbers in a single array.

In JavaScript, we declare array variables with an opening square bracket and putting the values separated by a comma, and then finally ending the declaration by a closing square bracket. 

```javascript
var myArray = ["Logan", "Mike", "Sam"];
var anotherArray = [10, 12, 15, 100, 42];
var oneMoreArray = ["New York", 92, "LA", 25, 46];
```

You can also nest arrays (put one array inside another array)

```javascript
var nestedArray = [["Dogs", 4], ["Cats", 7]];
``` 

In the above example, one array named `nestedArray` is a container for two other arrays `["Dogs",4]` and `["Cats", 7]`.
This kind of array is also called a *multi-dimensional array*.

## Accessing Data inside Arrays

Data stored inside the arrays can be accessed using *indexes*. Just like strings, arrays also have *zero-based* indexing i.e., the first element of the array has an index on *zero*, the second element has an index of *one*, the third element has an index of *two* and so on. 

To access the data inside an array all you need to do is, write the name of the array along with the index of data you want to access in square brackets (`[]`).

You can either output this value or store it in another variable for further use. 

```javascript
var myArray = [10, 45, 87, 56];
console.log(myArray[0]);   // output: 10 
console.log(myArray[1]);   // output: 45
var myData = myArray[2];   // variable holds 87 as value 
var myData2 = myArray[3];  // variable holds 56 as value
```

## Accessing Data inside Multi-Dimensional Array

Accessing of data inside multi-dimensional arrays can also be done using *indexes*, but this time we have to use two sets of square brackets. The first one for the outer-most array (that is the container of all the other arrays) and the second one for the inside array. 

```javascript
var alsoArray = [[90, 45, 65], [34, 72, 46], [100, 81, 94]];
console.log(alsoArray[0][2]);   // output: 65
console.log(alsoArray[2][0]);   // output: 100
```

## Modifying Data inside Arrays

Arrays are mutable in Javascript and can be modified easily. This is also done using *indexes*. Just write the index of the element you want to modify and in the following manner :

```javascript
var myArray = [10, 26, 30];
myArray[0] = 20;  // now myArray becomes [20, 26,30]
```

## Manipulating Arrays with push() function

There is a `push()` function in JavaScript that helps to append data to the end of the array upon its calling. This function takes one or more parameters and *pushes* them onto the end of the array.

```javascript
var myArray = [10, 56];
myArray.push(35);   // now myArray is [10, 56, 35]
myArray.push(9);    // now myArray is [10, 56, 35, 9]
myArray.push("Zack");   // now myArray is [10, 56, 35, 9, "Zack"]
```

## Manipulating Arrays with pop() function

When the `pop()` is invoked or called it *pops* a value from the end of an array i.e., it removes the last value from the array. But this is not the only thing this function does, when invoked `pop()` function also returns the *popped off* value and you can store it in another variable.

```javascript
var breakfast = ["apple", "milk", "toast"];
var removedItem = breakfast.pop();  // now array is ["apple", "milk"]
console.log(removedItem);   // output: toast
```

## Manipulating Arrays With shift() function

Opposite of `pop()` function, the `shift()` function is used to remove the first value from the array. This function also returns the *shifted off* value and can be stored in another variable.

```javascript
var superheros = ["batman", "black panther", "superman"];
var removedHero = superhero.shift();    // now array is ["black panther", "superman"]
console.log(removedHero);   // output: batman
```

## Manipulating Arrays With unshift() function

The `unshift()` function is somewhat like the `push()` function, the only difference is that it adds the given value to the front of the array instead of the end of the array.

```javascript
var myLove = ["linux", "java",];
unshift("javascript");  // now array is ["javascript", "linux", "java"]
```

HURRAY! You did it. This is all you needed to know about Arrays in JavaScript as a beginner. 

![GIF](https://media.giphy.com/media/26xBuwDvSNN9w8sda/giphy.gif)


