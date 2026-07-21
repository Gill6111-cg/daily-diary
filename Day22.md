#  MERN Stack Training Diary – Day 22
**Date:** 21 July 2026

#  Topic: Displaying Data from Backend, Understanding Frontend–Backend Flow, and Creating Delete API

Today was the twenty-second day of my MERN Stack training. In today's session, I focused on displaying data from the MongoDB database in my React application using the **Get All Users API** that I had created previously. I also learned how the frontend and backend are connected and how a request travels from the React application to the Express server and finally to the MongoDB database.
After understanding the complete flow of a MERN application, I created a **Delete API** that allows users to remove records from the database. This session helped me understand CRUD (Create, Read, Update, Delete) operations more clearly.

---

#  Displaying All Users in React

The first task of today's session was to display all users stored in the MongoDB database on the Home page.

To achieve this, I updated the **Home.jsx** component and used the `getAllUsers()` service function to fetch data from the backend.

I learned that React's `useEffect()` Hook is used to call an API automatically when the component loads, while `useState()` is used to store the fetched data.

### Concepts Used

- `useState`
- `useEffect`
- Axios
- API Calling
- Async/Await
- Conditional Rendering
- `map()` function

---

## Home.jsx

```jsx
import { useEffect, useState } from "react";
import { getAllUsers } from "../services/userServices";

function Home() {

  const [users, setUsers] = useState([]);

  const fetchUsers = async () => {

    try {

      const res = await getAllUsers();

      setUsers(res.data.users);

    }
    catch(error){

      console.log(error);

      alert("Failed to fetch users");

    }

  };

  useEffect(() => {

    fetchUsers();

  }, []);

  return (

    <div style={{ padding: "30px" }}>

      <h2>Users List</h2>

      <table
        border="1"
        cellPadding="10"
        cellSpacing="0"
        style={{
          width: "60%",
          margin: "20px auto",
          textAlign: "center",
          borderCollapse: "collapse",
        }}
      >

        <thead>

          <tr>
            <th>Name</th>
            <th>Age</th>
          </tr>

        </thead>

        <tbody>

          {
            users.length > 0 ?

            users.map((user) => (

              <tr key={user._id}>
                <td>{user.name}</td>
                <td>{user.age}</td>
              </tr>

            ))

            :

            <tr>
              <td colSpan="2">No Users Found</td>
            </tr>

          }

        </tbody>

      </table>

    </div>

  );

}

export default Home;
```

---

#  Updating the Service File

After updating the Home component, I added a new function inside **userServices.js** to fetch all users from the backend.

I learned that service files help keep API calls separate from React components, making the project more organized and reusable.

### userServices.js

```javascript
export const getAllUsers = async () => {

    try{

        return await axios.get(
            "http://localhost:5000/users"
        );

    }
    catch(error){

        console.log(error);

        throw error;

    }

}
```

---

#  Working of Data Fetching

I learned the complete process of displaying data from the database.

The flow is:

1. The React component loads.
2. `useEffect()` automatically calls `fetchUsers()`.
3. `fetchUsers()` calls the `getAllUsers()` service.
4. Axios sends a GET request to the backend.
5. The Express route receives the request.
6. The controller calls `User.find()` using Mongoose.
7. MongoDB returns all user documents.
8. The backend sends the response back to React.
9. React stores the data using `useState()`.
10. The `map()` function displays all users inside the table.

This helped me understand how every part of a MERN application communicates with one another.

---

#  Understanding the Complete MERN Request Flow

One of the most important topics I learned today was the complete flow of data between the frontend and backend.

The complete flow is:

```
React Component

        ↓

userServices.js (Axios)

        ↓

HTTP Request

        ↓

Express Route

        ↓

Controller

        ↓

Mongoose

        ↓

MongoDB Database

        ↓

Response Returned

        ↓

React Component

        ↓

Displayed on the Screen
```

Understanding this flow gave me a much clearer idea of how full-stack web applications work internally.

---

#  Creating the Delete API

After successfully displaying users, I learned how to delete data from the MongoDB database.

I created a **Delete API**, which removes a specific user from the database using their unique MongoDB ID.

I learned that every document stored in MongoDB automatically receives a unique `_id`. This ID is used to identify the exact document that needs to be deleted.

### Concepts Learned

- DELETE Request
- Route Parameters (`:id`)
- MongoDB `_id`
- `findByIdAndDelete()`
- CRUD Operations

The Delete API is useful because it allows users to permanently remove records from the database whenever they are no longer needed.

---

#  Key Learning Outcomes

- Learned how to display data stored in MongoDB on the React frontend.
- Used `useEffect()` to fetch data automatically after component loading.
- Used `useState()` to store API responses.
- Created the `getAllUsers()` service using Axios.
- Displayed database records using the `map()` function.
- Understood conditional rendering when no data is available.
- Learned the complete request and response flow between frontend and backend.
- Understood how React, Axios, Express, Controllers, Mongoose, and MongoDB work together.
- Created a Delete API to remove data from the database.
- Improved my understanding of CRUD operations in a MERN Stack application.

---

sion helped me connect everything I had learned over the past few days. Instead of only creating APIs, I successfully displayed database records on the frontend, which made the application feel much more complete. Understanding the entire flow—from a React component sending a request, to the backend processing it, and finally displaying the response on the webpage—gave me a clear picture of how MERN applications work. Learning to create the Delete API also completed another important CRUD operation and increased my confidence in developing full-stack web applications.

**Status:**  Day 22 Successfully Completed
