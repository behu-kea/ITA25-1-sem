

## Exercises: The Mongo Client

- Create a new node project
- In the terminal run `npm install mongodb --save`

- Inspect the following code

```javascript
const {MongoClient} = require("mongodb");

let mongoDB;

MongoClient.connect("mongodb://localhost:27017", { useUnifiedTopology: true })
    .then((client) => {
        console.log("Connected to MongoDB");
        mongoDB = client.db("pokemons");

        fetchAllData();
  			//Call more functions here
    })

async function fetchAllData(){
    const trainers = await mongoDB.collection("trainers").find().toArray()
    console.log(trainers)
}

//Write more functions here
```



**If we want to find all trainers from "Pallet Town and only receive their name and hometown the query looks like this:**

```javascript
db.trainers.find(
  { hometown: "Pallet Town" },
  { name: 1, hometown: 1, _id: 0 }
);
```



#### **Exercises**

**A)** Write a new function that finds all trainers who are younger than 20

**B)** Write a new function that finds all trainers with "Pikachu" as their favourite pokemon

**C)** Write a function that takes a Javascript object as argument and inserts the data to mongoDB

**D)** Write a function that takes a pokemon name as argument. 

- If the pokemon name is found all data about the pokemon is written to the console.
- If no pokemon is found, the console will write out "404 - sorry"

**E)** Write a function that counts the number of trainers from each Hometown

- Hint: https://www.mongodb.com/docs/manual/reference/operator/aggregation/sum/



## Exercises: MongoDB & Express

Consider the following 2 scripts:

```javascript
//npm install express --save
const express = require("express");
//npm install mysql2 --save
const mysql = require("mysql2");
//npm install cors --save
const cors = require("cors");
//npm install mongodb --save
const {MongoClient} = require("mongodb");

const port = 3000;
const app = express();

app.use(cors());

let mongoDB;
MongoClient.connect("mongodb://localhost:27017", { useUnifiedTopology: true })
    .then((client) => {
        console.log("Connected to MongoDB");
        mongoDB = client.db("pokemons");
    })

app.get('/', (req, res) => {
    res.send('Hello, world!');
});

app.get("/trainers", async (req, res) => {
    const trainers = await mongoDB.collection("trainers").find().toArray();
    res.json(trainers);
});

app.listen(port, () => {
    console.log(`Server running on http://localhost:${port}`);
});
```



```javascript
//npm install express --save
const express = require("express");
//npm install mysql2 --save
const mysql = require("mysql2");
//npm install cors --save
const cors = require("cors");
//npm install mongodb --save
const mongoClient = require("mongodb");

const app = express();
const port = 3000;

app.use(cors());

//Host, user, password database
const mysqlConnection = mysql.createConnection({
    host: process.env.DBHOST,
    user: process.env.DBUSER,
    password: process.env.DBPASSWORD,
    database: process.env.DBNAME
});

//Find single pokemon by name
app.get('/pokemon/:name/', (req,res)=>{
    const pokemonUserRequest = req.params.name;
    mysqlConnection.query('SELECT * FROM pokemon WHERE `name` = ?',
        [pokemonUserRequest],
        (error, results)=>{
            res.send(results);
        });

});

app.listen(port, () =>{
    console.log(`Application is now running on port ${port}`);
});
```

#### Preparation

**A) With your partner**

- Explain what is the difference between the scripts, what are they trying to achieve?
- What are the similiarities between the scripts?



**B)** Identify the parts of the script that you will need to connect to MySQL and mongoDB

- You do need **not** try/catch in this exercise
- In the above scripts - what are the names of the constants or variables needed to query MySQL or mongoDB



#### **Objective: To build an API with 2 data sources: MySQL & MongoDB**



**D) **Test the existing API such that `pokemon/:name` returns all data of a pokemon by providing it's name as a path variable



**E) Build a new endpoint** `/trainers`

- The end-point will contain the following [dataset](https://github.com/nicklasdean/data/blob/main/trainers.json)
  - Download as raw and import to MongoDB compass.
  - Build an API end-point that fetches all trainers from mongoDB and sends the data to the user



#### **End points to build**

**F)** `trainers/:name`

Returns all data of a trainer by providing it's name as a path variable

**G)** `trainers/:town`

Returns all data of a trainer by providing a town as a path variable

**H) ** `trainers/age`

returns the average age of all trainers



**Advanced (Optional)**

**I)** `trainers/details/:pokemon/`

Returns all pokemon data from a trainers pokemons.

- This requires data from both MySQL and MongoDB.