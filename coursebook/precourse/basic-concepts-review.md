## This document is a step-by-step review of most of the fundamental concepts that applicants learn during their first weeks of javascript studies.

**The example code can be pasted and run into *[repl.it](https://repl.it/)* for better understanding.**

**The following is a variable.**
**A variable is a way for us to save a piece of information inside a name that we can reuse inside our program.** We can use variables to save any type of data (string, num ...). **We declare a variable by giving it a name. We define it by assigning it a value with the equal sign (=).**

**ES5 syntax**
```
var num; // <- Declaring a variable.
var myFirstNum = 3; // <- Defining it by assigning it a value.
```

**ES6 syntax**
```
const name = "Mynah";
let mySecondNum = 5;

// If I want to see the value of a variable, I can console.log it.

console.log(name);
```

**It is important to understand what are the different data types used in Javascript and how different methods are meant to be used on different data types.**

### **Data types**

### Numbers

**Numbers** can be whole integers or decimal values, javascript doesn't have a separate type for floats and integers, (عدد صحيح وكسر).
```
var myInt = 2;
var myFloat = 5.5;
```
We can use the function `typeof` to see the data type of a variable.
```
console.log(typeof(myInt), typeof(myFloat));
```

Example of methods/functions that are used on numbers:
  - `Math.random()`
  - `Math.abs()`
  - `Math.pow()`
  - `Math.floor()`
  - `Number.prototype.toFixed()` -> *round to specified amount of decimals*
```
console.log((43 / 5.1).toFixed(2));
console.log(Math.random().toFixed(2));
```

### Booleans (true/ false)

Boolean values are usually the result of a comparison expression.

The comparison operators are:
** <, >, >=, <=, !=, !==, ==, === **

Example of comparison expression:
`5 > 10 // Evaluates to false`

Examples of methods that give us true or false:
  - `Regex.prototype.test()`

### Chars and Strings

Chars are single 4 bits (1 byte) characters. Each char has an ASCII code that allows the computer to map it to binary.
```
var myChar = "a";
var myNumAsChar = "3";
```

**Strings are a collection of chars. (Basically they are many chars put together).**
```
var myStr = "Hello, World!";
```
Example of methods for chars and strings.

  - `String.prototype.charCodeAt()` <- returns a number.
```
console.log(myStr.charCodeAt(0));
```

  - `String.prototype.substr()`
```
console.log(myStr.substr(7, 5));
```

  - `String.prototype.toUpperCase()` <- returns a string
```
console.log(myStr.toUpperCase());
```

  - `String.prototype.split()` <- returns an array
```
console.log(myStr.split(""));
```

  - `String.prototype.length` <- returns a number
```
console.log(myStr.length);
```

**We access characters in a string through `bracket notation []`**
```
var letter = myStr[1];
console.log(letter);
```

**Some methods can also isolate a single char or give you the index of a char in a string.**
```
var myIndex = myStr.indexOf("l");
console.log(myIndex);

var myIndex2 = myStr.charAt(2);
console.log(myIndex2);
```

### Arrays

**Arrays are basically a *list of "things"*.** They can contain any combination of data type: number, string, boolean, arrays, objects...
```
var arr = [2, 3, 4, 5];
var a2 = ["Mynah Marie", 24, true, {name: "Mynah", age: 38}, ["a", "b", "c"]];
```

Examples of methods that we can use on arrays:
  - `Array.prototype.slice()`
  - `Array.prototype.splice()`
  - `Array.prototype.push()`
  - `Array.prototype.join()`
  - `Array.prototype.map()`
  - `Array.prototype.filter()`
  - `Array.prototype.includes()`

**To access elements in an array we use brackets notation [].**
```
var age = a2[1];
var b = a2[4][1];
console.log(age, b);
```

### Objects

Objects are another way of grouping information and methods.
Instead of a list (like arrays), **they work with key/value pairs which allow us to access information differently and more specifically then in arrays.** They also allow us to create classes which are basically custom data types that we create ourselves.

**We store information in objects using key/value pairs.**
```
var student = {name: "Nareman", age: 30, graduated: false};
console.log(student.name);
console.log(student["name"]);
```
Examples of methods or functions that can be used on objects:
  - `Object.keys()`
```
console.log(Object.keys(student));
```
  - `Object.values()`
```
console.log(Object.values(student));
```

***
### About **Errors**

**SyntaxError**
These kinds of errors means something is wrong in the way the code is written (typos, missing brackets or semicolons, etc...)

**TypeError**
These errors usually mean the we are **trying to apply a method on the wrong data type** (*for example: using `Object.keys()` on an array or using `arr.push()` on a string*).

**Remember: Errors are there to help you!! Take the time to read them carefully and understand what they have to say about your code :D**
***

### Functions

### Anatomy of a function (هيكل\ مبنى الداله)
**A function takes an input in the form of arguments and gives us an output.** Sometimes we don't need any input in order to get the result we want.

| INPUT | DO SOMETHING | OUTPUT |
| ------ | ----------------- | ------------ |
| arguments | function body | return statement |

```
function nameOfFunction(argument) {
  //do something
}

//calling the function(input argument);
```
Example of a basic function:
```
function hi(name) {
  console.log("Hi " + name + "! :D");
  return "Hi Nareman";
}

hi("Nareman");

var helloNareman = hi("Nareman");
console.log(helloNareman);
```

The **return** gives you the **output**
The **input** is the **argument** `name` in the case of the example above.
The **do something** is the line with `console.log("Hi " + name + "! :D");` in the case of this example.

### Loops

**While loop**
A while loop will run **while a given condition is true.**
```
var i = 10;
while (i > 5) {
  console.log("while loop: i = ", i);
  i--;
}
// At this point, i === 5;
```
**Do-while loop**
 A do-while loop **will always run at least once, even if the condition is false.**
```
do {
  console.log("do-while loop: i = ", i);
  i++;
} while (i < 5);
```

**For loop**
A for loop **defines a starting value and executes as long as a condition involving this starting value is true.** It will also update the starting value as specified each time that the loop executes.
```
for (var j = 0; j > -5; j--) {
  console.log("for loop: j = ", j);
}
```
