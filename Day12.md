#  MERN Stack Training Diary – Day 12
**Date:** 07 July 2026

#  Topic: React Router, Routing, Navigation, and Page Switching

Today was the twelfth day of my MERN Stack training. Today's session focused on **React Router**, one of the most important libraries used in React applications. I learned why routing is required in React, how it works, and how multiple pages can be created inside a Single Page Application (SPA).

The session began with the introduction of React Router and its advantages. After understanding the theory, I installed the **react-router-dom** package in my project and configured routing using `createBrowserRouter` and `RouterProvider`. Finally, I created a practical project where I navigated between the **Home Page** and the **Display Page** using the `useNavigate()` hook.

This practical implementation helped me understand how navigation works in React applications without reloading the webpage.

---

#  Introduction to React Router

The session started with the introduction to **React Router**.

I learned that React is a **Single Page Application (SPA)**, meaning the webpage is loaded only once. Instead of loading a new HTML page every time, React changes only the required component on the screen.

To achieve this, React uses **React Router**.

React Router is a library that allows developers to navigate between different pages (components) without refreshing the browser.

---

# Importance of Routing in React

I understood why routing is important in React applications.

Some advantages of routing are:

- It allows navigation between different pages.
- It avoids full page reloads, making applications faster.
- It provides a better user experience.
- It helps organize large applications into multiple pages.
- It is widely used in websites such as dashboards, e-commerce sites, blogs, and job portals.

I realized that almost every React project requires routing because users need to move from one page to another smoothly.

---

#  Installing React Router

Before using routing, I installed the **react-router-dom** package.

### Installation Command

```bash
npm install react-router-dom
```

This command installs all the required files needed for routing inside a React application.

After installation, I imported the required components from the library.

---

#  Creating Routes Using createBrowserRouter

The first practical task was creating routes using `createBrowserRouter()`.

I learned that a route connects a URL path with a React component.

For example:

- `/` → Home Page
- `/rr` → Display Page

### App.jsx

```jsx
import { createBrowserRouter, RouterProvider } from "react-router-dom";
import Home from "./component/Home";
import Display1 from "./component/Display";

function App() {

  const router = createBrowserRouter([

    {
      path: "/",
      element: <Home />,
    },

    {
      path: "/rr",
      element: <Display1 />,
    },

  ]);

  return (
    <>
      <RouterProvider router={router} />
    </>
  );

}

export default App;
```

### Explanation

In this program:

- `createBrowserRouter()` creates all the routes.
- Each route contains a **path** and a **component**.
- `RouterProvider` displays the appropriate component based on the URL.

This was my first practical implementation of routing in React.

---

# Navigation Between Pages

After understanding basic routing, I learned how to move from one page to another using the **useNavigate()** hook.

Instead of manually changing the URL, React allows navigation programmatically.

The `useNavigate()` hook returns a function that can change the current route.

---

#  Practical Project – Navigation Between Home and Display Page

In this project, I created two pages:

- Home Page
- Display Page

The Home page contains a button that navigates to the Display page.

The Display page contains another button that navigates back to the Home page.

This project helped me understand real-world navigation inside React applications.

---

#  App.jsx

```jsx
import { createBrowserRouter, RouterProvider } from "react-router-dom";
import Home from "./component/Home";
import Display1 from "./component/Display";

function App() {

  const router = createBrowserRouter([

    {
      path: "/",
      element: <Home />,
    },

    {
      path: "/display",
      element: <Display1 />,
    },

  ]);

  return (
    <>
      <RouterProvider router={router} />
    </>
  );

}

export default App;
```

---

#  Home.jsx

```jsx
import { useNavigate } from "react-router-dom";

function Home() {

  const navigate = useNavigate();

  return (

    <>

      <h1>Home Page</h1>

      <button onClick={() => navigate("/display")}>
        Go to Display Page
      </button>

    </>

  );

}

export default Home;
```



---

# Display.jsx

```jsx
import { useNavigate } from "react-router-dom";

function Display() {

  const navigate = useNavigate();

  return (

    <>

      <h1>Display Page</h1>

      <button onClick={() => navigate("/")}>
        Back to Home
      </button>

    </>

  );

}

export default Display;
```



---

#  Concepts Practiced Today

During today's practical session, I revised and practiced several React concepts together:

- React Router
- Single Page Application (SPA)
- Installing external libraries using npm
- `createBrowserRouter()`
- `RouterProvider`
- Route configuration
- URL paths
- `useNavigate()` Hook
- Navigation between pages
- Component rendering based on routes

---

#  Key Learning Outcomes

- Learned the definition and purpose of React Router.
- Understood the importance of routing in React applications.
- Installed the `react-router-dom` package successfully.
- Learned how to configure routes using `createBrowserRouter()`.
- Understood the role of `RouterProvider`.
- Created multiple pages inside a React application.
- Learned to navigate between pages using the `useNavigate()` hook.
- Built a practical routing project with Home and Display pages.
- Improved my understanding of Single Page Applications (SPA) and client-side routing.

---


**Status:** ✅ Day 12 Successfully Completed
