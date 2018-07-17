# Introduction to CSS

![css](./assets/css/cssintro.png)

# OBJECTIVE

1.  What is CSS?
2.  What are selectors?
3.  What is CSS Syntax?
4.  How do we select elements by class?
5.  How do we select elements by id?

# CSS DEFINED

1.  What is CSS?
    - Cascading Style Sheets (CSS)
    - A style sheet language used for describing the presentation of a document written in a markup language like HTML. CSS is a cornerstone technology of the World Wide Web, alongside HTML and JavaScript.
    - CSS is designed to enable the separation of presentation and content, including layout, colors, and fonts.

# CSS DEMO

1.  Link: https://www.w3schools.com/css/css_intro.asp
    - Interact with the CSS Demo by switching stylesheets as indicated

# CSS SOLVED A BIG PROBLEM

1.  HTML was NEVER intended to contain tags for formatting a web page!
2.  HTML was created to describe the content of a web page, for example:

```html
<h1>This is a heading</h1>
<p>This is a paragraph.</p>
```

3.  CSS removed the style formatting from the HTML page!

# CSS SYNTAX

![selector](./assets/css/selector.gif)

1.  The selector points to the HTML element you want to style.
2.  The declaration block contains one or more declarations separated by semicolons.
3.  Each declaration includes a CSS property name and a value, separated by a colon.
4.  A CSS declaration always ends with a semicolon, and declaration blocks are surrounded by curly braces.

### EXAMPLE

In the following example all `<p>` elements will be center-aligned, with a red text color:

```css
p {
  color: red;
  text-align: center;
}
```

---

## 🎉 10 MINUTE BREAK

Tips on having an effective break:

1.  Bathroom
2.  Water
3.  Typing drills

---

# CSS SELECTORS

1.  In CSS, selectors declare which part of the markup a style applies to by matching tags and attributes in the markup itself.
2.  CSS selectors are used to "find" (or select) HTML elements based on their element name, id, class, attribute, and more.

# THE ELEMENT SELECTOR

1.  The element selector selects elements based on the element name.
2.  You can select all `<p>` elements on a page like this (in this case, all `<p>` elements will be center-aligned, with a red text color):

```css
p {
  color: red;
  text-align: center;
}
```

# THE ID SELECTOR

1.  The **id selector** uses the **id attribute** of an HTML element to select a specific element.
2.  The id of an element should be unique within a page, so the id selector is used to select one **unique element**!
3.  To select an element with a specific id, write a hash (#) character, followed by the id of the element.
4.  The style rule below will be applied to the HTML element with id="para1":

```css
#para1 {
  text-align: center;
  color: red;
}
```

# THE CLASS SELECTOR

1.  The class selector selects elements with a specific class attribute.
2.  To select elements with a specific class, write a period (.) character, followed by the name of the class.
3.  In the example below, all HTML elements with class="center" will be red and center-aligned:

```css
.center {
  text-align: center;
  color: red;
}
```

# THERE ARE 3 WAYS TO INCLUDE CSS INTO OUR WEB PAGES

# INLINE CSS

```html
<h1 style="color: red;">Mr. Bostwick</h1>

<body style="background-color: linen;">
  ...............
</body>

<p style="color: blue; border: 4px solid pink; background-color: purple;">
My Favorite Sports:
  <ol>
    <li>Basketball</li>
    <li>Football</li>
    <li>Flag Football</li>
  </ol>
</p>
```

# INTERNAL STYLESHEET

In between the `<head></head>` tags on our webpage, we nest `<style></style>` tags:

```
<!DOCTYPE html>
<html>
<head>
  <style>
  ..................
  ..................
  </style>
</head>
<body>
  ..................
  ..................
  ..................
  ..................
  ..................
</body>
</html>
```

# LINKING TO EXTERNAL STYLESHEETS

To link to an external stylesheet, we insert this:

```css
<link rel="stylesheet" type="text/css" href="mystyle.css">
```

in between our `<head></head>` tags.

For Example:

```html
<!DOCTYPE html>
<html>
<head>
<link rel="stylesheet" type="text/css" href="mystyle.css">
</head>
<body>
  ..................
  ..................
  ..................
  ..................
  ..................
</body>
</html>
```

---

## 🎉 10 MINUTE BREAK

Tips on having an effective break:

1.  Bathroom
2.  Water
3.  Typing drills

---

# EXERCISES

Answer the questions by writing your code inside the `<style></style>` tags on each page:

## SYNTAX

### EXERCISE #1: [Change the color of all `<p>` elements to "red".](https://www.w3schools.com/css/exercise.asp?filename=exercise_syntax1)

### EXERCISE #2: [Change the color of the element with id="para1", to "red".](https://www.w3schools.com/css/exercise.asp?filename=exercise_syntax2)

### EXERCISE #3: [Change the color of all elements with the class "colortext", to "red".](https://www.w3schools.com/css/exercise.asp?filename=exercise_syntax3)

### EXERCISE #4: [Change the color of all `<p>` and `<h1>` elements, to "red". Group the selectors to minimize code.](https://www.w3schools.com/css/exercise.asp?filename=exercise_syntax4)

---

## STYLESHEETS

### EXERCISE #5: [Remove all styles, except the external style sheet "mystyle.css".](https://www.w3schools.com/css/exercise.asp?filename=exercise_howto4)

### EXERCISE #6: [Set "background-color: linen" for the page, using an internal style sheet.](https://www.w3schools.com/css/exercise.asp?filename=exercise_howto2)

### EXERCISE #7: [Add an external style sheet with the URL: "mystyle.css".](https://www.w3schools.com/css/exercise.asp?filename=exercise_howto1)

---

## BACKGROUND COLORS

**ALL CSS BACKGROUND PROPERTIES: https://www.w3schools.com/css/css_background.asp**

### EXERCISE #8: [Set the background color for the page to "linen" and the background color for `<h1>` to "lightblue".](https://www.w3schools.com/css/exercise.asp?filename=exercise_background1)

---

## BORDERS

**ALL CSS BORDER PROPERTIES: https://www.w3schools.com/css/css_border.asp**

### EXERCISE #9: [Set a "4px", "dotted" border for `<p>`.](https://www.w3schools.com/css/exercise.asp?filename=exercise_border1)

### EXERCISE #10: [Set the border color for `<p>` to "red".](https://www.w3schools.com/css/exercise.asp?filename=exercise_border2)

### EXERCISE #11: [With the border property: Set the border for p to "10px", "solid" and "green".](https://www.w3schools.com/css/exercise.asp?filename=exercise_border4)

---

## CSS FONT

**ALL CSS FONT PROPERTIES: https://www.w3schools.com/css/css_font.asp**

### EXERCISE #12: [Show `<p>` elements as "italic" text.](https://www.w3schools.com/css/exercise.asp?filename=exercise_font2)

### EXERCISE #13: [Set the font size for the page to "20px", and the font size for `<h1>` to "3em".](https://www.w3schools.com/css/exercise.asp?filename=exercise_font3)

### EXERCISE #14: [Show `<p>` elements as "bold" text.](https://www.w3schools.com/css/exercise.asp?filename=exercise_font4)

---

## 🚨 CSS ACTIVITY 🚨

Below is what we finished yesterday in class together. You can either use my information below or quickly substitute your information. From there, answer the questions below.

```html
<!DOCTYPE html>
<html>
<head>
<title>Hello World</title>
<style>


</style>
</head>
<body>

<h1>Mr. Bostwick</h1>
<hr>
<p>This summer the Computer Science team is hosting three summer programs. Last week was our Discover program where we taught the elementary school Scratch. This week is our Tech Stars program where we are learning about HTML, CSS, and Javascript to create a TicTacToe game. Our last program  will take place on Colgate University where we will host a week long summer camp teaching scholars how to build a ToDo List and a Memory Game with HTML, CSS and Javascript.</p>

<p>
My Favorite TV Shows:
<ul>
<li>Power</li>
<li>Silicon Valley</li>
<li>Whatever a friend recommends on Netflix</li>
</ul>
</p>

<p>
My Favorite Sports:
<ol>
<li>Basketball</li>
<li>Football</li>
<li>Flag Football</li>
</ol>
</p>

<a href="http://gainorbostwick.com/" title="My Website" target="_blank">My Portfolio<a/>

<div>
<img src="http://www.modern-notoriety.com/wp-content/uploads/2016/07/air-jordan-1-bred_10.jpg" alt="Jordan 1 Bred" title="Sneakers" width="600px" height="auto" />
</div>

</body>
</html>
```

### ASSIGNMENT

1.  How would you target the `<h1>` tag and change the color and font-size?
    - Change Font Color
    - Change Font Size
2.  Give an **ID** to the **first** paragraph and style it.
    - Change Font Color
    - Change Font Size
    - Make the Font Bold
3.  Give a **CLASS** to the **second** paragraph and style it.
    - Make the Font italic
    - Change Font Size
4.  Target the `<div>` tag and add styles to it.
    - Add a Border
    - Add a Border Style
    - Add a Background Color
5.  How would you style the `<body>` tag?
    - Add a Background Color
    - Change the Font Color
    - Change Font Size

## 🚨 HTML ACTIVITY 🚨

1.  Go here: https://eraseallkittens.com/
2.  Sign In:
    - Email: **gbostwick@bronxexcellence.org**
    - Password: **scholar**

# REVIEW

1.  CSS selectors are used to "find" (or select) HTML elements based on their element name, id, class, attribute, and more.

![selector](./assets/css/selector.gif)

2.  The selector points to the HTML element you want to style.
3.  The declaration block contains one or more declarations separated by semicolons.
4.  Each declaration includes a CSS property name and a value, separated by a colon.
5.  A CSS declaration always ends with a semicolon, and declaration blocks are surrounded by curly braces.

# 🚨 CLOSING QUESTIONS 🚨

1.  What is CSS?
2.  What are selectors?
3.  What is CSS Syntax?
4.  How do we select elements by class?
5.  How do we select elements by id?
