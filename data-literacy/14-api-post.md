## Building an API with POST

https://github.com/nicklasdean/post-error-handling

### A) /new

- Create a POST end-point that receives all data in a POST request of a new pokémon. The new pokémon will be inserted into the database with mysql2.

### B) /updateHP

Create a POST endpoint that allows users to update the `hp` (health points) of an existing Pokémon by providing its `id`.

##### Steps

1. Create a `POST` route at `/updateHP` that accepts the Pokémon `id` and the new `hp` value in the request body.
2. Search the database for a Pokémon with the matching `id`.
3. If found, update the `hp` value and return a success response. If not found, return a 404 error.
4. Test the end-point with insomnia

### C) /updateHP

Update the applications such that a user can update the HP of a pokemon with an HTML/CSS/JS front-end.

**Steps**

1. Add another form next to "Register new pokemon"
2. submit the `id` and new HP  with a fetch call.
3. If found, update the `hp` value in the database of the pokemon. 

### D) Advanced (Optional)

- Enhance the API such that the applications checks if the pokemon already exists.
- If a duplicate is found, respond with a 409 status code and an appropriate error message.
