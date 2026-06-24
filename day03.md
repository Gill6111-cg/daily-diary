# MERN Stack Training Diary – Day 03
**Date:** 24 June 2026

##  Topic: HTML Div, CSS Flexbox and Grid, Node.js Installation, and Introduction to JavaScript

Today was the third day of my MERN Stack training, and it was one of the most interesting and informative sessions so far. Along with learning more about HTML and CSS, I was introduced to JavaScript, which is the programming language used to make webpages interactive and dynamic. I also completed the installation and setup of Node.js on my laptop, which is an important part of the MERN Stack development environment.
At the beginning of the session, I learned about the `<div>` tag in HTML and how it is used to structure and organize different sections of a webpage. After that, I explored modern CSS layout techniques such as Flexbox and Grid. In the second half of the session, I installed Node.js and started learning the fundamentals of JavaScript, including variables, data types, and operators.



##  Understanding the Div Tag in HTML

I started the session by learning about the `<div>` tag in HTML. I understood that a div is a container element used to group different HTML elements together. It does not have any visual appearance by itself, but it plays a very important role in organizing and structuring webpages.
I learned that developers use div elements to divide webpages into different sections such as headers, navigation bars, content sections, sidebars, and footers. This makes webpages more organized and easier to design and maintain.
I also learned how to assign an `id` to a div element. By giving different ids to different divs, I was able to apply specific CSS properties to each section separately. This practical exercise helped me understand how modern websites are built using multiple div containers.



##  Applying CSS Properties to Div Elements

After understanding div elements, I learned how CSS can be used to arrange and style them.

### CSS Flexbox

I learned about `display: flex`, which converts a normal container into a flex container. Flexbox is mainly used to arrange elements in a flexible and responsive manner.
I practiced the following properties:

### `display: flex`
This property makes the container flexible and arranges its child elements in a row by default.

### `justify-content`
This property controls the horizontal alignment of items inside the flex container. I experimented with different values and observed how elements can be placed at the center, spaced evenly, or positioned at different locations.

### `align-items`
This property controls the vertical alignment of items inside the flex container. I learned how elements can be aligned at the top, center, or bottom of the container.

Through practical examples, I understood that Flexbox makes it much easier to create navigation menus, cards, and other webpage layouts.

---

### CSS Grid

Next, I learned about `display: grid`, which is another modern layout technique in CSS. Grid allows developers to arrange elements in both rows and columns.

I practiced different Grid properties and observed how complex layouts can be created with comparatively less effort.

I learned about:

- `display: grid`
- `grid-template-columns`
- `grid-template-rows`
- `gap`
- `justify-content`
- `align-items`

I also understood the difference between Flexbox and Grid:

- **Flexbox** is mainly used for one-dimensional layouts where elements are arranged either in a row or a column.
- **CSS Grid** is used for two-dimensional layouts because it can manage both rows and columns simultaneously.

Learning these layout techniques gave me a better understanding of how professional webpages are designed.


##  Node.js Installation and Setup

After completing the frontend concepts, I moved to setting up the development environment.
I installed Node.js on my laptop and completed the setup process successfully. I learned that Node.js is an open-source JavaScript runtime environment that allows JavaScript code to run outside the browser.
I also learned that Node.js is an important technology in the MERN Stack because it is used for backend development and server-side programming.
During the installation process, I understood that installing Node.js automatically installs npm (Node Package Manager), which is used to install and manage different packages and libraries required for projects.
Successfully completing the installation gave me confidence because my system was now ready for future backend development.



##  Introduction to JavaScript

The next part of the session was my introduction to JavaScript. I learned that JavaScript is a programming language that adds functionality and interactivity to websites.
Unlike HTML, which creates the structure of a webpage, and CSS, which is responsible for its appearance, JavaScript is responsible for making webpages interactive and dynamic.
I found it exciting because JavaScript allows websites to respond to user actions and perform different tasks automatically.


##  Methods of Adding JavaScript

I learned three different ways of adding JavaScript code to an HTML document.

### Inline JavaScript
Inline JavaScript is written directly inside an HTML element using attributes such as `onclick`. It is useful for simple tasks and demonstrations.

### Internal JavaScript
Internal JavaScript is written inside the `<script>` tag within the HTML document. This method keeps JavaScript code separate from HTML elements while remaining inside the same file.

### External JavaScript
External JavaScript is written in a separate `.js` file and linked to the HTML document. I understood that this method is commonly used in real-world projects because it keeps code organized and easy to maintain.

I also practiced the `alert()` function and observed how JavaScript can display messages in a popup box on the browser.



##  Console Output in JavaScript

I learned about the `console.log()` function, which is used to display messages and values in the browser console.

I understood that `console.log()` is very useful for checking outputs and debugging programs because it allows developers to see what is happening inside their code.



##  Variables and Keywords in JavaScript

I learned that variables are containers used to store data in memory. JavaScript provides three keywords for declaring variables.

### `var`
Variables declared using `var` can be redeclared and updated. It was commonly used in older versions of JavaScript.

### `let`
Variables declared using `let` can be updated but cannot be redeclared within the same scope. It is widely used in modern JavaScript programming.

### `const`
Variables declared using `const` cannot be updated or redeclared after assigning a value. It is used when values should remain constant throughout the program.



##  Data Types in JavaScript

I learned about different types of data that JavaScript can store.

### String
Used to store textual information such as names and messages.

### Number
Used to store numeric values including integers and decimal numbers.

### Boolean
Stores only two values: `true` and `false`.

### Null
Represents an intentionally empty value.

### Undefined
Represents a variable that has been declared but has not been assigned any value.

I understood that data types are important because they determine the kind of information that a variable can store.



## ⚙️ Operators in JavaScript

After understanding variables and data types, I learned about operators. Operators are special symbols used to perform operations on values and variables.

### Arithmetic Operators
Arithmetic operators are used to perform mathematical calculations.

- `+` (Addition): Adds two values together.
- `-` (Subtraction): Subtracts one value from another.
- `*` (Multiplication): Multiplies two values.
- `/` (Division): Divides one value by another.
- `%` (Modulus): Returns the remainder after division.

### Assignment Operators
Assignment operators are used to assign and update values stored in variables.

- `=` Assigns a value to a variable.
- `+=` Adds a value and stores the result.
- `-=` Subtracts a value and stores the result.
- `*=` Multiplies and stores the result.
- `/=` Divides and stores the result.

### Logical Operators
Logical operators are used to combine multiple conditions and return either `true` or `false`.

- `&&` (AND): Returns true only if both conditions are true.
- `||` (OR): Returns true if at least one condition is true.
- `!` (NOT): Reverses the Boolean value.

### Comparison Operators
Comparison operators are used to compare two values and return either `true` or `false`.

- `<` Less than
- `>` Greater than
- `<=` Less than or equal to
- `>=` Greater than or equal to
- `==` Equal to (checks only values)
- `===` Strict Equal to (checks both value and data type)

### Increment Operator (`++`)
Increases the value of a variable by one.

### Decrement Operator (`--`)
Decreases the value of a variable by one.

Practicing these operators helped me understand how JavaScript performs calculations, comparisons, and logical decision-making.

---

##  Key Learning Outcomes

- Understood the purpose and importance of the `<div>` tag in HTML.
- Learned how to use ids to apply CSS properties to specific div elements.
- Practiced CSS Flexbox properties such as `display: flex`, `justify-content`, and `align-items`.
- Learned CSS Grid and understood how it differs from Flexbox.
- Successfully installed and configured Node.js on my laptop.
- Learned the different methods of adding JavaScript to webpages.
- Practiced `alert()` and `console.log()` functions.
- Understood JavaScript variables, data types, and operators in detail.
- Gained confidence in writing basic JavaScript programs.

**Status:** Day 03 Successfully Completed
