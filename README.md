# Sprint Challenge - JavaScript Fundamentals

**Read these instructions carefully. Understand exactly what is expected _before_ starting this Sprint Challenge.**

This challenge allows you to practice the concepts and techniques learned over the past week and apply them in project. This Sprint explored JavaScript Fundamentals. During this Sprint, you studied array methods, this keyword, prototypes, and class syntax. In your challenge this week, you will demonstrate proficiency by completing a range of JavaScript problems.

This is an individual assessment. All work must be your own. Your challenge score is a measure of your ability to work independently using the material covered through this sprint. You need to demonstrate proficiency in the concepts and objectives introduced and practiced in preceding days.

You are not allowed to collaborate during the sprint challenge.

## Introduction

The index.js file contains all of your challenges. Please review it in full before answering the questions. If you complete the stretch goals please leave them in your file but commented out so that they do not affect the MVP tasks

In meeting the minimum viable product (MVP) specifications listed below, you should have all tests passing. You can console.log to check your work and ensure you are submitting the correct results

### Commits

Set up codegrade early and commit your code regularly and meaningfully.

## Interview Questions

### (please edit this file and write your answer below each question.)

Demonstrate your understanding of this week's concepts by answering the following free-form questions.

Edit this document to include your answers after each question. Make sure to leave a blank line above and below your answer so it is clear and easy to read.

**For clarification on my examples: The dashes are meant to indicate indentation.**

1. Explain the differences between `.map`, `.reduce` and `.filter` and describe a use case for each.

- `.map()`, `.reduce()`, and .`filter()` all loop over the array they are applied to.

- **.map()** can take an array, change the values inside the array, and return a new array with the altered values. `.map()` does not affect the array it is mapping.

Example: const numbers = [1, 2, 3] ... numbers.map((num) => num - 1) when returned would give [0, 1, 2] as a new array.

- If I wanted to add 2 to each value inside an array, I would use the `.map()` method.

- **.reduce()** combines all elements within the array it is reducing, turning the array into a single value. Unlike `.map()` and `.filter()`, which create a new array when executed, `.reduce()` makes changes directly to the array it is reducing.

Example:  
const numbers = [1, 2, 3];  
numbers.reduce((accumulator, currentValue) => accumulator + currentValue) // when returned would give 6 alone.

- If I want to reduce an array to a single value, I would use the `.reduce()` method.

- **.filter()** uses a function to filter through an array to find items based on the argument you give it. The filtered array is returned as a new array, therefore leaving the array it filtered untouched, just like `.map()`. Unlike `.map()` and `.reduce()`, `.filter()` cannot alter the values inside the array, as it simply pulls the values from the array being filtered and pushes them to a new array that this method automatically creates.

Example: const numbers = [1, 2, 3]  
numbers.filter((num) => num === 1 || num === 2) when returned would give the new array [1, 2].

- If I want to have an array that only contains certain values from a previous array I made, I would use the .filter() method.

2. Explain the difference between a callback and a higher order function.

- A **higher order function** is a function that takes in a function or returns a function.

- A **callback function** is a function that gets passed into another function as its parameter.

- A callback function goes inside of another function, resulting in a higher order function. Callback and higher order functions must work hand in hand with each other.

3. Explain what a closure is.

- A **closure** is when an inner function (a function within a function) references information from outside itself to complete its task.

Example:  
const outerVar = "apple";  
function example() {  
--const introduction = "Hi, I am";  
--function iAmApple() {  
----return `${introduction} am ${outerVar}.`;  
--}  
--return iAmApple();  
// iAmApple() is using closure to provide context for "introduction" and "outerVariable". In other words, iAmApple() is reaching into example()'s scope to get context for "introduction" and is reaching into the global scope to get context for "outerVariable", which is what closure is all about.  
}  
console.log(example()); // Logs "Hi, I am apple."

- Closures are one way in, no way out. Children can reach into their parents, grand parents, etc., but not vice versa.

4. Describe the four principles of the 'this' keyword.

- First is **Global Object Binding**, which is also known as Window Object Binding. This is when `this` is set in the global scope. As a result, `this` would be the whole entire Javascript program, for that is the only context that could be provided to it.

Example: console.log(this); // would log the Window object (everything that makes up the Javascript program) if you do this in an empty console in Chrome.

- Second is **Implicit Binding**. This is when `this` is used to imply the object it is bound to without explicitly writing out what the object is.

Example:  
const john = {  
--age: 34,  
--name: "John",  
--introduction: function () {  
----return `Hello! My name is ${this.name} and I am ${this.age} years old.`;  
// The template literal is using implicit binding in the john introduction method because the method is inside the object john. In this case, the function sees the object john as the implied object since it is inside of john.  
--}  
};  
const introduceJohn = john.introduction();  
console.log(introduceJohn);

- Third is **New Binding**. This is when a constructor function uses `this` to refer to the object it is creating and returning. This principle is similar to implicit binding.

Example:  
function Walker(name) {  
--this.movement = "walking";  
--this.name = name;  
--this.walk = function () {  
----console.log(`${this.name} is now ${this.movement}.`);  
--};  
// In this constructor function, `this` refers to the object that will be created. Since `this` is used for referring to the object, the constructor function can be reused over and over for creating new objects. If `this` wasn't used, the constructor function couldn't work due to lack of adaptability.  
}  
const abe = new Walker("Abe");  
abe.walkToPark(); // would log "Abe is now walking."

- Forth and final is **Explicit Binding**. This is when we use the methods `.call()` and `.apply()` to overwrite `this` in the constructed object with an explicit input provided in the `.call()` or `.apply()` argument. This removes the adaptability of the created object because `this` is being swapped out with the argument. In other words, the object is explicitly being told what to be.

Example:  
**// continuing off the example for new binding!**
const bob = new Walker("Bob"); // created new bob object with the Walker construction function.  
abe.walk.apply(**bob**); // would log "Bob is walking."  
// Even though we are invoking the walk method on object "abe", the method `.apply()` (we could also use .call() which would produce the same result) explicitly tells all the `this` keywords in "abe" to refer to the object "bob".

5. Why do we need super() in an extended class?

- The **super()** keyword allows an extended class's (a sub-class) constructor to use its parent class's constructor properties (also known as keys). In addition, it also gives the extended class access to its parent class's methods.

You are expected to be able to answer questions in these areas. Your responses contribute to your Sprint Challenge grade.

## Instructions

### Task 1: Set up Project

Using VSCode and Command Line:

1. Fork the repo
2. Clone your forked version of the repo
3. cd into your repo and create a branch with your first and last name
4. open the terminal in your vs code and type `npm install`
5. next type `npm run test` in your terminal
6. Complete your work making regular commits, once you have all your tests passing and you are ready to submit your work please see canvas for instructions on how to submit

### Testing & Debugging

Open a second terminal inside of your project by clicking on the split terminal icon
![alt text](assets/split_terminal.png "Split Terminal")

Inside of your second terminal type `npm start`
![alt text](assets/npm_start.png "type npm start")

You will be running your tests in one terminal and debugging in the other. As you work on your code you should make use of `console.log` to check your progress and debug.
![alt text](assets/tests_debug_terminal_final.png "your terminal should look like this")

### Task 2: Project Requirements (MVP)

You must complete all tasks inside of `index.js` and answer the questions above.

In your solutions, it is essential that you follow best practices and produce clean and professional results. Schedule time to review, refine, and assess your work and perform basic professional polishing including spell-checking and grammar-checking on your work. It is better to submit a challenge that meets MVP than one that attempts too much and does not.

## Resources

[Sprint Challenge Study Guide](https://www.notion.so/lambdaschool/Unit-1-Sprint-3-Study-Guide-033a9a00659a4ef98c12eb97e49a6110)

## Submission format

Please submit your project via codegrade by following [these instructions](https://www.notion.so/lambdaschool/Submitting-an-assignment-via-Code-Grade-A-Step-by-Step-Walkthrough-07bd65f5f8364e709ecb5064735ce374)
