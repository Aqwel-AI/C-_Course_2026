# 08. Object-Oriented Programming

## Chapter title
**Classes, Objects, and Polymorphism**

## Learning goals
- Define classes and create objects
- Use constructors and destructors
- Apply encapsulation and access control
- Implement inheritance and polymorphism
- Use virtual functions and interfaces

## 📖 READ

### 1. What is this concept?
Object-oriented programming (OOP) is a way to organize code around “objects” that combine data and behavior. Instead of keeping data in one place and functions in another, OOP groups them together in classes. An object is just an instance of a class.

OOP helps you model real-world systems: a `Car` has data (speed, fuel) and behavior (accelerate, brake). In software, OOP gives structure, clarity, and reuse.

### 2. Why does this exist?
As programs grow, plain functions and global data become hard to manage. OOP exists to:
- Encapsulate complexity (hide internal details)
- Encourage reuse through inheritance
- Provide flexible design with polymorphism

C++ specifically needs OOP because it is used for large, long-lived systems. Without structure, big C++ projects become chaotic and difficult to maintain.

### 3. How it works under the hood
A class defines a layout in memory: its data members are stored in order, and each object uses that layout. Methods are just functions that take a hidden pointer called `this`.

Polymorphism uses **virtual tables** (vtables). When you call a virtual function, the program looks up the correct function in the vtable based on the actual object type. That lookup happens at runtime, enabling dynamic behavior.

### 4. Mental model
Think of a class as a blueprint. An object is a building created from that blueprint. Constructors build it, destructors tear it down.

Inheritance is like a specialized blueprint that extends a base design. A `Dog` is an `Animal` with extra features. Polymorphism is like calling a general “speak” command and letting each animal decide how to respond.

### 5. Common mistakes beginners make
- Forgetting virtual destructors in base classes
- Exposing internal data directly instead of controlling access
- Overusing inheritance when composition is simpler
- Object slicing by passing derived objects by value

### 6. When NOT to use this
- Do not force OOP in small scripts or simple procedural code
- Avoid deep inheritance hierarchies that are hard to understand
- Avoid base classes if you do not need polymorphism

Sometimes a simple struct with functions is clearer than a complex class hierarchy.

### 7. How this connects to other topics
OOP builds on functions and memory management. Constructors/destructors are tied to RAII. Polymorphism uses pointers and references. Templates and STL containers later will store objects and manage them with value semantics or pointers.

## Theory explanation
OOP models real-world concepts as classes and objects. Encapsulation hides internal details, inheritance allows code reuse, and polymorphism enables a unified interface for different types.

## Code examples (C++)
```cpp
class Animal {
public:
    virtual void speak() const {
        std::cout << "Animal sound\n";
    }
    virtual ~Animal() = default;
};

class Dog : public Animal {
public:
    void speak() const override {
        std::cout << "Woof!\n";
    }
};
```

## Common mistakes
- Missing `virtual` destructor in base classes
- Slicing objects by passing by value
- Exposing data members instead of using accessors

## Homework (easy / medium / hard)
1. (Easy) Create a `Person` class with name and age.
2. (Easy) Add getters and setters with validation.
3. (Easy) Create a constructor and destructor that log messages.
4. (Medium) Build a class hierarchy: `Shape` -> `Circle`, `Rectangle`.
5. (Medium) Use polymorphism to store shapes in a vector.
6. (Medium) Implement an interface-like class using pure virtuals.
7. (Hard) Demonstrate object slicing and fix it.

## Mini-project (when applicable)
**"Library Manager"**  
Design classes for `Book`, `Member`, and `Library` with basic operations.
