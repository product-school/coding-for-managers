# Solutions

## Javascript Basic

- [Exercise 1](http://www.w3resource.com/javascript-exercises/javascript-basic-exercise-1.php)
- [Exercise 2](http://www.w3resource.com/javascript-exercises/javascript-basic-exercise-2.php)
- [Exercise 3](http://www.w3resource.com/javascript-exercises/javascript-basic-exercise-3.php)
- [Exercise 4](http://www.w3resource.com/javascript-exercises/javascript-basic-exercise-4.php)
- [Exercise 5](http://www.w3resource.com/javascript-exercises/javascript-basic-exercise-5.php)
- [Exercise 6](http://www.w3resource.com/javascript-exercises/javascript-basic-exercise-6.php)
- [Exercise 7](http://www.w3resource.com/javascript-exercises/javascript-basic-exercise-7.php)
- [Exercise 8](http://www.w3resource.com/javascript-exercises/javascript-basic-exercise-8.php)
- [Exercise 9](http://www.w3resource.com/javascript-exercises/javascript-basic-exercise-9.php)
- [Exercise 10](http://www.w3resource.com/javascript-exercises/javascript-basic-exercise-10.php)


## Functions

### Tip Calculator
```js
var addTipElement = document.getElementById('add_tip');

addTipElement.addEventListener('click', addTipAmount)

function addTipAmount(event) {
      var tipAmount = prompt('what percentage tip would you like to leave?')

      var originalMealCost = document.getElementById("meal_cost").value
      var total = Math.round((1 + tipAmount/100) * originalMealCost);

      var totalCost = document.getElementById("total_cost").innerHTML = "You need to pay: $" + total

}
```
### Number Guesser

```js
var guessButton = document.getElementById('makeGuess')
guessButton.addEventListener('click', performGuess)

var AI_Guess = Math.round(Math.random() * 10)


function performGuess() {
      var userInput = document.getElementById("yourGuess").value * 1.0;
      var status = ""

      if (userInput == AI_Guess) {
            status = "Wow you got it!"
      } else if (userInput < AI_Guess) {
            status = "You guessed a smaller number"
      } else {
            status = "Your guess is too high"
      }
      console.log('status is: ', status)

      var output = document.getElementById("status")
      output.innerHTML = status;
}
```

### The Fortune Teller

```js
function tellFortune(jobTitle, geoLocation, partner, numKids) {
    var future = 'You will be a ' + jobTitle + ' in ' + geoLocation + ' and married to ' +
   partner + ' ' + ' with ' + numKids + ' kids.';
    console.log(future);
}

tellFortune('bball player', 'spain', 'Shaq', 3);
tellFortune('stunt double', 'Japan', 'Ryan Gosling', 3000);
tellFortune('Elvis impersonator', 'Russia', 'The Oatmeal', 0);
```

### The Puppy Age calculator
```js
function calculateDogAge(age) {
    var dogYears = 7*age;
    console.log("Your doggie is " + dogYears + " years old in dog years!");
}

calculateAge(1);
calculateAge(0.5);
calculateAge(12);
```

### The Lifetime Supply calculator
```js
function calculateSupply(age, numPerDay) {
  var maxAge = 100;
  var totalNeeded = (numPerDay * 365) * (maxAge - age);
  var message = 'You will need ' + totalNeeded + ' cups of tea to last you until the ripe old age of ' + maxAge;
  console.log(message);
}

calculateSupply(28, 36);
calculateSupply(28, 2.5);
calculateSupply(28, 400);
```

### The Geometrizer
```js
function calcGeometry(radius) {
  var circumference = Math.PI * 2*radius;
  console.log("The circumference is " + circumference);
  var area = Math.PI * radius*radius;
  console.log("The area is " + area);
}
```

### The Temperature Converter
```js
function celsiusToFahrenheit(celsius) {
  var celsiusInF = (celsius*9)/5 + 32;
  console.log(celsius + '°C is ' + celsiusInF + '°F');
}

function fahrenheitToCelsius(fahrenheit) {
  var fahrenheitInC = ((fahrenheit - 32)*5)/9;
  console.log(fahrenheit + '°F is ' + fahrenheitInC + '°C');
}
```
