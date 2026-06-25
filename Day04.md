# MERN Stack Training Diary – Day 04
**Date:** 25 June 2026

## 📚Topic: Conditional Statements and Loops in JavaScript

Today was the fourth day of my MERN Stack training, and the entire session was focused on understanding the decision-making and repetition capabilities of JavaScript. I learned how programs can make decisions based on different conditions and how repetitive tasks can be performed efficiently using loops.
The session began with conditional statements, which allow a program to execute different blocks of code depending on whether a condition is true or false. After that, I learned about loops, which are used to execute a block of code repeatedly until a specific condition is met.
These concepts are very important because they form the foundation of programming logic and are used in almost every real-world application.

---

##  Conditional Statements in JavaScript

Conditional statements help a program make decisions based on certain conditions. They allow different code blocks to run depending on the situation.

### 1. If Statement

The `if` statement is the simplest conditional statement. It executes a block of code only when the specified condition is true.

### Syntax


if(condition){
    // code to execute
}
```

### Example


let age = 18;

if(age >= 18){
    console.log("You are eligible to vote.");
}
```

### Explanation

In this example, the condition `age >= 18` is true, so the message is displayed. If the condition were false, nothing would be executed.

---

### 2. If-Else Statement

The `if-else` statement is used when there are two possible outcomes. If the condition is true, the `if` block executes; otherwise, the `else` block executes.

### Syntax


if(condition){
    // code if condition is true
}
else{
    // code if condition is false
}
```

### Example


let age = 16;

if(age >= 18){
    console.log("Eligible to vote");
}
else{
    console.log("Not eligible to vote");
}
```

### Explanation

Since the age is less than 18, the condition becomes false and the `else` block executes.

---

### 3. Else-If Ladder

The `else-if` ladder is used when multiple conditions need to be checked.

### Syntax


if(condition1){
    // code
}
else if(condition2){
    // code
}
else{
    // code
}
```

### Example


let marks = 75;

if(marks >= 90){
    console.log("Grade A");
}
else if(marks >= 70){
    console.log("Grade B");
}
else if(marks >= 50){
    console.log("Grade C");
}
else{
    console.log("Fail");
}
```

### Explanation

The program checks conditions one by one. As soon as a true condition is found, its corresponding block executes and the remaining conditions are skipped.

---

### 4. Nested If-Else

A nested if-else means placing one if statement inside another if statement.

### Syntax


if(condition1){
    if(condition2){
        // code
    }
}
```

### Example

let age = 20;
let hasLicense = true;

if(age >= 18){
    if(hasLicense){
        console.log("You can drive");
    }
    else{
        console.log("Get a driving license first");
    }
}
else{
    console.log("You are underage");
}


### Explanation

The second condition is checked only if the first condition is true.

---

### 5. Switch Statement

The switch statement is used when multiple cases need to be checked against a single value. It makes code cleaner and easier to read compared to multiple if-else statements.

### Syntax


switch(expression){
    case value1:
        // code
        break;

    case value2:
        // code
        break;

    default:
        // code
}
```

### Example


let day = 3;

switch(day){
    case 1:
        console.log("Monday");
        break;

    case 2:
        console.log("Tuesday");
        break;

    case 3:
        console.log("Wednesday");
        break;

    default:
        console.log("Invalid Day");
}
```



##  Discount Calculator Program

During the practical session, I created a discount calculator using the `switch` statement.

### Code


let amount = 500;
let discount = 0;

switch (true) {

    case (amount < 200):
        discount = amount * 0.20;
        break;

    case (amount < 600):
        discount = amount * 0.40;
        break;

    default:
        discount = 70;
        break;
}

console.log(discount);
```


```

Output:


200
```

This activity helped me understand how conditions can be used in real-world scenarios such as shopping and billing systems.

---

##  Loops in JavaScript

After learning conditional statements, I moved on to loops.
I learned that loops are used when we need to execute the same block of code multiple times. Instead of writing the same code repeatedly, loops allow us to automate repetitive tasks efficiently.

---

### 1. While Loop

The `while` loop executes a block of code as long as the condition remains true.

### Syntax


while(condition){
    // code
}
```

### Example


let i = 1;

while(i <= 5){
    console.log(i);
    i++;
}
```

### Output 

1
2
3
4
5
```

### Explanation

The loop continues until the condition `i <= 5` becomes false.

---

### 2. Do-While Loop

The `do-while` loop executes the code block at least once, even if the condition is false.

### Syntax


do{
    // code
}
while(condition);
```

### Example


let i = 1;

do{
    console.log(i);
    i++;
}
while(i <= 5);
```

### Output


1
2
3
4
5
```

### Explanation

The code inside the `do` block runs first, and then the condition is checked.
This is the main difference between `while` and `do-while`.

---

### 3. For Loop

The `for` loop is the most commonly used loop in JavaScript. It is used when the number of iterations is known in advance.

### Syntax


for(initialization; condition; increment/decrement){
    // code
}


### Example


for(let i = 1; i <= 5; i++){
    console.log(i);
}


### Output


1
2
3
4
5
```

### Explanation

The for loop consists of three parts:

1. Initialization – Starts the loop variable.
2. Condition – Checks whether the loop should continue.
3. Increment/Decrement – Updates the loop variable after each iteration.

Because all three parts are written in one line, the for loop is considered more compact and easier to use.

---

##  Difference Between While, Do-While, and For Loop

| While Loop | Do-While Loop | For Loop |
|------------|---------------|----------|
| Condition checked before execution | Condition checked after execution | Condition checked before execution |
| May execute zero times | Executes at least once | May execute zero times |
| Suitable when iterations are unknown | Suitable when code must run at least once | Suitable when iterations are known |

---

##  Key Learning Outcomes

- Understood the concept of decision-making in JavaScript.
- Learned and practiced `if`, `if-else`, `else-if`, nested `if`, and `switch` statements.
- Implemented a discount calculator using the switch statement.
- Learned the purpose and working of loops.
- Practiced `while`, `do-while`, and `for` loops with examples.
- Understood the differences between various looping statements.
- Improved logical thinking and problem-solving skills through programming exercises.

---


**Status:** ✅ Day 04 Successfully Completed
