# CAPSTONE PROJECT

DEMO: https://codepen.io/GainorB/full/XBXVge/

# OBJECTIVE

1.  Create HTML structure for game board
2.  Create CSS for game board
3.  Start building game logic
4.  Develop a basic understanding regarding the logic in our game

# YESTERDAY

We learned how to work with variables, loops and functions. Let's get some practice by doing these challenges!

# CRITICAL THINKING (20 MINUTES)

Spend the next 20 minutes working on these challenges:

1.  Print 100 numbers to the console. Either 0-99 or 1-100. Whatever method makes sense to you.
2.  https://repl.it/repls/LavenderThinNumericalanalysis
3. https://repl.it/repls/ImpracticalWorthlessTerabyte
4. Create an array of 10 **random** numbers. Loop through this array and print to console **ONLY** the numbers greater than 5.
5. Create a function named canIWatch that takes in a parameter named age. This function should output "No, you can't watch this movie" if I am younger than 14 or "Yes, you can watch this movie" if I am older than 14.

# AFTER

Log into CodePen. If you remember your login information, GREAT! If not, give us a second to help you!

# HTML (10 MINS)

Our game board will consist of this layout!

**REVIEW:**

1.  Does anyone remember the difference between giving our HTML elements classes vs. ids?
2.  Does anyone see any HTML elements we've never learned before?
3.  How many unique HTML attributes are there?

Lets spend the next 10 minutes making our HTML document more unique! Use your imagination! Do whatever you like, whatever you think makes sense. Make your game standout. **Add in any additional HTML elements!**

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

# CSS (20 MINUTES)

Here's my code below. Spend some time making my code, yours! **REMEMBER**, CSS gives us the power to transform plain HTML elements and make them look unique. I know there are CSS attributes below we haven't learned, but it doesn't hurt to change a value to see what happens! Explore for the next 20 minutes, make changes!

**Great Resource:** https://www.w3schools.com/css/default.asp

**Hints for making this CSS yours!:**

- Change Font colors
- Change Background colors
- Maybe add a background image to our gameboard? or our webpage?
- Change Font Sizes
- Change Border Colors
- Change Border Sizes
- Change Hover Effects (notice what happens when our mouse hovers over a box)
- Change Border Styles
- Change the size of the box (**HINT:** right now each box is 200px by 200px)
- Change the Animation colors (**HINT:** checkout @keyframes)
  - Add more colors?
  - Add different colors?
  - Add less colors?

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
  0% {
    background-color: red;
  }
  25% {
    background-color: yellow;
  }
  50% {
    background-color: blue;
  }
  100% {
    background-color: green;
  }
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

1.  Document Object Model (DOM)
2.  The DOM represents the document as nodes and objects. That way, programming languages can connect to the page.
3.  Every element in a document—the document as a whole, the head, tables within the document, table headers, text within the table cells—is part of the document object model for that document, so they can all be accessed and manipulated using the DOM and a scripting language like JavaScript.

```javascript
// SELECT ELEMENTS FROM THE DOM
const boxes = document.querySelectorAll(".box");
let status = document.getElementById("status");
```

# CAPSTONE PROJECT DEVELOPMENT

FULL DISCLOSURE: There are pieces of code you won't understand. Truthfully, explaining everything at this point may make you more confused. So you will touch the important topics.

🤦🏾‍🤬😶🤓😢😎🙈💀

# STEP 1 (5 MINUTES)

1.  This example below, will select all the HTML elements with a class of `.box` and store them in a variable named `boxes`.
2.  We select the `status` element by its id and store it in a variable named `status`.

```javascript
// SELECT ELEMENTS FROM THE DOM
const boxes = document.querySelectorAll(".box");
let status = document.getElementById("status");
```

# STEP 2 (5 MINUTES)

1.  What we're doing here is pretty interesting. Remember yesterday, we learned `[]`'s are for creating arrays. **ADVANCED TOPIC:** Above when we selected the boxes using the class `.box`, when we use **querySelectorAll**, it returns a NodeList. A NodeList is a collection of document nodes, and is an 'array-like' list. Therefore, we need to convert it to an array using the spread operator.

```javascript
// CONVERT NODELIST TO AN ARRAY
const boxesArr = [...boxes];
```

# STEP 3 (5 MINUTES)

1.  We are declaring a variable named `player` and setting it equal to `true`. This is an example of a datatype we haven't learned in class. This datatype is called a `Boolean`, which stores either true or false.

```javascript
// USED TO FLIP BETWEEN PLAYERS
// PLAYER X IS TRUE
// PLAYER O IS FALSE
let player = true;
```

# STEP 4 (5 MINUTES)

1.  We are looping through the array we defined above. We haven't learned what a method is, but `Arrays` have several 'functions' (methods) attached to them, which give us power to manipulate our arrays. In this example, we are looping through our array and attaching an event listener to **each** item in our array.

```javascript
// LOOP THROUGH DOM ELEMENTS AND ADD CLICK EVENTS TO EACH
boxesArr.forEach(e => e.addEventListener("click", markASpot));
```

# STEP 5 (20 MINUTES)

1.  This function will be `invoked` every time we click on a box in our game.
2.  In this function we are toggling our players.
3.  We see that player X goes first, because in our `if statement` our condition evaluates to `true`.
4.  Inside the curly brackets we define everything that belongs to each player.

# 🚨 CHALLENGE 🚨

1.  At this point, you realize our game is only working for one player!
2.  Notice the 2nd part of our `if statement` was accidentally deleted. 😢 How will we fix this to make player **O** play?
3.  Take hints from what we did for Player X to complete Player O.

```javascript
// THIS FUNCTION IS RESPONSIBLE FOR MARKING SPOTS ON THE GRID (PLACING X OR O)
function markASpot(e) {
  // PLAYER X
  if (player) {
    // PLAYER X

    // CHANGE THE BOX TO X
    e.target.innerHTML = "X";

    // TELL THE USER WHO'S TURN IT IS
    status.innerHTML = "Player O's turn!";

    // REPLACE THE DOM ELEMENT IN THE ARRAY WITH THE CURRENT MARK (X)
    boxesArr.splice(event.target.id, 1, "X");

    // ADD A CLASS TO THE DIV FOR STYLING
    e.target.classList.add("player1");

    // PREVENTS DOUBLE CLICKING
    // checkForPrevious(e.target, 'X');

    // CHECK FOR A WINNER
    // checkForWinner('X');

    // SWITCH PLAYER
    player = false;
  } else {
    // PLAYER O
  }
}
```

# STEP 6 (5 MINUTES)

1.  This function is called a helper function, its purpose is to prevent double clicking on a square by removing the EventListener if a player's mark is already there.
2.  Notice we are using an `if statement`. Whatever condition we store inside the `()` must evaluate to either true or false. If true, we continue and do whats immediately next inside the `{}` brackets. If false, we do nothing!

```javascript
// THIS FUNCTION IS RESPONSIBLE FOR CHECKING IF THE CURRENT POSITION IS ALREADY USED
// POSITION: IS THE CURRENT TARGET (WHERE THE MARK IS TRYING TO BE PLACED)
// PLAYER: EITHER X OR O
function checkForPrevious(position, player) {
  // IF THE TARGETED DIV'S INNERHTML EQUALS THE CURRENT PLAYER
  if (position.innerHTML === player) {
    // REMOVE EVENT LISTENER IF THE SPOT IS USED
    position.removeEventListener("click", markASpot);
  }
}
```

# STEP 7 (35 minutes)

1. Another helper function that is invoked **every** time a player leaves a mark.
2. This function checks every possible winning scenario. If a winning scenario is found, the game is over.
    * How many winning scenarios are there?

# 🚨 CHALLENGE 🚨
1. Finish the 4 remaining winning scenarios. 
2. Hints:
    * Hmm... Notice that we are checking the values stored at specific array indexes. Is there a way to output the values stored in `boxesArr`? Once figured out, do `CMD + OPTION + J` to view your results in the javascript console.
    * How long is our array? (How many items are in our array)
    * Observe patterns

```javascript
// THIS FUNCTION IS RESPONSIBLE CHECKING FOR A WINNER
function checkForWinner(player) {
  // CHECK FIRST COLUMN
  if (boxesArr[0] === boxesArr[1] && boxesArr[1] === boxesArr[2]) {
    status.innerHTML = `Player ${player} won!`;
    remove();
  }

  // CHECK SECOND COLUMN
  if (boxesArr[3] === boxesArr[4] && boxesArr[4] === boxesArr[5]) {
    status.innerHTML = `Player ${player} won!`;
    remove();
  }

  // CHECK THIRD COLUMN
  if (boxesArr[6] === boxesArr[7] && boxesArr[7] === boxesArr[8]) {
    status.innerHTML = `Player ${player} won!`;
    remove();
  }

  // CHECK FIRST ROW
  // ........ ?


  // CHECK SECOND ROW
  // ........ ?


  // CHECK THIRD ROW
  // ........ ?

  // CHECK RIGHT DIAGONAL ROW
  if (boxesArr[0] === boxesArr[4] && boxesArr[4] === boxesArr[8]) {
    status.innerHTML = `Player ${player} won!`;
    remove();
  }

  // CHECK LEFT DIAGONAL ROW
  // ........ ?

}
```

# STEP 8

1. Another helper function that serves one purpose and one purpose only: this function removes the EventListeners from the remaining boxes once the game is over.
2. Without this function, you'll be able to continue playing the game after someone wins.

```javascript
// THIS FUNCTION IS RESPONSIBLE FOR REMOVING THE REMANING EVENTLISTENERS
function remove() {
  boxesArr
    .filter(e => e !== 'X' && e !== 'O') 
    // FILTER OUT THE DIVS WITH MARKED POSITIONS
    .forEach(e => e.removeEventListener('click', markASpot)); 
    // REMOVE EVENTLISTENER FROM REMAINING DIVS
}
```
