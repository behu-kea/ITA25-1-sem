## Download mongoDB compass

https://www.mongodb.com/try/download/community

https://www.mongodb.com/products/tools/compass



## Import the dataset

https://github.com/nicklasdean/data/blob/main/pokemon.json

- Download raw file



## Read the documentation

https://www.mongodb.com/docs/manual/tutorial/query-documents/

- Equality CoAndition
- Query Operators
  - https://www.mongodb.com/docs/manual/reference/operator/query/#std-label-query-selectors
- AND conditions
- OR conditions
- AND and OR condition



## Exercises

**A)**

Retrieve all pokemon of type "Water"

- 52 retrieved

**B)**

Retrieve all pokemon that has an attack greater than 100

- 169 retrieved

**C)**

Retrieve all pokemon from generation 1-3

- 386 retrieved

**D)**

Retrieve all Pokémon with a type1 of either "grass" or "fire" and with an attack value greater than 50.

- 104 retrieved

**E)**

Retrieve all pokemon that are either water-type or grass type from generation 1 or 2

- 74 retrieved

**F)**

Find all Pokémon that have more than one ability.

- Hint you can use [regex](https://www.mongodb.com/docs/manual/reference/operator/query/regex/) in mongoDB
- 692 retrieved

**Advanced Optional**

**G)**

Find all Pokémon that have the ability "Overgrow" or "Blaze" and a speed greater than 90

- 10 Retrieved

**H)** 

Find all pokemon with the following criteria: 

- They are either of type "electric" or "psychic".
- They have an attack value greater than 70.
- Their base happiness is greater than 50.
- They belong to generation 1 or 2.
- They do not have any abilities containing the word "Intimidate".



- 13 Retrieved



