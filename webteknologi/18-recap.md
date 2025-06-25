# Recap



## Overblik

- IT-Arkitektur sang: https://cdn1.suno.ai/52f3504e-398f-49bd-a80c-4c41684d7538_1.mp4
- Recap af emner
- Prøveeksamen. Er der nogle der tør?
- Opgaver



## Generative AI feedback





## Opgaver



### Color Mixer - level 1

**Description**: Create a function `mixColors(color1, color2)` that takes two color names as strings (e.g., 'red', 'blue') and returns the name of the new color created by mixing them. Assume only primary and secondary colors are used.

Example: 

```javascript
console.log(mixColors("red", "white")); // pink
```



### Temperature Converter - Level 1

**Objective**: Write a function `convertTemperature(temp, unit)` that converts temperatures between Celsius and Fahrenheit. The `unit` parameter specifies the unit to convert to ('C' for Celsius, 'F' for Fahrenheit).

```javascript
console.log(convertTemperature(32, 'C')); // Should output: 0 (Fahrenheit to Celsius)
console.log(convertTemperature(0, 'F')); // Should output: 32 (Celsius to Fahrenheit)
```



### Event Scheduler - level 3

**Objective**: Write a function `scheduleEvents(events, start)` that takes an array of event objects (each with a `name` and `duration` in minutes) and a start time. The function should return a schedule mapping each event to its start time.

Example

```javascript
const events = [
  { name: "Meeting", duration: 30 },
  { name: "Workshop", duration: 45 }
];
console.log(scheduleEvents(events, "09:00"));
// Should output: { "09:00": "Meeting", "09:30": "Workshop" }
```



### Path Finder - level 3

Objective: Write a function `findPath(maze, start, end)` that determines a path through a maze.

#### Description:

1. **The Maze**: The maze is represented as a 2D array where each element can either be `0` or `1`. A `0` represents an open space where one can move, and a `1` represents a wall which cannot be traversed.
2. **Start and End Points**: The `start` and `end` parameters are coordinates in the maze, given as an array of two numbers, `[rowIndex, columnIndex]`. Your function should find a path from the start coordinate to the end coordinate.
3. **Moving Through the Maze**: You can move up, down, left, or right, but cannot move diagonally. Also, you cannot go outside the bounds of the maze.
4. **Return Value**: The function should return an array of strings, each string being a move: `'up'`, `'down'`, `'left'`, or `'right'`. This array should represent the sequence of moves that leads from the start to the end point. If no path is possible, the function can return an indication of this, like `null` or an empty array.

#### Example:

Suppose we have the following maze:

```
javascript
const maze = [
  [0, 0, 0, 0, 1],
  [1, 1, 0, 1, 1],
  [0, 0, 0, 0, 0],
  [0, 1, 1, 1, 0],
  [0, 0, 0, 0, 0]
];
```

And we call the function with:

```
javascript
findPath(maze, [0, 0], [4, 4]);
```

Here, `[0, 0]` is the top-left corner (starting point) and `[4, 4]` is the bottom-right corner (ending point).

#### Expected Output:

The function should return an array of moves that will take you from `[0, 0]` to `[4, 4]`, navigating through open spaces (`0`) and avoiding walls (`1`). For example, one possible solution could be:

```
javascript
['right', 'right', 'down', 'down', 'down', 'right', 'right', 'up', 'up']
```

This sequence would navigate the maze from the start to the end as specified.