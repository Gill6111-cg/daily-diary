#  MERN Stack Training Diary – Day 19
**Date:** 16 July 2026

#  Topic: Connecting MongoDB with Backend, Creating Schema, Model, Controller, and Routes

Today was the nineteenth day of my MERN Stack training. The session focused on connecting the backend application with **MongoDB** using **Mongoose**. After learning how to set up MongoDB Atlas and install Mongoose in the previous session, today I connected my Node.js application to the database.
I also learned how to organize a backend project using different folders such as **config**, **models**, **controllers**, and **routes**. This structure makes the code clean, reusable, and easy to maintain. I created a database connection file, designed my first MongoDB schema and model, wrote a controller to insert data into the database, and created routes to handle client requests.
By the end of the session, I successfully stored user data in MongoDB through my Express API.

---

#  Connecting MongoDB with Backend

The first task was connecting my backend application with MongoDB using **Mongoose**.

Instead of writing the database connection code directly inside `server.js` or `app.js`, I created a separate file named **Db.js**. This keeps the project organized and makes the connection code reusable.

I learned that `mongoose.connect()` is used to establish a connection between the Node.js application and the MongoDB database. The database connection string is stored inside the `.env` file and accessed using `process.env.MONGO_URL`.

Using environment variables improves security because sensitive information such as database URLs is not written directly into the source code.

---

#  Database Connection File (Db.js)

```javascript
import mongoose from "mongoose";

const db = async () => {
  try {
    await mongoose.connect(process.env.MONGO_URL);

    console.log("MongoDB Connected");
  } catch (error) {
    console.log("Database Connection Error");
    console.log(error);
  }
};

export default db;
```

### Explanation

- Imported the **Mongoose** library.
- Created an asynchronous function to connect to MongoDB.
- Used `mongoose.connect()` to establish the connection.
- Retrieved the MongoDB connection string from the `.env` file.
- Displayed a success message if the connection was established.
- Displayed an error message if the connection failed.

---

#  Creating the User Schema (Model)

After connecting the database, I learned about **Schemas** and **Models**.

A **Schema** defines the structure of the documents that will be stored inside a MongoDB collection. It specifies the fields, their data types, and validation rules.

I created a `userSchema` containing two fields:

- **name**
- **age**

Both fields were marked as required, and the `trim` property was used to remove unnecessary spaces from user input.

I also learned about timestamps, which automatically add **createdAt** and **updatedAt** fields to every document.

---

#  User Model (User.js)

```javascript
import mongoose from "mongoose";

const userSchema = new mongoose.Schema(
  {
    name: {
      type: String,
      required: true,
      trim: true,
    },

    age: {
      type: String,
      required: true,
      trim: true,
    },
  },
  {
    timestamps: true,
  }
);

const User = mongoose.model("User", userSchema);

export default User;
```

### Explanation

- Created a schema using `mongoose.Schema()`.
- Defined two fields: **name** and **age**.
- Added validation using `required`.
- Used `trim: true` to remove extra spaces.
- Enabled automatic timestamps.
- Created a model named **User**.
- Exported the model for use in controllers.

---

#  Creating the Controller

Next, I learned about **Controllers**.

A controller contains the business logic of the application. Instead of writing all the code inside the route file, controllers separate the application logic from routing, making the project easier to manage.

I created a controller named `userController.js` and wrote a function to add new users to the database.

---

#  userController.js

```javascript
import User from "../models/User.js";

export const addUser = async (req, res) => {
  try {
    const { name, age } = req.body;

    const user = await User.create(req.body);

    if (user) {
      res.status(200).json({
        message: "User added",
        user: user,
      });
    }
  } catch (error) {
    res.status(500).json({
      error: error.message,
    });
  }
};
```

### Explanation

- Imported the User model.
- Created an asynchronous function named `addUser`.
- Received user data from `req.body`.
- Used `User.create()` to insert data into MongoDB.
- Returned a success response after storing the data.
- Used `try...catch` for error handling.

---

#  Creating Routes

After creating the controller, I created a separate route file.

Routes receive client requests and pass them to the appropriate controller function.

Instead of writing all the logic inside the route, I simply imported the controller and connected it with the POST request.

---

#  userRoutes.js

```javascript
import { addUser } from "../controllers/userController.js";
import express from "express";

const router = express.Router();

router.post("/", addUser);

export default router;
```




#  Configuring app.js

Finally, I connected all the routes with the Express application.

I also enabled JSON middleware so that Express could read JSON data sent from the client.

---

#  app.js

```javascript
import express from "express";
import dotenv from "dotenv";
import userRoutes from "./routes/userRoutes.js";

dotenv.config();

const app = express();

// Middleware
app.use(express.json());

// Routes
app.use("/users", userRoutes);

export default app;
```

### Explanation

- Imported Express and Dotenv.
- Loaded environment variables.
- Enabled JSON middleware.
- Connected all user-related routes using `/users`.
- Exported the Express application.

---

#  Project Flow

After completing today's practical work, I understood how the complete backend request flow works:

```
Client Request
      │
      ▼
userRoutes.js
      │
      ▼
userController.js
      │
      ▼
User Model (Schema)
      │
      ▼
MongoDB Database
```

This flow helped me understand how different backend files work together in a structured Express application.

---

#  Key Learning Outcomes

- Learned how to connect MongoDB with a Node.js backend using Mongoose.
- Created a separate database connection file (`Db.js`).
- Understood the importance of environment variables (`.env`).
- Learned the concept of Schemas and Models in Mongoose.
- Created a `User` schema with validation rules.
- Learned how to create controllers for handling application logic.
- Used `User.create()` to insert data into MongoDB.
- Created separate route files using Express Router.
- Connected routes with controller functions.
- Configured middleware and routes in `app.js`.
- Understood the overall backend folder structure and request flow.

---


---

**Status:**  Day 19 Successfully Completed
