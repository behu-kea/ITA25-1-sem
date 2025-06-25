# Web og data porteføljeaflevering



## Web - Guess my number

The project is a game where you have to guess a number.

The starter for the project can be [found here](https://github.com/jonasschmedtmann/complete-javascript-course/tree/master/05-Guess-My-Number/starter). Copy the files into a new project in Webstorm! Run the `index.html` file. You will see that the UI looks as expected **but** the functionality is not working. We have to make it work. 

 Here is how the website should work 👇

- When clicking the `Check!` `button` check if what the user wrote in the `input` matches the number they have to guess
  - If it's wrong increase the Score by 1 and clear the input
  - If it is correct and smaller than Highscore set the new score as the highscore and clear the input. Also show the correct number in the `?`
- If the `Again` `button` is clicked clear the score and the highscore and start from scratch
- If the user writes a number that is not between 1 - 20, then an error message should be shown to the user. Or if the user writes something that is not a number
- Create a way to show what numbers have been guessed so far. This is like a history of guesses
- *Optional* - Add confetti when the correct number is guessed
- *Optional* - Play diferent sounds when the correct or wrong number is guessed
- Add a feature you think could be fun!



### 📝 Portfolio dark mode/light mode
Now its time to work on your portfolio!

Create lightmode/darkmode functionality on your portfolio. When clicking a button the colors of your website should change from being in light mode (light-coloured background, darkish text) to dark mode (darkcolored background and lightcolored text)

Here are some examples: [https://webflow.com/made-in-webflow/lightmode](https://webflow.com/made-in-webflow/lightmode)



## Database design

### **Escape Room Game Design and Player Analytics Platform**

**Project Overview:** Design a MySQL database for an escape room business that allows game designers to manage different escape room scenarios, track team progress through rooms, record success rates, and analyze player behaviors. The database supports managing different escape room experiences, logging player actions, tracking team completions, and providing analytics on game difficulty and player performance.

### **Entities & Relationships**

1. **Escape Rooms**:
   - **RoomID**, `Title`, `Theme` (e.g., "Haunted Mansion", "Alien Invasion"), `DifficultyLevel`, `Duration` (in minutes).
   - Each room can have multiple **Puzzles** and can host multiple **Teams**.
2. **Puzzles**:
   - **PuzzleID**, `RoomID`, `PuzzleName`, `Description`, `PuzzleType` (e.g., "Logic", "Search", "Riddle"), `DifficultyRating`.
   - Puzzles are linked to **Escape Rooms**.
3. **Teams**:
   - **TeamID**, `TeamName`, `StartTime`, `EndTime`, `CompletionStatus` (e.g., "Solved", "Timed Out").
   - Teams can play different escape rooms, and each team consists of multiple **Players**.
4. **Players**:
   - **PlayerID**, `Name`, `Nickname`, `Email`.
   - Players join **Teams**, and their performance is tracked during the game.
5. **Team Progress**:
   - **ProgressID**, `TeamID`, `PuzzleID`, `StartTime`, `EndTime`, `SolvedStatus` (e.g., "Solved", "Failed").
   - Tracks team progress on each puzzle to determine which were solved and how long each took.
6. **Hints**:
   - **HintID**, `PuzzleID`, `HintText`, `UsageCount`.
   - Tracks the hints available for each puzzle and how often they were requested.
7. **Player Actions**:
   - **ActionID**, `PlayerID`, `PuzzleID`, `ActionType` (e.g., "Attempt", "HintRequest"), `ActionTimestamp`.
   - Records significant actions performed by each player during the game for deeper analytics.
     - The escape room host will record actions when observing the players

### **Key Features**

- **Room Management**: Game designers can add new escape rooms and puzzles, manage the duration, and define the difficulty level.
- **Team and Player Tracking**: Track which players are part of a team, their time spent in each room, and puzzles solved.
- **Hint Usage and Analytics**: Keep track of hints requested for each puzzle to understand common pain points and difficulties faced by players.
- **Player and Team Analytics**: Generate reports on which rooms are the hardest, which puzzles take the longest, and individual player performance.



- Populate the tables with data and write 3 query examples that queries the database and provides insight in the data.
- Export an EER diagram showcasing the database design



## Query data

Find the data in the **World database:** https://dev.mysql.com/doc/index-other.html

### 1. Find Countries with a Population Greater Than the Global Average

**Exercise:** Write a query to find all countries where the population is greater than the average population of all countries in the dataset.

### 2. Top 5 Most Spoken Languages

**Exercise:** Write a query to find the top 5 most spoken languages in the world, along with their total number of speakers.

### 3. Calculate the Population Density

**Exercise:** Write a query to calculate the population density (population / area) for each country, and return the country name along with its population density. Only include countries with a non-zero area.

### 4. Countries with No Cities

**Exercise:** Write a query to find all countries that do not have any cities listed in the `cities` table.

### 5. Average Life Expectancy by Continent

**Exercise:** Write a query to calculate the average life expectancy for each continent. Include the continent name in the result.

### 6. Cities in Countries with Similar Population

**Exercise:** Write a query to find cities in countries that have a population within 10% of the population of 'Japan'. Display the city name, country name, and population.

### 7. Rank Countries by GDP

**Exercise:** Write a query to rank countries by their GDP in descending order. Show the country name and its GDP, and add a rank column.

### 8. Countries with a Higher GDP than Their Neighboring Countries

**Exercise:** Write a query to find countries whose GDP is higher than that of any of their neighboring countries. Assume neighboring countries are defined by the `neighbor` relationship in the `countries` table.

### 9. Language Distribution Across Countries

**Exercise:** Write a query to find the number of countries where each language is spoken. Show the language and the count of countries speaking that language, ordered by the count in descending order.

### 10. Cities with Population Greater than Their Country’s Average

**Exercise:** Write a query to find all cities where the city population is greater than the average population of their respective countries. Show the city name, country name, and both populations.



## Aflevering på Fronter

Porteføljeopgaven skal afleveres **individuelt inden d. 13/10 kl 23:59**

I skal aflevere linket til github portfoliet hvor koden er!

[Fronter aflevering](https://kea-fronter.itslearning.com/LearningToolElement/ViewLearningToolElement.aspx?LearningToolElementId=1294101)





