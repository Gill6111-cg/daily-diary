#  MERN Stack Training Diary – Day 24
**Date:** 23 July 2026

#  Topic: Food Recipe System Project Planning and Backend Setup

Today was the twenty-fourth day of my MERN Stack training. The session began with planning my major MERN Stack project. After exploring different project ideas, I decided to develop a **Food Recipe System**. Before writing any code, I planned the features, user authentication, and the overall structure of the application.
After completing the project planning, I started developing the backend. I initialized a new Node.js project, installed all the required packages, configured environment variables, connected the application to MongoDB, and prepared the backend structure for future development.

---

#  Project Planning – Food Recipe System

The first activity of today's session was planning the project requirements and deciding what features would be included in the application.

I decided to build a **Food Recipe System** where users can explore different recipes, create their own recipes, and manage their favourite recipes.

### Planned Features

- User Registration
- User Login
- Home Page
- Favourite Recipes Page
- My Recipes Page
- Add Recipe
- Update Recipe
- Delete Recipe
- View Recipe Details
- User Authentication

This planning helped me understand the complete workflow of my project before starting the development process.

---

#  Authentication Planning

One of the important decisions was implementing **User Authentication**.

I planned that users who are **not logged in** will have limited access to the application.

### Without Login

A user can:

- View all food recipes.
- Browse recipes available on the Home page.

A user cannot:

- Add new recipes.
- Share recipes.
- Edit recipes.
- Delete recipes.
- Add recipes to favourites.
- Access the "My Recipes" page.

### After Login

Once a user successfully logs in, they will be able to:

- Add new recipes.
- Update their own recipes.
- Delete their own recipes.
- Add recipes to favourites.
- View favourite recipes.
- Manage recipes from the "My Recipes" page.

This authentication flow improves application security by restricting important operations to authenticated users only.

---

#  Backend Project Initialization

After planning the project, I started setting up the backend.

First, I created a new folder named **backend**.

Then, I initialized a Node.js project using the following command:

```bash
npm init -y
```

### Purpose

This command automatically creates the **package.json** file, which stores all project information and dependencies.

---

#  Installing Required Packages

After initializing the project, I installed the required packages.

### Install Nodemon

```bash
npm i nodemon
```

### Purpose

Nodemon automatically restarts the server whenever changes are made to the project files, making development faster and easier.

---

### Install Dotenv

```bash
npm i dotenv
```

### Purpose

Dotenv is used to store sensitive configuration values, such as the server port and MongoDB connection string, inside a `.env` file instead of hardcoding them in the source code.

---

### Install Express

```bash
npm i express
```

### Purpose

Express.js is a lightweight web framework for Node.js that helps build APIs, manage routes, and handle HTTP requests efficiently.

---

### Install CORS

```bash
npm i cors
```

### Purpose

CORS (Cross-Origin Resource Sharing) allows the frontend and backend to communicate even when they are running on different ports or domains.

---

### Install Mongoose

```bash
npm i mongoose
```

### Purpose

Mongoose is an Object Data Modeling (ODM) library that simplifies interaction with MongoDB by providing schemas, models, and database methods.

---

#  Creating server.js

After installing the required packages, I created the main server file named **server.js**.

### server.js

```javascript
const express = require("express");
const app = express();

const dotenv = require("dotenv").config();

const connectDb = require("./config/connectionDb");

const PORT = process.env.PORT || 3000;

connectDb();

app.use(express.json());

app.listen(PORT, () => {
    console.log(`App is listening on port ${PORT}`);
});
```

### Explanation

- Imported Express.js.
- Loaded environment variables using Dotenv.
- Imported the database connection file.
- Connected the backend with MongoDB.
- Enabled JSON middleware using `express.json()`.
- Started the Express server on the specified port.

---

#  Creating the .env File

Next, I created a **.env** file to store environment variables.

### .env

```env
PORT=5000

CONNECTION_STRING="mongodb://localhost:27017/foodRecipe"
```

### Explanation

- **PORT** defines the port on which the backend server runs.
- **CONNECTION_STRING** stores the MongoDB connection URL.

Using a `.env` file improves security because sensitive information is kept separate from the source code.

---

#  Creating Database Connection File

To connect the backend with MongoDB, I created **connectionDb.js** inside the **config** folder.

### connectionDb.js

```javascript
const mongoose = require("mongoose");

const connectDb = async () => {

    await mongoose
        .connect(process.env.CONNECTION_STRING)
        .then(() => console.log("Connected to MongoDB..."));

};

module.exports = connectDb;
```

### Explanation

This file is responsible for connecting the backend application with the MongoDB database.

It performs the following tasks:

- Imports Mongoose.
- Reads the MongoDB connection string from the `.env` file.
- Establishes the database connection.
- Displays a success message after a successful connection.
- Exports the function so it can be used inside `server.js`.

Keeping the database connection in a separate file makes the project cleaner, modular, and easier to maintain.

---

#  Backend Project Structure

The backend folder structure created today is as follows:

```
backend/

│── config/
│     └── connectionDb.js

│── node_modules/

│── .env

│── package.json

│── server.js
```

This organized structure makes it easier to manage backend files as the project grows.

---

#  Key Learning Outcomes

- Planned the complete Food Recipe System project.
- Decided the features of the application.
- Understood authentication flow for logged-in and guest users.
- Initialized a Node.js backend project using `npm init -y`.
- Installed Nodemon for automatic server restart.
- Installed Dotenv for environment variable management.
- Installed Express.js to build backend APIs.
- Installed CORS for frontend-backend communication.
- Installed Mongoose for MongoDB integration.
- Created the `server.js` file.
- Created and configured the `.env` file.
- Connected the backend application with MongoDB using Mongoose.
- Learned the importance of separating configuration files from application logic.




---

**Status:**  Day 24 Successfully Completed
