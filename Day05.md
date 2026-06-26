# MERN Stack Training Diary – Day 05
**Date:** 26 June 2026

##  Topic: Functions and Arrays in JavaScript

Today was the fifth day of my MERN Stack training, and the session focused on two important JavaScript concepts: **Functions** and **Arrays**. Both of these concepts are widely used in programming because they help developers write clean, organized, and efficient code.

The session started with functions, where I learned how to create reusable blocks of code for performing specific tasks. After that, I learned about arrays, which allow us to store multiple values in a single variable. Along with the theory, I practiced several examples to understand how these concepts are used in real-world programming.

---

#  Functions in JavaScript

The first topic of today's session was **Functions**.

A function is a block of code written to perform a specific task. Instead of writing the same code again and again, we can write it once inside a function and call it whenever required. This makes the code more organized, reusable, and easier to maintain.

I also learned that functions improve the readability of programs because large problems can be divided into smaller and manageable parts.

---

## Structure of a Function

A JavaScript function consists of the following parts:

- **function keyword** – Used to declare a function.
- **Function Name** – The name used to identify the function.
- **Parameters** – Variables that receive values when the function is called.
- **Function Body** – Contains the statements that perform the required task.
- **Return Statement (Optional)** – Returns a value from the function.
- **Function Call** – Executes the function.

### Syntax

```javascript
function functionName(parameter1, parameter2){
    // statements
    return value;
}

functionName(argument1, argument2);
```

---

## Parameters and Arguments

One of the important concepts I learned today was the difference between **parameters** and **arguments**.

### Parameters

Parameters are the variables written inside the function definition. They act as placeholders that receive values when the function is called.

### Example

```javascript
function greet(name){
    console.log("Hello " + name);
}
```

In this example, **name** is the **parameter**.

### Arguments

Arguments are the actual values passed to a function while calling it.

### Example

```javascript
greet("Chanchal");
```

Here, **"Chanchal"** is the **argument**.

From this, I understood that **parameters receive values**, whereas **arguments provide those values** during the function call.

---

# Types of Functions in JavaScript

During today's practical session, I learned four different types of functions.

---

## 1. Named Function

A Named Function is a function that has its own name. It can be called multiple times from anywhere in the program after its declaration.

### Syntax

```javascript
function functionName(){
    // code
}
```

### Example

```javascript
function welcome(){
    console.log("Welcome to JavaScript");
}

welcome();
```

### Explanation

The function is declared with the name **welcome()** and is executed whenever it is called.

---

## 2. Anonymous Function

An Anonymous Function is a function without a name. It is usually stored inside a variable or passed as an argument to another function.

### Syntax

```javascript
let variableName = function(){
    // code
};
```

### Example

```javascript
let greet = function(){
    console.log("Hello Everyone");
};

greet();
```

### Explanation

Although the function has no name, it is stored in the variable **greet**, which is used to call the function.

---

## 3. Arrow Function

Arrow Functions were introduced in ES6 to provide a shorter and cleaner way of writing functions. They are widely used in modern JavaScript and React applications.

### Syntax

```javascript
const functionName = () => {
    // code
};
```

### Example

```javascript
const add = (a, b) => {
    return a + b;
};

console.log(add(10, 20));
```

### Explanation

Arrow functions reduce the amount of code and improve readability, especially for small functions.

---

## 4. Nested Function

A Nested Function is a function that is defined inside another function. The inner function can access the variables of the outer function.

### Syntax

```javascript
function outerFunction(){

    function innerFunction(){
        // code
    }

    innerFunction();
}
```

### Example

```javascript
function outer(){

    function inner(){
        console.log("This is the inner function.");
    }

    inner();
}

outer();
```

### Explanation

The **inner()** function exists inside the **outer()** function and can only be accessed from within the outer function.

---

#  Arrays in JavaScript

The second major topic of today's session was **Arrays**.

I learned that an array is a special type of variable that stores multiple values in a single variable. Instead of creating many separate variables, arrays help us keep related data together.

Arrays are commonly used to store collections of data such as names, marks, product prices, cities, or any list of values.

---

## Creating an Array

### Syntax

```javascript
let arrayName = [value1, value2, value3];
```

### Example

```javascript
let fruits = ["Apple", "Mango", "Orange"];
```

In this example, all three fruit names are stored inside a single array.

---

# Basic Operations on Arrays

After creating arrays, I practiced several built-in array methods.

---

## 1. push()

The **push()** method is used to add one or more elements at the **end** of an array.

### Syntax

```javascript
arrayName.push(value);
```

### Example

```javascript
let fruits = ["Apple", "Mango"];

fruits.push("Orange");

console.log(fruits);
```

### Output

```javascript
["Apple", "Mango", "Orange"]
```

---

## 2. unshift()

The **unshift()** method adds one or more elements at the **beginning** of an array.

### Syntax

```javascript
arrayName.unshift(value);
```

### Example

```javascript
let fruits = ["Apple", "Mango"];

fruits.unshift("Banana");

console.log(fruits);
```

### Output

```javascript
["Banana", "Apple", "Mango"]
```

---

## 3. pop()

The **pop()** method removes the **last element** from an array.

### Syntax

```javascript
arrayName.pop();
```

### Example

```javascript
let fruits = ["Apple", "Mango", "Orange"];

fruits.pop();

console.log(fruits);
```

### Output

```javascript
["Apple", "Mango"]
```

---

## 4. shift()

The **shift()** method removes the **first element** from an array.

### Syntax

```javascript
arrayName.shift();
```

### Example

```javascript
let fruits = ["Apple", "Mango", "Orange"];

fruits.shift();

console.log(fruits);
```

### Output

```javascript
["Mango", "Orange"]
```

---

## 5. indexOf()

The **indexOf()** method returns the position (index) of a particular element in an array. If the element is not found, it returns **-1**.

### Syntax

```javascript
arrayName.indexOf(value);
```

### Example

```javascript
let fruits = ["Apple", "Mango", "Orange"];

console.log(fruits.indexOf("Mango"));
```

### Output

```javascript
1
```

---

## 6. includes()

The **includes()** method checks whether a particular element exists in an array.

It returns either **true** or **false**.

### Syntax

```javascript
arrayName.includes(value);
```

### Example

```javascript
let fruits = ["Apple", "Mango", "Orange"];

console.log(fruits.includes("Apple"));
```

### Output

```javascript
true
```

---

## 7. length

The **length** property returns the total number of elements present in an array.

### Syntax

```javascript
arrayName.length
```

### Example

```javascript
let fruits = ["Apple", "Mango", "Orange"];

console.log(fruits.length);
```

### Output

```javascript
3
```

---

#  Key Learning Outcomes

- Understood the concept and importance of functions in JavaScript.
- Learned the structure of a function and the difference between parameters and arguments.
- Practiced different types of functions including Named Function, Anonymous Function, Arrow Function, and Nested Function.
- Understood how functions help in writing reusable and organized code.
- Learned the concept of arrays and how they store multiple values in a single variable.
- Practiced important array methods like `push()`, `pop()`, `shift()`, `unshift()`, `indexOf()`, `includes()`, and `length`.
- Improved my understanding of writing cleaner and more efficient JavaScript programs.

---



**Status:** ✅ Day 05 Successfully Completed
