# Objects



## Learning goals

- What is an object
- Accessing data using a key
- Changing data using a key
- Array of objects



## Teacher instruction

- Context for where in js we are
  - Basics
  - DOM
  - API
  - Visualisation
- Divide your problem into smaller problems first
- Opgave 6 kl 14:15



## Peer instruction 1 min



### Question 1

What is the value of `orResult`?

```javascript
function orFunction(a, b) {
  const result = a && b;
}

const orResult = orFunction(true, false);
```

1. `true`
2. `false`
3. `true&&false`
4. None of the above



### Question 2

What will the following code log out?

```javascript
const user = {
	name: "Alisa",
	age: 43
};

user.age = "43";
console.log(user.age)
```

1. 43
2. "43"
3. "age"
4. "User.age"
5. Syntax error



## Flipped classroom videos

- [Object In JavaScript | JavaScript Object Tutorial For Beginners](https://www.youtube.com/watch?v=TCXQsQL5kPo)



## What is an object?



### What problem does obejcts solve?

Let's say we wanted to store the name, age and email of a user with what we have learned so far. We could fx create 3 variables to hold this information:

```javascript
const user1Name = 'Camilla';
const user1Age = 37;
const user1Email = 'cam123@gmail.com';
```

This would work **but** we would very quickly run into problems when we get more users. What if we had 1000 users, now we would need to create 3000 variables 😱. That would obviously not work. 



What about storing this data (name, age and email) in an array. Let's try that:

```javascript
const user1 = ['Camilla', 37, 'cam123@gmail.com'];
```

This is a bit better **but** what if we forgot where we stored the different values. Let's say we have 30 things we want to store on a user. Was the favorite food stored in index 27 or 28? Or what if we forgot where we stored these things? Now we would have to create an extra array that keeps that of where we store what information

```javascript
const userIndexInformation = ['name', 'age', 'email'];
```

Hmm now we are creating extra work and extra confusion. What if there was a data structure where we save information using a the name what we are storing (key). 



Well we are in luck 👇



### Objects

In an object we instead use a key to refer to some data. Objects are a key-value pair that can store any data type, including other objects. They're used to store data about a single thing and are often used to store data about a user or a product. Let's solve the problem we outlined above: 

```javascript
const user = {
  name: 'Camilla',
  age: 37,
  email: 'cam123@gmail.com'
};
```

Here we create a new object with 3 keys: `name`, `age` and `email`. What is smart is that it is easy to access the kind of data we are interested in.



### Accessing data using key

Let's try and access some of the data form the `user` object

```javascript
const user = {
  name: 'Camilla',
  age: 37,
  email: 'cam123@gmail.com'
};

// Give me the value at the key called name
console.log(user.name); // 'Camilla'
console.log(user['name']); // 'Camilla'
// Give me the value at the key called age
console.log(user.age); // 37
console.log(user['age']); // 37
// Give me the value at the key called email
console.log(user.email); // 'cam123@gmail.com'
console.log(user['email']); // 'cam123@gmail.com'
```

We can access data at a key using either dot notation of square brackets. This is the same: `console.log(user.email)` and `console.log(user['email'])`. 



### Changing data using key

We are not only able to access data using key, but we can also change it. 

```javascript
const user = {
  name: 'Camilla',
  age: 37,
  email: 'cam123@gmail.com'
};

// We can use either dot notation
user.age = 38;
console.log(user); // { name: 'Camilla', age: 38, email: 'cam123@gmail.com' }

// Or square bracket notation
user['age'] = 56;
console.log(user); // { name: 'Camilla', age: 56, email: 'cam123@gmail.com' }
```



## Array of objects

When working with data in javascript it is often in the form of an array of objects. Take a look at [this json file](https://gist.githubusercontent.com/pankaj28843/08f397fcea7c760a99206bcb0ae8d0a4/raw/02d8bc9ec9a73e463b13c44df77a87255def5ab9/movies.json) that contain movie data. It is an array of objects. Let's take a closer look at it 🔎

```json
// This top line i have added!
const movies = [
  {
    "title": "'71",
    "year": 2014,
    "rating": 7.2,
    "votes": 41702,
    "running_times": 5940
  },
  {
    "title": "'A' gai wak",
    "year": 1983,
    "rating": 7.4,
    "votes": 11942,
    "running_times": 6300
  },
]
```

Every object in the array represents a movie and has the following keys: `title`, `year`, `rating`, `votes`, `running_times`. If i wanted to get the second movies rating in javascript i would write 

```javascript
const secondMovieRating = movies[1].rating;
```



## Exercises



### 📝 Exercise 1 - level 1

The objects below have some syntax issues - try and fix them all!

```javascript
const kitten = {
    fur colour: "orange",
    age "23"
};

const laptop =
    brand: "Lenovo"
    ram "5GB"
}

const phone = {
    operating system "iOS",
    hasStylus: true,
    megapixels 12
    "batteryLife": "24 hours"
```



### 📝 Exercise 2 - level 1

Create an object that describes you. Fx a key called `age` with the value of `28`. Add a key that holds an array. Add minimum 6 keys



### 📝 Exercise 3 - level 1

Log the values of each property of `kitten`

```javascript
// console.log the values of each property of "kitten"
let kitten = {
  ageMonths: 3,
  isFemale: true,
  furColour: "brown",
};

// your code here
```



### 📝 Exercise 4 - level 1

Write code in the space provided so that the expected values output

```javascript
const dog = {
  name: "Billy",
  wantsToPlay: false,
};

// WRITE CODE BELOW THIS LINE
// WRITE CODE ABOVE THIS LINE

console.log(dog.name); // Rex
console.log(dog.wantsToPlay); // true
```

*Exercises taken from here: https://syllabus.codeyourfuture.io/js-core-2/week-1/lesson*



### 📝 Exercise 5 - level 2

The following object represents all the people that are in space right now. 

Data is taken from [here](http://api.open-notify.org/astros.json)

```javascript
const data = {
  people: [
    { craft: "ISS", name: "Oleg Kononenko" },
    { craft: "ISS", name: "Nikolai Chub" },
    { craft: "ISS", name: "Tracy Caldwell Dyson" },
    { craft: "ISS", name: "Matthew Dominick" },
    { craft: "ISS", name: "Michael Barratt" },
    { craft: "ISS", name: "Jeanette Epps" },
    { craft: "ISS", name: "Alexander Grebenkin" },
    { craft: "ISS", name: "Butch Wilmore" },
    { craft: "ISS", name: "Sunita Williams" },
    { craft: "Tiangong", name: "Li Guangsu" },
    { craft: "Tiangong", name: "Li Cong" },
    { craft: "Tiangong", name: "Ye Guangfu" }
  ],
  number: 12,
  message: "success"
};

```

Using the `astronautsInSpace` variable log out the following things

1. The number of astronauts in space right now
2. The name of the craft of the last person in the array
3. The lastname of the first astronaut in the ISS



### 📝 Exercise 6 - Lets analyze this code in class

- What does it do?
- How od we communicate about code?
- How should we improve it?

```javascript
var global_variable = 'I am global!';

function calc_price(cart) {
    var total_price = 0;
    for(i in cart) {
        if(i.price != undefined && i.quantity != undefined) {
            total_price = total_price + i.price * i.quantity;
        }
    }
    console.log(global_variable);
    alert('Total price is ' + total_price);
    return total_price;
}

var my_cart = [
    {name: 'apple', price: 1, quantity: 3},
    {name: 'banana', price: 2, quantity: 2},
    {name: 'cherry', price: 3, quantity: 1}
];

calc_price(my_cart);
```



### 📝 Exercise 7 - Please improve the following code

```javascript
function ChkPass(user_data) {
  usr = user_data['user'];
  pw = user_data['password'];
  if (usr.length > 0 && pw.length > 0) {
    status = 'valid';
  }
  else {
    status = 'invalid';
  }
  alert('Status: ' + status);
}

ChkPass({user: "test", password: "1234"});
```



### 8 - Build a sentiment analyzer

A sentiment analyzer is some functionality that figures out how positive/negative a sentence is. 

Fx the sentence "I am mega super awesome happy" Should have a high score
The sentence "I hate doing boring stuff" should have a low score.

Create a function that takes a string as a parameter. Calling the function will return an object with `score`, `positiveWords` and `negativeWords`. You decide how the score should be implemented and what words are negative and positive.

Here is an example of using the function:

```javascript
const sentimentScoreObject = getSentimentScore('I am mega super awesome happy');

console.log(sentimentScoreObject);
/*
{
  score: 3,
  positiveWords: ['happy', 'awesome', 'super'],
  negativeWords: [],
}
*/
```



### 9 - Character frequencies - optional

Write a function that counts the frequency of characters in a string:

```javascript
console.log(getCharacterFrequencies('happy'));
/*
{
  characters: [
    {
      character: 'a',
      count: 1
    },
    {
      character: 'h',
      count: 1
    },
    {
      character: 'p',
      count: 2
    },
    {
      character: 'y',
      count: 1
    }
  ], length: 5
}
*/
```



### 10 - Credit card number formatter - optional

This is a very real world example of a problem i got at my previous work. I was tasked to implement one of the smart credit card input fields, where the credit card numbers are seperated with a space. Fx inputting 123456789 would show 1234 5678 9.

![Credit card formatter](assets/credit-card-formatter.png)

Create a function that takes a number as parameter. The function should return the following object:

```javascript
const formattedCreditCardObject = formatCreditCardNumber(123456789);
console.log(formattedCreditCardObject);
/*
{
  original: 123456789,
  formatted: "1234 5678 9",
}
*/
```

Things to consider:

- What should happen if the function is called with an argument that is not a number?



## Algebraic notation chess svær opgave

Lav en funktion der kan tage imod en chess notation og vurdere om den er valid. 

https://www.youtube.com/watch?v=iDnW0WiCqNc

https://www.chess.com/terms/chess-notation



<!--

## 📝 Handin - Individual



### 1 - What to wear

Create a function (that you have to name) that has temperature as parameter. Based on the temperature it should return a string with what the user should wear. You decide what the user should wear based on the temperature.

An example is:

```javascript
const clothesToWear = youCreateThisFunctionName(18);
console.log(clothesToWear); // Logs out: "shorts and a t-shirt"
```

![Wearing jackets](https://media.giphy.com/media/26u6dryuZH98z5KuY/giphy.gif)



### 2 - Dice game 🎲

Write a function that simulates a dice roll. You call the function with the number of times you would like to roll the dice. 

Every time the dice hits a 6 log out `You just hit 6!`

```javascript
// This means roll the dice 3 times. 6 is hit once
rollTheDice(3);
// You just hit 6

// The dice is rolled 5 times with 2 hits
rollTheDice(5);
// You just hit 6
// You just hit 6

// Here the user rolls 5 times but does not hit 6 even once
rollTheDice(5);
```



**Part 2**

If the user hits 6 in every roll the log out `Jackpot 🎉`

```javascript
// Hits 6 twice
rollTheDice(2); // Jackpot 🎉

// Does not hit 6
rollTheDice(2);

// Hits 6 once
rollTheDice(2);
// You just hit 6
```



### 3 - Build a sentiment analyzer

A sentiment analyzer is some functionality that figures out how positive/negative a sentence is. 

Fx the sentence "I am mega super awesome happy" Should have a high score
The sentence "I hate doing boring stuff" should have a low score.

Create a function that takes a string as a parameter. Calling the function will return an object with `score`, `positiveWords` and `negativeWords`. You decide how the score should be implemented and what words are negative and positive.

Here is an example of using the function:

```javascript
const sentimentScoreObject = getSentimentScore('I am mega super awesome happy');

console.log(sentimentScoreObject);
/*
{
  score: 3,
  positiveWords: ['happy', 'awesome', 'super'],
  negativeWords: [],
}
*/
```





### 4 - Character frequencies - optional

Write a function that counts the frequency of characters in a string:

```javascript
console.log(getCharacterFrequencies('happy'));
/*
{
  characters: [
    {
      character: 'a',
      count: 1
    },
    {
      character: 'h',
      count: 1
    },
    {
      character: 'p',
      count: 2
    },
    {
      character: 'y',
      count: 1
    }
  ], length: 5
}
*/
```



### 5 - Credit card number formatter - optional

This is a very real world example of a problem i got at my previous work. I was tasked to implement one of the smart credit card input fields, where the credit card numbers are seperated with a space. Fx inputting 123456789 would show 1234 5678 9.

![Credit card formatter](assets/credit-card-formatter.png)

Create a function that takes a number as parameter. The function should return the following object:

```javascript
const formattedCreditCardObject = formatCreditCardNumber(123456789);
console.log(formattedCreditCardObject);
/*
{
  original: 123456789,
  formatted: "1234 5678 9",
}
*/
```

Things to consider:
- What should happen if the function is called with an argument that is not a number?



### Handin

Handin on [Fronter here](https://kea-fronter.itslearning.com/LearningToolElement/ViewLearningToolElement.aspx?LearningToolElementId=1182596). The handin is the **10-10-2022 23:59**

Handin the link for the code on GitHub!

When the handin date has passed you will be assigned a classmate to review

Review metrics:

- Nævn en ting der inspirerede dig ved opgaven
- Find et eksempel på en variabel der har et godt navn og et der har et dårligt navn. Begrund hvorfor
- Vælg en af opgaverne og besvar om der var en tydelig og god struktur i koden? Begrund hvorfor/hvorfor ikke

-->
