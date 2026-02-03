# 06. Pointers and References

## Chapter title
**Memory and Indirection**

## Learning goals
- Understand memory layout (stack vs heap)
- Declare and use pointers and references
- Perform safe pointer arithmetic
- Recognize common pointer bugs

## 📖 READ

### 1. What is this concept?
Pointers and references are ways to work with memory locations directly. A pointer stores an address. A reference is an alias for an existing object. This allows you to share data, modify it through different names, and build advanced structures like linked lists or dynamic arrays.

This is the first truly “systems-level” concept in the course. It gives you power and performance, but also responsibility. If you point to the wrong place, you can crash the program.

### 2. Why does this exist?
In early programming, data was accessed directly in memory. C brought that power into a high-level language. C++ inherited that need because:
- Performance-critical systems require direct memory access
- Dynamic data structures require references to other objects
- Functions sometimes need to modify variables without copying them

Without pointers and references, you could not build many of the core structures and systems that C++ is known for.

### 3. How it works under the hood
Memory is just a large array of bytes. A pointer is a variable that stores the address of a byte (or the first byte of an object). When you dereference a pointer (`*p`), the CPU reads or writes to that memory location.

References are usually implemented as hidden pointers by the compiler. They do not take extra syntax to use because the compiler automatically inserts the pointer dereference when needed.

Stack memory is allocated automatically when a function runs. Heap memory is allocated manually using `new` and released with `delete`. Pointers are how you access heap memory.

### 4. Mental model
Think of memory as a neighborhood of houses. Each house has an address. A pointer is like a piece of paper with a house address on it. Dereferencing the pointer means going to that house and interacting with what is inside.

A reference is like a nickname for a person. Whether you call them by their full name or nickname, you are still talking to the same person.

### 5. Common mistakes beginners make
- Dereferencing a pointer before it points to valid memory
- Forgetting to initialize a pointer
- Returning a reference to a local variable (which disappears)
- Confusing pointer value with the value it points to
- Doing pointer arithmetic without understanding bounds

### 6. When NOT to use this
- Do not use raw pointers when smart pointers or references can do the job safely
- Do not use pointers to share ownership of objects without a clear ownership model
- Do not expose raw pointers in APIs when a safer alternative exists

If you can solve the problem with `std::vector`, `std::string`, or references, avoid raw pointers.

### 7. How this connects to other topics
Pointers connect directly to memory management and RAII. Arrays decay to pointers, which is why you need this to understand C-style arrays. OOP uses references and pointers for polymorphism. Later, smart pointers and move semantics will build on this foundation.

## Theory explanation
Pointers store memory addresses. References act as aliases for existing objects. Pointers allow dynamic memory and low-level control but can cause crashes if misused. The stack stores local variables; the heap stores dynamically allocated objects.

## Code examples (C++)
```cpp
int x = 10;
int *p = &x;
int &r = x;

*p = 20;   // changes x
r = 30;    // also changes x

int arr[3] = {1, 2, 3};
int *q = arr;
std::cout << *(q + 1) << "\n"; // prints 2
```

## Common mistakes
- Dereferencing null or uninitialized pointers
- Returning references to local variables
- Pointer arithmetic outside array bounds

## Homework (easy / medium / hard)
1. (Easy) Create a pointer to an integer and modify it through the pointer.
2. (Easy) Swap two numbers using references.
3. (Easy) Print an array using pointer arithmetic.
4. (Medium) Implement a function that finds the max using pointers.
5. (Medium) Write a function that counts characters in a C-string.
6. (Medium) Explain stack vs heap in your own words.
7. (Hard) Implement a basic dynamic array using `new` and `delete`.

## Mini-project (when applicable)
**"Pointer Visualizer"**  
Create a console program that prints memory addresses of variables and shows how pointer arithmetic moves through an array.
