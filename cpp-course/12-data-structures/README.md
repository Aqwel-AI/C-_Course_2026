# 12. Data Structures

## Chapter title
**Building Blocks of Programs**

## Learning goals
- Implement linked lists, stacks, queues
- Understand trees and graphs
- Implement hash tables at a basic level

## 📖 READ

### 1. What is this concept?
Data structures are ways of organizing data so that you can access and modify it efficiently. Different problems need different structures. A list is good for sequential access, a tree is good for hierarchical data, and a hash table is good for fast lookups.

Data structures are not just academic. They determine how fast your program runs and how easy it is to implement features.

### 2. Why does this exist?
Without data structures, you would store everything in a flat array and handle all operations manually. That becomes slow and messy as data grows. Data structures exist to solve problems like:
- Fast search (hash tables, trees)
- Ordered traversal (trees, linked lists)
- Efficient insertion/removal (linked lists, queues)

C++ needs these because it is used in systems where performance matters. You cannot afford to choose the wrong structure.

### 3. How it works under the hood
Each data structure has a memory layout:
- Linked lists use nodes with pointers to the next node
- Stacks and queues are often built on arrays or linked lists
- Trees store nodes with pointers to left/right children
- Hash tables use arrays plus a hash function to map keys to buckets

These layouts directly impact memory usage and cache performance. Pointer-heavy structures may be slower due to cache misses, even if they look efficient on paper.

### 4. Mental model
Think of data structures as different ways to organize a library:
- A **list** is a stack of books in order
- A **queue** is a line at a checkout counter
- A **tree** is a folder system on your computer
- A **hash table** is like a card catalog that jumps directly to a shelf

### 5. Common mistakes beginners make
- Using the wrong structure for the job
- Forgetting to handle edge cases like empty structures
- Leaking memory in custom implementations
- Confusing time complexity with actual runtime performance

### 6. When NOT to use this
- Do not build custom data structures if the STL already provides them
- Avoid pointer-heavy structures when a contiguous array is faster
- Do not over-engineer: if a vector is enough, use it

### 7. How this connects to other topics
Data structures rely on pointers and memory management. Algorithms depend on data structures for efficiency. STL containers are real-world implementations of these ideas. Performance topics later show how data layout affects cache and speed.

## Theory explanation
Data structures organize data for efficient access and modification. Choosing the right structure is essential for performance. This chapter focuses on understanding how structures work internally rather than only using STL.

## Code examples (C++)
```cpp
struct Node {
    int value;
    Node *next;
};

struct Stack {
    Node *top = nullptr;
    void push(int v) {
        Node *n = new Node{v, top};
        top = n;
    }
    void pop() {
        if (!top) return;
        Node *old = top;
        top = top->next;
        delete old;
    }
};
```

## Common mistakes
- Forgetting to update pointers when removing nodes
- Leaking memory in custom data structures
- Confusing tree depth with height

## Homework (easy / medium / hard)
1. (Easy) Implement a singly linked list with insert.
2. (Easy) Implement a stack using a vector.
3. (Easy) Implement a queue using a deque.
4. (Medium) Implement a binary search tree insertion.
5. (Medium) Traverse a tree in-order and pre-order.
6. (Medium) Implement BFS on a graph adjacency list.
7. (Hard) Implement a hash table with open addressing.

## Mini-project (when applicable)
**"Contact Manager"**  
Build a contact manager using your own hash table or tree for lookups.
