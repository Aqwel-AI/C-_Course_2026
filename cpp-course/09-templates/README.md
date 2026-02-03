# 09. Templates

## Chapter title
**Generic Programming**

## Learning goals
- Write function and class templates
- Use template specialization
- Understand and apply concepts (C++20)

## 📖 READ

### 1. What is this concept?
Templates are C++’s way of writing code that works for many types without rewriting the same logic. Instead of writing one function for `int`, one for `double`, and one for `std::string`, you write a single template and let the compiler generate the specific versions.

This is called **generic programming**. It lets you express ideas like “max of two values” or “a container of items” without caring about the exact type until later.

### 2. Why does this exist?
Before templates, programmers duplicated code for each type. That created bugs and wasted time. Templates solve this by:
- Eliminating duplication
- Allowing generic algorithms and containers
- Letting the compiler optimize each type-specific version

C++ needs templates because it aims for both performance and abstraction. Templates provide high-level reuse without runtime overhead.

### 3. How it works under the hood
Templates are expanded at compile time. When you call a template with a specific type, the compiler generates a new function or class for that type. This is called **instantiation**.

Because of this, templates can increase compile times and lead to large binaries, but they also allow the compiler to fully optimize code for each type. Concepts (C++20) help the compiler check whether a type is valid before instantiating, giving clearer errors.

### 4. Mental model
Think of a template as a cookie cutter. The cutter shape is the template, and the dough you press into it is the type. Each time you use a template with a different type, you get a new cookie of the same shape.

Another analogy: templates are like a fill-in-the-blank form. You write the form once, then fill in the type later.

### 5. Common mistakes beginners make
- Writing templates when simple overloads would be clearer
- Forgetting `typename` in dependent names, causing confusing errors
- Accepting any type without constraints and getting unreadable compiler messages
- Putting template definitions in `.cpp` files (they must be visible in headers)

### 6. When NOT to use this
- Do not use templates for very simple code that only needs one type
- Avoid overly complex template meta-programming when clarity is more important
- Do not use templates if runtime polymorphism is a better fit

Templates are powerful, but they can make code harder to read and compile if overused.

### 7. How this connects to other topics
Templates are the foundation of the STL. `std::vector`, `std::map`, and `std::sort` are all template-based. Concepts connect to modern C++. Templates also connect to performance because type-specific code can be optimized aggressively by the compiler.

## Theory explanation
Templates allow you to write code that works with many types. The compiler generates type-specific versions at compile time. Specialization provides custom behavior for specific types. Concepts constrain templates for clearer errors and safer code.

## Code examples (C++)
```cpp
template <typename T>
T maxValue(T a, T b) {
    return (a > b) ? a : b;
}

template <typename T>
class Box {
public:
    explicit Box(T v) : value(v) {}
    T get() const { return value; }
private:
    T value;
};

template <>
class Box<const char*> {
public:
    explicit Box(const char* v) : value(v) {}
    const char* get() const { return value; }
private:
    const char* value;
};
```

## Common mistakes
- Forgetting `typename` for dependent names
- Overusing templates for simple code
- Writing unconstrained templates that accept invalid types

## Homework (easy / medium / hard)
1. (Easy) Write a template function to swap two values.
2. (Easy) Create a template `minValue` function.
3. (Easy) Build a templated `Pair` struct.
4. (Medium) Add specialization for `std::string`.
5. (Medium) Use templates to implement a generic sum of a vector.
6. (Medium) Write a template class `Stack<T>`.
7. (Hard) Use C++20 concepts to restrict a template to arithmetic types.

## Mini-project (when applicable)
**"Generic Container"**  
Implement a templated container with push/pop and bounds checking.
