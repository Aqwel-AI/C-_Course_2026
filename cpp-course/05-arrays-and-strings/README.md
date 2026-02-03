# 05. Arrays and Strings

## Chapter title
**Collections of Data**

## Learning goals
- Use C-style arrays and understand their limits
- Use `std::array` for fixed-size arrays
- Use `std::string` for text
- Work with multidimensional arrays

## 📖 READ

### 1. What is this concept?
Arrays and strings are ways to store multiple pieces of data. An array is a fixed-size sequence of items of the same type. A string is a sequence of characters, usually handled with `std::string` in modern C++.

Arrays let you treat many values as a single unit, which makes loops and algorithms possible. Strings are specialized arrays of characters with extra behavior, like length tracking and concatenation.

### 2. Why does this exist?
Programs need to handle collections: scores, names, coordinates, and more. Without arrays, you would need separate variables for each element, which is not practical. Early C programs used raw arrays and C-style strings, but they were error-prone because they had no bounds checking.

C++ adds safer alternatives like `std::array` and `std::string` to reduce these errors and to make working with data collections easier and more expressive.

### 3. How it works under the hood
Arrays store elements in contiguous memory. That means `a[i]` is just a memory offset from `a[0]`. This makes arrays fast, but it also means the compiler does not automatically check bounds.

`std::string` is usually a small wrapper around a dynamic character buffer. It keeps track of length and capacity, and may allocate memory on the heap. When you append to a string, it may reallocate a larger buffer and copy data.

### 4. Mental model
Imagine an array as a row of numbered boxes on a shelf. Each box holds the same type of object. If you know the index, you know exactly where to find the item.

A string is like a word written on a strip of paper. The strip can grow when you add more letters, but if it runs out of space, you need a longer strip and copy the word over. That is why appending to strings sometimes costs extra time.

### 5. Common mistakes beginners make
- Accessing elements outside the array bounds
- Forgetting that C-style arrays do not store their own size
- Confusing C-style strings (`char[]`) with `std::string`
- Assuming strings are always mutable or always fixed length

### 6. When NOT to use this
- Do not use raw C-style arrays when `std::array` or `std::vector` is available
- Do not use a fixed-size array if the size needs to change dynamically
- Do not use `std::string` for binary data (use `std::vector<char>` instead)

Choose the simplest container that matches your needs.

### 7. How this connects to other topics
Arrays connect directly to pointers because array names decay to pointers. This will matter in the next chapter. Strings connect to memory management and the STL. Understanding arrays will make it easier to understand algorithms, data structures, and performance later in the course.

## Theory explanation
Arrays store elements of the same type in contiguous memory. C-style arrays are fast but unsafe. `std::array` wraps a fixed-size array with safer methods. `std::string` provides dynamic, safe text handling.

## Code examples (C++)
```cpp
int a[5] = {1, 2, 3, 4, 5};
std::array<int, 3> b = {10, 20, 30};

std::string s = "hello";
s += " world";

int grid[2][3] = {{1, 2, 3}, {4, 5, 6}};
```

## Common mistakes
- Accessing out of bounds
- Forgetting that C-style arrays do not know their length
- Mixing `std::string` and C-style strings incorrectly

## Homework (easy / medium / hard)
1. (Easy) Read 5 integers into an array and print them.
2. (Easy) Compute the maximum of an array.
3. (Easy) Reverse a string using a loop.
4. (Medium) Count vowels in a string.
5. (Medium) Rotate an array by one position.
6. (Medium) Sum each row of a 2D array.
7. (Hard) Implement a simple palindrome checker for strings.

## Mini-project (when applicable)
**"Word Analyzer"**  
Read a sentence and output the number of words, vowels, and longest word length.
