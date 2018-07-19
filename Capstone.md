# Capstone Project

DEMO: https://codepen.io/GainorB/full/XBXVge/

# OBJECTIVE
1. Create HTML structure for game board
2. Create CSS for game board
3. Start building game logic
4. Develop a basic understanding regarding the logic in our game

# DO NOW

Yesterday we learned how to work with variables, loops and functions. Let's get some practice by doing these challenges!

# CHALLENGES
Spend the next 25 minutes working on these challenges:
1. Print 100 numbers to the console. Either 0-99 or 1-100. Whatever method makes sense to you.
2. https://repl.it/repls/LavenderThinNumericalanalysis
3. https://repl.it/repls/LavenderThinNumericalanalysis

# AFTER DO NOW

Log into CodePen. If you remember your login information, GREAT! If not, give us a second to help you!

# HTML

Our gameboard will consist of this layout!

**Review:**
1. Does anyone remember the difference between giving our HTML elements classes vs. ids?
2. Does anyone see any HTML elements we've never learned before?
3. How many unique HTML attributes are there?

Lets spend the next 10 minutes making our HTML document more unique! Use your imagination! Do whatever you like, whatever you think makes sense. Make your game standout.

```html
<html>
<head>
  <title>TicTacToe by Mr. B</title>
</head>

<body>
  <h1 id="status">Click a box, let's play!</h1>
  <div id="gameboard">
      <div class="box" id="0"></div>
      <div class="box" id="1"></div>
      <div class="box" id="2"></div>
      <div class="box" id="3"></div>
      <div class="box" id="4"></div>
      <div class="box" id="5"></div>
      <div class="box" id="6"></div>
      <div class="box" id="7"></div>
      <div class="box" id="8"></div>
  </div>
</body>

</html>
```

# CSS

Here's my code below. Spend some time making my code, yours! **Remember**, CSS gives us the power to transform plain HTML elements and make them look unique. I know there are CSS attributes below we haven't learned, but it doesn't hurt to change a value to see what happens! Explore for the next 20 minutes.

Great Resource: http://www.speedcoder.net/lessons/css/1/

Hints for making this CSS yours!:
  * Change Font colors
  * Change Background colors
  * Maybe add a background image to our gameboard? or our webpage?
  * Change Font Sizes
  * Change Border Colors
  * Change Border Sizes
  * Change Hover Effects (notice what happens when our mouse hovers over a box)
  * Change Border Styles
  * Change the size of the box (HINT: right now each box is 200px x 200px)
  * Change the animation Colors (HINT: checkout @keyframes)
    * Add more colors?
    * Add different colors?
    * Add less colors?

```css
.player1 {
  color: white;
  background-color: blue;
}

.player2 {
 color: white;
 background-color: red;
}

#gameboard {
  display: grid;
  grid-template-columns: repeat(3, 200px);
  grid-template-rows: repeat(3, 200px);
  grid-gap: 10px;
}

.box {
  display: flex;
  align-items: center;
  justify-content: center;
  border: 1px solid black;
  font-size: 130px;
  transition: background-color 1s, transform 3s;
}

.box:hover {
  cursor: crosshair;
  background-color: black;
  transform: rotate(180deg);
}

.box:nth-child(5) {
  animation-name: changeColor;
  animation-duration: 4s;
  animation-timing-function: ease-in;
  animation-iteration-count: infinite;
}

@keyframes changeColor {
  0%   {background-color: red;}
  25%  {background-color: yellow;}
  50%  {background-color: blue;}
  100% {background-color: green;}
}
```

---

## 🎉 10 MINUTE BREAK

Tips on having an effective break:

1.  Bathroom
2.  Water
3.  Typing drills

---

# JS

## THE DOM
1. Document Object Model (DOM)
2. A programming interface for HTML documents. It represents the page so that programs can change the document structure, style, and content.
3. The DOM represents the document as nodes and objects. That way, programming languages can connect to the page.
4. A Web page is a document.
5. The DOM is not a programming language, but without it, the JavaScript language wouldn't have any model or notion of web pages.
6. Every element in a document—the document as a whole, the head, tables within the document, table headers, text within the table cells—is part of the document object model for that document, so they can all be accessed and manipulated using the DOM and a scripting language like JavaScript.
```javascript
// SELECT ELEMENTS FROM THE DOM
const boxes = document.querySelectorAll('.box');
let status = document.getElementById('status');
```

# Capstone Project Development

# STEP 1

1. This example below, will select all the HTML elements with a class of `.box` and store it in a variable named `boxes`.
2. We select the `status` element by its id and store it in a variable named `status`.

```javascript
// SELECT ELEMENTS FROM THE DOM
const boxes = document.querySelectorAll('.box');
let status = document.getElementById('status');
```

# STEP 2

1. What we're doing here is pretty interesting. Remember yesterday, we learned `[]`'s are for creating arrays. **ADVANCED TOPIC:** Above when we selected the boxes using the class `.box`, when we use **querySelectorAll**, it returns a NodeList. A NodeList is a collection of document nodes, and is an 'array-like' list. Therefore, we need to convert it to an array using the spread operator.

```javascript
// CONVERT NODELIST TO AN ARRAY
const boxesArr = [...boxes];
```

# STEP 3

1. We are declaring a variable named `player` and setting it equal to `true`. This is an example of a datatype we haven't learned in class. This datatype is called a `Boolean`, which stores either true or false.

```javascript
// USED TO FLIP BETWEEN PLAYERS
// PLAYER X IS TRUE
// PLAYER O IS FALSE
let player = true;
```

# STEP 4

1. We are looping through the array we defined above. We haven't learned what a method is, but `Arrays` have several 'functions' (methods) attached to them, which give us power to manipulate our arrays. In this example, we are looping through our array and attaching an event listener to **each** item in our array.

```javascript
// LOOP THROUGH DOM ELEMENTS AND ADD CLICK EVENTS TO EACH
boxesArr.forEach(e => e.addEventListener('click', markASpot));
```

# STEP 5

1. This function will be `invoked` every time we click on a box in our game.
2. In this function we are toggling our players.
3. We see that player X goes first, because in our **if** statement our condition evaluates to `true`.
4. Inside the curly brackets we define everything that belongs to each player.

```javascript
// THIS FUNCTION IS RESPONSIBLE FOR MARKING SPOTS ON THE GRID (PLACING X OR O)
function markASpot(e) {
  // PLAYER X
  if (player) {
    e.target.innerHTML = 'X'; // CHANGE THE DOM ELEMENT TO X
    boxesArr.splice(event.target.id, 1, 'X'); // REPLACE THE DOM ELEMENT IN THE ARRAY WITH THE CURRENT MARK (X)
    e.target.classList.add('player1'); // ADD A CLASS TO THE DIV FOR STYLING
    // checkForPrevious(e.target, 'X'); // PREVENTS DOUBLE CLICKING ON A DIV/CHANGING THE MARK
    // checkForWinner('X'); // CHECK FOR A WINNER
    player = false; // SWITCH PLAYER
  } else {
    // PLAYER O
    // ..............?
  }
}
```

# STEP 6

1. This function is called a helper function, its purpose is to prevent double clicking on a square by removing the EventListener if a player's mark is already there.
2. Notice we are using an `if statement`. Whatever condition we store inside the `parentheses ()` must evaluate to either true or false. If true, we continue and do whats immediately next inside the `{}` brackets.

```javascript
// THIS FUNCTION IS RESPONSIBLE FOR CHECKING IF THE CURRENT POSITION IS ALREADY USED
// POSITION: IS THE CURRENT TARGET (WHERE THE MARK IS TRYING TO BE PLACED)
// PLAYER: EITHER X OR O
function checkForPrevious(position, player) {
  // IF THE TARGETED DIV'S INNERHTML EQUALS THE CURRENT PLAYER
  if (position.innerHTML === player) {
    // REMOVE EVENT LISTENER IF THE SPOT IS USED
    position.removeEventListener('click', markASpot);
  }
}
```