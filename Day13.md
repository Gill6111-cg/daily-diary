#  MERN Stack Training Diary – Day 13
**Date:** 08 July 2026

#  Topic: Building a Multi-Page React Website using React Router, Layout Components, and Outlet

Today was the thirteenth day of my MERN Stack training. In today's session, I applied all the React concepts that I had learned over the previous few days to build the frontend of a simple multi-page website. The main focus of today's class was understanding how to organize a React project using **components**, **React Router**, and **nested routing**.
I learned how to create multiple pages in a React application and connect them using React Router. Instead of displaying only one component, I created different pages such as **Home**, **Product**, **About**, and **Contact**. I also learned how to use the **children** property inside `createBrowserRouter()` to create nested routes and how the **Outlet** component displays child pages inside a common layout.
By the end of the session, I had successfully created a simple website with a reusable Header and Footer component, which gave me a better understanding of how real React applications are structured.

---

#  Creating Multiple Pages using React Router

The session started with creating multiple pages inside a React application.

I created the following pages:

- Home
- Product
- About
- Contact

Instead of placing all the content inside a single component, I created separate files for each page. This makes the application more organized and easier to maintain.

---

#  Configuring Routes using createBrowserRouter()

I learned how to configure routing using `createBrowserRouter()`.

Instead of creating individual routes separately, I used the **children** array to define nested routes under a common layout.

### App.jsx

```jsx
import { createBrowserRouter, RouterProvider } from "react-router-dom";
import Layout1 from "./component/Layout";
import Home from "./Pages/Home";
import Product from "./Pages/Product";
import Content from "./Pages/Content";
import About from "./Pages/About";

function App() {

  const route = createBrowserRouter([

    {
      path: "/",
      element: <Layout1 />,

      children: [

        {
          path: "/",
          element: <Home />
        },

        {
          path: "/product",
          element: <Product />
        },

        {
          path: "/contact",
          element: <Content />
        },

        {
          path: "/about",
          element: <About />
        }

      ]
    }

  ]);

  return (
    <>
      <RouterProvider router={route} />
    </>
  );
}

export default App;
```


---

#  Creating Individual Pages

I created separate components for each page.

### Home.jsx

```jsx
function Home(){

    return(

        <>
            <h1>In Home Page</h1>
        </>

    );

}

export default Home;
```

---

### About.jsx

```jsx
function About(){

    return(

        <>
            <h1>In About Page</h1>
        </>

    );

}

export default About;
```

---

### Contact.jsx

```jsx
function Content(){

    return(

        <>
            <h1>In Contact Page</h1>
        </>

    );

}

export default Content;
```

---

### Product.jsx

```jsx
function Product(){

    return(

        <>
            <h1>In Product Page</h1>
        </>

    );

}

export default Product;
```

Creating separate files for each page made the project cleaner and easier to understand.

---

#  Creating a Common Layout Component

After creating the pages, I learned how to create a **Layout Component**.

The layout contains the Header, Footer, and the Outlet component.

### Layout.jsx

```jsx
import Header1 from "./Header";
import Footer1 from "./Footer";
import { Outlet } from "react-router-dom";

function Layout1(){

    return(

        <>

            <Header1 />

            <h1>Hii Everyone</h1>

            <Outlet />

            <Footer1 />

        </>

    );

}

export default Layout1;
```

---

#  Understanding Outlet in React Router

One of the most important concepts I learned today was **Outlet**.

I learned that the `<Outlet />` component acts as a placeholder where child routes are displayed.

For example:

- The Header remains the same.
- The Footer remains the same.
- Only the page between them changes.

Without the Outlet component, nested routing would not work properly.

This concept is very useful because it prevents repeating the Header and Footer code on every page.

---

# Creating the Header Component

I created a reusable Header component for the website.

### Header.jsx

```jsx
function Header1(){

    return(

        <>

            <header>

                <div className="logo">
                    Logo
                </div>

                <nav>

                    <div>Home</div>
                    <div>Product</div>
                    <div>About</div>
                    <div>Contact</div>

                </nav>

                <div className="auth">

                    <div>Signin</div>
                    <div>Signup</div>

                </div>

            </header>

        </>

    );

}

export default Header1;
```

I understood that creating separate components improves code reusability and keeps the project well organized.

---

#  Creating the Footer Component

I also created a Footer component containing the shop information.

### Footer.jsx

```jsx
function Footer1(){

    return(

        <>

            <footer className="footer">

                <h2>MyShop</h2>

                <p>Your one-stop destination for quality products.</p>

                <div className="contact">

                    <p>Ludhiana, Punjab</p>
                    <p>+91 98765 43210</p>
                    <p>myshop@gmail.com</p>

                </div>

                <hr />

                <p className="copyright">

                    © 2026 MyShop. All Rights Reserved.

                </p>

            </footer>

        </>

    );

}

export default Footer1;
```

---

#  Styling the Website using CSS

Finally, I added CSS styling to improve the appearance of the website.

### index.css

```css
*{
  margin:0;
  padding:0;
  box-sizing:border-box;
}

header{
  display:flex;
  justify-content:space-around;
  align-items:center;
  padding:1.2rem 0rem;
}

header,
nav,
.auth{
  display:flex;
  gap:2rem;
  align-items:center;
}

.footer{
  background:#333;
  color:white;
  text-align:center;
  padding:30px 20px;
  margin-top:40px;
}

.footer h2{
  color:orange;
}

.contact{
  margin:20px 0;
}

.footer hr{
  width:80%;
  margin:20px auto;
}

.copyright{
  color:#ccc;
}
```

This styling made the Header and Footer look cleaner and gave the website a more professional appearance.

---

#  Key Learning Outcomes

- Built a multi-page React application.
- Learned how to organize a React project using components.
- Understood nested routing using the **children** property.
- Configured routing using `createBrowserRouter()`.
- Learned the importance of reusable components.
- Created separate pages for Home, Product, About, and Contact.
- Understood the purpose and working of the `<Outlet />` component.
- Built reusable Header and Footer components.
- Applied CSS styling to improve the user interface.
- Improved my understanding of React project structure and routing.

---


**Status:**  Day 13 Successfully Completed
