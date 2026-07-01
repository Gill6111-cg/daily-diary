#  MERN Stack Training Diary – Day 08
**Date:** 29 June 2026

#  Topic: Local Storage in JavaScript and To-Do List Project

Today was the eighth day of my MERN Stack training. The session focused on **Local Storage**, one of the most useful features provided by the browser to store data on the user's device. Before this session, the data entered into a webpage would disappear whenever the page was refreshed. Today, I learned how Local Storage can be used to save data permanently inside the browser so that it remains available even after refreshing or closing the webpage.
After understanding the theory of Local Storage, I learned how to store and retrieve different types of data such as variables, arrays, and objects. Finally, I applied all these concepts by developing my first mini project—a **To-Do List Application** using HTML, CSS, JavaScript, and Local Storage.

---

#  Local Storage in JavaScript

The session started with an introduction to **Local Storage**.

I learned that Local Storage is a Web Storage API that allows developers to store data in the browser as key-value pairs. Unlike normal JavaScript variables, the data stored in Local Storage remains available even after refreshing or reopening the browser.
Some important features of Local Storage are:

- Stores data permanently until it is removed manually.
- Data is stored as **key-value pairs**.
- Data is stored as **strings**.
- Complex data like arrays and objects must be converted into JSON format before storing.
- Local Storage is commonly used for saving user preferences, login information, shopping carts, notes, and task management applications.

---

#  setItem()

I learned that the **setItem()** method is used to store data in Local Storage.

### Syntax

```javascript
localStorage.setItem("key", value);
```

### Example (Variable)

```javascript
let name = "Chanchal";

localStorage.setItem("username", name);
```

In this example, the value of the variable is stored inside Local Storage using the key **username**.

---

#  getItem()

The **getItem()** method is used to retrieve previously stored data.

### Syntax

```javascript
localStorage.getItem("key");
```

### Example

```javascript
let user = localStorage.getItem("username");

console.log(user);
```

This retrieves the value stored under the key **username**.

---

#  Storing Arrays in Local Storage

Since Local Storage only stores strings, arrays must first be converted into JSON format using **JSON.stringify()**.

### Example

```javascript
let fruits = ["Apple", "Mango", "Orange"];

localStorage.setItem("fruits", JSON.stringify(fruits));
```

To retrieve the array, I learned to use **JSON.parse()**.

```javascript
let data = JSON.parse(localStorage.getItem("fruits"));

console.log(data);
```

This converts the JSON string back into an array.

---

#  Storing Objects in Local Storage

I also learned how to store JavaScript objects.

### Example

```javascript
let student = {

    name: "Chanchal",
    course: "B.Tech CSE"

};

localStorage.setItem("student", JSON.stringify(student));
```

Retrieving the object:

```javascript
let info = JSON.parse(localStorage.getItem("student"));

console.log(info);
```

Using `JSON.stringify()` and `JSON.parse()` allows objects to be stored and retrieved correctly.

---

#  Mini Project – To-Do List Application

After learning Local Storage, I developed my first mini project—a **To-Do List Application**.

The objective of this project was to allow users to add daily tasks along with a date. I designed the user interface using HTML and CSS, while JavaScript handled the application logic and Local Storage stored the tasks permanently.
The project helped me combine everything I had learned over the past few days, including HTML, CSS, JavaScript, DOM Manipulation, Arrays, Objects, Functions, Loops, and Local Storage.

---

#  HTML and CSS Design

I created an attractive user interface containing:

- A heading for the application
- Task input field
- Date input field
- Add Task button
- Area to display all saved tasks

I also used CSS properties like:

- Flexbox
- Box Shadow
- Border Radius
- Hover Effects
- Background Gradient
- Responsive Container

These properties made the application look clean and user-friendly.

### HTML Code

```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>To-Do List</title>

<style>

*{
margin:0;
padding:0;
box-sizing:border-box;
font-family:Arial, Helvetica, sans-serif;
}

body{
background:linear-gradient(135deg,#4facfe,#00f2fe);
height:100vh;
display:flex;
justify-content:center;
align-items:center;
}

.container{
width:420px;
background:white;
padding:30px;
border-radius:15px;
box-shadow:0 10px 25px rgba(0,0,0,.3);
}

input{
width:100%;
padding:12px;
margin:10px 0;
}

button{
width:100%;
padding:12px;
cursor:pointer;
}

#list{
margin-top:20px;
}

</style>

</head>

<body>

<div class="container">

<h1> My To-Do List</h1>

<input type="text" placeholder="Enter Task" id="task">

<input type="date" id="date">

<button onclick="add()">
Add Task
</button>

<div id="list"></div>

</div>

<script src="todo.js"></script>

</body>
</html>
```

---



### JavaScript Code

```javascript
let todos = JSON.parse(localStorage.getItem("todos")) || [];

display();

function add(){

    let task = document.querySelector("#task").value;

    let date = document.querySelector("#date").value;

    todos.push({

        taskname: task,

        taskdate: date

    });

    localStorage.setItem("todos", JSON.stringify(todos));

    display();

    document.querySelector("#task").value = "";

    document.querySelector("#date").value = "";

}

function display(){

    let result = "";

    for(let i=0;i<todos.length;i++){

        result += `
        ${todos[i].taskname} - ${todos[i].taskdate}<br>
        `;

    }

    document.querySelector("#list").innerHTML = result;

}
```

---

#  Key Learning Outcomes

- Understood the concept and importance of Local Storage.
- Learned how to use `setItem()` and `getItem()`.
- Learned to store and retrieve variables using Local Storage.
- Practiced storing arrays using `JSON.stringify()` and retrieving them using `JSON.parse()`.
- Learned how to store JavaScript objects in Local Storage.
- Developed a complete To-Do List project using HTML, CSS, JavaScript, and Local Storage.
- Improved my understanding of DOM manipulation and dynamic webpage updates.
- Gained practical experience in building a real-world JavaScript project.

---


**Status:** ✅ Day 08 Successfully Completed
