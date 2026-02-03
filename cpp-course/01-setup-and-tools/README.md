# 01. Setup and Tools

## Chapter title
**Building a Professional C++ Environment**

## Learning goals
- Install and use GCC, Clang, or MSVC
- Understand IDE options (VS Code, CLion)
- Create a basic CMake project
- Use a debugger to step through code
- Understand a simple Git & GitHub workflow

## 📖 READ

### 1. What is this concept?
The C++ toolchain is the set of tools that turn your text files into a working program and help you build, test, and maintain it. It includes a compiler (to translate your code), a build system (to organize how code is compiled), an editor or IDE (to write and navigate your code), a debugger (to inspect running programs), and version control (to track changes).

This is not optional “extra stuff.” C++ is a compiled language. Without these tools, your code cannot run. A strong setup makes you faster, safer, and more confident because you can build, test, and debug like a professional.

### 2. Why does this exist?
Before build systems and debuggers, programmers had to compile files manually, track dependencies by hand, and debug by printing messages everywhere. That was slow and error-prone. As C++ projects grew, it became impossible to manage builds with one command. CMake and IDEs exist to solve these problems:
- **CMake** solves cross-platform build complexity
- **Debuggers** solve the “I have no idea why it crashed” problem
- **Git** solves collaboration and history problems

C++ specifically needs this because it supports large, multi-file projects and because compile-time errors are common. You need good tools to handle complexity.

### 3. How it works under the hood
When you press “build,” several steps happen:
1. The build system (CMake) generates platform build files (like Makefiles or Visual Studio projects).
2. The compiler translates each `.cpp` file to an object file.
3. The linker combines object files and libraries into a single executable.

The debugger works by running the executable under a special controller that pauses execution, reads memory, and shows variable values. Git stores snapshots of your repository in a hidden `.git` folder and allows you to move between versions.

### 4. Mental model
Think of your code as a blueprint. The compiler is the factory that turns blueprints into parts. The linker assembles parts into a finished product. CMake is the foreman who tells the factory which parts to build and in what order. The debugger is like an X-ray machine that lets you see inside the product while it runs. Git is your time machine, letting you move back and forth between versions of the blueprint.

### 5. Common mistakes beginners make
- Installing tools but not checking that the terminal uses the correct one
- Editing CMake but forgetting to reconfigure or rebuild
- Running without debug symbols and then wondering why the debugger shows nothing
- Not committing early, leading to lost work or confusion

### 6. When NOT to use this
- If you are writing a single-file experiment, you can compile directly without CMake
- If you are exploring logic, a simple editor may be enough
- If a project is purely educational and not shared, Git can be optional (but still recommended)

Avoid overengineering the tool setup for tiny scripts. Use the simplest tool that still makes you productive.

### 7. How this connects to other topics
Every chapter after this depends on being able to compile and run code. Debugging will matter when you learn pointers and memory management. Git will matter when you build projects. CMake will become essential as soon as you have multiple files and libraries.

## Theory explanation
A good toolchain makes C++ development faster and safer. You need:
- **Compiler**: GCC, Clang, or MSVC
- **Build system**: CMake to manage projects
- **IDE/editor**: VS Code or CLion for productivity
- **Debugger**: gdb, lldb, or Visual Studio debugger
- **Version control**: Git for history and collaboration

### CMake basics
CMake generates platform-specific build files. You write a `CMakeLists.txt` that tells CMake what to compile and how.

## Code examples (C++)
**Basic compile command (GCC/Clang):**
```bash
g++ -std=c++17 -O2 -Wall -Wextra main.cpp -o app
```

**Minimal CMake project:**
```cmake
cmake_minimum_required(VERSION 3.16)
project(hello_cpp LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_executable(app main.cpp)
```

**Simple debugging session (gdb):**
```bash
g++ -std=c++17 -g main.cpp -o app
gdb ./app
```

## Common mistakes
- Installing multiple compilers but using the wrong one in your PATH
- Building without `-g` and wondering why the debugger has no symbols
- Editing CMakeLists but forgetting to re-run CMake configure
- Committing build folders (`build/`) to Git

## Homework (easy / medium / hard)
1. (Easy) Install a compiler and verify `g++ --version` or `clang++ --version`.
2. (Easy) Create a repo and push a single commit to GitHub.
3. (Easy) Build a "Hello C++" app using a command line compile.
4. (Medium) Create a CMake project that builds two executables.
5. (Medium) Use a debugger to set a breakpoint and step into a function.
6. (Medium) Add a `.gitignore` with `build/`, `*.o`, and `*.exe`.
7. (Hard) Compare GCC and Clang error messages for the same bug.

## Mini-project (when applicable)
**"Build It Twice"**  
Create a project that can compile with both GCC and Clang, and document the steps in a `BUILD.md`.
