# MERN Stack Training Diary – Day 21
**Date:** 20 July 2026

# Topic: Creating GET API, Login API, and Connecting Backend with Frontend

Today was the twenty-first day of my MERN Stack training. In today's session, I continued working on the backend of my project by creating new APIs and then connecting them with the React frontend. I learned how to retrieve all users from the MongoDB database, check whether a user exists before logging in, and consume backend APIs from the frontend using Axios.
The session helped me understand how the frontend and backend communicate with each other. I also learned how to handle API responses, display success and error messages, and navigate users to another page after a successful login.

---

#  Creating the Get All Users API

The first task of today's session was creating an API to retrieve all users stored in the MongoDB database.

I learned that whenever we need to fetch data from the database, we use the **GET** request. Using Mongoose, I used the `find()` method to retrieve all user documents from the collection.

### Purpose of `User.find()`

- Fetches all users from the database.
- Returns the data in the form of an array.
- Commonly used to display all records on the frontend.

### Controller Code

```javascript
export const getAllUsers = async (req, res) => {
    try {

        const users = await User.find();

        if(users){
            res.status(200).json({
                message: "User added",
                users: users
            });
        }

    } catch(error){

        res.status(500).json({
            error: error,
        });

    }
}
```

### Working

- The API receives a GET request.
- `User.find()` fetches all users from MongoDB.
- If users are found, the API returns a success response with the complete list of users.
- If an error occurs, an error response is sent.

---

#  Creating the Login API

After creating the Get API, I created a **Login API** to verify whether the user already exists in the database.

Instead of adding a new user every time, this API checks whether the entered username exists using the `findOne()` method.

### Purpose of `User.findOne()`

- Searches for a single document.
- Returns the matching user if found.
- Returns `null` if no matching user exists.

### Controller Code

```javascript
export const loginUser = async (req, res) => {

    try {

        const { name } = req.body;

        const user = await User.findOne({ name });

        if(user){

            res.status(200).json({
                message: "User login Successful"
            });

        }
        else{

            res.status(404).json({
                message: "User not found"
            });

        }

    }
    catch(error){

        res.status(500).json({
            error: error,
        });

    }

}
```



#  Updating the Routes

After creating the controller functions, I added their routes inside the **userRoutes.js** file.

I learned that routes connect incoming HTTP requests to the appropriate controller functions.

### userRoutes.js

```javascript
import { Router } from "express";
import { addUser, getAllUsers, loginUser } from "../controllers/userController.js";

const router = Router();

router.post("/", addUser);

router.get("/", getAllUsers);

router.post("/login", loginUser);

export default router;
```


#  Connecting Backend with Frontend using Axios

After completing the backend APIs, I connected them with my React frontend.

I created a **services** folder inside the `src` directory and added a file named **userServices.js**.
I learned that creating service files keeps API calls separate from React components, making the code cleaner, reusable, and easier to maintain.

### userServices.js

```javascript
import axios from "axios";

export const addUser = async(userData) => {

    try{

        return await axios.post(
            "http://localhost:5000/users",
            userData
        );

    }
    catch(error){

        console.log(error);

    }

}

export const loginUser = async(userData) => {

    try{

        return await axios.post(
            "http://localhost:5000/users/login",
            userData
        );

    }
    catch(error){

        console.log(error);
        throw error;

    }

}
```

### What I Learned

- `axios.post()` sends data from React to the backend.
- API calls are written separately inside service files.
- The same service can be reused in multiple components.

---

#  Using the Login API in React

After creating the service file, I used the `loginUser()` function inside my **Signin.jsx** component.

I used the **useState Hook** to store the values entered by the user and **useNavigate()** from React Router to redirect the user after a successful login.

### Main Concepts Used

- `useState`
- `useNavigate`
- Event handling
- Form validation
- Async/Await
- Axios
- React Router

### Signin.jsx

```javascript
import { useState } from "react";
import { useNavigate } from "react-router-dom";
import { loginUser } from "../services/userServices";

function Signin() {

    const navigate = useNavigate();

    const [formData, setForm] = useState({
        name: "",
        age: "",
    });

    const handleChange = (e) => {

        setForm({
            ...formData,
            [e.target.name]: e.target.value,
        });

    };

    const handleSubmit = async (e) => {

        e.preventDefault();

        if (!formData.name || !formData.age) {

            alert("Please fill all fields");
            return;

        }

        try {

            const res = await loginUser(formData);

            alert(res.data.message);

            setForm({
                name: "",
                age: "",
            });

            navigate("/product");

        }
        catch(error){

            console.error(error);

            alert(error.response?.data?.message || "Something went wrong");

        }

    };

    return (

        <div className="signin-container">

            <form className="signin" onSubmit={handleSubmit}>

                <h2>Sign In</h2>

                <div>

                    <label>Name</label><br />

                    <input
                        type="text"
                        placeholder="Enter Name"
                        name="name"
                        value={formData.name}
                        onChange={handleChange}
                    />

                </div>

                <br />

                <div>

                    <label>Age</label><br />

                    <input
                        type="number"
                        placeholder="Enter Age"
                        name="age"
                        value={formData.age}
                        onChange={handleChange}
                    />

                </div>

                <br />

                <button type="submit">Submit</button>

            </form>

        </div>

    );

}

export default Signin;
```

---





#  Key Learning Outcomes

- Learned how to create a **Get All Users API** using `User.find()`.
- Learned how to create a **Login API** using `User.findOne()`.
- Understood the difference between `find()` and `findOne()`.
- Added GET and Login routes in `userRoutes.js`.
- Created a reusable **userServices.js** file for API calls.
- Connected the React frontend with the Express backend using Axios.
- Learned how to call backend APIs from React components.
- Used `async/await` for handling asynchronous requests.
- Practiced form validation before sending data.
- Used `useNavigate()` to redirect users after successful login.
- Improved my understanding of frontend-backend communication in a MERN application.

---


**Status:**  Day 21 Successfully Completed
