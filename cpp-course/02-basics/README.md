# 02. C++ Basics

## Chapter title
**Syntax, Variables, and I/O**

## Learning goals
- Write valid C++ syntax and understand program structure
- Declare variables and use built-in data types
- Read input and print output
- Use comments effectively

## 📖 READ

### 1. What is this concept?
The basics of C++ are the building blocks: how to write statements, how to store data, and how to communicate with the user through input and output. This includes variables, data types, operators, and the structure of a simple program. Think of this as learning the alphabet and grammar of the language before writing essays.

Without these basics, nothing else in C++ makes sense. Every advanced feature—classes, templates, memory management—still depends on understanding how basic types and expressions work.

### 2. Why does this exist?
Programs must store information and manipulate it. Before programming languages existed, computers were controlled by raw machine instructions. That was extremely hard and error-prone. High-level languages like C++ exist to make programming understandable while still efficient.

C++ specifically needs strong fundamentals because it gives you direct access to low-level details. If you misunderstand basic types or operations, you can create bugs that are hard to detect. The language assumes you know what you are doing.

### 3. How it works under the hood
When you declare a variable, the compiler reserves space in memory for it. For example, `int` typically uses 4 bytes, `double` often uses 8 bytes. The compiler tracks the type so it knows how to interpret the bits in memory.

Input/output uses streams. `std::cin` reads bytes from the input buffer, converts them into the correct type, and stores them in your variables. `std::cout` converts values to text and writes them to the output buffer. At runtime, these buffers are managed by the standard library and the operating system.

### 4. Mental model
Imagine variables as labeled boxes. The type of the variable tells you what kind of item is allowed inside the box. An `int` box holds whole numbers, a `double` box holds decimal numbers, and a `std::string` box holds text. When you print a variable, you are taking the value from the box and showing it on the screen.

Input is like receiving a package from a delivery belt. `std::cin` pulls the package off the belt and places it in the right box. Output is like placing a label on a box and putting it onto an outgoing belt.

### 5. Common mistakes beginners make
- Forgetting to initialize variables before using them
- Using the wrong data type and getting unexpected results
- Assuming `std::cin` can read full sentences (it stops at spaces)
- Misusing `=` in conditions instead of `==`

### 6. When NOT to use this
You cannot avoid these basics in C++, but you can avoid overcomplicating them. For example:
- Do not use `long long` everywhere unless you need large numbers
- Do not use `double` if integer arithmetic is enough
- Do not add complex input/output code when a simple print is enough

Keep things simple until your program demands more.

### 7. How this connects to other topics
Variables and types are the foundation for everything else. Control flow depends on conditions, which depend on expressions. Functions depend on passing data types. Later, pointers and references will make these same variables more powerful, but also more dangerous.

## Theory explanation
A C++ program is built from statements and expressions. You use types to tell the compiler what a variable can store. Input and output are handled through the `<iostream>` library with `std::cin` and `std::cout`.

Key data types:
- `int`, `long long` for integers
- `double`, `float` for floating point
- `char`, `bool` for characters and boolean values

## Code examples (C++)
```cpp
#include <iostream>
#include <string>

int main() {
    int age = 20;
    double height = 1.75;
    bool is_student = true;

    std::cout << "Age: " << age << "\n";
    std::cout << "Height: " << height << "\n";
    std::cout << "Student: " << is_student << "\n";

    std::cout << "Enter your name: ";
    std::string name;
    std::cin >> name;
    std::cout << "Hello, " << name << "!\n";
    return 0;
}
```

## Common mistakes
- Forgetting semicolons
- Using `=` instead of `==` in comparisons
- Mixing `std::cout` with `printf` without flushing
- Reading strings with spaces using `std::cin` (use `std::getline`)

## Homework (easy / medium / hard)
1. (Easy) Declare 5 variables of different types and print them.
2. (Easy) Read two integers and output their sum and product.
3. (Easy) Use `std::getline` to read a full name.
4. (Medium) Convert temperatures between Celsius and Fahrenheit.
5. (Medium) Write a program that calculates the area of a circle.
6. (Medium) Print a small multiplication table (1 to 5).
7. (Hard) Read three numbers and output them sorted without using arrays.

## Mini-project (when applicable)
**"Interactive Profile"**  
Create a console program that asks for user data (name, age, city) and prints a formatted profile card.
