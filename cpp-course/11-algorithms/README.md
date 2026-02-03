# 11. Algorithms

## Chapter title
**Efficiency and Problem Solving**

## Learning goals
- Understand Big-O notation
- Implement sorting and searching algorithms
- Measure practical performance

## 📖 READ

### 1. What is this concept?
An algorithm is a clear, step-by-step procedure for solving a problem. It is the logic behind the code. Two programs can solve the same problem but use different algorithms—and one may be far faster than the other.

In C++, algorithms are important because performance often matters. Choosing the right algorithm is usually more important than micro-optimizing code.

### 2. Why does this exist?
As soon as data grows, naive approaches become too slow. Sorting a million items with a quadratic algorithm is painfully slow compared to an O(n log n) algorithm. Algorithms exist to provide efficient ways to solve common problems like searching, sorting, or pathfinding.

C++ needs strong algorithmic foundations because it is used in performance-critical systems where time and memory are limited.

### 3. How it works under the hood
Algorithms are implemented as loops, recursion, and data movement. For example, sorting algorithms typically compare elements and swap or merge them. Searching algorithms compare values and reduce the search space.

The compiler does not change the algorithm itself—it only optimizes the low-level instructions. If the algorithm is poor, the compiled program will still be slow.

### 4. Mental model
Think of an algorithm as a recipe. A bad recipe might say “look at every ingredient for every step,” which is slow. A good recipe says “divide the ingredients into groups, work smarter, and finish faster.”

Another analogy: searching a book. A linear search is like reading every page. Binary search is like using the table of contents and repeatedly cutting the search space in half.

### 5. Common mistakes beginners make
- Choosing a slow algorithm because it is easier to implement
- Ignoring worst-case performance
- Assuming the compiler will “optimize away” algorithmic inefficiency
- Forgetting that memory usage can matter as much as time

### 6. When NOT to use this
- Do not implement custom algorithms when a trusted STL algorithm already exists
- Avoid complex algorithms if the input size is tiny and simple code is clearer
- Do not over-engineer with advanced algorithms without evidence that they are needed

### 7. How this connects to other topics
Algorithms rely on control flow, functions, and data structures. The STL provides many algorithms ready to use. Competitive programming and performance topics later in the course build heavily on algorithmic thinking.

## Theory explanation
Algorithms are step-by-step procedures for solving problems. Efficiency matters because input sizes grow. Big-O describes growth rate: O(1), O(log n), O(n), O(n log n), O(n^2), etc.

## Code examples (C++)
```cpp
int binarySearch(const std::vector<int> &a, int target) {
    int l = 0, r = static_cast<int>(a.size()) - 1;
    while (l <= r) {
        int m = l + (r - l) / 2;
        if (a[m] == target) return m;
        if (a[m] < target) l = m + 1;
        else r = m - 1;
    }
    return -1;
}
```

## Common mistakes
- Using linear search on sorted data
- Ignoring input size constraints
- Confusing average and worst-case complexity

## Homework (easy / medium / hard)
1. (Easy) Implement bubble sort and test it.
2. (Easy) Implement linear search.
3. (Easy) Count comparisons for a small array sort.
4. (Medium) Implement merge sort.
5. (Medium) Implement binary search.
6. (Medium) Compare runtime of two sorts on random data.
7. (Hard) Implement quicksort with random pivot.

## Mini-project (when applicable)
**"Sorting Benchmark"**  
Build a console app that times sorting algorithms for multiple input sizes.
