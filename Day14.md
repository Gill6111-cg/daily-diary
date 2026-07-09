# 🚀 MERN Stack Training Diary – Day 14
**Date:** 08 July 2026

##  Topic: Navigation Using Link in React Router DOM and Lottie React Animations

Today was the fourteenth day of my MERN Stack training. I continued working on my React project by improving the navigation system and enhancing the user interface with animations. The session started with learning how to navigate between different pages using the **Link** component from **React Router DOM**. I updated the Header component so that users can move from one page to another without refreshing the browser.
After completing the navigation part, I learned about **Lottie React**, a library used to display lightweight and attractive animations in React applications. I downloaded an animation from the **LottieFiles** website, saved it in my project, and displayed it on the Sign In page. This made the application look more interactive and professional.

---

## Navigation Using Link in React Router DOM

The session started with learning about the **Link** component provided by **React Router DOM**.
I learned that the `<Link>` component is used for navigation between different pages in a React application. Unlike the HTML `<a>` tag, which reloads the entire webpage, the Link component changes pages without refreshing the browser. This makes React applications faster and provides a smoother user experience.

### Advantages of Link

- Navigates between pages without reloading the browser.
- Improves the speed of the application.
- Provides a smooth user experience.
- Preserves the application state while navigating.
- Commonly used in Single Page Applications (SPA).

---

##  Updating the Header Component

I modified my **Header.jsx** file and added navigation links for all the pages of my website using the `Link` component.

### Header.jsx

```jsx
import { Link } from "react-router-dom";

function Header1() {
  return (
    <>
      <header>
        <div className="logo">Logo</div>

        <nav>
          <div>
            <Link to="/">Home</Link>
          </div>

          <div>
            <Link to="/product">Product</Link>
          </div>

          <div>
            <Link to="/about">About</Link>
          </div>

          <div>
            <Link to="/contact">Contact</Link>
          </div>
        </nav>

        <div className="auth">
          <div>
            <Link to="/signin">Signin</Link>
          </div>

          <div>
            <Link to="/login">Login</Link>
          </div>
        </div>
      </header>
    </>
  );
}

export default Header1;
```

After implementing this code, I was able to navigate between all the pages of my project by simply clicking the navigation links.

---

##  Introduction to Lottie React

After completing the navigation section, I learned about **Lottie React**.
I understood that Lottie React is a React library that allows developers to use beautiful animations in their web applications. Instead of using GIFs or videos, it uses lightweight JSON files, which load faster and provide smooth animations.
I also learned that many modern websites use Lottie animations to improve the user interface and make applications more engaging.

---

##  Importance of Lottie React

During today's session, I learned the following benefits of using Lottie React:

- Makes websites more attractive.
- Provides smooth and high-quality animations.
- Uses lightweight JSON files.
- Faster than GIF images.
- Easy to integrate into React projects.
- Improves the overall user experience.

---

##  Downloading an Animation

To use an animation in my project, I followed these steps:

1. Visited the **LottieFiles** website.
2. Selected a robot animation.
3. Downloaded the animation in **JSON** format.
4. Created a new folder named **animation** inside the **src** folder.
5. Saved the downloaded file as **robot.json**.
6. Imported the animation into my React component.

This helped me understand how external animation files can be used inside React applications.

---

##  Displaying Animation on the Sign In Page

After downloading the animation, I displayed it on the **Sign In** page using the `Lottie` component.

### Signin.jsx

```jsx
import Lottie from "lottie-react";
import robot from "../animation/robot.json";

function Signin() {
  return (
    <>
      <div>
        <h2>This is Sign In Page</h2>

        <Lottie
          animationData={robot}
          loop={true}
          style={{ height: 300, width: 300 }}
        />
      </div>
    </>
  );
}

export default Signin;
```

When I ran the project, the robot animation appeared on the Sign In page and played continuously. It made the page look much more attractive and interactive.

---

##  Key Learning Outcomes

- Learned how to use the **Link** component from React Router DOM.
- Understood the difference between the HTML `<a>` tag and React's `<Link>` component.
- Added navigation links to the Header component.
- Learned about the **Lottie React** library.
- Understood the importance and advantages of using animations.
- Downloaded an animation from the LottieFiles website.
- Imported a JSON animation into a React project.
- Displayed the animation on the Sign In page using the `Lottie` component.
- Improved the appearance and user experience of my React application.

---


**Status:** ✅ **Day 14 Successfully Completed**
