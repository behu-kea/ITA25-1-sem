## API x MongoDB project

Today we will create an extract-transfer-load (ETL) application.

- We want to build a database of characters from Star-Wars.
- We will fetch data from the following API: https://swapi.dev/documentation



The data will be **extracted** from the API.

It will be **transfered** to our server (localhost).

It will be **loaded** into MongoDB.



We will build an algorithm that fetches the first 10 characters of the swapi API.

- The algorithm will be implemented in a node.js script.

```http
https://swapi.dev/api/people/1/
```

Study the following API call and notice the end-point ends with 1.



When called the API answers with the following response:

```json
HTTP 200 OK
Content-Type: application/json
Vary: Accept
Allow: GET, HEAD, OPTIONS

{
    "name": "Luke Skywalker", 
    "height": "172", 
    "mass": "77", 
    "hair_color": "blond", 
    "skin_color": "fair", 
    "eye_color": "blue", 
    "birth_year": "19BBY", 
    "gender": "male", 
    "homeworld": "https://swapi.dev/api/planets/1/", 
    "films": [
        "https://swapi.dev/api/films/1/", 
        "https://swapi.dev/api/films/2/", 
        "https://swapi.dev/api/films/3/", 
        "https://swapi.dev/api/films/6/"
    ], 
    "species": [], 
    "vehicles": [
        "https://swapi.dev/api/vehicles/14/", 
        "https://swapi.dev/api/vehicles/30/"
    ], 
    "starships": [
        "https://swapi.dev/api/starships/12/", 
        "https://swapi.dev/api/starships/22/"
    ], 
    "created": "2014-12-09T13:50:51.644000Z", 
    "edited": "2014-12-20T21:17:56.891000Z", 
    "url": "https://swapi.dev/api/people/1/"
}
```



## Application boilerplate

https://github.com/nicklasdean/swapi-mongo

```javascript
const axios = require("axios");
const { MongoClient } = require("mongodb");

// MongoDB connection URI (update if needed)
const mongoURI = "mongodb://localhost:27017";
const dbName = "swapiDB";
const collectionName = "people";

async function fetchDataAndSave() {
    let client;

    try {
        // Connect to MongoDB
        client = new MongoClient(mongoURI, { useNewUrlParser: true, useUnifiedTopology: true });
        await client.connect();
        console.log("Connected to MongoDB");

        //Choose a database to work in
        const db = client.db(dbName);
        const collection = db.collection(collectionName);

        // Fetch data from the SWAPI API
        const response = await axios.get("https://swapi.dev/api/people/1/");
        const data = response.data;

        // Fetch a single person from the database and display it
        const existingPerson = await collection.findOne({ url: data.url });

        // Insert the data into MongoDB
        const result = await collection.insertOne(data);
        console.log("Data saved to MongoDB with ID:", result.insertedId);

    } catch (error) {
        console.error("Error fetching or saving data:", error);

    } finally {
        // Close the MongoDB connection
        if (client) {
            await client.close();
            console.log("MongoDB connection closed");
        }
    }
}

// Run the function
fetchDataAndSave();

```



## ETL Exercises

In the following exercises you should figure out how the algorithm should be changed in pseudocode before changing the code.

```
//Pseudocode
Create a connection to MongoDB
Choose a database to work in
Fetch data from the API
Insert the data in MongoDB
```



**A)** Update/Patch the ETL appliation such that: 

- The database-name that is created in mongoDB is: star-wars
- The collection name is: Characters

**B)** Update/Patch the ETL application such that the data that is fetched from the application is printed out by `console.log`

**C)** Update/Patch the ETL application such that 10 characters are fetched and inserted instead of only 1

**D)** Update/Patch the ETL application such that if a character that is already in the database is fetched, we should **not** insert the character in the database

**Advanced (optional)**

- Update/Patch the ETL application such that it fetches and inserts all characters from the API.

  - Hint: Notice the response you will get from a call:

    - https://swapi.dev/api/people/200/
    - vs
    - https://swapi.dev/api/people/20/

  - You can look at the response header by using `response.data.header`

    

## Query exercises

In the mongoDB shell

**A) ** Find all characters with a height greater than 170 cm and mass less than 80 kg.

**B)** Display all characters that is in the first film `"https://swapi.dev/api/films/1/"`

**C)** Find all characters with blue eye color and fair skin color

**D) **Count how many characters are classified under each gender (e.g., male, female, n/a, etc.).