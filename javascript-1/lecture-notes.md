# Javascript

## What you'll learn in this course
* Understand what JavaScript is
* Learn about 'Data Types' in JS
* Learn what a function is and how to write it
* Understand Control Flow
* Understand how JS is used in the browser


Like Java, Python, and Ruby, JavaScript is a scripting language that allows you to build dynamic software systems. One of the benefits of JavaScript is that it can run in your browser, serving as a client-side scripting language. Through technologies like Node.js, JavaScript can also be used as a server-side scripting language. Almost all interactive effects that you see on a webpage are likely enabled by JavaScript.

#### Background:

JavaScript was created in 1995 by Brendan Eich, an engineer at Netscape, and first released with Netscape 2 early in 1996.
JavaScript is the only scripting language that can be run by your browser.

**Practice 1: Interacting with the user directly through the browser**

JavaScript is powerful because it allows us to interact with the user through the browser.
* open a tab in Chrome and try the following:
    * `alert(5 + 7)`
    * `alert("The date and time is now " + new Date());`
    * `var favoritePark = prompt("What is your favorite park in San Francisco?")`
    * `console.log("Your favorite park in SF is", favoritePark)`

#### Writing JavaScript directly within HTML files and linking to external scripts

**Within the head or body of your HTML Files:**

```html
<!DOCTYPE html>
<html>
 <head>
    <title>JS Test</title>
    <style>
      #player_title {
        font-family: 'helvetica neue', helvetica, sans-serif;
        letter-spacing: 1px;
        text-transform: uppercase;
        text-align: center;
        border: 2px solid rgba(0,0,200,0.6);
        background: rgba(0,0,200,0.3);
        color: white;
        box-shadow: 1px 1px 2px rgba(0,0,200,0.4);
        border-radius: 10px;
        padding: 3px 10px;
        display: inline-block;
        cursor: pointer;
      }
    </style>
 </head>
 <body>
    <div id="player_title">
      Player 1: Jennifer
    </div>
    <script>
      // js goes here
    </script>
 </body>
</html>
```

**Practice 2: Interacting with the DOM directly through Javascript**

What is the DOM? The DOM is the Document Object Model. Basically, the entire webpage (all the elements, from the `body` to each invividual `div`) is represented as a series of Javascript Objects that have methods and properties.

JavaScript allows us to interact with HTML/CSS by directly manipulating items on the DOM - we can select DOM elements by using CSS/Element selectors and change them dynamically. We can also create elements on the fly. All of this functionality is accessed off of the `document` object in the browser. Let's check it out in our chrome developer console.

Event listeners are one of the most important components of interactivity on a webpage. They allow us to execute code when a certain user action takes place, like a `click`. Add the following code into the `script` section in your HTML file:

 ```js
var playerTitleElement = document.getElementById('player_title');

playerTitleElement.addEventListener('click', updateName);

function updateName(event) {
  var name = prompt('Enter a new name');
  event.target.textContent = 'Player 1: ' + name;
}
 ```

#### JS Syntax

Javascript is similar to Ruby with some notable exceptions:
* instead of using the `end` keyword to the delimit the bounds of a function, conditional or loop, JS makes heavy use of curly braces `{}`.
* in a conditional statement, the condition (that evaluates to true/false) must go inside of parentheses `()`.
* JS uses the `var` keyword to define a variable and the `function` keyword to define a function.

Example conditional:

```js
var dayIndex = new Date().getDay();
if (dayIndex === 1){
  console.log("Have the Monday blues?! Write some JavaScript and it'll make everything better :)")
} else {
  console.log("Don't worry, Friday is only", 5 - dayIndex, "days away!")
}
```

#### JS Functions

Similar to Ruby function, JS functions take optional arguments and return values. The default return value is `undefined` and we must explicitly use the `return` keyword to return anything else. There are several ways to define a function:

```js
   var multiplyByThree = function(num) {
     return num * 3;
   }

  function multiplyByThree(num) {
    return num * 3;
  }

  console.log(multiplyByThree(5));
```

**Exercise 1:**

Add another user prompt into the `updateName()` function. It should ask the user to enter a color. Store that color into a new variable called `color`. Then use that variable to change the color of the playerTitle element's background. *Hint: you can access an element's css through its `.style` property. You can change it by simply reassigning the value to the new color*

**Linking to external JavaScript files:**

```html
 <script src="/path-to-a-javascript-file"></script>
 ```

**Exercise 2:**

Let's move our JavaScript into an external file. Name it `script.js`. Reference it in the `<script>` tag by defining the relative path of the file in the `src` property. Make sure it's working by testing out the functionality of the `player` button.

#### Data Types, Arithmetic Operators, & Comparisons
JavaScript has many of the same datatypes as Ruby:

* Number: 1, 23452345
* String: 'Hello World', "Hi there'
* Boolean: true, false
* Array: [1, 2, 3]
* Null, Undefined

#### Making Comparisons: JavaScript evaluates the comparison, returning true or false

* Greater than: `>`
* Less than: `<`
* Equality: `==`; Converts operands if they aren't the same type, then applies strict equality; Eg: 1 == "1"
* Strict Equality: `===` Two operands are equal without type conversion: Eg: 1 === 1
* Not equal: !=
* Strict not equal: !==
* Greater or equal: >=
* Less or equal: <=

#### Arithmetic Operators: 5 operators with the same order of operations as your traditional arithmetic

* Multiplication: `*`. Eg: 5 * 10 = 50;
* Division: `/`. Eg: 10/5 = 2;
* Addition: `+`. Eg: 5 + 7 = 12;
* Subtraction: `-`. Eg: 7 - 5 = 2;
* Modulus: `%`: Performs division and returns the remainder. Eg: 6 % 3 = 0; Eg: 7 % 3 = 1;

**Exercise 3:**

Let's create a simple tip calculator. Under the `player_title` `div`, let's add:

```html
<br/>
<input id="meal_cost" type="number" placeholder="Meal Cost"/>
<br/>
<button id="add_tip">Add Tip</button>
<br/>
<div id="total_cost"></div>
```

Create a function called `AddTip` that has a `prompt` in it that asks the user what percent tip they want to leave. The prompt should store the value into a variable called `tipAmount`. You can get the meal price from the input box by selecting the element using its ID and then accessing the `value` property. Save this amount into another variable called `mealPrice`. Try doing some simple arithmetic and update the `textContent` of the `total_cost` div with the total amount. Finally, add a `click` listener onto the `add_tip` button and specify your `AddTip` function as the callback. *Your solution will have a small but critical issue - what is it any why is it happening?*

#### JS Objects:

JS objects are similar to hashes in Ruby. One critical difference is that a JS object can have a functions as a value. The `this` keyword refers to the object itself, much like in ruby when `self` is used to refer to current Class or Instance.

```js
var harry = {};
harry.height = "6 feet";
harry.weight = "190 lbs";
harry.profession = "Barber";
harry.children = ["Jack", "Jill", "Gretta"];
harry.praiseChildren = function(){
  var praises = ["kind", "curious", "adventurous", "hard working", "musically gifted"];
  for (var i = 0; i < this.children.length; i++){
    console.log(this.children[i], "is so", praises[Math.floor(Math.random()*3)])
  }
}
```

* Methods: JavaScript objects, arrays and functions each have their own unique properties and methods available to them
• Full list of built in JavaScript methods: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Methods_Index

#### Loops/Iterators
**Loops allow you to execute a block of code multiple times until a condition is met**

* For Loops: executed until a specific condition returns false.
```js
for (initialization; condition; increment) {
  // statements
}

var ages = [30, 35, 10, 22, 18, 12];

for (var i = 0; i < ages.length; i++) {
  console.log(ages[i] + " years old");
}
```

* While Loops: Executed while a condition is true.
```js
var start = 1;
while (start < 10) {
  console.log("start: " + start);
  start++; // shorthand for start = start + 1
}
```

**Exercise 4:**

Using a `while` loop, create a number guessing game. You will need two variables, one for the guess and one for the answer. To supercharge your game, give the user hints about whether their number is high or low depending on their guess - you can use conditionals and comparison operators for this. *Hint: The computer can choose a starting number between 0-100 by using `Math.round(Math.random()*100)`*

#### Extra Resources
* https://www.codecademy.com/learn/javascript
* https://www.tutorialspoint.com/javascript/
* https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/JavaScript_basics
