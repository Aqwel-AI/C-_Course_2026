# 18. Game Dev Basics

## Chapter title
**Game Loops and Engine Concepts**

## Learning goals
- Understand a game loop
- Learn basic ECS (Entity-Component-System) ideas
- Get an overview of C++ in game engines like Unreal

## 📖 READ

### 1. What is this concept?
Game development basics focus on the real-time nature of games. A game is a loop that repeatedly processes input, updates the world, and renders a new frame. This loop runs many times per second.

The goal is to keep the game responsive and consistent. ECS (Entity-Component-System) is a popular design approach for organizing game objects in a flexible way.

### 2. Why does this exist?
Games are interactive and must respond to player input instantly. Unlike a normal program that runs once and exits, a game runs continuously until the player quits. That requires a structure that repeats the same sequence every frame.

C++ is widely used in game development because it delivers performance, low-level control, and the ability to integrate with graphics and physics libraries.

### 3. How it works under the hood
The game loop is a timed loop. It calculates how much time has passed, updates game logic, and renders graphics. ECS typically stores components in arrays for cache-friendly access, while systems iterate through those arrays to update behavior.

Rendering often uses a graphics API (like OpenGL, Vulkan, or DirectX) that communicates with the GPU. The CPU prepares data, and the GPU draws it.

### 4. Mental model
Imagine a movie projector that updates the screen 60 times per second. Each update is a “frame.” The game loop is the machine that produces these frames. ECS is like a factory where each component is a part (health, position, velocity), and each system is a worker that processes all parts of a certain type.

### 5. Common mistakes beginners make
- Trying to do everything inside the render step
- Ignoring timing and frame rate issues
- Mixing data and behavior too tightly
- Using slow data structures that cause frame drops

### 6. When NOT to use this
- Avoid building your own engine if a simple library or engine already solves the problem
- Do not overbuild ECS for tiny projects
- If your game is small, a simpler object-oriented approach may be enough

### 7. How this connects to other topics
Game development relies on performance, memory management, and data structures. It also depends on multithreading for background tasks and asset loading. The project section will bring these ideas together in practical work.

## Theory explanation
Game development often requires real-time updates. A game loop handles input, updates game state, and renders output. ECS is a design pattern that separates data (components) from behavior (systems), improving flexibility and performance.

## Code examples (C++)
```cpp
bool running = true;
while (running) {
    // 1) Handle input
    // 2) Update game state
    // 3) Render frame
}
```

## Common mistakes
- Doing heavy work on the render path
- Mixing game logic with rendering too tightly
- Ignoring fixed timestep vs variable timestep issues

## Homework (easy / medium / hard)
1. (Easy) Write pseudocode for a game loop.
2. (Easy) Define Entity, Component, System in your own words.
3. (Easy) Research one C++ game engine and summarize.
4. (Medium) Implement a basic text-based game loop.
5. (Medium) Create a simple ECS-like data layout with structs.
6. (Medium) Explain fixed timestep vs variable timestep.
7. (Hard) Prototype a minimal component system with arrays.

## Mini-project (when applicable)
**"Text RPG Tick"**  
Build a console-based game loop with a player that can move and collect items.
