# Functions: Basics

- Defining functions
- Scope
- Argument/Parameters
- Return Values
- Static Methods



### Flipped classroom videos

- [JavaScript FUNCTIONS are easy! 📞](https://www.youtube.com/watch?v=HFaxylC7bUc)

- [Function basics](https://javascript.info/function-basics)



## Exercises A

### 📝 Exercise 1

- Create two arrays with the following values: [5,6,3,4,6,34,5,5] [5,5,5,66,7,3,1,1,1,4]

- Concatenate the arrays and sort the concatenated array

- Ensure the array has been sorted by logging the results

  

### 📝 Exercise 2

```javascript
//Create the initial javascript like this:
let number = "22";
let number2 = "22";

console.log(number + number2);
//Output: 2222
```

- Use the [parseInt method](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/parseInt) to parse the two strings to integers, such that we can obtain a result of 44 instead of 2222



### 📝 Exercise 3 (advanced)

```javascript
//Create the initial javascript like this:
participants = ["nicklas;33","benjamin;44","lars;55"]
```

- Use a loop, the [split method](https://www.w3schools.com/jsref/jsref_split.asp) and the [parseInt](https://www.w3schools.com/jsref/jsref_split.asp) method to calculate the total age of all participants



## Exercises B

### 📝 Exercise 1

Create a function that takes a string and then logs that string out

```javascript
someFunctionName("hello"); // logs out hello
someFunctionName("abcde"); // logs out abcde
```



### 📝 Exercise 1.1

Create a function that adds two numbers together

```javascript
const returnedNumber = someFunctionName(2, 6);
console.log(returnedNumber); // 8
```



### 📝 Exercise 2

Create a function that takes a name and returns `true` if the first character is the character `a` otherwise `false`

```javascript
console.log(someFunctionName('kea')); // false
console.log(someFunctionName('anna')); // true
```

*Hint: Check out [https://stackoverflow.com/questions/3427132/how-to-get-first-character-of-string](https://stackoverflow.com/questions/3427132/how-to-get-first-character-of-string)*



### 📝 Exercise 3

The following exercises requires you to understand how to convert celcius to fahrenheit and back again. 

**Celsius to Fahrenheit Formula:** (°C * 1.8) + 32 = °F

**Fahrenheit to Celsius Formula:** (°F - 32) / 1.8 = °C



### 📝 Exercise 3A

Create a function called `celciusToFahreneit` it should have a parameter called `celcius`. 

It should return a string in the following format `[CONVERTED_TEMPERATURE] degree fahrenheit` fx `23 degree fahrenheit`

Reflect:

- What are meaningful variables for the function

```javascript
console.log(celciusToFahreneit(30)); // 86 degree fahrenheit
```



### 📝 Exercise 3B

Create a second function called `fahrenheitToCelcius` it should have a parameter called `fahrenheit`

It should return a string in the following format `[CONVERTED_TEMPERATURE] degree celcius`

```javascript
function convertTemperature(fahrenheit){
  //Your code here
}
```



### 📝 Exercise 3c

Create a third function called `convertTemperature` it should have two parameters `inputScale` and `degrees`

- If the inputScale argument is equal to "fahrenheit", the function should call the `celciusToFahrenheit` and log the result
- If the inputScale argument is equal to "celcius", the function should call the `FahrenheitToCelcius` and log the result
- If the inputscale argument is not equal to either, the function should log `invalid input`

```javascript
function convertTemperature(inputScale, degrees){
  //Your code here
}
```



### 📝 Exercise 4

Create a function called `increaseByHalf` that should

- Take a number as an input
- Return this input number increased by half of the input number

Here is an example of the output

```javascript
console.log(increaseByHalf(50)); // 75
console.log(increaseByHalf(100)); // 150
```



### 📝 Exercise 5

Examine out the code below:

```javascript
function printMessage(x) {
  console.log("Hello, nice to meet you " + x);
}

function getMessage(name) {
  return "Hello, nice to meet you " + name;
}

printMessage("Mitch");
printMessage("August");
getMessage("Laetitia");
```

The functions above behave similarly but *differ* in some important ways.

Study the code above and then answer the following questions:

1. How many times is the function `printMessage` called ?
2. How many times is the function `getMessage` called ?
3. What is the parameter name for the function `printMessage` ?
4. What is the parameter name for the function `getMessage` ?

> From [Code your future](https://syllabus.codeyourfuture.io/js-core-1/week-1/lesson/#functions)



### 📝 Exercise 6

Create a function that has two parameters: `stringToLog` and `numberOfTimesToLog`

When calling the function it should log out the `stringToLog` the amount of times specified in `numberOfTimesToLog`

If the `numbersOfTimesToLog` is longer than the string length, the function should log: `Invalid parameters`

Here is an example of the output 👇

```javascript
logString('hello', 3);
// Log output
// hello
// hello
// hello
```



### 📝 Exercise 7 (Advanced - optional)

- Create a function that will return either true or false.

- The function returns true if it receives an argument that is a valid CPR-number.

- The function receives input from the user by using the `prompt()` function in javascript
  - https://www.w3schools.com/jsref/met_win_prompt.asp




### 📝 Exercise 8 (Advanced - optional)

When working with data we often need to convert data from one format to another therefore: Create a function that takes a date in the following format: `MONTH/DAY/YEAR` fx `10/24/2022`. It should return a date in the following format: `DAY-MONTH-YEAR` fx `24-10-2022`

*Hint: research the `.split` method*

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/split

```javascript
const reformattedDate = someFunctionName('10/24/2022');
console.log(reformattedDate); // 24-10-2022

const reformattedDate = someFunctionName('5/9/2020');
console.log(reformattedDate); // 9-5-2020
```

The function receives input from the user by using the `prompt()` function in javascript

- https://www.w3schools.com/jsref/met_win_prompt.asp

  

### 📝 Exercise 9 (Advanced - optional)

Create a function (that you have to name) that has temperature as parameter. Based on the temperature it should return a string with what the user should wear. You decide what the user should wear based on the temperature.

An example is:

```javascript
const clothesToWear = youCreateThisFunctionName(18);
console.log(clothesToWear); // Logs out: "shorts and a t-shirt"
```

![Wearing jackets](assets/giphy.gif)



### 📝 Exercise 10 (Advanced - optional)

You specify how many days from today an event is being held. The function then figures out what weekday the event is being held. Here is an example:

Today is Sunday and the event is in 5 days. Therefore the event will be held on a friday.

```javascript
// With todays weekday a tuesday
console.log(getEventWeekday(9)); // Logs out "Thursday"

// With todays weekday a Friday
console.log(getEventWeekday(2)); // Logs out "Sunday"
```

You should get the today's day from the system.

Hint: use remainder operator, array indexes and investigate `new Date` in js.

