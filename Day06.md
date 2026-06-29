# MERN Stack Training Diary – Day 06
**Date:** 27 June 2026

##  Topic: Advanced Array Methods, Objects, and DOM Manipulation in JavaScript

Today was the sixth day of my MERN Stack training, and it was one of the most practical sessions so far. The session mainly focused on **advanced array methods**, **objects**, and **Document Object Model (DOM)** manipulation in JavaScript.
The first half of the session was about advanced array functions, which help perform operations on arrays in a simpler and more efficient way. After that, I learned about JavaScript objects, how to create them, access their values, update existing properties, add new properties, and delete properties. Finally, I was introduced to the DOM, where I learned how JavaScript can interact with HTML elements and dynamically change their content and styling.

---

# Advanced Array Methods

I started today's session by learning some advanced methods available in JavaScript arrays. These methods make it easier to process data without writing lengthy loops. They also improve the readability and efficiency of the code.

---

## 1. map()

The **map()** method is used to create a new array by performing an operation on every element of an existing array. It does not modify the original array.

### Syntax

```javascript
array.map(function(element){
    return operation;
});
```

### Example

```javascript
let numbers = [1, 2, 3, 4];

let square = numbers.map(function(num){
    return num * num;
});

console.log(square);
```

### Output

```javascript
[1, 4, 9, 16]
```

### Explanation

The `map()` method applies the given operation to every element and returns a new array containing the updated values.

---

## 2. forEach()

The **forEach()** method is used to execute a function for every element of an array. Unlike `map()`, it does not return a new array.

### Syntax

```javascript
array.forEach(function(element){
    // code
});
```

### Example

```javascript
let fruits = ["Apple", "Mango", "Orange"];

fruits.forEach(function(item){
    console.log(item);
});
```

### Output

```javascript
Apple
Mango
Orange
```

### Explanation

The `forEach()` method is mainly used when we want to perform an action on every element without creating a new array.

---

## 3. filter()

The **filter()** method creates a new array containing only those elements that satisfy a given condition.

### Syntax

```javascript
array.filter(function(element){
    return condition;
});
```

### Example

```javascript
let numbers = [10, 20, 30, 40, 50];

let result = numbers.filter(function(num){
    return num > 25;
});

console.log(result);
```

### Output

```javascript
[30, 40, 50]
```

### Explanation

Only the elements that satisfy the condition are included in the new array.

---

## 4. find()

The **find()** method returns the first element that satisfies a specified condition.

### Syntax

```javascript
array.find(function(element){
    return condition;
});
```

### Example

```javascript
let numbers = [5, 15, 25, 35];

let value = numbers.find(function(num){
    return num > 20;
});

console.log(value);
```

### Output

```javascript
25
```

### Explanation

Unlike `filter()`, which returns all matching elements, `find()` returns only the first matching element.

---

## 5. slice()

The **slice()** method is used to create a copy of a selected portion of an array. It does not modify the original array.

### Syntax

```javascript
array.slice(startIndex, endIndex);
```

### Example

```javascript
let numbers = [10, 20, 30, 40, 50];

console.log(numbers.slice(1,4));
```

### Output

```javascript
[20, 30, 40]
```

### Explanation

The `slice()` method returns elements from the starting index up to, but not including, the ending index.

---

## 6. splice()

The **splice()** method is used to add, remove, or replace elements in an array. Unlike `slice()`, it modifies the original array.

### Syntax

```javascript
array.splice(start, deleteCount, newElement);
```

### Example

```javascript
let fruits = ["Apple", "Mango", "Orange"];

fruits.splice(1,1,"Banana");

console.log(fruits);
```

### Output

```javascript
["Apple", "Banana", "Orange"]
```

### Explanation

In this example, `"Mango"` is removed and replaced with `"Banana"`.

---

#  Objects in JavaScript

The next topic was **Objects**.

I learned that an object is a collection of related data stored in the form of **key-value pairs**. Objects are used when we want to store multiple properties of a single entity.

For example, instead of storing a student's name, age, and course in different variables, we can store them together inside one object.

---

## Creating an Object

### Syntax

```javascript
let objectName = {
    key : value,
    key : value
};
```

### Example

```javascript
let student = {
    name: "Chanchal",
    age: 21,
    course: "B.Tech CSE"
};
```

---

## Displaying Object Values

Object values can be accessed using either dot notation or bracket notation.

### Syntax

```javascript
objectName.key
```

### Example

```javascript
console.log(student.name);
console.log(student.age);
```

### Output

```javascript
Chanchal
21
```

---

## Updating an Existing Value

I learned that existing object values can be updated by assigning a new value to the key.

### Syntax

```javascript
objectName.key = newValue;
```

### Example

```javascript
student.age = 22;
```

### Explanation

The value of the `age` property changes from **21** to **22**.

---

## Adding a New Key-Value Pair

A new property can be added simply by assigning a value to a new key.

### Syntax

```javascript
objectName.newKey = value;
```

### Example

```javascript
student.city = "Ludhiana";
```

### Explanation

A new property named `city` is added to the object.

---

## Deleting a Property

The `delete` keyword removes a property from an object.

### Syntax

```javascript
delete objectName.key;
```

### Example

```javascript
delete student.age;
```

### Explanation

The `age` property is permanently removed from the object.

---

#  Array of Objects

I also learned about **Array of Objects**, where multiple objects are stored inside a single array.

### Example

```javascript
let students = [

{
    name:"Chanchal",
    age:21
},

{
    name:"Ashish",
    age:22
}

];
```

### Explanation

Each object represents one student's information, while the array stores multiple student records together. This concept is widely used in real-world applications like employee management systems, e-commerce websites, and student databases.

---

# Document Object Model (DOM)

The final topic of today's session was the **Document Object Model (DOM)**.

I learned that the DOM is a programming interface that represents an HTML document as a tree structure. JavaScript uses the DOM to access, modify, and update HTML elements dynamically without reloading the webpage.

This makes webpages interactive and allows developers to change content, styles, and behavior based on user actions.

---

# Selecting HTML Elements

I practiced different methods of selecting HTML elements using JavaScript.

---

## 1. getElementById()

Selects an element using its unique id.

### Syntax

```javascript
document.getElementById("idName");
```

### Example

```javascript
let heading = document.getElementById("heading");
```

---

## 2. getElementsByClassName()

Selects all elements having the same class name.

### Syntax

```javascript
document.getElementsByClassName("className");
```

---

## 3. getElementsByTagName()

Selects all elements with a particular HTML tag.

### Syntax

```javascript
document.getElementsByTagName("p");
```

---

## 4. querySelector()

Selects the first element matching a CSS selector.

### Syntax

```javascript
document.querySelector("selector");
```

### Example

```javascript
document.querySelector("#heading");
```

---

## 5. querySelectorAll()

Selects all elements matching a CSS selector.

### Syntax

```javascript
document.querySelectorAll(".box");
```

---

# Changing HTML Element Properties

After selecting HTML elements, I learned how JavaScript can modify their appearance and content.

### Changing Text Color

```javascript
element.style.color = "red";
```

Changes the text color of the selected element.

---

### Changing Background Color

```javascript
element.style.backgroundColor = "yellow";
```

Changes the background color of the selected element.

---

### Changing Border Radius

```javascript
element.style.borderRadius = "10px";
```

Creates rounded corners around the element.

---

### Changing Padding

```javascript
element.style.padding = "20px";
```

Adds spacing inside the element.

---

### Changing Text

```javascript
element.innerText = "Welcome to JavaScript";
```

Changes the text displayed inside the selected HTML element.

---

# Key Learning Outcomes

- Learned advanced array methods such as `map()`, `forEach()`, `filter()`, `find()`, `slice()`, and `splice()`.
- Understood the purpose and practical use of each array method.
- Learned how to create and use JavaScript objects.
- Practiced displaying, updating, adding, and deleting object properties.
- Understood the concept of arrays of objects and their real-world applications.
- Learned the basics of the Document Object Model (DOM).
- Practiced selecting HTML elements using different DOM methods.
- Learned how to change HTML element properties such as text color, background color, border radius, padding, and inner text using JavaScript.

---



**Status:** Day 06 Successfully Completed
