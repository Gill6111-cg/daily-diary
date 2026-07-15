#  MERN Stack Training Diary – Day 18
**Date:** 15 July 2026

#  Topic: PUT & DELETE Routes in Express.js and MongoDB Atlas Setup

Today was the eighteenth day of my MERN Stack training. The session focused on understanding the **PUT** and **DELETE** routes in Express.js in greater detail. I learned how these routes are used to update and remove data from a server. One of the most important concepts I learned today was the use of **Route Parameters (`:id`)**. I understood why an **ID** is required while updating or deleting data and how Express uses `req.params` to identify a specific record.
After practicing these routes with an array of objects, I moved on to the database setup. I created a **MongoDB Atlas** account, configured a cloud database, changed the network access IP address to **0.0.0.0/0** so that it could be accessed from anywhere, and installed **Mongoose** in my project. I also learned why Mongoose is used to connect a Node.js application with MongoDB.
Overall, today's session introduced me to updating and deleting records through APIs and took my first step toward integrating a real database into my backend application.

---

#  Understanding the PUT Route

The session started with a detailed explanation of the **PUT** request.
I learned that the **PUT** method is used to update existing data on the server. Unlike the POST method, which creates new data, PUT modifies the existing record. To update the correct record, the server must know **which object needs to be changed**, and for this purpose an **ID** is used.

---

#  Importance of `:id` in PUT and DELETE Routes

One of the most important topics I learned today was the use of **Route Parameters (`:id`)**.

I understood that if multiple records are stored in an array or database, the server needs a unique way to identify which record should be updated or deleted. This unique identifier is usually called **ID**.

For example:

```text
/student/1
/student/2
/student/3
```

Here:

- `1`, `2`, and `3` are route parameters.
- Express stores these values inside `req.params`.
- We can access them using:

```javascript
req.params.id
```

Since route parameters are received as strings, I learned that they are converted into numbers using the `Number()` function before comparing them with numeric IDs.

```javascript
const productId = Number(req.params.id);
```

Without an ID, the server would not know which particular record should be updated or deleted.

---

#  Updating Data Using PUT Route

After understanding route parameters, I practiced updating an object stored inside an array.

First, I received the ID from the URL.

```javascript
const productId = Number(req.params.id);
```

Then, I searched for the object's index using the `findIndex()` method.

```javascript
const index = arr.findIndex(s => s.id === productId);
```

Finally, I replaced the existing object with the new data received from the request body.

```javascript
arr[index] = req.body;
```

The server then returned a JSON response containing a success message and the updated array.

---

#  PUT Route Code

```javascript
app.put("/:id", (req, res) => {

    const productId = Number(req.params.id);

    const index = arr.findIndex(s => s.id === productId);

    arr[index] = req.body;

    res.json({
        message: "Updated Successfully",
        data: arr
    });

});
```

---

#  Understanding the DELETE Route

Next, I learned about the **DELETE** request.

The DELETE method removes existing data from the server. Just like the PUT request, DELETE also requires an ID to identify which record should be removed.
After receiving the ID, I again used `findIndex()` to locate the object's position inside the array.

Instead of updating the object, I removed it using the `splice()` method.

```javascript
arr.splice(index, 1);
```

This removes one element from the specified index.

---

#  DELETE Route Code

```javascript
app.delete("/:id", (req, res) => {

    const productId = Number(req.params.id);

    const index = arr.findIndex(s => s.id === productId);

    arr.splice(index, 1);

    res.json({
        message: "Deleted Successfully",
        data: arr
    });

});
```

---

#  Methods Used Today

### `req.params`

Used to read route parameters from the URL.

```javascript
req.params.id
```

---

### `Number()`

Converts the string received from the URL into a number.

```javascript
Number(req.params.id);
```

---

### `findIndex()`

Returns the index of the object whose condition matches.

```javascript
arr.findIndex(s => s.id === productId);
```

---

### `splice()`

Removes elements from an array.

```javascript
arr.splice(index, 1);
```

---

#  MongoDB Atlas Setup

After completing the Express routes, I started learning about **MongoDB Atlas**.

I learned that MongoDB Atlas is a **cloud-based database service** provided by MongoDB. Unlike the local MongoDB server, Atlas stores databases on the cloud, making them accessible from anywhere.

I created a new MongoDB Atlas account and learned the complete setup process.

---

#  Configuring Network Access

One important step during the setup was configuring **Network Access**.

I changed the IP address to:

```text
0.0.0.0/0
```

This allows connections from any IP address.

I learned that during development this setting is commonly used because it allows the application to connect from different devices and networks. However, for production applications, network access should be restricted for better security.

---

#  Installing Mongoose

After completing the Atlas setup, I installed **Mongoose** in my project.

### Installation Command

```bash
npm i mongoose
```

---

#  What is Mongoose?

I learned that **Mongoose** is an Object Data Modeling (ODM) library for MongoDB and Node.js.

It acts as a bridge between the Express application and the MongoDB database.

Using Mongoose, developers can:

- Connect Node.js with MongoDB.
- Create schemas and models.
- Perform CRUD (Create, Read, Update, Delete) operations.
- Validate data before saving it into the database.
- Write cleaner and more organized database queries.

I understood that Mongoose makes working with MongoDB much easier compared to using the native MongoDB driver.

---

#  Key Learning Outcomes

- Learned the working of PUT requests in Express.js.
- Understood the purpose of DELETE requests.
- Learned why `:id` is important in update and delete operations.
- Practiced using `req.params` to read route parameters.
- Used `Number()` to convert route parameters into numeric values.
- Learned how `findIndex()` searches for an object inside an array.
- Used `splice()` to remove objects from an array.
- Set up a MongoDB Atlas cloud database.
- Configured network access by setting the IP address to `0.0.0.0/0`.
- Installed Mongoose using `npm i mongoose`.
- Understood the role of Mongoose in connecting Node.js with MongoDB.

---


---

**Status:**  Day 18 Successfully Completed
