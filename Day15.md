#  MERN Stack Training Diary – Day 15
**Date:** 09 July 2026

##  Topic: Handling Forms in React Using useState and Event Handling

Today was the fifteenth day of my MERN Stack training. The entire session focused on handling forms in React using the **useState Hook**. I learned how to fetch data entered by users in Sign In and Login forms and manage it efficiently using React state.
The trainer explained that forms are one of the most important parts of web applications because they are used for user registration, login, feedback, searching, and many other purposes. Instead of accessing HTML elements directly like in JavaScript DOM manipulation, React uses **controlled components**, where the input fields are connected to the component's state using the `useState` Hook.
Along with form handling, I also learned about **event handling** in React, the **event object (`e`)**, the **preventDefault()** function, and how to clear input fields after submitting the form. I practiced these concepts by building a simple Sign In form.

---

#  Handling Forms Using useState

I learned that React forms are handled differently from traditional HTML forms.
Instead of directly reading values from the input fields, React stores all input values inside the component's state. Every time the user types something, the state is updated automatically using the `onChange` event.
This approach is called a **Controlled Component** because React completely controls the values of the form fields.

### Advantages of Controlled Forms

- Keeps form data synchronized with React state.
- Makes validation easier.
- Allows real-time updates.
- Makes forms easier to manage.
- Provides better control over user input.

---

#  Using an Object in useState

One important concept I learned today was why we store form data inside an **object** instead of creating multiple state variables.
Since the Sign In form contains multiple input fields such as **email** and **password**, storing them inside a single object makes the code cleaner and easier to manage.

### Example

```jsx
const [formData, setForm] = useState({
  email: "",
  password: "",
});
```

Here,

- `email` stores the email entered by the user.
- `password` stores the password entered by the user.

Using an object allows multiple form fields to be managed using a single state variable.

---

#  Event Handling in React

I learned that React uses **events** to respond to user actions such as clicking buttons, typing in input fields, or submitting forms.

Some common events are:

- `onClick`
- `onChange`
- `onSubmit`
- `onFocus`
- `onBlur`

In today's practical, I mainly worked with **onChange** and **onSubmit** events.

---

#  Understanding the Event Object (`e`)

The trainer explained the **event object (`e`)**, which is automatically passed to an event handler whenever an event occurs.

The event object contains useful information about the event, such as:

- Which element triggered the event.
- The current value of the input field.
- The type of event.
- Other related information.

Example:

```jsx
function handleChange(e) {
    console.log(e.target.value);
}
```

Here,

- `e` represents the event object.
- `e.target` refers to the HTML element that triggered the event.
- `e.target.value` returns the value entered by the user.

---

#  Updating Form Data Using onChange

I learned how to update the state whenever the user types something into an input field.

For this, I used:

```jsx
function handelchange(e) {
  setForm({
    ...formData,
    [e.target.name]: e.target.value,
  });
}
```

### Explanation

- `...formData` copies all existing values.
- `[e.target.name]` identifies which input field is being updated.
- `e.target.value` stores the latest value entered by the user.

This allows a single function to update multiple input fields.

---

#  preventDefault() Function

I also learned about the **preventDefault()** function.

Normally, when a form is submitted, the browser automatically reloads the page. This causes all entered data to disappear.

To stop this default behavior, React uses:

```jsx
e.preventDefault();
```

### Importance of preventDefault()

- Prevents page refresh.
- Keeps data available for processing.
- Allows JavaScript to handle form submission.
- Commonly used in React forms.

---

#  Form Submission

After filling the form, I learned how to submit the data using the `onSubmit` event.
During submission, the entered data is displayed in the browser console.

Example:

```jsx
console.log(formData);
```

This helped me verify that the form values were being stored correctly in the React state.

---

#  Clearing Input Fields

After submitting the form, I learned how to clear all the input fields.

This is done by resetting the state object.

```jsx
setForm({
    email: "",
    password: "",
});
```

As soon as the form is submitted, both input fields become empty, making the form ready for new input.

---

#  Practical Program – Sign In Form

To understand all these concepts, I created a Sign In form using React.

### Signin.jsx

```jsx
import { useState } from "react";

function Signin() {

  const [formData, setForm] = useState({
    email: "",
    password: "",
  });

  function handelchange(e) {
    setForm({
      ...formData,
      [e.target.name]: e.target.value,
    });
  }

  function handleSubmit(e) {
    e.preventDefault();

    console.log(formData);

    setForm({
      email: "",
      password: "",
    });
  }

  return (
    <>
      <div>
        <form className="signin" onSubmit={handleSubmit}>

          <div>
            <label>Email</label>
            <br />

            <input
              type="email"
              placeholder="Enter email"
              name="email"
              value={formData.email}
              onChange={handelchange}
            />

            <br />
          </div>

          <div>
            <label>Password</label>
            <br />

            <input
              type="password"
              placeholder="Enter password"
              name="password"
              value={formData.password}
              onChange={handelchange}
            />

            <br />
          </div>

          <button type="submit">Submit</button>

        </form>
      </div>
    </>
  );
}

export default Signin;
```

---

#  Key Learning Outcomes

- Learned how to handle forms in React using the `useState` Hook.
- Understood the concept of controlled components.
- Learned why form data is stored inside an object.
- Practiced updating multiple input fields using a single function.
- Understood the importance of the event object (`e`).
- Learned how `e.target.name` and `e.target.value` work.
- Learned the purpose of the `preventDefault()` function.
- Displayed submitted form data in the browser console.
- Cleared input fields after successful form submission.
- Improved my understanding of React form handling and event management.

---


**Status:**  **Day 15 Successfully Completed**
