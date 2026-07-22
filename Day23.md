# 🚀 MERN Stack Training Diary – Day 23
**Date:** 22 July 2026

#  Topic: Implementing Edit and Delete Functionality in a MERN Application

Today was the twenty-third day of my MERN Stack training. In today's session, I completed the remaining CRUD operations by implementing **Edit** and **Delete** functionality in my MERN application. I added **Edit** and **Delete** buttons to the Users table on the Home page and created the required backend APIs, frontend services, and React components to update and remove user records from the MongoDB database.

This session helped me understand how data can be modified and deleted through the frontend while keeping the database synchronized.

---

#  Adding Edit and Delete Buttons

The first task of today's session was to add **Edit** and **Delete** buttons for every user displayed in the Users table.

I learned that each button performs a different operation:

- **Edit** button opens a new page where the selected user's information can be updated.
- **Delete** button removes the selected user from the MongoDB database.

This made the application fully interactive and completed all CRUD operations.

---

#  Creating the Delete User API

After adding the Delete button, I created a backend API to delete a user using their MongoDB ID.

I learned that MongoDB automatically assigns a unique `_id` to every document, which is used to identify the exact record that needs to be deleted.

### Controller (userController.js)

```javascript
export const deleteUser = async (req, res) => {

    try{

        const { id } = req.params;

        const user = await User.findByIdAndDelete(id);

        if(user){

            res.status(200).json({
                message: "User deleted",
            });

        }
        else{

            res.status(404).json({
                message: "User not found",
            });

        }

    }
    catch(error){

        res.status(500).json({
            error: error.message,
        });

    }

}
```

### Working

- Receives the user ID from the URL.
- Searches for the user using `findByIdAndDelete()`.
- Deletes the record if it exists.
- Returns a success message.
- Displays an error if the user is not found.

---

#  Adding Delete Route

After creating the controller, I added the route inside **userRoutes.js**.

```javascript
router.delete("/:id", deleteUser);
```

This route allows the frontend to send a DELETE request to remove a specific user.

---

# Creating Delete Service

Next, I created a reusable service function in **userServices.js** to call the Delete API using Axios.

```javascript
export const deleteUser = async (id) => {

    try{

        return await axios.delete(
            `http://localhost:5000/users/${id}`
        );

    }
    catch(error){

        console.log(error);
        throw error;

    }

};
```

This service keeps API calls separate from React components and improves code organization.

---

#  Creating the Edit User API

After completing the Delete functionality, I created an API to update user information.

I learned that Mongoose provides the `findByIdAndUpdate()` method, which updates an existing document using its unique ID.

### Controller (userController.js)

```javascript
export const editUser = async (req, res) => {

    try{

        const { id } = req.params;

        const user = await User.findByIdAndUpdate(
            id,
            req.body,
            { new: true }
        );

        if(user){

            res.status(200).json({
                message: "User updated successfully",
                user,
            });

        }
        else{

            res.status(404).json({
                message: "User not found",
            });

        }

    }
    catch(error){

        res.status(500).json({
            error: error.message,
        });

    }

};
```

### Working

- Receives the user ID.
- Updates the record using the new data received from the frontend.
- Returns the updated document.
- Sends an error if no matching user is found.

---

#  Adding Edit Route

I then added the Edit route inside **userRoutes.js**.

```javascript
router.put("/:id", editUser);
```

This route handles HTTP PUT requests for updating user details.

---

#  Creating Edit Service

I created another service function inside **userServices.js** for updating user information.

```javascript
export const editUser = async (id, userData) => {

    try{

        return await axios.put(
            `http://localhost:5000/users/${id}`,
            userData
        );

    }
    catch(error){

        console.log(error);
        throw error;

    }

};
```

This service sends updated user data to the backend.

---

#  Creating the EditForm Component

After completing the backend APIs, I created a new React page named **EditForm.jsx**.

This page opens whenever the Edit button is clicked.

I used:

- `useParams()` to get the user ID from the URL.
- `useEffect()` to fetch existing user data.
- `useState()` to store the form values.
- `useNavigate()` to return to the Home page after updating the user.

### EditForm.jsx

import { useState, useEffect } from "react";
import { useNavigate, useParams } from "react-router-dom";
import { editUser, getAllUsers } from "../services/userServices";

function EditForm() {
  const navigate = useNavigate();
  const { id } = useParams();

  const [formData, setFormData] = useState({
    name: "",
    age: "",
  });

  // Fetch user data and fill form
  const fetchUser = async () => {
    try {
      const res = await getAllUsers();
      const user = res.data.users.find((u) => u._id === id);

      if (user) {
        setFormData({
          name: user.name || "",
          age: user.age || "",
        });
      }
    } catch (error) {
      console.log(error);
      alert("Failed to fetch user");
    }
  };

  useEffect(() => {
    fetchUser();
  }, [id]);

  const handleChange = (e) => {
    setFormData({
      ...formData,
      [e.target.name]: e.target.value,
    });
  };

  const handleSubmit = async (e) => {
    e.preventDefault();

    try {
      await editUser(id, formData);
      alert("User updated successfully");
      navigate("/");
    } catch (error) {
      console.log(error);
      alert("Failed to update user");
    }
  };

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
          Edit User
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
            type="number"
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
            Update User
          </button>
        </form>
      </div>
    </div>
  );
}

export default EditForm;
---

# 🏠 Updating the Home Page

Finally, I updated **Home.jsx** by adding **Edit** and **Delete** buttons inside the Users table.

### Edit Button

```jsx
<button
    onClick={() => navigate(`/edit/${user._id}`)}
>
    Edit
</button>
```

When clicked, it opens the **EditForm** page with the selected user's ID.

---

### Delete Button

```jsx
<button
    onClick={() => handleDelete(user._id)}
>
    Delete
</button>
```

When clicked:

- A confirmation message appears.
- If confirmed, the Delete API is called.
- The user is removed from the database.
- The table refreshes automatically.

---



# Key Learning Outcomes

- Added Edit and Delete buttons to the Users table.
- Created a Delete API using `findByIdAndDelete()`.
- Created an Edit API using `findByIdAndUpdate()`.
- Added PUT and DELETE routes in Express.
- Created reusable Axios service functions for Edit and Delete operations.
- Learned how to use `useParams()` to access route parameters.
- Used `useNavigate()` for page navigation.
- Created a separate `EditForm.jsx` component for updating user details.
- Learned how to prefill form data before editing.
- Refreshed the user list automatically after deleting a record.
- Completed all CRUD operations (Create, Read, Update, Delete) in the MERN application.

---


**Status:** ✅ Day 23 Successfully Completed
