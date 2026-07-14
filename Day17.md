#  MERN Stack Training Diary – Day 17
**Date:** 14 July 2026

#  Topic: Backend Routes (GET, POST, PUT, DELETE) and Introduction to Postman

Today was the seventeenth day of my MERN Stack training. The session focused on learning the basics of **routing in the backend** using Express.js. I learned how different HTTP request methods are used to perform different operations on data. These methods include **GET**, **POST**, **PUT**, and **DELETE**, and they form the foundation of building REST APIs.
After understanding the theory behind these routes, I installed **Postman** on my computer. I learned why Postman is an important tool for backend development and how it helps developers test APIs without creating a frontend. Finally, I created a simple Express application where I stored data in an array of objects and used the **POST** route to add new objects through Postman.
Overall, today's session gave me a practical understanding of how backend APIs work and how client requests are handled by the server.

---

#  Introduction to Backend Routes

The session began with learning about **Routes** in Express.js.

I learned that a route is a path that allows the client to communicate with the server. Every route is associated with an HTTP request method such as GET, POST, PUT, or DELETE.
Routes help the server understand what action needs to be performed when a request is received.

The basic syntax of a route is:

```javascript
app.method(path, (req, res) => {
    // code
});
```

Where:

- `app` is the Express application.
- `method` represents the HTTP request method.
- `path` is the URL endpoint.
- `req` contains the data sent by the client.
- `res` is used to send a response back to the client.

---

#  GET Route

The **GET** method is used to retrieve data from the server.

Whenever a client requests information, the GET route sends the requested data back without making any changes.

### Syntax

```javascript
app.get("/", (req, res) => {
    res.send("Hello World");
});
```

### Example

```javascript
app.get("/", (req, res) => {
    res.send("Working");
});
```

### Explanation

When the browser or Postman sends a GET request to the root (`/`) route, the server responds with the message:

```
Working
```

GET requests are commonly used to fetch users, products, recipes, or any stored data.

---

#  POST Route

The **POST** method is used to send new data from the client to the server.

Whenever users submit a form, register, log in, or add new records, the POST method is generally used.

### Syntax

```javascript
app.post("/", (req, res) => {
    // process data
});
```

### Example

```javascript
app.post("/", (req, res) => {
    arr.push(req.body);
    res.json(arr);
});
```

### Explanation

In this route, the data sent from Postman is available inside `req.body`.

The server stores the received object inside the array and then sends the updated array as the response.

---

#  PUT Route

The **PUT** method is used to update existing data on the server.

Instead of creating new data, it modifies previously stored information.

### Syntax

```javascript
app.put("/:id", (req, res) => {
    // update data
});
```

### Example

```javascript
app.put("/:id", (req, res) => {
    res.send("Data Updated");
});
```

### Explanation

PUT requests are mainly used to edit existing records such as updating a user's profile, changing a password, or modifying product information.

---

#  DELETE Route

The **DELETE** method is used to remove data from the server.

### Syntax

```javascript
app.delete("/:id", (req, res) => {
    // delete data
});
```

### Example

```javascript
app.delete("/:id", (req, res) => {
    res.send("Data Deleted");
});
```

### Explanation

DELETE requests are used whenever records need to be removed from a database or collection.

Examples include deleting users, products, recipes, or comments.

---

#  Introduction to Postman

After learning about backend routes, I installed **Postman** on my computer.

I learned that Postman is one of the most popular API testing tools used by backend developers.

Instead of building a frontend every time, Postman allows developers to send HTTP requests directly to the server and view the response.

This makes API development and testing much faster and easier.

### Importance of Postman

- Tests backend APIs without creating a frontend.
- Sends GET, POST, PUT, and DELETE requests easily.
- Helps verify API responses.
- Allows sending JSON data.
- Makes debugging APIs much easier.
- Saves time during backend development.

---

#  Practical Program – Adding Data Using POST Request

To understand POST requests practically, I created an Express application where I stored data inside an array of objects.

Initially, I created an array containing one object.

```javascript
const arr = [
    {
        name: "chanchal",
        class: 10
    }
];
```

I also enabled JSON middleware so that Express could read JSON data sent from Postman.

```javascript
app.use(express.json());
```

---

#  Complete Code (app.js)

```javascript
import express from "express";
import dotenv from "dotenv";

const app = express();

// Configure dotenv
dotenv.config();

// Middleware
app.use(express.json());

// Array of Objects
const arr = [
    {
        name: "chanchal",
        class: 10
    }
];

// GET Route
app.get("/", (req, res) => {
    res.send("Working");
});

// POST Route
app.post("/", (req, res) => {
    arr.push(req.body);
    res.json(arr);
});

export default app;
```

---

#  Testing API Using Postman

After creating the backend, I tested the POST route using Postman.

### Steps I Followed

1. Opened Postman.
2. Selected the **POST** request method.
3. Entered the API URL.

```
http://localhost:5000/
```

4. Opened the **Body** section.
5. Selected **raw**.
6. Chose **JSON** format.
7. Entered the following JSON data.

```json
{
    "name": "Rahul",
    "class": 12
}
```

8. Clicked the **Send** button.

The server successfully received the data and added the new object to the array.

The response displayed the updated array.

```json
[
    {
        "name": "chanchal",
        "class": 10
    },
    {
        "name": "Rahul",
        "class": 12
    }
]
```

This practical activity helped me understand how data is sent from the client to the backend using a POST request.

---

#  Key Learning Outcomes

- Learned the concept of backend routing in Express.js.
- Understood the purpose of HTTP methods: GET, POST, PUT, and DELETE.
- Learned the syntax and working of each route.
- Installed and configured Postman for API testing.
- Understood the importance and advantages of Postman.
- Learned how to send JSON data using Postman.
- Created an Express application with an array of objects.
- Added new objects to the array using the POST request.
- Understood the use of `req.body` and `res.json()`.
- Improved my understanding of REST API development and backend request handling.

---


---

**Status:** ✅ Day 17 Successfully Completed
