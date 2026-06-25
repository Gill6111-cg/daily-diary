# MERN Stack Training Diary – Day 04
**Date:** 25 June 2026

## Topic: Conditional Statements and Loops in JavaScript

Today was the fourth day of my MERN Stack training. The session mainly focused on understanding how JavaScript makes decisions and performs repetitive tasks. These concepts are very important because they form the foundation of programming logic and are used in almost every application and website.

At the beginning of the session, I learned about conditional statements, which help a program make decisions based on different situations. After that, I learned about loops, which are used to execute the same block of code multiple times without writing it repeatedly. Through theory and coding practice, I understood how these concepts help developers write efficient and logical programs.

---

## Conditional Statements in JavaScript

Conditional statements allow a program to execute different blocks of code depending on whether a condition is true or false. They are used whenever a program needs to make decisions.

### 1. If Statement

The `if` statement is the simplest conditional statement. It checks whether a condition is true. If the condition is true, the code inside the `if` block executes. If the condition is false, the code is skipped.

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

In this example, the condition `age >= 18` is true, so the message is displayed on the console. If the age were less than 18, nothing would be printed because there is no alternative block provided.

---

### 2. If-Else Statement

The `if-else` statement is used when there are two possible outcomes. If the condition is true, one block of code executes; otherwise, another block executes.

### Syntax


if(condition){
    // code if condition is true
}
else{
    // code if condition is false
}
```

### Example

`
let age = 16;

if(age >= 18){
    console.log("Eligible to vote");
}
else{
    console.log("Not eligible to vote");
}
```

### Explanation

Since the value of age is 16, the condition becomes false. Therefore, the code inside the `else` block executes and displays "Not eligible to vote".

---

### 3. Else-If Ladder

The `else-if` ladder is used when multiple conditions need to be checked. The program checks each condition one by one until it finds a true condition.

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

The program first checks whether marks are greater than or equal to 90. Since the condition is false, it checks the next condition. The condition `marks >= 70` is true, so Grade B is displayed and the remaining conditions are skipped.

---

### 4. Nested If-Else

A nested if-else means placing one `if` statement inside another `if` statement. This is useful when a second condition needs to be checked only after the first condition becomes true.

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
```

### Explanation

In this example, the first condition checks whether the person is 18 years old or above. If that condition is true, the program checks whether the person has a driving license. Since both conditions are true, the message "You can drive" is displayed.

---

### 5. Switch Statement

The switch statement is used when multiple conditions need to be checked against a single value. It makes the code cleaner and easier to read compared to writing many `if-else` statements.

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

### Explanation

The value of `day` is 3, so the third case executes and displays "Wednesday". The `break` statement stops the execution after the matching case is found.

---



## Loops in JavaScript

After learning conditional statements, I moved on to loops.

I learned that loops are used when we need to execute the same block of code repeatedly. Instead of writing the same code many times, loops allow us to perform repetitive tasks efficiently and reduce the amount of code.

---

### 1. While Loop

The `while` loop executes a block of code as long as the specified condition remains true.

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

The loop starts with the value of `i` equal to 1. After each iteration, the value of `i` increases by one. The loop continues until the condition `i <= 5` becomes false.

---

### 2. Do-While Loop

The `do-while` loop is similar to the while loop, but it guarantees that the code block will execute at least once.

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

In a do-while loop, the code executes first and the condition is checked afterward. This means the loop will run at least one time even if the condition is false.

---

### 3. For Loop

The `for` loop is the most commonly used loop in programming. It is generally used when the number of iterations is known beforehand.

### Syntax


for(initialization; condition; increment/decrement){
    // code
}
```

### Example


for(let i = 1; i <= 5; i++){
    console.log(i);
}
```
## Output
1
2
3
4
5
```

**Status:** Day 04 Successfully Completed
