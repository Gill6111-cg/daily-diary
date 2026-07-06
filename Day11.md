#  MERN Stack Training Diary – Day 11
**Date:** 06 July 2026

#  Topic: Conditional Rendering and useState Hook in React

Today was the eleventh day of my MERN Stack training, and I learned some of the most important concepts in React. The session started with **Conditional Rendering**, where I learned different ways to display content based on certain conditions. After understanding conditional rendering, I moved on to **React Hooks**, especially the **useState Hook**, which is one of the most commonly used hooks in React.
I also created practical programs using the `useState` hook. The first program was a simple counter application, and the second program was a form that accepted user input and displayed it dynamically. These practical activities helped me understand how React manages data and updates the user interface automatically whenever the state changes.

---

#  Conditional Rendering in React

The first topic covered today was **Conditional Rendering**.

I learned that conditional rendering is the process of displaying different UI elements based on a condition. Instead of always showing the same content, React allows us to decide what should be displayed according to the application's state or user actions.
Conditional rendering is widely used in real-world applications such as:

- Login and Logout pages
- Showing loading messages
- Displaying user profiles
- Showing error or success messages
- Hiding and displaying content dynamically

---

# 1. Using if-else Statement

The **if-else** statement is used when we need to execute different blocks of code depending on a condition.

### Syntax

```jsx
if(condition){
    return <Component1 />;
}
else{
    return <Component2 />;
}
```

### Example

```jsx
function App(){

    let isLogin = true;

    if(isLogin){
        return <h1>Welcome User</h1>;
    }
    else{
        return <h1>Please Login</h1>;
    }

}
```

### Explanation

If the condition is true, React displays **Welcome User**; otherwise, it displays **Please Login**.

---

# 2. Using Ternary Operator

The **Ternary Operator** provides a shorter way to write conditional rendering.

### Syntax

```jsx
condition ? expression1 : expression2
```

### Example

```jsx
function App(){

    let isLogin = false;

    return(
        <>
            {
                isLogin ?
                <h1>Welcome User</h1>
                :
                <h1>Please Login</h1>
            }
        </>
    );

}
```

### Explanation

The ternary operator checks the condition and returns one of two expressions depending on whether the condition is true or false.

---

# 3. Using Logical AND (&&)

The **Logical AND (`&&`)** operator is used when we want to display content only if a condition is true.

### Syntax

```jsx
condition && <Component />
```

### Example

```jsx
function App(){

    let isAdmin = true;

    return(
        <>
            {isAdmin && <h2>Admin Panel</h2>}
        </>
    );

}
```

### Explanation

If the condition is true, the component is displayed. If the condition is false, nothing is rendered.

---

#  React Hooks

After completing conditional rendering, I learned about **React Hooks**.

I understood that Hooks are special functions introduced in React that allow functional components to use React features such as state and lifecycle methods without writing class components.

Some common React Hooks are:

- useState()
- useEffect()
- useContext()
- useRef()
- useReducer()

Among these, today's session focused on the **useState Hook**.

---

#  useState Hook

The **useState** hook is used to create and manage state inside a functional component.

I learned that state stores data that can change during the execution of the application. Whenever the state changes, React automatically updates the user interface.

### Syntax

```jsx
const [state, setState] = useState(initialValue);
```

Where:

- **state** → stores the current value.
- **setState** → updates the value.
- **initialValue** → initial value of the state.

---

#  Practical Program 1 – Counter Application

To understand the working of `useState`, I created a **Counter Application**.

The application contains:

- Increment Button (+)
- Decrement Button (-)
- Reset Button

Whenever a button is clicked, the counter value updates automatically.

### Code

```jsx
import { useState } from "react";

function App() {

  const [count, setCount] = useState(0);

  return (
    <>

      <h1>{count}</h1>

      <button onClick={() => setCount(count + 1)}>
        +
      </button>

      <button onClick={() => setCount(count - 1)}>
        -
      </button>

      <button onClick={() => setCount(0)}>
        Reset
      </button>

    </>
  );
}

export default App;
```



This project helped me understand how React automatically updates the UI whenever the state changes.

---

# 📝 Practical Program 2 – Form Handling using useState

The second practical activity was creating a form using the **useState** hook.

I created two input fields:

- Name
- Age

As the user types into the input fields, the entered values are displayed immediately on the webpage.

### Code

```jsx
import { useState } from "react";

function Form1(){

    const [name, setName] = useState("");
    const [age, setAge] = useState("");

    return(

        <>

            <br/>

            <input
                type="text"
                placeholder="Enter Name"
                value={name}
                onChange={(e)=>setName(e.target.value)}
            />

            <h1>{name}</h1>

            <input
                type="number"
                placeholder="Enter Age"
                value={age}
                onChange={(e)=>setAge(e.target.value)}
            />

            <h1>{age}</h1>

        </>

    );

}

export default Form1;
```

### Explanation


This activity helped me understand how React handles user input efficiently using state.

---

#  Key Learning Outcomes

- Understood the concept of Conditional Rendering in React.
- Learned three methods of conditional rendering:
  - Using `if-else`
  - Using the Ternary Operator
  - Using the Logical AND (`&&`) operator
- Learned about React Hooks and their importance.
- Understood the working of the `useState` hook.
- Learned the syntax and structure of `useState`.
- Built a Counter Application using `useState`.
- Created a Form Application to handle user input dynamically.
- Understood how React automatically updates the UI whenever the state changes.
- Improved my practical understanding of React state management.

---


**Status:**  Day 11 Successfully Completed
