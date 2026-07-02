# 🚀 MERN Stack Training Diary – Day 07
**Date:** 30 June 2026

##  Topic: Document Object Model (DOM) and Interactive JavaScript Programs

Today was the seventh day of my MERN Stack training. The session was completely focused on the **Document Object Model (DOM)**. I learned that the DOM is an interface that allows JavaScript to access and manipulate HTML elements dynamically. Instead of creating static web pages, DOM makes it possible to update the content, styles, and attributes of HTML elements based on user interactions without refreshing the webpage.
I also revised different DOM selection methods such as `getElementById()`, `querySelector()`, `querySelectorAll()`, and learned how to change properties like `innerText`, `style`, `src`, `value`, and `type`. To understand these concepts better, I built three practical programs.

---

# Practical Program 1 – Dark Mode / Light Mode Toggle

The first program was a **Dark Mode and Light Mode Toggle**. I created a button that changes the background color of the webpage whenever it is clicked.
In this program, I used a Boolean variable named `isDark` to keep track of the current background color. Using an `if-else` statement, the webpage switches between white and black backgrounds every time the button is pressed.



### Program

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dark Mode Toggle</title>
</head>
<body>

<h1 id="text">Welcome to My Page</h1>

<button onclick="togglefn()">
    Click for Toggle Button
</button>

<script>

let isDark = false;

function togglefn(){

    if(isDark){

        document.body.style.backgroundColor = "white";
        isDark = false;

    }
    else{

        document.body.style.backgroundColor = "black";
        isDark = true;

    }

}

</script>

</body>
</html>
```



---

# Practical Program 2 – Password Show/Hide Toggle and Display User Input

The second practical program was based on user input.

First, I created a password field where users can show or hide their password. I changed the `type` attribute of the input field between `password` and `text`.
In the same program, I created another input field where the user enters their name. After clicking the Submit button, JavaScript reads the entered value and displays a welcome message on the webpage.



### Program

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Password Toggle</title>
</head>
<body>

<input type="password" id="hi">

<button onclick="to()">
    Show / Hide
</button>

<br><br>

<input type="text" placeholder="Enter Your Name" id="tex">

<button onclick="submitData()">
    Submit
</button>

<h1 id="display"></h1>

<script>

function to(){

    let y = document.querySelector("#hi");

    if(y.type === "text"){

        y.type = "password";

    }
    else{

        y.type = "text";

    }

}

function submitData(){

    let user_input = document.querySelector("#tex").value;

    let myheading = document.querySelector("#display");

    myheading.innerText = "Welcome " + user_input;

}

</script>

</body>
</html>
```

### Learning

This practical helped me understand how JavaScript can read user input, update HTML content dynamically, and modify HTML attributes.

---

#  Practical Program 3 – Bulb ON/OFF Toggle

The third practical program was an **Image Toggle** project.

I created a virtual electric bulb that changes from OFF to ON whenever the button is clicked. Along with changing the bulb image, the button text also changes accordingly.
This program uses a Boolean variable to determine whether the bulb is currently ON or OFF.


### Program

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bulb Toggle</title>
</head>
<body>

<img src="off.png" height="200px" id="bulb">

<br><br>

<button onclick="to()" id="btn">
    Click for ON Bulb
</button>

<script>

let ison = false;

function to(){

    let myimage = document.querySelector("#bulb");
    let mybtn = document.querySelector("#btn");

    if(ison){

        myimage.src = "off.png";
        mybtn.innerText = "Click for ON Bulb";
        ison = false;

    }
    else{

        myimage.src = "on.png";
        mybtn.innerText = "Click for OFF Bulb";
        ison = true;

    }

}

</script>

</body>
</html>
```

### Learning

This project helped me understand how JavaScript can dynamically change images and button text using the DOM. It also improved my understanding of event handling and conditional statements.

---

#  Key Learning Outcomes

- Understood the concept and importance of the Document Object Model (DOM).
- Learned how JavaScript interacts with HTML elements dynamically.
- Practiced DOM selection methods like `getElementById()`, `querySelector()`, and `querySelectorAll()`.
- Learned to modify HTML content using `innerText`.
- Practiced changing CSS properties dynamically using JavaScript.
- Learned how to update HTML attributes such as `type` and `src`.
- Built three interactive projects using DOM manipulation.
- Improved my understanding of event handling and user interaction.

---


**Status:** ✅ Day 07 Successfully Completed
