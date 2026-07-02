# 🚀 MERN Stack Training Diary – Day 09
**Date:** 2 July 2026

#  Topic: Introduction to React and Creating Reusable Components

Today was the ninth day of my MERN Stack training. Today's session marked the beginning of learning **React.js**, one of the most popular JavaScript libraries used for building modern and interactive user interfaces. Before today, I had been creating webpages using HTML, CSS, and JavaScript. React introduced me to a new way of building web applications by dividing the user interface into small, reusable components.

The session started with an introduction to React, followed by the installation and setup process. I learned how to create a new React project using Vite, understood the folder structure of a React application, and finally created reusable components using **export** and **import**.

---

# Introduction to React

The session began with an introduction to **React.js**.

I learned that React is an open-source JavaScript library developed by **Meta (Facebook)** for building fast, dynamic, and interactive user interfaces. React is based on the concept of **components**, where each part of a webpage can be created independently and reused whenever needed.

Some important features of React that I learned are:

- Component-based architecture
- Reusable code
- Faster rendering using Virtual DOM
- Easy to maintain and update applications
- Widely used for Single Page Applications (SPA)

I understood that React makes web development more organized because developers can divide large applications into smaller reusable components.

---

#  React Setup and Installation

After learning the basics of React, I installed React on my laptop and set up the development environment.

I learned that **Vite** is a modern build tool used to create React projects quickly and efficiently.

The commands I practiced during the installation process were:

### Create a New React Project

```bash
npm create vite@latest
```

This command creates a new React project using Vite.

---

### Install Required Packages

```bash
npm install
```

This command installs all the dependencies mentioned in the `package.json` file.

---

### Run the Development Server

```bash
npm run dev
```

This command starts the local development server and provides a localhost URL where the React application can be viewed in the browser.

After running this command successfully, I opened the project in my browser using the localhost link and confirmed that the React application was working correctly.

---

#  Understanding the React Project Structure

After creating the project, I explored the folder structure of a React application.

I learned the purpose of different files and folders used in a React project.

### `node_modules`

This folder contains all the installed packages and dependencies required by the project. It is automatically created after running the `npm install` command.

### `public`

The public folder stores static files such as images, icons, and other assets that do not require processing by React.

### `src`

The `src` folder is the most important folder because it contains the application's source code. Most of the development work is done inside this folder.

### `App.jsx`

This file contains the main React component where the application's UI is created. I learned that I can modify this file to display my own content instead of the default React page.

### `main.jsx`

This is the entry point of the React application. It renders the main `App` component into the browser.

### `package.json`

This file stores project information, installed dependencies, and npm scripts used to run the project.

Understanding the folder structure helped me know where different parts of the project are located and how React applications are organized.

---

# Making Changes in App.jsx

After understanding the project structure, I opened the **App.jsx** file and experimented by modifying its content.

I removed the default React template and displayed my own text on the webpage. Every time I saved the file, the browser updated automatically without refreshing the page.

This introduced me to React's **Hot Reloading** feature, which instantly reflects changes made in the code.

Through this activity, I understood that React development becomes much faster because developers can immediately see the changes they make.

---

#  Creating Reusable Components

The final topic of today's session was **React Components**.

I learned that a component is an independent and reusable piece of code that returns a part of the user interface.

Instead of writing the same HTML repeatedly, React allows developers to create one component and reuse it multiple times.

I also learned how components are created using JavaScript functions.

### Example

```jsx
function Header(){

    return(

        <h1>Welcome to React</h1>

    );

}

export default Header;
```

The `export default` statement makes the component available for use in other files.

---

#  Importing Components

After creating a component, I learned how to import it into another file.

### Example

```jsx
import Header from "./Header";

function App(){

    return(

        <div>

            <Header />

        </div>

    );

}

export default App;
```

Using the `import` statement, I was able to reuse the component inside the `App.jsx` file.

This activity helped me understand how React applications are built by combining multiple reusable components.

---

#  Key Learning Outcomes

- Learned the basics and importance of React.js.
- Understood the advantages of component-based development.
- Successfully installed and configured React using Vite.
- Learned the commands required to create and run a React project.
- Explored the folder structure of a React application.
- Modified the default React project by editing the `App.jsx` file.
- Learned the concept of reusable components.
- Practiced creating and importing components using `export` and `import`.
- Gained confidence in setting up and running React projects independently.

---



**Status:** Day 09 Successfully Completed
