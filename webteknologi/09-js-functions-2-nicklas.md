# Functions: Advanced

- Anonymous functions
- Functions as arguments
- ForEach
- Filter & Map

### Preparation

[Anonymous functions video](https://youtu.be/h33Srr5J9nY?si=o1ETfMU44KnnPkkx)

[Function expressions](https://javascript.info/function-expressions)

[Arrow functions](https://javascript.info/arrow-functions-basics)

[Filter video](https://youtu.be/4_iT6EGkQfk?si=vg4eIesb8nIK0F8O)



## Exercises A



### 📝 Exercise 1

Write a function that takes three numbers as parameter, sums the integers and returns the result.

The function should be defined as an [arrow function](https://javascript.info/arrow-functions-basics)

The functions should **return** the result

```javascript
console.log(someFunctionName(10, 20, 5)); // 35
```



### 📝 Exercise 2

Write a function that takes three numbers as parameter, identifies the largest number and returns the result.

- The function should be defined as an [arrow function](https://javascript.info/arrow-functions-basics)

- The functions should not **return** anything (void function) - it should print the result to the HTML page using [document.write()](https://www.w3schools.com/jsref/met_doc_write.asp)



### 📝 Exercise 3

Write a function that receives two parameters. An array of numbers and a number.

- The function will return **true** if the number is higher than the array average
- The function will return **false** if the number is lower than the array average

The function should be defined as an [arrow function](https://javascript.info/arrow-functions-basics)



### 📝 Exercise 4 (Optional advanced)

Write a function that takes an array of numbers as parameter, identifies the largest number and returns the result.

The function should be defined as an [arrow function](https://javascript.info/arrow-functions-basics)

The functions should not **return** anything (void function) - it should print the result to the HTML page using [document.write()](https://www.w3schools.com/jsref/met_doc_write.asp)



### 📝 Exercise 5 (Optional advanced)

Write a function that accepts a list of country names as input and returns the longest country name.

The function should be defined as an [arrow function](https://javascript.info/arrow-functions-basics)

*Sample data* : 

```javascript
["Australia", "Germany", "United States of America"]
```

*Expected output* : "United States of America"



### 📝 Exercise 6 (Optional advanced)

Write a function that accepts a list of country names as input and returns the country with the most amount of words in the name.

The function should be defined as an [arrow function](https://javascript.info/arrow-functions-basics)

*Sample data* : 

```javascript
["Australia", "Germany", "United States of America","Denmark","The United Kingdom of Great Britain and Northern Ireland","Independent and Sovereign Republic of Kiribati	"]
```

*Expected output* : "The United Kingdom of Great Britain and Northern Ireland"



## Exercises B



### 📝Exercise 1

Write a function that iterates through an array of strings and returns the average amount of letters pr. word

The function should use [the foreach syntax](https://www.w3schools.com/jsref/jsref_foreach.asp) loop

Remember that a string also has a [.length property](https://www.w3schools.com/jsref/jsref_length_string.asp) 

```javascript
const strings = ["dog","cat","lazy","fox","jumps","over","the","fence","javascript","tobias rahim"]
```



### 📝Exercise 2

Write a function that filters all names above the length of 5 letters.

The function should use the [filter syntax](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)

```javascript
const firstNames = [
  "Alice",
  "Bob",
  "Charlie",
  "David",
  "Eve",
  "Frank",
  "Grace",
  "Hannah",
  "Isabel",
  "Jack",
  "Katherine",
  "Liam",
  "Mia",
  "Noah",
  "Olivia",
  "Sophia",
  "Thomas",
  "Victoria",
  "William",
];
```



### 📝Exercise 3

Write a function takes an array of numbers as parameter. The function filters away all numbers that are even and returns an array only of uneven numbers

The function should use the [filter syntax](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)

```javascript
const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
```



### 📝 Exercise 4

Write a function that converts an array of numbers representing hours to their corresponding amount of seconds.

The function should use the [map syntax](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)

```javascript
const hours = [2,4,12,1,0.5,3,4,5,10]
```



### 📝Exercise 5 (advanced optional)

Write a function with two parameters, an array and a letter.

- The function returns an array with all the words starting with the letter put in the function argument

  

```javascript
const words = ["apple", "banana", "cherry", "agøøørk","date", "fig", "grape", "kiwi", "lemon", "mango", "orange"];

filterLetters(words, "a"); //returns [apple, agøøørk]
```



### 📝 Exercise 6 (advanced optional)

Write a function that takes an array of integers as paramter and removes all unique numbers. The function returns an array with only 1 entry of each unique number.

```javascript
const numbers = [1, 2, 3, 2, 4, 5, 6, 3, 7, 8, 9, 1, 10];
```



### 📝Exercise 7 (advanced optional)

Write a function that receives an array of cpr numbers.

The function will filter all cpr numbers that do not follow the following rules of a cpr number:

- It should be 11 characters long
- The first 2 indices cannot be higher than 31
- The next 2 indicies cannot be higher than 12
- The next character should be a "-"

```javascript
const strings = [
  "121256-7890",
  "987654-3210",
  "1004890123",
  "112233-44552",
  "111244-556611",
  "150690-3152asd",     
];
```
