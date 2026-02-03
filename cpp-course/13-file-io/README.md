# 13. File I/O

## Chapter title
**Reading and Writing Data**

## Learning goals
- Read and write text files
- Work with binary files
- Understand simple serialization

## 📖 READ

### 1. What is this concept?
File I/O (input/output) is how a program reads data from files and writes data back to disk. It is the difference between a program that forgets everything when it closes and a program that can save and load information.

In C++, file I/O is handled through streams like `std::ifstream` and `std::ofstream`. These streams let you treat files as if they were input/output devices, similar to `std::cin` and `std::cout`.

### 2. Why does this exist?
Programs need persistence: saving settings, recording logs, storing data. Without file I/O, every program would be temporary. Before file I/O libraries, programmers handled files with low-level system calls, which were complex and error-prone.

C++ provides stream-based file I/O to make common tasks easy while still allowing low-level control when needed.

### 3. How it works under the hood
When you open a file stream, the runtime requests a file handle from the operating system. Reads and writes happen through buffers for efficiency. Closing the stream releases the handle.

Text mode interprets bytes as characters (and may translate line endings). Binary mode treats bytes as raw data. Serialization is the process of converting data structures into a storable byte format and later reconstructing them.

### 4. Mental model
Think of files as notebooks. Reading is like opening the notebook and reading pages. Writing is like adding notes to the notebook. Binary files are like notebooks written in a special code: faster to write and smaller, but not readable without a translator.

### 5. Common mistakes beginners make
- Forgetting to check if the file opened successfully
- Assuming a file exists without verifying
- Mixing text and binary formats
- Writing data in one format and trying to read it in another

### 6. When NOT to use this
- Do not use file I/O for short-lived data that only matters during program execution
- Avoid binary files if you need easy human readability
- Avoid manual serialization if a standard format (JSON/CSV) is sufficient for the task

### 7. How this connects to other topics
File I/O builds on strings, streams, and error handling. It connects to data structures because you often store collections. Exceptions and RAII help manage file resources safely. Projects later will rely heavily on persistence.

## Theory explanation
File I/O enables persistent storage. Use `std::ifstream` for reading and `std::ofstream` for writing. Binary files store raw bytes and are faster and smaller but less human-readable.

## Code examples (C++)
```cpp
std::ofstream out("data.txt");
out << "Hello file\n";
out.close();

std::ifstream in("data.txt");
std::string line;
std::getline(in, line);
```

## Common mistakes
- Forgetting to check if a file opened successfully
- Writing binary data as text or vice versa
- Not closing files (though RAII handles this in streams)

## Homework (easy / medium / hard)
1. (Easy) Write a program that saves 5 numbers to a file.
2. (Easy) Read the numbers back and print the sum.
3. (Easy) Append a new line to an existing file.
4. (Medium) Store and load a list of student records.
5. (Medium) Write and read a binary file of integers.
6. (Medium) Implement a simple CSV reader.
7. (Hard) Build a small serialization format for a custom struct.

## Mini-project (when applicable)
**"Logbook"**  
Create a program that appends daily notes to a text file with timestamps.
