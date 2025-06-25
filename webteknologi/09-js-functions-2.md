# Functions 2



## Learning goals

- Asynchronicity in javascript
  - `setTimeout`
  - `setInterval`
- Arrow function



## Teacher instruction

- Vi arbejder i små tilfældige grupper idag
- Husk aflevering søndag. Ane kommer til at give jer feedback!
- There are a lot of exercises. They are not meant to be finished all of them. 
- Level 1 I expect you to finish



## Flipped classroom videos

- [Learn JavaScript setTimeout() in 6 minutes! ⏰](https://www.youtube.com/watch?v=shWr5DNVeCI)
- [JavaScript ES6 Arrow Functions Tutorial](https://www.youtube.com/watch?v=h33Srr5J9nY)



## Peer instruction



### Question 1 - 1 min

What is the value of `sumOfNumbers`?

```javascript
function adder(a, b) {
  console.log(a + b);
}

const sumOfNumbers = adder(4, 4);
```

1. `8`
2. `"8"`
3. `4+4`
4. None of the above



### Question 2 - 1 min

What is the value of `sumOfNumbers`?

```javascript
const emojiPrinter = () => {
  console.log("🎉❤️🚀");
}

console.log(emojiPrinter)
```

1. `"🎉❤️🚀"`
2. `🎉❤️🚀`
3. `undefined`
4. None of the above





## Asynchronicity in javascript

### `setTimeout`

`setTimeout` is a way to run some javascript after some time. Let's try and log a string after 10 seconds👇

```javascript
setTimeout(function() {
  console.log("hello");
}, 10000);
```

`setTimeout` takes two arguments

1. A function (also called a callback function)
2. Delay in milliseconds

Basiscally `setTimeout` waits for 10000 milliseconds (10 seconds). After that time it need to run some code. The way we tell `setTimeout` what to do is by giving a function to it. This function is called a callback function. It's a function (`setTimeout`) that takes another function 🤯



### `setInterval`

`setInterval` is a function that runs some code each interval. So if we want to log `"hello"` every 2 seconds we can do that using `setInterval`👇

```javascript
setInterval(function() {
	console.log("hello");
}, 2000);
```

This will log `hello` every 2 seconds to the browser.



## Arrow functions

There are two ways of defining a function

1. Function declaration using the `function` keyword
2. Arrow function using an arrow `=>`

Let's take a look at converting a function into an arrow function 👇

```javascript
function printName(name, age) {
  console.log(name, age);
}

// Is the same as
const printName = (name, age) => {
  console.log(name, age);
};
```

So we create a variable that gets assigned to the arrow function. The parameters works exactly like with the function declaration. After the parameters we add the arrow `=>`. The rest of the function is the same as before

It is possible to make the arrow function even more consice like shown below. But it it not necessary!

```javascript
function circleArea(radius) {
    return radius * 2 * Math.pi;
}

// Remove the function keyword add in arrow
const circleArea1 = (radius) => {
    return radius * 2 * Math.pi;
}

// If there is only one parameter, we can remove the paranthesis
const circleArea2 = radius => {
    return radius * 2 * Math.pi;
}

// If there is only one line in the function we can remove the curly braces and the return statement
// radius * 2 * Math.pi is AUTOMATICALLY being returned
const circleArea3 = radius => radius * 2 * Math.pi;
```



## Exercises



### 📝 Exercise 1 - level 1

Create a sum function using only arrow functions



In the following exercises you can decide if you want to use arrow functions or normal function



### 📝 Exercise 2 - level 1

Write a function that takes three numbers as parameter, sums the integers and returns the result.

```javascript
console.log(someFunctionName(10, 20, 5)); // 35
```



### 📝 Exercise 3 - level 1

Write a function that returns a string with an emoji added to the end. You choose the emoji

```javascript
console.log(someFunctionName('Nicklas')); // Nicklas🚀
```



### 📝 Exercise 4 - level 1

Write a method that takes a string as parameter and returns the string in uppercase.

```javascript
const uppercaseString = someFunctionName('kea');
console.log(uppercaseString); // 'KEA'
```



### 📝 Exercise 6 - level 1

Write a function that checks if the last character is a questionmark

```javascript
console.log(someFunctionName('Hello!')); // false
console.log(someFunctionName('Denmark')); // false
console.log(someFunctionName('How are you?')); // true
```



### 📝 Exercise 7 - teachers and students

Duration: 20 min. Preparation: 15 min. presentation 5 min.

In the following exercise one group will randomly be selected to be teachers and the other group will be students

In groups of two people prepare a small 5 minute lecture. 

The lecture should explain **functions, arguments, parameters and return**:

- How functions work
- One or more practical examples



- As teachers present the 5 minute lecture
- As students ask good interesting questions



### 📝 Exercise 8 - level 2

Create a stopwatch using `document.write` and `setInterval` that keeps counting up. First solve this task using the `function` keyword, then solve it using arrow functions



### 📝 Exercise 9 - level 2

Create a function that as an argument takes how many ghosts to print and then prints that number of ghosts

```javascript
logGhosts(4); // 👻👻👻👻
logGhosts(1); // 👻
```



### 📝 Exercise 10 - level 2

Implement a BMI calculator function. Identify the needed parameters and return type.



### 📝 Exercise 11 - level 3

Create a function that sums the digits from a number. Fx the sum of the number 12400 is 7 because 1+2+4+0+0=7

```javascript
const sumOfNumbers = someFunctionName(195);
console.log(sumOfNumbers); // 15
```



### 📝 Exercise 12 - level 3

[Latitude and longitude](https://www.youtube.com/watch?v=swKBi6hHHMA) is used for finding a position on earth. It is often used when working with data. We can even get the position of our browser 👇 

Its so cool how easy it is to access this super advanced technology!

```javascript
if (navigator.geolocation) {
  navigator.geolocation.getCurrentPosition(showPosition, showError);
} else {
  alert("Geolocation is not supported by this browser.");
}

const showPosition = (position) => {
    console.log(position.coords.latitude, position.coords.longitude);
    // Your code here
}
const showError = (error) => console.log(error);

getLocation();
```

Create a function that takes the latitude and longitude from the browser and returns a string with the following format: `latitude:51.5555;longitude:16.888 `

Write the position to the document using `document.write`



### 📝 Exercise 13 - Flight booking fullname function - level 3

Even for a startup as successful as Smart-ease there needs to be money in the bank. A customer from a flight booking website has  asked for our help creating a specific part of their application:

When a user books a flight they **write their firstname and surname**, but when the ticket is printed a **fullname should be displayed**. It is our responsibility to create that.

Create a function called `getFullname` that returns a fullname. It should have two parameters: `firstname` and `surname`.

```javascript
getFullname("Benjamin", "Hughes"); // returns "Benjamin Hughes"
```

Test that the function works by calling the function with some different names



#### Formal fullname

On the flight website the user has the possibility to **check a checkbox** that **indicates** if the user wants to be **adressed formally**. Lets also change `getFullname` to include support for formal name.

Create an extra parameter `useFormalName` that is a boolean. If it is true the function should add a `Lord` in front of the name.

```javascript
getFullname("Benjamin", "Hughes", true); // returns "Lord Benjamin Hughes"`
getFullname("Benjamin", "Hughes", false); // returns "Benjamin Hughes"
```

What do we do if `useFormalName` is not given as an argument?

Remember to consider someone calling the function with an empty string as firstname and lastname.

Try out your code by pasting your `getFullname` function in the javascript part of this codepen: https://codepen.io/hackyourfuture-cph/pen/jJWwbN

But what if the person is a woman? Describe how you would fix the `getFullname` so it also works for women

> Exercise taken from [HackyourFuture](https://github.com/HackYourFuture-CPH/JavaScript/blob/main/javascript1/week2/homework.md)



### 📝 Exercise 14 - Work on portfolio