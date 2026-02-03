# 10. STL (Standard Template Library)

## Chapter title
**Containers, Iterators, and Algorithms**

## Learning goals
- Use common STL containers (`vector`, `map`, `set`, `unordered_map`)
- Understand iterators and iterator categories
- Use algorithms and lambdas effectively

## 📖 READ

### 1. What is this concept?
The Standard Template Library (STL) is a collection of ready-made data structures and algorithms that work together. It includes containers like `vector`, `map`, `set`, and algorithms like `sort`, `find`, and `accumulate`. The STL is one of C++’s biggest strengths because it gives you powerful tools out of the box.

STL is built around the idea of **generic programming**: containers hold any type, and algorithms can operate on any container through iterators.

### 2. Why does this exist?
Before STL, every programmer wrote their own lists, stacks, and sorting functions. That caused duplication, bugs, and inconsistent performance. STL solves this by providing:
- Standard, tested containers
- Efficient algorithms
- A consistent interface through iterators

C++ needs STL because it aims to be a systems language with high-level productivity. STL provides productivity without sacrificing performance.

### 3. How it works under the hood
Most STL components are templates. When you write `std::vector<int>`, the compiler generates a vector implementation specialized for `int`.

Iterators are like generalized pointers. They let algorithms work with any container that provides iterator access. `std::sort`, for example, doesn’t care if it’s sorting a vector or a deque, as long as the iterator supports random access.

### 4. Mental model
Think of STL as a toolbox. Containers are the boxes that hold things. Algorithms are the tools that operate on those boxes. Iterators are the handles that let the tools reach inside any box in a consistent way.

Another analogy: containers are shelves, algorithms are workers, and iterators are the paths the workers use to reach each item.

### 5. Common mistakes beginners make
- Choosing the wrong container for the job
- Ignoring iterator invalidation rules
- Copying large containers unnecessarily
- Using manual loops when a standard algorithm exists

### 6. When NOT to use this
- Do not use `std::map` when a flat vector would be faster for small data
- Avoid `std::list` unless you truly need constant-time insertion in the middle
- Do not rely on heavy STL abstractions in very low-level embedded environments if memory is extremely limited

Use STL when it makes code clearer and safer, but be aware of performance trade-offs.

### 7. How this connects to other topics
STL builds directly on templates and iterators. It is used heavily in algorithms, data structures, and competitive programming. Modern C++ features like lambdas and `auto` make STL easier to use and more powerful.

## Theory explanation
The STL provides high-performance containers and algorithms that work together through iterators. This standard library saves time and reduces bugs by using well-tested components.

## Code examples (C++)
```cpp
std::vector<int> v = {3, 1, 4};
std::sort(v.begin(), v.end());

std::unordered_map<std::string, int> freq;
freq["apple"]++;

for (const auto &x : v) {
    std::cout << x << " ";
}
```

## Common mistakes
- Using `map` when `unordered_map` is faster for lookups
- Invalidating iterators after `vector` reallocation
- Forgetting that `set` elements are unique and sorted

## Homework (easy / medium / hard)
1. (Easy) Use `vector` to store and print 10 integers.
2. (Easy) Use `map` to store word frequencies.
3. (Easy) Use `set` to remove duplicates from a list.
4. (Medium) Use `sort` with a custom comparator.
5. (Medium) Implement a frequency counter using `unordered_map`.
6. (Medium) Use `find_if` with a lambda.
7. (Hard) Implement a simple LRU cache using `list` + `unordered_map`.

## Mini-project (when applicable)
**"Student Registry"**  
Store students in a map with IDs and provide lookup, insert, and delete commands.
