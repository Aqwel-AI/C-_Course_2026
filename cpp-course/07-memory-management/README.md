# 07. Memory Management

## Chapter title
**Owning Resources Safely**

## Learning goals
- Use `new` and `delete` correctly
- Understand RAII and deterministic cleanup
- Use smart pointers (`unique_ptr`, `shared_ptr`)
- Detect and avoid memory leaks

## 📖 READ

### 1. What is this concept?
Memory management is about controlling the lifetime of data in your program. In C++, you can allocate memory yourself and decide exactly when it is released. This gives you power but also responsibility. If you forget to release memory, you leak it. If you release it too early, you crash.

Modern C++ encourages a safer approach called RAII, where objects automatically clean up when they go out of scope. Smart pointers are tools that help you follow this model.

### 2. Why does this exist?
Older languages made programmers manage memory manually because hardware was limited. C++ inherited this model because it needs to be fast and flexible. But manual memory is dangerous:
- It creates memory leaks
- It causes crashes from double deletes
- It makes large programs harder to maintain

RAII and smart pointers exist to fix this. They keep performance while reducing human error.

### 3. How it works under the hood
When you call `new`, the runtime asks the heap allocator for a chunk of memory. It returns an address. That address is stored in a pointer. When you call `delete`, the allocator marks that memory as free so it can be reused.

RAII ties cleanup to object lifetime. When a stack object goes out of scope, its destructor runs automatically. Smart pointers store the raw pointer and automatically call `delete` when they are destroyed. `shared_ptr` also keeps a reference count, and only deletes when the count reaches zero.

### 4. Mental model
Think of memory as rented storage lockers. If you rent a locker (allocate memory), you must return the key when you are done (free memory). If you forget, you keep paying forever (memory leak). If you give the key back too early, you cannot access your stuff (use-after-free).

RAII is like automatic rental contracts: when you leave the building, your contract ends and the locker is cleaned automatically.

### 5. Common mistakes beginners make
- Forgetting to delete memory after `new`
- Using `delete` instead of `delete[]` for arrays
- Copying raw pointers and deleting the same memory twice
- Mixing ownership (not clear who is responsible for freeing)

### 6. When NOT to use this
- Do not use raw `new`/`delete` for most application code
- Avoid `shared_ptr` unless you truly need shared ownership
- Do not manage memory manually when a standard container (`std::vector`, `std::string`) already manages it

Manual memory management should be the exception, not the rule.

### 7. How this connects to other topics
This chapter builds on pointers and references. It prepares you for classes and object lifetime in OOP. It also connects to performance, because memory allocation costs time and cache behavior. Later, move semantics and RAII patterns will depend on this understanding.

## Theory explanation
Manual memory management is powerful but dangerous. RAII (Resource Acquisition Is Initialization) ties resource lifetimes to object lifetimes, preventing leaks. Smart pointers manage memory automatically and should be preferred over raw pointers.

## Code examples (C++)
```cpp
int *p = new int(42);
delete p;

auto up = std::make_unique<int>(10);
auto sp1 = std::make_shared<int>(20);
auto sp2 = sp1; // shared ownership
```

## Common mistakes
- Using `delete` on memory not allocated with `new`
- Forgetting `delete[]` for arrays
- Copying raw pointers and causing double free

## Homework (easy / medium / hard)
1. (Easy) Allocate and delete an integer dynamically.
2. (Easy) Allocate an array dynamically and fill it.
3. (Easy) Replace raw pointers with `unique_ptr`.
4. (Medium) Explain RAII with a real-world analogy.
5. (Medium) Implement a class that owns a dynamic array.
6. (Medium) Demonstrate `shared_ptr` reference counting.
7. (Hard) Build a small leak detector using a counter in a class.

## Mini-project (when applicable)
**"Smart Pointer Refactor"**  
Take an earlier project and refactor all raw allocations to use smart pointers.
