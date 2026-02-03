# 00. Introduction

## Chapter title
**What Is C++ and Why It Matters**

## Learning goals
- Understand what C++ is and where it is used
- Compare C++ with C and other languages at a high level
- Learn the compile-link-run pipeline
- Get comfortable with the structure of a simple C++ program

## 📖 READ

### 1. What is this concept?
C++ is a programming language that lets you talk to the computer at two levels at once. You can write high-level ideas like “a list of players” or “a pathfinding algorithm,” but you can also decide how memory is used and how fast everything runs. Think of it as a language that is both expressive and close to the hardware. It is not a tool for one niche; it is a foundation language used for building other tools and systems.

When you learn C++, you are learning how modern software can be written with full control. You are learning a language that can build a game engine, a web server, an operating system, or a compiler itself. C++ is not just syntax; it is a way to think about performance, resources, and structure at the same time.

### 2. Why does this exist?
Early programming languages either gave you speed but no safety (like C) or gave you safety but limited control (like very high-level scripting languages). Programmers needed a language that could:
- Build complex systems without drowning in low-level details
- Still allow direct access to memory for performance
- Scale to huge codebases with millions of lines

C++ was created to solve this exact gap. It keeps the power of C but adds tools like classes, templates, and the standard library so developers can build larger, safer systems without starting from scratch every time. C++ specifically needs this because its main audience builds performance-critical systems where “easy but slow” is not acceptable.

### 3. How it works under the hood
A C++ program does not run directly. You write **source code**, and a compiler translates it to machine code. The compiler checks types, optimizes instructions, and produces object files. A **linker** then connects those object files with libraries and creates a final executable.

In memory, the program gets separated into areas:
- **Code segment**: compiled instructions
- **Stack**: local variables and function calls
- **Heap**: dynamically allocated objects

At runtime, the CPU executes the compiled instructions step by step. C++ gives you access to these layers, which is why it is powerful and also why it can be dangerous if you ignore memory and correctness.

### 4. Mental model
Imagine C++ as a factory where you design both the machines and the assembly line. High-level languages let you order finished products. C++ lets you build the machines that build the products. You decide how the conveyor belt moves (control flow), how parts are stored (memory), and how fast the machines run (performance).

Another analogy: C++ is like cooking with professional equipment. You can do anything, but you must understand heat, timing, and ingredients. If you use it well, you can produce excellent results. If you ignore the rules, you can burn the kitchen down.

### 5. Common mistakes beginners make
- Thinking C++ is only about syntax, and ignoring how programs are built and executed
- Assuming the compiler “fixes” mistakes at runtime
- Believing C++ is outdated because it is older than other languages
- Underestimating memory and performance issues because they are invisible at first

### 6. When NOT to use this
- When your project is extremely small and time-to-market is more important than performance
- When you do not need control over memory and low-level details
- When a simpler language already meets the requirements without extra complexity

C++ is powerful but heavy. If you are building a quick prototype, a scripting language may be a better fit.

### 7. How this connects to other topics
This introduction is the foundation for everything else. Understanding what C++ is makes the setup and tools chapter meaningful. Knowing that C++ is compiled helps you understand errors and debugging. The mental model of “control plus abstraction” will guide you through pointers, memory management, and performance later in the course.

## Theory explanation
C++ is a general-purpose programming language focused on performance, control, and abstraction. It powers game engines, operating systems, robotics, finance, real-time systems, and high-performance backend services. C++ is often chosen when you need both speed and control over memory.

At a high level, a C++ program goes through:
1. **Preprocessing**: includes headers and expands macros.
2. **Compilation**: converts C++ code into object files.
3. **Linking**: merges object files and libraries into an executable.
4. **Execution**: the operating system runs the executable.

Compared to C, C++ adds classes, templates, and the standard library. Compared to higher-level languages like Python or JavaScript, C++ gives you more control over memory and performance, at the cost of more complexity.

## Code examples (C++)
```cpp
#include <iostream>

int main() {
    std::cout << "Hello, C++!" << std::endl;
    return 0;
}
```

## Common mistakes
- Thinking C++ is only for games or low-level code
- Confusing compilation errors with runtime errors
- Ignoring the difference between source code and executables

## Homework (easy / medium / hard)
1. (Easy) Write a paragraph describing three areas where C++ is used.
2. (Easy) Explain the difference between compile-time and runtime errors.
3. (Easy) Draw the compile-link-run pipeline as a diagram.
4. (Medium) Compare C vs C++ in a short table (3-5 rows).
5. (Medium) Explain why C++ is preferred over Python for real-time systems.
6. (Medium) Find a C++ open-source project and list its purpose.
7. (Hard) Describe what a linker does and why missing symbols cause errors.

## Mini-project (when applicable)
**"Hello Systems" Report**  
Create a one-page markdown report that explains how a C++ program turns into a running process, using your own words.
