# 19. Backend and Systems

## Chapter title
**Networking and Server Concepts**

## Learning goals
- Understand networking basics
- Learn REST concepts
- See how C++ servers are structured

## 📖 READ

### 1. What is this concept?
Backend and systems programming focuses on building services that handle communication, data processing, and storage. These systems sit behind the scenes, serving requests from users or other programs. They often need to be fast, reliable, and stable under heavy load.

In C++, backend development is about writing high-performance servers, handling network connections, and managing resources efficiently.

### 2. Why does this exist?
Modern applications depend on services: APIs, databases, authentication, and real-time communication. Backend systems exist to provide these services. C++ is chosen for backend work when low latency and high throughput are required (trading systems, game servers, high-performance APIs).

### 3. How it works under the hood
Networking is based on sockets. A server opens a socket, listens for incoming connections, and then reads/writes data. TCP provides reliable streams, while UDP provides fast but unreliable packets.

Servers often run in loops, handling events and requests. Many use concurrency (threads or async I/O) to handle multiple clients at once. Data is usually parsed, validated, and then stored or processed.

### 4. Mental model
Think of a backend server as a restaurant kitchen. Clients are customers placing orders (requests). The server reads the order, prepares the response, and sends it back. If the kitchen is slow, customers wait; if it is efficient, many customers can be served quickly.

### 5. Common mistakes beginners make
- Blocking the main thread and freezing all connections
- Ignoring input validation and causing security issues
- Assuming network operations are instant and always succeed
- Forgetting to handle disconnects and timeouts

### 6. When NOT to use this
- Do not use C++ for backend work if rapid development is more important than performance
- Avoid custom server implementations for small projects when existing frameworks are enough
- Do not handle raw sockets unless you need fine-grained control

### 7. How this connects to other topics
Backend systems rely on multithreading, performance, and data structures. Networking builds on file I/O concepts (streams and buffers). Projects later will allow you to design small server-like applications.

## Theory explanation
Backend systems handle communication, data processing, and storage. C++ is used for low-latency systems, trading, game servers, and high-performance services. Understanding networking basics (TCP/UDP, sockets) helps you build reliable services.

## Code examples (C++)
```cpp
// Pseudocode for a server loop
while (server_running) {
    // accept new connection
    // read request
    // process
    // send response
}
```

## Common mistakes
- Blocking the main thread without timeouts
- Ignoring error codes from network calls
- Not validating input data

## Homework (easy / medium / hard)
1. (Easy) Explain TCP vs UDP in a short paragraph.
2. (Easy) Define REST in your own words.
3. (Easy) List 3 real-world backend systems built with C++.
4. (Medium) Draw a simple client-server request flow.
5. (Medium) Research a C++ networking library and summarize it.
6. (Medium) Explain why latency matters in backend systems.
7. (Hard) Design a basic chat server architecture (no code required).

## Mini-project (when applicable)
**"Request-Response Simulator"**  
Create a console app that simulates client requests and server responses using classes.
