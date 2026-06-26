# MERN Stack Training Diary – Day 05
**Date:** 26 June 2026

##  Topic: Functions and Arrays in JavaScript

Today was the fifth day of my MERN Stack training, and the session focused on two important JavaScript concepts: **Functions** and **Arrays**. These are fundamental building blocks of JavaScript and are used in almost every program and web application.
The session began with functions, where I learned how to write reusable blocks of code that perform specific tasks. After understanding different types of functions, I moved on to arrays, which are used to store multiple values in a single variable. Along with theory, I practiced several examples to understand how functions and arrays work in real-world programming.

---

##  Functions in JavaScript

I started the session by learning about functions. A function is a block of code that is designed to perform a particular task. Instead of writing the same code repeatedly, a function allows us to write the code once and use it whenever required. This makes programs shorter, more organized, and easier to maintain.
I also learned that functions improve code reusability and readability, making them one of the most important concepts in programming.

---

##  Structure of a Function

A JavaScript function consists of the following parts:

- **Function Keyword (`function`)** – Used to declare a function.
- **Function Name** – The name given to the function.
- **Parameters** – Variables that receive values when the function is called.
- **Function Body** – Contains the statements that perform the required task.
- **Return Statement (Optional)** – Returns a value from the function.
- **Function Call** – Executes the function.

### Syntax


function functionName(parameter1, parameter2){
    // code
    return value;
}

functionName(argument1, argument2);
```

---

## 🔹 Parameters and Arguments

One of the important concepts I learned today was the difference between **parameters** and **arguments**.

### Parameters

Parameters are the variables written inside the function definition. They act as placeholders that receive values when the function is called.

### Example


function greet(name){
    console.log("Hello " + name);
}
```

Here, `name` is the **parameter**.

---

### Arguments

Arguments are the actual values passed to the function when it is called.

### Example


greet("Chanchal");
```

Here, `"Chanchal"` is the **argument**.

I understood that parameters receive values, while arguments provide those values during the function call.

---

# Types of Functions in JavaScript

## 1. Named Function

A named function is a function that has its own name. It can be called multiple times from anywhere in the program after its declaration.

### Syntax


function functionName(){
    // code
}
```

### Example


function welcome(){
    console.log("Welcome to JavaScript");
}

welcome();
```

### Explanation

The function `welcome()` is declared with a name and is called using that name whenever needed.

---

## 2. Anonymous Function

An anonymous function is a function that does not have a name. It is generally assigned to a variable or used as an argument to another function.

### Syntax


let variableName = function(){
    // code
};
```

### Example


let greet = function(){
    console.log("Hello Everyone");
};

greet();
```

### Explanation

The function has no name, but it is stored inside the variable `greet`, which is used to execute it.

---

## 3. Arrow Function

Arrow functions provide a shorter and cleaner syntax for writing functions. They were introduced in modern JavaScript (ES6).

### Syntax


const functionName = () => {
    // code
};
```

### Example


const add = (a, b) => {
    return a + b;
};

console.log(add(10, 20));
```

### Explanation

Arrow functions reduce the amount of code and are widely used in modern JavaScript applications, especially in React.

---

## 4. Nested Function

A nested function is a function defined inside another function. The inner function can access the variables of the outer function.

### Syntax


function outerFunction(){

    function innerFunction(){
        // code
    }

    innerFunction();
}
```

### Example


function outer(){

    function inner(){
        console.log("This is the inner function.");
    }

    inner();
}

outer();
```

### Explanation

The `inner()` function exists inside the `outer()` function and can only be accessed from within the outer function.

---

# 📦 Arrays in JavaScript

After learning functions, I moved on to arrays.

I learned that an array is a special type of variable used to store multiple values in a single variable. Instead of creating separate variables for each value, arrays allow us to keep related data together.

Arrays are useful for storing collections of data such as student names, marks, product prices, or city names.

---

## Creating an Array

### Syntax

let arrayName = [value1, value2, value3];
```

### Example


let fruits = ["Apple", "Mango", "Orange"];
```

Here, all three fruit names are stored inside a single array.

---

# Basic Operations on Arrays

## 1. push()

The `push()` method is used to add one or more elements at the **end** of an array.

### Syntax

arrayName.push(value);
```

### Example


let fruits = ["Apple", "Mango"];

fruits.push("Orange");

console.log(fruits);
```

### Output


["Apple", "Mango", "Orange"]
```

---

## 2. unshift()

The `unshift()` method adds one or more elements at the **beginning** of an array.

### Syntax


arrayName.unshift(value);
```

### Example


let fruits = ["Apple", "Mango"];

fruits.unshift("Banana");

console.log(fruits);
```

### Output


["Banana", "Apple", "Mango"]
```

---

## 3. pop()

The `pop()` method removes the **last element** from an array.

### Syntax


arrayName.pop();
```

### Example


let fruits = ["Apple", "Mango", "Orange"];

fruits.pop();

console.log(fruits);
```

### Output


["Apple", "Mango"]
```

---

## 4. shift()

The `shift()` method removes the **first element** from an array.

### Syntax


arrayName.shift();
```

### Example


let fruits = ["Apple", "Mango", "Orange"];

fruits.shift();

console.log(fruits);
```

### Output


["Mango", "Orange"]
```

---

## 5. indexOf()

The `indexOf()` method returns the index (position) of a specified element in an array.

If the element is not found, it returns **-1**.

### Syntax


arrayName.indexOf(value);
```

### Example


let fruits = ["Apple", "Mango", "Orange"];

console.log(fruits.indexOf("Mango"));
```

### Output


1
```

---

## 6. includes()

The `includes()` method checks whether an element exists in an array.

It returns either `true` or `false`.

### Syntax


arrayName.includes(value);
```

### Example


let fruits = ["Apple", "Mango", "Orange"];

console.log(fruits.includes("Apple"));
```

### Output


true
```

---

## 7. length

The `length` property returns the total number of elements present in an array.

### Syntax


arrayName.length
```

### Example


let fruits = ["Apple", "Mango", "Orange"];

console.log(fruits.length);
```

### Output


3
```

---

## 🎯 Key Learning Outcomes

- Understood the concept and importance of functions in JavaScript.
- Learned the structure of a function and the difference between parameters and arguments.
- Practiced different types of functions, including Named Function, Anonymous Function, Arrow Function, and Nested Function.
- Understood how functions improve code reusability and organization.
- Learned the definition and purpose of arrays.
- Practiced creating arrays and performing basic operations such as `push()`, `pop()`, `shift()`, `unshift()`, `indexOf()`, `includes()`, and `length`.
- Gained confidence in writing reusable code and managing collections of data efficiently.

---



**Status:** ✅ Day 05 Successfully Completed
