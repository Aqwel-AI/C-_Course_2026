# 20. Competitive Programming

## Chapter title
**Fast I/O and Problem-Solving**

## Learning goals
- Use fast input/output techniques
- Apply common STL tricks
- Recognize typical problem-solving patterns

## 📖 READ

### 1. What is this concept?
Competitive programming is a style of problem-solving where you must write correct code under time pressure. Problems are usually algorithmic and come with strict time limits. The goal is to solve problems quickly and efficiently.

C++ is the dominant language in competitive programming because it balances speed, control, and a powerful standard library.

### 2. Why does this exist?
Competitions test algorithmic thinking, efficiency, and coding skill. They push programmers to think about constraints and optimize their solutions.

C++ is used because many problems require fast execution and memory efficiency, which higher-level languages may not provide under strict limits.

### 3. How it works under the hood
Fast I/O techniques disable synchronization with C streams and untie input from output, reducing overhead. Many competitive patterns rely on precomputations and data structures to reduce time complexity.

The compiler optimizes heavily, but the algorithm still matters most. A slow algorithm will fail even with the fastest I/O.

### 4. Mental model
Imagine a contest like a race. Every second counts. Fast I/O is like wearing lighter shoes. Efficient algorithms are like choosing the shortest route. You need both to win.

### 5. Common mistakes beginners make
- Ignoring constraints and writing slow algorithms
- Overusing complex data structures when simpler ones work
- Debugging too late instead of testing early
- Forgetting edge cases (empty input, large values)

### 6. When NOT to use this
- Do not prioritize contest-style optimizations in real-world business code
- Avoid overly compact code if readability matters more than speed
- Do not use fast I/O tricks when input sizes are small

Competitive programming style is great for contests but not always best for production systems.

### 7. How this connects to other topics
Competitive programming depends on algorithms, data structures, and STL knowledge. It also benefits from modern C++ features and performance awareness. The patterns learned here help with interviews and problem-solving in general.

## Theory explanation
Competitive programming emphasizes speed and correctness. You often need optimized I/O and a toolbox of algorithms and data structures. Patterns include prefix sums, two pointers, binary search on answers, and greedy strategies.

## Code examples (C++)
```cpp
std::ios::sync_with_stdio(false);
std::cin.tie(nullptr);

int n;
std::cin >> n;
```

## Common mistakes
- Forgetting fast I/O for large input
- Overcomplicating solutions
- Ignoring constraints

## Homework (easy / medium / hard)
1. (Easy) Implement fast I/O setup in a template.
2. (Easy) Solve a prefix sum range query.
3. (Easy) Use two pointers to find a pair with target sum.
4. (Medium) Implement binary search on answer for minimum time.
5. (Medium) Solve a greedy scheduling problem.
6. (Medium) Use BFS for shortest path in an unweighted graph.
7. (Hard) Solve a problem that combines two patterns.

## Mini-project (when applicable)
**"Contest Template"**  
Create a personal competitive programming template with common utilities.
