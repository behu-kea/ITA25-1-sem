<!--

De har haft om:

- Variable
- Conditional
- Arrays
- Lidt om funktioner. Lav lige en opgave med det
- HTML og CSS

-->



# HTML og Javascript porteføljeaflevering



## Rekonstrurer hjemmeside - HTML og CSS

Tag et screenshot af en hjemmeside du bruger dagligt og rekonstruer det vha html og css. I opgavebesvarelsen husk at tilføje screenshot af hjemmesiden



Hvor meget i detaljen du går er op til dig selv. Det vigtigste er at layoutet stemmer nogenlunde overens. Om i lige får den rigtige skygge, farve eller animation er ikke så relevant. Fokus er på layoutdelen



## Javascript opgaver



### JavaScript Exercise: Student Grades Analysis

**Objective:**
In this exercise, students will create a program that analyzes student grades, determines the highest and lowest grades, and calculates the average grade. This exercise will reinforce their understanding of arrays, variables, and conditionals.



**Instructions:**

1. **Create an array** that holds 8 grades (integers between 0 and 100) representing the scores of different students - level 1
2. Log out how many grades there are -  level 1
3. Classify each grade into one of the following categories - level 2
   - `A` if the grade is 90 or above.
   - `B` if the grade is between 80 and 89.
   - `C` if the grade is between 70 and 79.
   - `D` if the grade is between 60 and 69.
   - `F` if the grade is below 60.
4. Evaluate overall class performance - level 2
   - If the average grade is 90 or above, the class performance is `Excellent`.
   - If the average grade is between 80 and 89, the performance is `Good`.
   - If the average grade is between 70 and 79, the performance is `Satisfactory`.
   - If the average grade is below 70, the performance is `Needs Improvement`.
5. *Optional* - Determine - level 3
   - The highest grade in the array.
   - The lowest grade in the array.
   - The average grade.
6. Output:
   - The highest grade with its category.
   - The lowest grade with its category.
   - The average grade.
   - A list of all grades with their corresponding categories.



**Example of Expected Output:**

For the following input:

```javascript
let grades = [85, 92, 78, 63, 95, 88, 72, 54, 81, 67];
```

The expected output should be:

```javascript
There are 10 grades in the class

Grades:
90: A
97: A
83: B
68: D
100: A
93: A
77: C
59: F
86: B
72: C

Overall Class Performance: Good

Highest Grade: 100 (A)
Lowest Grade: 59 (F)
Average Grade: 82.5
```



### **Treasure Hunter**

**Scenario:**

You are on a small island, and there's a treasure box hidden somewhere! Your job is to move around the island to find it.



**Instructions:**

1. **Island Setup:**
   - The island is represented by a 1D array of 5 elements.
   - One of these elements is the hidden treasure (`T`), and the rest are empty (`-`).

Example:

```javascript
const island = ['-', '-', '-', 'T', '-'];
```



**Objectives**:

1. Log out how many moves there are in the island - level 1
2. For each move log the following out - level 2
   If there is a treasure log out: `Treasure found at move 3 :)`
   If there is not a treasure log out: `No treasure found :(`
3. Log out how many treasures there are in the island - level 3



Example output:

The following array should output the following:

```javascript
let island = ['-', '-', 'T', '-', '-'];
```

```
There are 5 moves in the island

No treasure found :(
No treasure found :(
Treasure found at move 3 :)
No treasure found :(
No treasure found :(

There were 1 treasures in the island
```



Another example:

```javascript
let island = ['T', 'T', 'T', '-'];
```

```
There are 4 moves in the island

Treasure found at move 1 :)
Treasure found at move 2 :)
Treasure found at move 3 :)
No treasure found :(

There were 3 treasures in the island
```



### Startup name generator

Let's create a function that can generate startup names:

Create a function called `getStartupName`. When called it should return a random startup name. Here is how it should work:

1. Inside the function there should be two arrays with starutp words
2. Use the two arrays to get a random word from each array and return the new startup name with the two words



Here is an example with the following two arrays:

```javascript
// Array 1: First part of the startup name
const firstWords = ["Tech", "Inno", "Smart", "Blue", "Next", "Bright", "Quantum", "Rapid", "Future", "Digital"];

// Array 2: Second part of the startup name
const secondWords = ["Vision", "Solutions", "Systems", "Works", "Dynamics", "Hub", "Network", "Innovations", "Labs", "Path"];
```

Output 1:

```
Your startup name could be: Quantum Hub
```

Output 2:

```
Your startup name could be: Smart Solutions
```

*Hint: to figure out how to get a random number. Try asking google or ChatGPT*



## Fronter aflevering

Porteføljeopgaven skal afleveres **individuelt inden d. 29/9 kl 23:59**

I skal aflevere linket til github portfoliet hvor koden er!

[Fronter aflevering](https://kea-fronter.itslearning.com/LearningToolElement/ViewLearningToolElement.aspx?LearningToolElementId=1294087)
