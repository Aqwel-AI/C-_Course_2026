# 04. Functions

## Chapter title
**Reusable Logic**

## Learning goals
- Declare and define functions
- Pass parameters by value and by reference
- Use return values correctly
- Understand inline functions and recursion

## 📖 READ

### 1. What is this concept?
A function is a named block of code that performs a specific task. It takes inputs, does work, and may return an output. Functions are the building blocks of larger programs because they let you break a big problem into smaller, manageable pieces.

In C++, functions are not just a convenience—they are essential for organizing logic, reusing code, and keeping programs understandable. Without functions, you end up with one massive `main()` full of repeated code.

### 2. Why does this exist?
Before structured programming, code was often a long sequence of instructions with jumps. It was difficult to maintain, modify, or reuse. Functions solve these problems by:
- Encapsulating behavior
- Allowing reuse across different parts of a program
- Giving names to behavior, making code easier to read

C++ needs functions to scale. C++ projects can be millions of lines long. Functions allow teams to divide work and build libraries that can be reused across projects.

### 3. How it works under the hood
When you call a function, the program:
1. Pushes arguments onto the stack
2. Jumps to the function’s code location
3. Creates a new stack frame for local variables
4. Executes the body
5. Returns to the caller with a return value (if any)

The compiler decides how to pass parameters (often in registers or on the stack) and where to store return values. This is why recursion uses memory: each call creates a new stack frame.

### 4. Mental model
Think of a function like a machine in a factory. You feed raw materials (parameters) into the machine, it processes them, and it outputs a product (return value). You can run the machine many times without rewriting how it works.

Another analogy: functions are like recipes. If you need to bake a cake multiple times, you don’t rewrite the steps—you just follow the same recipe again.

### 5. Common mistakes beginners make
- Forgetting to return a value from a non-void function
- Passing large objects by value and causing unnecessary copies
- Recursion without a base case, leading to stack overflow
- Writing functions that do too many things at once

### 6. When NOT to use this
- Do not create tiny one-line functions if they reduce readability
- Do not overuse recursion for problems that are simpler with loops
- Do not design functions with too many parameters (use structs or classes instead)

Functions are powerful, but too many small or overly complex functions can make code harder to follow.

### 7. How this connects to other topics
Functions connect directly to control flow, because they contain loops and conditions. They also connect to memory and stack behavior, which becomes crucial in recursion and later topics like pointers and references. Templates will extend functions to handle multiple types, and OOP will add member functions to classes.

## Theory explanation
Functions help you organize code into reusable blocks. A declaration tells the compiler about a function’s signature; a definition provides the body. Parameters can be passed by value (copy) or reference (no copy). Recursion is a function calling itself, useful for divide-and-conquer problems.

## Code examples (C++)
```cpp
int add(int a, int b) {
    return a + b;
}

int factorial(int n) {
    if (n <= 1) return 1;
    return n * factorial(n - 1);
}

void swapValues(int &x, int &y) {
    int tmp = x;
    x = y;
    y = tmp;
}
```

## Common mistakes
- Forgetting to return a value in non-void functions
- Passing large objects by value unintentionally
- Recursion without a base case

## Homework (easy / medium / hard)
1. (Easy) Write a function that returns the square of a number.
2. (Easy) Write a function that checks if a number is even.
3. (Easy) Use a function to compute the sum of 1..N.
4. (Medium) Implement recursive Fibonacci (and note performance).
5. (Medium) Write a function that reverses digits of an integer.
6. (Medium) Create a `maxOfThree` function.
7. (Hard) Implement power function using fast exponentiation recursion.

## Mini-project (when applicable)
**"Math Toolkit"**  
Create a small library of 5-8 math functions and a console menu to use them.
