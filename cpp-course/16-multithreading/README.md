# 16. Multithreading

## Chapter title
**Concurrency in C++**

## Learning goals
- Create threads with `std::thread`
- Protect shared data with `std::mutex`
- Understand race conditions and deadlocks
- Use `std::async` and `std::future`

## 📖 READ

### 1. What is this concept?
Multithreading is the ability to run multiple tasks at the same time within a single program. Instead of doing work step by step on one CPU core, a program can divide work into threads and execute them concurrently.

In C++, multithreading is a way to improve performance or responsiveness, but it also introduces complexity. Threads must coordinate when they share data, or the program can break in subtle ways.

### 2. Why does this exist?
Modern CPUs have multiple cores. If a program only uses one core, it wastes hardware. Multithreading exists to:
- Speed up CPU-heavy tasks by splitting work
- Keep applications responsive while background tasks run
- Handle many independent tasks (like server connections)

C++ needs multithreading because it is used for performance-critical software where every core matters.

### 3. How it works under the hood
When you create a thread, the operating system schedules it on a CPU core. Each thread has its own stack but shares the same process memory. This shared memory is what makes threads powerful and dangerous.

Race conditions occur when two threads access the same data without synchronization. A mutex is a lock that ensures only one thread can access a piece of data at a time.

### 4. Mental model
Think of threads as multiple workers in a kitchen. If each worker has their own ingredients, they can work independently. But if they all reach for the same pot, you need rules to avoid chaos. A mutex is like a sign that says “only one person can use this pot at a time.”

### 5. Common mistakes beginners make
- Forgetting to join threads, causing crashes or unfinished work
- Accessing shared data without locks
- Locking in inconsistent order, causing deadlocks
- Assuming threads always make programs faster

### 6. When NOT to use this
- Avoid multithreading for small programs where simplicity matters
- Do not use threads if the task is I/O-bound and the bottleneck is disk or network
- Avoid sharing data across threads unless absolutely necessary

Multithreading is powerful but often overused. Simpler single-threaded code is easier to debug.

### 7. How this connects to other topics
Multithreading builds on functions and memory management. It interacts with performance and system-level concepts. It also requires strong debugging skills because concurrency bugs are difficult to reproduce.

## Theory explanation
Multithreading allows multiple tasks to run concurrently. Shared data must be protected to avoid race conditions. Futures and async tasks simplify concurrency by handling threads automatically.

## Code examples (C++)
```cpp
std::mutex mtx;
int counter = 0;

void work() {
    for (int i = 0; i < 1000; i++) {
        std::lock_guard<std::mutex> lock(mtx);
        counter++;
    }
}

int main() {
    std::thread t1(work);
    std::thread t2(work);
    t1.join();
    t2.join();
    std::cout << counter << "\n";
}
```

## Common mistakes
- Forgetting to `join` or `detach` threads
- Accessing shared data without a mutex
- Lock ordering issues leading to deadlocks

## Homework (easy / medium / hard)
1. (Easy) Launch two threads that print different messages.
2. (Easy) Use a mutex to protect a shared counter.
3. (Easy) Explain what a race condition is.
4. (Medium) Implement a producer-consumer with a queue and mutex.
5. (Medium) Use `std::async` to compute two tasks in parallel.
6. (Medium) Measure speedup from using two threads.
7. (Hard) Implement a thread pool with a task queue.

## Mini-project (when applicable)
**"Parallel Word Count"**  
Split a text file into chunks and count words in parallel.
