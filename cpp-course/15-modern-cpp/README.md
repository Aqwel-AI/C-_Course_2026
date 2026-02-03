# 15. Modern C++

## Chapter title
**C++11 to C++20 Features**

## Learning goals
- Use `auto` and range-based loops
- Apply `constexpr` and `consteval` basics
- Understand move semantics and rvalue references
- Use `nullptr`, `enum class`, and smart pointers

## 📖 READ

### 1. What is this concept?
Modern C++ refers to the language updates from C++11 onward that made C++ safer, clearer, and more expressive. These features reduce boilerplate, prevent common bugs, and improve performance. Examples include `auto`, range-based loops, smart pointers, and move semantics.

Modern C++ is not a separate language. It is the same C++ with better tools, encouraging patterns that are easier to write correctly.

### 2. Why does this exist?
Classic C++ was powerful but verbose and error-prone. Developers wanted:
- Safer memory management
- Less boilerplate code
- Better performance without manual tricks

Modern C++ provides these improvements while staying backward compatible. C++ needs this evolution because the industry demands productivity and safety alongside performance.

### 3. How it works under the hood
Many modern features are compile-time improvements:
- `auto` lets the compiler deduce types
- Range-based loops are transformed into iterator-based loops
- Move semantics allow resources to be transferred instead of copied

Move semantics rely on rvalue references. When you “move” an object, you transfer its internal resources (like heap memory) rather than copying them. The compiler can optimize many operations using moves, especially with temporary objects.

### 4. Mental model
Think of modern C++ as upgrading from manual tools to power tools. You still build the same structures, but the tools are faster, safer, and reduce mistakes.

Move semantics are like handing over the keys to a car instead of making a duplicate car. You avoid the cost of copying while still transferring ownership.

### 5. Common mistakes beginners make
- Using `auto` everywhere, making types unclear
- Moving from an object and then using it as if nothing happened
- Mixing old C-style patterns with modern features inconsistently
- Assuming `constexpr` makes everything faster automatically

### 6. When NOT to use this
- Avoid `auto` in public APIs where explicit types improve readability
- Do not use move semantics when you still need the original object
- Avoid modern features if your compiler or project constraints do not support them

Use modern features thoughtfully, not blindly.

### 7. How this connects to other topics
Modern C++ ties together many earlier topics: RAII, smart pointers, and templates. It is essential for performance and large codebases. Later topics like multithreading and systems programming benefit from modern features that reduce errors.

## Theory explanation
Modern C++ focuses on safety, clarity, and performance. Features like `auto`, range-based loops, and smart pointers reduce boilerplate and bugs. Move semantics allow efficient transfer of resources without copying.

## Code examples (C++)
```cpp
std::vector<int> v = {1, 2, 3};
for (auto x : v) {
    std::cout << x << "\n";
}

std::unique_ptr<int> p = std::make_unique<int>(5);

std::string a = "hello";
std::string b = std::move(a); // move, not copy
```

## Common mistakes
- Overusing `auto` when it hurts readability
- Using moved-from objects without reinitializing
- Confusing `constexpr` with `const`

## Homework (easy / medium / hard)
1. (Easy) Replace a manual loop with a range-based loop.
2. (Easy) Use `auto` to simplify iterator declarations.
3. (Easy) Use `enum class` in a small example.
4. (Medium) Write a `constexpr` factorial function.
5. (Medium) Demonstrate move semantics with a custom class.
6. (Medium) Compare `nullptr` vs `0` in a pointer example.
7. (Hard) Use `std::optional` to model missing values.

## Mini-project (when applicable)
**"Modernized Refactor"**  
Refactor an earlier project with modern C++ features and explain the changes.
