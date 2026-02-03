# 03. Control Flow

## Chapter title
**Decisions and Loops**

## Learning goals
- Use `if`, `else if`, and `else` for branching
- Use `switch` for multi-way selection
- Master `for`, `while`, and `do-while` loops
- Use `break` and `continue` safely

## 📖 READ

### 1. What is this concept?
Control flow is how a program decides what to do next. Without control flow, a program would run from top to bottom and always do the same thing. Control flow lets a program react to input, repeat tasks, and make decisions. This is what turns code from a static script into real logic.

Branching (`if`/`else`/`switch`) lets you choose different paths. Loops (`for`, `while`, `do-while`) let you repeat work without copying code. Together, they form the “decision-making” and “repetition” abilities of a program.

### 2. Why does this exist?
Early programs were linear and limited. As soon as programmers needed to handle different cases or repeat tasks, they needed a way to control execution. Without control flow, you would have to write the same code many times or rely on hardware-level jumps.

C++ needs clear control flow because it is used to build complex systems: games, engines, servers, and tools all need to react to events, handle multiple conditions, and repeat tasks efficiently.

### 3. How it works under the hood
At compile time, control flow statements are translated into machine-level jump instructions. For example:
- `if` becomes a conditional jump based on a CPU flag
- `switch` often becomes a jump table
- `for` and `while` become loops with backward jumps

At runtime, the CPU evaluates a condition, then jumps to the correct instruction address. Loops are just repeated jumps until a condition fails. There is no “loop magic” in hardware—just careful sequencing of jumps.

### 4. Mental model
Imagine your program as a train on a track. Control flow are the switches that change the track direction. An `if` statement is a fork that chooses left or right. A loop is a circular track that you ride multiple times until a gate opens and lets you exit.

Another analogy: control flow is like a cooking recipe. Sometimes you “if the sauce is too thick, add water.” Sometimes you “stir for 5 minutes.” Those decisions and repetitions are control flow.

### 5. Common mistakes beginners make
- Forgetting to update the loop counter, causing infinite loops
- Writing conditions backwards and getting wrong branch behavior
- Off-by-one errors (looping too many or too few times)
- Using `switch` without `break`, causing fall-through surprises

### 6. When NOT to use this
- Do not use complex nested `if` blocks when a simpler logic or data structure could solve the problem
- Do not use loops when a standard algorithm already exists in the STL
- Do not use `switch` when values are not discrete or cleanly mapped

Overusing control flow can make code hard to read. Prefer clarity and avoid deep nesting.

### 7. How this connects to other topics
Control flow builds directly on expressions and variables. Functions rely on control flow for logic. Algorithms and data structures later are built from loops and branching. Debugging also depends on understanding which path your program took.

## Theory explanation
Control flow determines how a program moves through code. Branching lets you choose paths based on conditions; loops let you repeat work efficiently. Use `for` when you know the iteration count, `while` for condition-based repetition, and `do-while` when the loop must run at least once.

## Code examples (C++)
```cpp
int x = 7;
if (x % 2 == 0) {
    std::cout << "Even\n";
} else {
    std::cout << "Odd\n";
}

switch (x) {
    case 1: std::cout << "One\n"; break;
    case 7: std::cout << "Seven\n"; break;
    default: std::cout << "Other\n"; break;
}

for (int i = 1; i <= 5; i++) {
    std::cout << i << " ";
}
```

## Common mistakes
- Forgetting `break` in `switch` cases
- Infinite loops due to wrong update logic
- Off-by-one errors in loop bounds

## Homework (easy / medium / hard)
1. (Easy) Print numbers 1 to 20 with a `for` loop.
2. (Easy) Check if a number is positive, negative, or zero.
3. (Easy) Use `switch` to map 1-7 to day names.
4. (Medium) Sum all even numbers between 1 and N.
5. (Medium) Count digits in a number using a `while` loop.
6. (Medium) Find the smallest divisor of a number greater than 1.
7. (Hard) Print all primes up to N using basic loops.

## Mini-project (when applicable)
**"Number Guessing Game"**  
Implement a guessing game where the program picks a number and the user tries to guess it with hints.
