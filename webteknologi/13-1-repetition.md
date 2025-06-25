# Repetition

## Loops

### Exercise level 1

Create a for loop that goes from 90-100



### Exercise level 1

Create a for loop that runs 10 times



### Exercise level 1

Create a for loop that runs the number of times that an array has items

```javascript
const numbers = [1, 34, 77];
// Create a for loop that runs 3 times

const numbers = [1, 34, 77, 88, 1];
// Create a for loop that runs 5 times
```



### Exercise level 2

Create a for loop that iterates through an array logging out all the names in uppercase

```javascript
const names = ['Peter', 'Azra', 'Nadine'];
// Your code here
// should log out 
// PETER
// AZRA
// NADINE
```



## Arrays

### Exercise - Level 1

Lav et array af strenge med 6 elementer

Log det første element ud og elementet på index 4.



### Exercise - level 1

Log out last element of the following array

```javascript
const prices = [100, 300, 489, 532, 34];
```



### Exercise - level 1

Add an extra price to the end of the prices array



### Exercise - level 2

Print "First is bigger" if the first element is bigger than the last element of the array



### Exercise - level 3

Using the `prices` array print the average of the prices



## Objects & Functions exercises

### Level 1 - Write an object that represents a cat from The Sims

- A cat has the following properties:
  - Name, age, color, hunger, isFemale
  - Think about what data type will represent the property best



### Level 1 - Using the cat object

- Print a string with all properties of the cat: name, age, color, hunger and isFemale



### Level 2 - Using the cat object

- Write a function that receives a Cat object and prints the name and age of the cat



### Level 2 - Using the list of cats

- Write a function that takes a list of cats and **returns** a single string with all their names
- Print the string outside of the function scope



### Level 2 - Using the cat object 

- Write an array with 4 cat objects
- Write a function that returns the amount of female cats
- Print the amount outside of the function scope



### Level 3 - Using the list of cats

- Add more cats to the list (6 in total)
- Write a function that prints the amount of breedable pairs
  - A breedable pair is a female cat, a male cat whom that are both less than 7 years in age



## DOM exercise: Guess my number

The project is a game where you have to guess a number. Here are the rules

- When clicking the `Check!` `button` check if what the user wrote in the `input` matches the number they have to guess
  - If it's wrong increase the Score by 1 and clear the input
  - If it is correct and smaller than Highscore set the new score as the highscore and clear the input. Also show the correct number in the `?`
- If the `Again` `button` is clicked clear the score and the highscore and start from scratch
- Add a couple of extra features you think could be cool!

The starter for the project can be [found here](https://github.com/jonasschmedtmann/complete-javascript-course/tree/master/05-Guess-My-Number/starter). Create a new project and copy the files into a new project!
