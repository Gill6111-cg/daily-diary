#  MERN Stack Training Diary – Day 23
**Date:** 22 July 2026

#  Topic: Edit and Delete User Functionality using React, Express, MongoDB, and Axios

Today was the twenty-third day of my MERN Stack training. The main focus of today's session was to implement the **Update (Edit)** and **Delete** operations of CRUD in my MERN application. I learned how to create backend APIs for editing and deleting users from the MongoDB database and then connected those APIs with the React frontend using Axios services.

I also created an **Edit User Form** that automatically displays the existing details of the selected user, allowing them to update their information. On the Home page, I added **Edit** and **Delete** buttons for every user displayed in the table. This completed the CRUD (Create, Read, Update, Delete) operations in my project and gave me a better understanding of full-stack application development.

---

#  Update (Edit) Operation

The first concept I learned today was the **Update** operation.

Updating data means modifying the existing information stored in the database. To update a particular user, the application requires the user's unique **MongoDB ID**, which is passed through the URL.

I learned that Express provides route parameters using `req.params`, while the updated information entered by the user is available through `req.body`.

The update operation is performed using Mongoose's:

```javascript
findByIdAndUpdate()
```

### Syntax

```javascript
Model.findByIdAndUpdate(id, updatedData, {
    new: true
});
```

The option:

```javascript
new: true
```

returns the updated document after modification.

---

#  Delete Operation

The next concept I learned was deleting records from MongoDB.

To delete a user, I again used the user's unique **_id**.

Mongoose provides the following method:

```javascript
findByIdAndDelete()
```

### Syntax

```javascript
Model.findByIdAndDelete(id);
```

This permanently removes the selected document from the database.

---

#  Backend API – Delete User

I created a new API in **userController.js** to delete a user from MongoDB.

### userController.js

```javascript
export const deleteUser = async (req, res) => {
  try {
    const { id } = req.params;

    const user = await User.findByIdAndDelete(id);

    if (user) {
      res.status(200).json({
        message: "User deleted",
      });
    } else {
      res.status(404).json({
        message: "User not found",
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

- Reads the user's ID from the URL.
- Deletes the user from MongoDB.
- Sends a success message if deletion is successful.
- Returns an error message if the user is not found.

---

#  Delete Route

After creating the controller, I added its route in **userRoutes.js**.

```javascript
router.delete("/:id", deleteUser);
```

This route allows the frontend to send a DELETE request for a specific user.

---

#  Delete Service (Frontend)

Next, I created the delete service inside **userServices.js**.

```javascript
export const deleteUser = async (id) => {
  try {
    return await axios.delete(
      `http://localhost:5000/users/${id}`
    );
  } catch (error) {
    console.log(error);
    throw error;
  }
};
```

### Explanation

This service sends a DELETE request from React to the backend API using Axios.

---

#  Backend API – Edit User

After completing the delete functionality, I created the **Edit User API**.

### userController.js

```javascript
export const editUser = async (req, res) => {
  try {
    const { id } = req.params;

    const user = await User.findByIdAndUpdate(
      id,
      req.body,
      {
        new: true,
      }
    );

    if (user) {
      res.status(200).json({
        message: "User updated successfully",
        user,
      });
    } else {
      res.status(404).json({
        message: "User not found",
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

- Receives the user's ID.
- Receives updated data from the frontend.
- Updates the database.
- Returns the updated user object.

---

#  Edit Route

I added the edit route in **userRoutes.js**.

```javascript
router.put("/:id", editUser);
```

This route handles all update requests.

---

#  Edit Service (Frontend)

Next, I connected the update API with React.

### userServices.js

```javascript
export const editUser = async (id, userData) => {
  try {
    return await axios.put(
      `http://localhost:5000/users/${id}`,
      userData
    );
  } catch (error) {
    console.log(error);
    throw error;
  }
};
```

### Explanation

This service sends updated user information to the backend using Axios.

---

#  Creating EditForm Component

After creating the APIs, I created a new page named **EditForm.jsx**.

The purpose of this page is to:

- Display the selected user's existing details.
- Allow the user to edit them.
- Submit the updated information.
- Redirect back to the Home page after updating.

### EditForm.jsx

```jsx
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

  const fetchUser = async () => {
    try {
      const res = await getAllUsers();

      const user = res.data.users.find(
        (u) => u._id === id
      );

      if (user) {
        setFormData({
          name: user.name,
          age: user.age,
        });
      }
    } catch (error) {
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
      alert("Failed to update user");
    }
  };

  return (
    <form onSubmit={handleSubmit}>
      <input
        name="name"
        value={formData.name}
        onChange={handleChange}
      />

      <input
        name="age"
        value={formData.age}
        onChange={handleChange}
      />

      <button>Update User</button>
    </form>
  );
}

export default EditForm;
```

### Explanation

In this component, I learned:

- `useParams()` to get the user ID from the URL.
- `useEffect()` to fetch existing user data.
- `useState()` to manage form data.
- `navigate()` to redirect after updating.
- Controlled form inputs.

---

#  Updating Home.jsx

After completing the Edit page, I modified **Home.jsx** by adding **Edit** and **Delete** buttons for every user.

### Home.jsx

```jsx
<button
  onClick={() =>
    navigate(`/edit/${user._id}`)
  }
>
  Edit
</button>

<button
  onClick={() =>
    handleDelete(user._id)
  }
>
  Delete
</button>
```

### Explanation

- **Edit Button**
  - Opens the EditForm page.
  - Passes the selected user's ID.

- **Delete Button**
  - Calls the delete API.
  - Removes the selected user from the database.
  - Refreshes the user list automatically.

---










---

#  Key Learning Outcomes

- Learned the Update (PUT) operation in MongoDB.
- Learned the Delete (DELETE) operation in MongoDB.
- Created the Delete User API.
- Created the Edit User API.
- Added PUT and DELETE routes in Express.
- Connected backend APIs with React using Axios services.
- Created an Edit User form using React.
- Used `useParams()` to read dynamic route parameters.
- Used `useNavigate()` for page navigation.
- Used `useEffect()` to fetch existing user data.
- Added Edit and Delete buttons to the Home page.
- Completed all CRUD operations in the MERN application.

---




**Status:**  Day 23 Successfully Completed
