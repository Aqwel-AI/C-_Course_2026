# 17. Performance and Optimization

## Chapter title
**Fast Code, Safe Code**

## Learning goals
- Understand CPU cache and memory locality
- Use profiling to find bottlenecks
- Apply compiler optimizations correctly
- Recognize undefined behavior

## 📖 READ

### 1. What is this concept?
Performance and optimization are about making programs run faster and use fewer resources. This includes choosing efficient algorithms, storing data in cache-friendly ways, and letting the compiler generate fast machine code.

Performance is not just “make code faster.” It is about measuring, understanding bottlenecks, and improving the right parts of a program.

### 2. Why does this exist?
Computers are fast, but real-world programs handle huge data, real-time constraints, and limited resources. Poor performance leads to slow apps, laggy games, and overloaded servers. Optimization exists to:
- Meet time or memory constraints
- Use hardware efficiently
- Scale with larger input sizes

C++ needs performance knowledge because it is chosen specifically for speed and control.

### 3. How it works under the hood
Performance depends on how the CPU accesses memory. Data in cache is fast; data in RAM is slower. Algorithms that access memory sequentially are often faster than those that jump around.

The compiler also plays a role. With optimization flags (like `-O2`), the compiler can inline functions, remove dead code, and reorder instructions. Undefined behavior breaks these guarantees and can produce unpredictable results.

### 4. Mental model
Think of performance like managing a warehouse. If tools are close and organized, you work quickly. If you keep walking across the building for every item, you waste time. Cache locality is about keeping data “close” to the CPU.

Profiling is like timing workers: you measure where time is spent before deciding what to improve.

### 5. Common mistakes beginners make
- Optimizing without measuring first
- Writing complex micro-optimizations while ignoring algorithm choice
- Ignoring cache effects and memory layout
- Triggering undefined behavior and expecting stable results

### 6. When NOT to use this
- Do not optimize code that is already fast enough
- Avoid premature optimization in early prototypes
- Do not sacrifice readability for tiny performance gains unless needed

Optimization is a tool, not a default.

### 7. How this connects to other topics
Performance connects to algorithms, data structures, and memory management. Multithreading is often used to improve performance. Modern C++ features like move semantics also reduce unnecessary copies, improving efficiency.

## Theory explanation
Performance comes from good algorithms, cache-friendly data, and correct use of compiler optimizations. Premature optimization is harmful, so measure first. Undefined behavior can silently break programs and optimizations.

## Code examples (C++)
```cpp
// Cache-friendly traversal
std::vector<int> v(1'000'000, 1);
long long sum = 0;
for (size_t i = 0; i < v.size(); i++) {
    sum += v[i];
}
```

## Common mistakes
- Optimizing without profiling
- Writing code that triggers undefined behavior
- Using micro-optimizations instead of algorithmic improvements

## Homework (easy / medium / hard)
1. (Easy) Explain what CPU cache is in your own words.
2. (Easy) Compare O(n^2) vs O(n log n) for large n.
3. (Easy) Compile with `-O0` and `-O2` and compare runtime.
4. (Medium) Use a profiler to find a slow function.
5. (Medium) Compare vector vs list traversal speed.
6. (Medium) Identify undefined behavior in a small code snippet.
7. (Hard) Build a benchmark harness for two algorithms.

## Mini-project (when applicable)
**"Optimization Report"**  
Pick a slow program, profile it, optimize it, and write a report of improvements.
