#  MERN Stack Training Diary – Day 10
**Date:** 03 July 2026

#  Topic: React Components, Tailwind CSS, Portfolio Development, and Props

Today was the tenth day of my MERN Stack training, and it was one of the most interesting sessions because I learned more advanced concepts of **React**. I started by understanding React components in greater detail and learned why components are considered the building blocks of React applications. After that, I installed **Tailwind CSS** in my React project and explored how it helps developers create modern and responsive user interfaces using utility classes.

To strengthen my understanding, I built my own **Personal Portfolio** in React. While developing the project, I divided the application into reusable components by creating separate files for the navigation bar and footer. Finally, I learned about **Props (Properties)**, which allow data to be passed from one component to another. Overall, today's session helped me understand how React applications are structured and organized in real-world development.

---

#  Understanding React Components

The session began with a detailed discussion about **React Components**.

I learned that a component is an independent and reusable piece of code that represents a specific part of the user interface. Instead of writing all the code in a single file, React allows developers to divide the application into smaller components. These components can be reused multiple times, making the code cleaner, easier to manage, and more maintainable.

I also understood the advantages of using components:

- Code becomes reusable.
- Applications become easier to maintain.
- Development becomes faster.
- Large projects can be divided into smaller modules.
- Different developers can work on different components simultaneously.

This concept helped me understand why React is widely used for developing large-scale web applications.

---

#  Introduction to Tailwind CSS

After learning about components, I installed **Tailwind CSS** in my React project.

I learned that Tailwind CSS is a utility-first CSS framework that provides predefined classes for styling HTML elements. Instead of writing separate CSS files for every project, developers can directly use Tailwind utility classes inside HTML or JSX elements.

Some benefits of Tailwind CSS that I learned are:

- Faster UI development.
- Responsive design becomes easier.
- Less custom CSS is required.
- Easy to maintain consistent styling.
- Highly customizable.

Although I only explored the basics of Tailwind today, I understood how useful it is for designing modern user interfaces quickly.

---

#  Personal Portfolio Project in React

After understanding components and installing Tailwind CSS, I built my own **Personal Portfolio** using React.

In this project, I displayed my personal information, educational details, hobbies, career goal, and contact information. I also imported my profile image from the **assets** folder and displayed it inside the application.

While building the project, I revised several React concepts that I had learned over the previous days, such as:

- JSX syntax
- Importing images
- Inline styling
- Rendering HTML elements
- Tables
- Lists
- Components

Working on this project helped me understand how React combines JavaScript and HTML to create dynamic user interfaces.

---

#  Creating Reusable Components

One of the most important concepts I practiced today was creating **reusable components**.

Instead of writing all the code inside `App.jsx`, I separated different sections of the application into individual components.

For example, I created:

- `Nav2` component for the Navigation Bar.
- `Footer1` component for the Contact Section.

I then imported these components into `App.jsx` using the `import` statement.

### Footer Component

```jsx
function Footer1(){

    return(

        <>
            <h2>Contact</h2>

            <p>
                Email: chanchal@gmail.com
                <br />
                Phone: +91-9876543210
            </p>

        </>

    );

}

export default Footer1;
```

I imported this component into `App.jsx` using:

```jsx
import Footer1 from "./component/footer";
```

and rendered it by writing:

```jsx
<Footer1 />
```

This practical activity helped me understand the real power of reusable components in React. Instead of repeating the same code multiple times, I could simply create one component and use it wherever needed.

---

#  Portfolio Application (App.jsx)

The main application displayed my complete portfolio using JSX.

---

#  App.jsx Code

The following is the main React component that I created for my personal portfolio project.

```jsx
import her from "./assets/im.png";
import Footer1 from "./component/footer";
import Nav2 from "./component/Navi";

function App() {
  return (
    <div style={{ textAlign: "center", fontFamily: "Arial" }}>
      <h1>My Personal Portfolio</h1>

      <Nav2 />

      <img
        src={her}
        alt="Profile"
        height="150px"
        width="150px"
        style={{ borderRadius: "50%" }}
      />

      <h2>About Me</h2>

      <p className="p4">
        Hello Everyone! My name is <b>Chanchal Gill</b>.
        <br />
        I am pursuing <b>B.Tech in Computer Science and Engineering</b>
        <br />
        from <b>Guru Nanak Dev Engineering College</b>.
        <br />
        I am passionate about technology and enjoy learning new things in
        programming and web development.
      </p>

      <h2>My Hobbies</h2>

      <ul
        style={{
          display: "inline-block",
          textAlign: "left",
        }}
      >
        <li>Coding</li>
        <li>Playing Cricket</li>
        <li>Learning New Technologies</li>
      </ul>

      <h2>Educational Details</h2>

      <table
        border="1"
        style={{
          margin: "auto",
          borderCollapse: "collapse",
          padding: "10px",
        }}
      >
        <thead>
          <tr>
            <th>Name</th>
            <th>Course</th>
            <th>College</th>
          </tr>
        </thead>

        <tbody>
          <tr>
            <td>Chanchal Gill</td>
            <td>B.Tech CSE</td>
            <td>Guru Nanak Dev Engineering College</td>
          </tr>
        </tbody>
      </table>

      <h2>My Goal</h2>

      <p>
        My goal is to become a successful Full Stack Developer and create
        useful and innovative web applications using modern technologies.
      </p>

      <Footer1 />
    </div>
  );
}

export default App;
```

---



This practical implementation helped me understand how React components can be separated into different files and reused whenever required. It also made my code cleaner, easier to read, and easier to maintain.

---

#  Introduction to Props in React

The final topic of today's session was **Props (Properties)**.

I learned that Props are used to pass data from one component to another. They make components more flexible and reusable because the same component can display different information depending on the values passed to it.

I understood that:

- Props are passed from the parent component to the child component.
- Props are read-only.
- They help make components dynamic.
- Different values can be displayed without changing the component code.

### Syntax

```jsx
function Student(props){

    return(

        <h2>{props.name}</h2>

    );

}
```

Passing data:

```jsx
<Student name="Chanchal" />
<Student name="Ashish" />
<Student name="Rahul" />
```

Output:

```
Chanchal

Ashish

Rahul
```

This example helped me understand how a single component can display different data using props.

---

#  Key Learning Outcomes

- Learned React components in greater detail.
- Understood the advantages of component-based architecture.
- Installed and configured Tailwind CSS in a React project.
- Gained basic knowledge of Tailwind utility classes.
- Built a personal portfolio using React.
- Imported and displayed images from the assets folder.
- Created reusable components for the navigation bar and footer.
- Learned how to use `export` and `import` for component reuse.
- Understood the concept of Props and how data is passed between components.
- Improved my confidence in developing React applications.

---


**Status:**  Day 10 Successfully Completed
