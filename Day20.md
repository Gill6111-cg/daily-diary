#  MERN Stack Training Diary – Day 20
**Date:** 17 July 2026

#  Topic: Connecting React Frontend with Express Backend using Axios and CORS

Today was the twentieth day of my MERN Stack training. The main objective of today's session was to connect the **React frontend** with the **Express backend**. Until now, I had built the frontend and backend separately, but today I learned how they communicate with each other.
The session started with installing **Axios**, a popular HTTP client used to send API requests from the frontend. I created a separate **services** folder to keep all API-related functions organized. After that, I updated my React login form so that the user data entered in the form could be sent directly to the backend and stored in the MongoDB database.
Finally, I learned about **CORS (Cross-Origin Resource Sharing)**, why it is required, and how to configure it in the backend to allow communication between the React frontend and the Express server.

Overall, today's session helped me understand the complete flow of sending data from the frontend to the backend and storing it in the database.

---

#  Introduction to Axios

The session began with learning about **Axios**.

I learned that Axios is a JavaScript library used to send HTTP requests from the frontend to the backend. It allows React applications to communicate with APIs easily and supports methods such as **GET**, **POST**, **PUT**, and **DELETE**.

### Installation Command

```bash
npm i axios
```

### Advantages of Axios

- Sends HTTP requests easily.
- Supports GET, POST, PUT, and DELETE methods.
- Automatically converts JavaScript objects into JSON.
- Provides better error handling using `try...catch`.
- Returns responses in a structured format.
- Widely used in React applications.

---

#  Creating the Services Folder

After installing Axios, I created a new folder named **services** inside the `src` directory.

I learned that API-related functions should be written in a separate folder instead of directly inside React components. This keeps the code clean, reusable, and easier to maintain.
Inside the **services** folder, I created a file named **userServices.js**.

---

#  userServices.js

```javascript
import axios from "axios";

export const addUser = async (userData) => {
  try {
    return await axios.post(
      "http://localhost:5000/users",
      userData
    );
  } catch (error) {
    console.log(error);
  }
};
```



#  Updating the React Login Form

After creating the service function, I updated my React login page.

Instead of directly sending data inside the component, I imported the `addUser()` function from the services folder.

I also used the **useState Hook** to manage the form data.

Whenever the user entered their name and age, the values were stored inside a state object. After clicking the **Save User** button, the data was sent to the backend using Axios.
If the request was successful, the server returned a success message, and the input fields were cleared automatically.

This practical activity helped me understand how React forms interact with backend APIs.

---

#  Login.jsx

```javascript
import { useState } from "react";
import { addUser } from "../services/userServices";

function Login() {
  const [formData, setFormData] = useState({
    name: "",
    age: "",
  });

  function handleChange(e) {
    setFormData({
      ...formData,
      [e.target.name]: e.target.value,
    });
  }

  async function handleSubmit(e) {
    e.preventDefault();

    try {
      const res = await addUser(formData);

      alert(res.data.message);

      setFormData({
        name: "",
        age: "",
      });
    } catch (error) {
      console.log(error);
      alert("Something went wrong");
    }
  }

  return (
    <div
      style={{
        height: "100vh",
        backgroundColor: "#f4f4f4",
        display: "flex",
        justifyContent: "center",
        alignItems: "center",
      }}
    >
      <div
        style={{
          width: "380px",
          backgroundColor: "white",
          padding: "30px",
          borderRadius: "10px",
          boxShadow: "0px 0px 15px rgba(0,0,0,0.2)",
          textAlign: "center",
        }}
      >
        <h1 style={{ marginBottom: "20px", color: "#333" }}>
          Add User
        </h1>

        <form onSubmit={handleSubmit}>
          <input
            type="text"
            placeholder="Enter Name"
            name="name"
            value={formData.name}
            onChange={handleChange}
            style={{
              width: "100%",
              padding: "12px",
              marginBottom: "15px",
              border: "1px solid #ccc",
              borderRadius: "5px",
              fontSize: "16px",
            }}
          />

          <input
            type="text"
            placeholder="Enter Age"
            name="age"
            value={formData.age}
            onChange={handleChange}
            style={{
              width: "100%",
              padding: "12px",
              marginBottom: "20px",
              border: "1px solid #ccc",
              borderRadius: "5px",
              fontSize: "16px",
            }}
          />

          <button
            type="submit"
            style={{
              width: "100%",
              padding: "12px",
              backgroundColor: "#ff6600",
              color: "white",
              border: "none",
              borderRadius: "5px",
              fontSize: "18px",
              cursor: "pointer",
            }}
          >
            Save User
          </button>
        </form>
      </div>
    </div>
  );
}

export default Login;
```

---

#  Working of the React Form

The complete flow of the form is:

1. The user enters **Name** and **Age**.
2. `handleChange()` updates the state using `useState`.
3. Clicking the **Save User** button triggers `handleSubmit()`.
4. `e.preventDefault()` prevents the page from refreshing.
5. The `addUser()` function sends the data to the backend using Axios.
6. The backend stores the data in MongoDB.
7. The server returns a success message.
8. An alert displays the response.
9. The input fields are cleared.

---

#  Introduction to CORS

After connecting the frontend and backend, I learned about **CORS (Cross-Origin Resource Sharing)**.

I understood that the React frontend and Express backend run on different ports:

- Frontend → `http://localhost:5173`
- Backend → `http://localhost:5000`

Since these are different origins, the browser blocks requests by default for security reasons. To allow communication between them, CORS must be enabled on the backend.

---

#  Installing CORS

I installed the CORS package using the following command:

```bash
npm i cors
```

---

#  Configuring CORS in app.js

After installing CORS, I imported it into my backend and configured it to allow requests from the React frontend.

```javascript
import express from "express";
import dotenv from "dotenv";
import cors from "cors";
import userRoutes from "./routes/userRoutes.js";

dotenv.config();

const app = express();

app.use(express.json());

app.use(
  cors({
    origin: "http://localhost:5173",
  })
);

app.use("/users", userRoutes);

export default app;
```


#  Complete Data Flow

```
React Form
     │
     ▼
handleSubmit()
     │
     ▼
Axios (POST Request)
     │
     ▼
Express Backend
     │
     ▼
Controller
     │
     ▼
MongoDB Database
     │
     ▼
Response
     │
     ▼
React Frontend
```

This flow helped me understand how data travels from the frontend to the backend and finally gets stored in the database.

---

#  Key Learning Outcomes

- Installed Axios in the React project.
- Learned the purpose and advantages of Axios.
- Created a separate **services** folder for API functions.
- Built a reusable `addUser()` API function using Axios.
- Updated the React login form to send data to the backend.
- Used `useState` to manage form input values.
- Learned how to submit form data using asynchronous functions.
- Displayed success messages returned by the backend.
- Cleared input fields after successful submission.
- Installed the CORS package in the backend.
- Understood the purpose of CORS and why it is required.
- Configured CORS to allow communication between the React frontend and Express backend.
- Successfully connected the frontend, backend, and MongoDB database.

---


---

**Status:**  Day 20 Successfully Completed
