## Building a basic API with database

#### A) /all

- Create an end point that displays all data of all pokemon

#### B) /all/names

- Create an end point that displays the names of all pokemon

#### **C) /:primary**

- Create an endpoint that displays the name of all pokemon with the parameter as primary type
  - If a product cannot be found, the API will respond with a [404 status code and a message that informs the user](https://expressjs.com/en/starter/faq.html#how-do-i-handle-404-responses)


#### D) /:speed

- Create an endpoint that displays all pokemon with a speed higher than the provided parameter

#### E) /highest/:stat

- Create an endpoint that returns the Pokémon with the highest value for the specified stat. The available stats are "attack," "defense," "hp," "specialAttack," "specialDefense," and "speed."
  - If the API receives another stat such as: secondarytype it will respond with an error

#### F) /average/:primaryType/

- Create an endpoint that displays all pokemon with a speed higher than the average of the provided primary type

#### G) /total/:name

- Create an endpoint that displays the total of a provided pokemons stat
  - I.E. if :name = Bublasaur.
  - Bulbasaur has the following stats: 45, 65, 65, 49, 49,45.
  - Return the sum of those numbers.



#### Advanced(Optional)

#### E) /:name/:stat

- Create an endpoint that displays true or false if the provided pokemons stat is higher than the average pokemon stat in that stat category
  - I.E.  if :name = squirtle & :stat = defence
  - Return true if squirtle's defence is higher than the average pokemons defence


#### F) /compare/:pokemon1/:pokemon2

- Design an endpoint that compares two Pokémon based on their stats and returns the one with higher overall stats.
  - If either Pokémon is not found, respond with a 404 status code and a relevant message.

#### G) counter/:name

- Design an endpoint that displays all types that provided pokemon is weak against. You will need to implement more logic and/or data in the end-point.
  - I.E if :name = squirtle
    - Squirtle is a water pokemon. Water pokemon are weak against electric and grass.
    - The API will answer: [Electric, Grass]