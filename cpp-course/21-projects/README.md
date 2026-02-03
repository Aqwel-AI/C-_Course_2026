# 21. Projects

## Chapter title
**Applied Projects Portfolio**

## Learning goals
- Practice complete, end-to-end C++ projects
- Build a portfolio of practical applications
- Integrate concepts from previous chapters

## 📖 READ

### 1. What is this concept?
Projects are full applications that combine everything you have learned. They force you to design, implement, test, and polish a complete program. A project is not just about code—it is about solving a real problem with structure and discipline.

This is where theory becomes practice. You are no longer solving isolated exercises; you are building something that works end-to-end.

### 2. Why does this exist?
Learning concepts in isolation is not enough. Real software requires planning, organization, and integration. Projects exist to:
- Build practical skills
- Show how pieces fit together
- Prepare you for real-world development

C++ projects also teach you how to manage complexity, which is essential in professional work.

### 3. How it works under the hood
Projects often involve multiple files, modules, and build configurations. The compiler builds each file separately and links them together. Data flows between modules through interfaces. File I/O, error handling, and data structures are all used together.

This is the first time you see the full lifecycle: design, implementation, debugging, and refinement.

### 4. Mental model
Think of a project like building a house. You do not just start placing bricks. You design the plan, gather materials, build the foundation, then assemble the structure piece by piece. Each chapter before is like learning how to use a tool; now you use all tools together.

### 5. Common mistakes beginners make
- Starting without requirements or a plan
- Putting all code in one file
- Ignoring testing and validation
- Overengineering before the core features work

### 6. When NOT to use this
- Do not start a big project before you understand the basics
- Avoid building projects that are too large for your current level
- Do not copy tutorials blindly without understanding design decisions

Start small and scale up with experience.

### 7. How this connects to other topics
Projects connect everything: algorithms, data structures, memory management, file I/O, error handling, and performance. They also prepare you for the final capstone and real-world development.

## Theory explanation
Projects are where the ideas come together. Each project focuses on real-world constraints: input validation, data structures, modular design, and performance.

## Code examples (C++)
```cpp
// Example project structure (header + implementation)
// calculator/
//   main.cpp
//   calculator.hpp
//   calculator.cpp
```

## Common mistakes
- Starting without a plan or requirements list
- Mixing all code in one file
- Skipping testing and validation

## Homework (easy / medium / hard)
1. (Easy) Choose a project and write a requirements list.
2. (Easy) Draw a simple class diagram for a project.
3. (Easy) Break one project into 3-5 modules.
4. (Medium) Implement unit tests for one module.
5. (Medium) Add file I/O to an existing project.
6. (Medium) Add error handling and logging.
7. (Hard) Measure and optimize performance of one project feature.

## Mini-project (when applicable)
**"Project Scaffold"**  
Create a CMake-based template for any new project you will build.

## Required projects in this course
1. **Console Calculator**  
   - Arithmetic operations, input validation, history log.
2. **Todo App**  
   - Add, list, complete, delete tasks. Use file storage.
3. **File-Based Database**  
   - Store and query structured data (CSV or binary).
4. **Simple Game**  
   - Text-based or SFML-style loop. Minimal assets.
5. **Mini Engine Architecture**  
   - Game loop + ECS-like structure + resource manager.
6. **Final Capstone**  
   - See `final-project` directory for full requirements.
