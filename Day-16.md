#  MERN Stack Training Diary – Day 16
**Date:** 13 July 2026

##  Topic: Introduction to Server, Node.js, Express.js, Project Setup, and Environment Variables

Today was the sixteenth day of my MERN Stack training. The session marked the beginning of backend development. Until now, I had mainly worked on the frontend using HTML, CSS, JavaScript, and React. Today, I learned how the backend works and how it communicates with the frontend.
The trainer started by explaining the concept of a **server**, its role in web development, and why it is required. After that, I learned about **Node.js**, its features, and why it is widely used for backend development. I also understood the basic folder structure of a Node.js project, including the purpose of files such as **server.js**, **app.js**, **routes**, and **middleware**.
After learning the theoretical concepts, I set up my first backend project by initializing Node.js, installing the required packages such as **Express**, **Nodemon**, and **Dotenv**, and configuring environment variables.

---

#  Introduction to Server

The session began with the concept of a **server**.

I learned that a server is a computer or software that receives requests from users (clients), processes those requests, and sends back the appropriate response. Whenever we open a website or use an application, the browser sends a request to the server, and the server responds with the required data.

For example:

- When we log in to a website, the request is sent to the server.
- The server verifies the user's information.
- It then sends a response indicating whether the login is successful or not.

### Importance of a Server

- Stores and manages application data.
- Processes requests from users.
- Connects the frontend with the database.
- Handles authentication and authorization.
- Performs business logic.
- Sends responses back to the client.

---

#  Introduction to Node.js

After understanding servers, I learned about **Node.js**.

Node.js is a JavaScript runtime environment that allows JavaScript code to run outside the browser. Before Node.js, JavaScript was mainly used for frontend development. With Node.js, developers can build backend applications using JavaScript.

I also learned that Node.js is built on Google's V8 JavaScript Engine, which makes it very fast and efficient.

### Importance of Node.js

- Allows JavaScript to run on the server.
- Fast and lightweight.
- Uses a non-blocking and event-driven architecture.
- Suitable for scalable web applications.
- Large collection of packages through NPM.
- Widely used for backend development.

---

#  Basic Project Structure

The trainer explained the purpose of different files and folders used in a backend project.

### `server.js`

This is the entry point of the application. It starts the server and listens for incoming client requests.

### `app.js`

This file contains the main Express application. It is used to configure middleware, routes, and other application settings, making the code cleaner and easier to maintain.

### `routes`

The **routes** folder contains different route files. Routes define which function should execute when a specific URL is requested by the client.

### `middleware`

Middleware functions execute before the request reaches the final route handler. They are commonly used for logging, authentication, request validation, and error handling.

Learning this project structure helped me understand how backend applications are organized in real-world development.

---

#  Initializing a Node.js Project

After learning the theory, I created my first backend project.

I initialized the project using the following command:

```bash
npm init -y
```

This command automatically created a **package.json** file with the default project configuration.

The `package.json` file stores important information such as:

- Project name
- Version
- Installed dependencies
- Scripts
- Project metadata

---

#  Installing Nodemon

Next, I installed **Nodemon**.

```bash
npm install nodemon
```

I learned that Nodemon automatically restarts the server whenever changes are made to the project files. This saves time because we do not need to stop and restart the server manually after every modification.

After installing Nodemon, I updated the **package.json** file by adding a new script.

```json
"scripts": {
    "dev": "nodemon server"
}
```

Now I can start the server using:

```bash
npm run dev
```

This makes the development process much faster and more convenient.

---

#  Installing Express.js

After setting up Nodemon, I installed **Express.js** using the following command:

```bash
npm install express
```

I learned that Express.js is a web framework built on top of Node.js. It simplifies backend development by providing features for routing, middleware, request handling, and response handling.

### Advantages of Express.js

- Easy to create web servers.
- Simplifies routing.
- Supports middleware.
- Faster backend development.
- Easy integration with databases.

---

#  Using Environment Variables with Dotenv

The final topic of today's session was **Dotenv**.

I learned that sensitive information such as:

- Database URLs
- API keys
- Secret keys
- Port numbers

should never be written directly inside the source code.

Instead, they should be stored inside a **.env** file.

First, I installed Dotenv using:

```bash
npm install dotenv
```

Then I created a `.env` file in the project folder.

Example:

```env
PORT=5000
```

After creating the file, I configured Dotenv inside **app.js**.

```javascript
require("dotenv").config();
```

Now I can access environment variables anywhere in the project using:

```javascript
process.env.PORT
```

Using environment variables makes the application more secure and easier to manage.

---

#  Key Learning Outcomes

- Understood the concept and importance of a server.
- Learned how the frontend communicates with the backend.
- Studied the basics and importance of Node.js.
- Understood the purpose of `server.js`, `app.js`, `routes`, and `middleware`.
- Initialized a Node.js project using `npm init -y`.
- Learned the role of the `package.json` file.
- Installed and configured Nodemon.
- Added a development script to `package.json`.
- Installed Express.js and understood its advantages.
- Learned how to use Dotenv for environment variables.
- Configured the `.env` file and accessed environment variables using `process.env`.

---


**Status:**  **Day 16 Successfully Completed**
