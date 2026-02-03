# Final Project (Capstone)

## Objective
Build a complete C++ application that demonstrates mastery of core C++ concepts, modern C++ features, and software design. This is the final portfolio piece for the course.

## Project options (choose one or propose your own)
1. **Mini Task Manager (CLI)**  
   - Tasks with priority, due dates, and tags  
   - Persistent storage (CSV or binary)  
   - Search and filter commands  

2. **File-Based Inventory System**  
   - Add/update/delete items  
   - Stock tracking and reports  
   - Data saved to disk  

3. **Text Adventure Game**  
   - Rooms, items, and inventory  
   - Command parser  
   - Save/load game state  

4. **Custom Project**  
   - Must be approved by your instructor  
   - Must include file I/O and multiple modules  

## Minimum technical requirements
- **Language**: C++17 or C++20
- **Build**: CMake project
- **Structure**: multiple source files (`.cpp`) and headers (`.hpp`)
- **Features**:
  - Classes with constructors/destructors
  - At least one STL container
  - Error handling (exceptions or error codes)
  - File I/O for persistence
  - Clear separation of responsibilities

## Deliverables
1. Source code in a clean repo
2. `README.md` with usage instructions
3. Sample data files (if applicable)
4. Short report on design decisions and trade-offs

## Suggested milestones
1. **Week 1**: Requirements + basic data model
2. **Week 2**: Core functionality + file I/O
3. **Week 3**: Error handling + refactor
4. **Week 4**: Testing + polish

## Evaluation rubric (example)
- **Correctness (30%)**: Works as intended, handles edge cases
- **Design (25%)**: Clean structure, good class responsibilities
- **Modern C++ (15%)**: Proper use of RAII, smart pointers, etc.
- **Usability (15%)**: Clear CLI/UX and documentation
- **Code quality (15%)**: Readability, naming, comments, formatting

## Testing suggestions
- Add unit tests for core logic (optional but encouraged)
- Provide a few sample input files and expected output

## Stretch goals
- Add a simple GUI (optional)
- Add multithreading for background tasks
- Support data export/import
