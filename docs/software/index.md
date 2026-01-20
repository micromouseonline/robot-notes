---
# 1. FRONT MATTER (REQUIRED)
# The MkDocs title is automatically used for the navigation and the page heading.
# title: Template
subtitle: 
description:
icon:
status:
---

# Software

***Placeholder Page - AI suggested Outline***

## 1. Introduction
- What “software” means in the context of small robots  
- How embedded programming differs from desktop programming  
- Overview of this section

## 2. Language Choices and Tools
- Common languages for microcontrollers (C, C++, MicroPython, Rust, Arduino‑style C++)  
- Toolchains, IDEs, and build systems  
- Choosing the right language for your robot project

## 3. Basic Programming Concepts
- **Variables and loops**  
  - Types, scope, iteration patterns
- **Functions and classes**  
  - Encapsulation, modularity, reusability
- **Arrays and lists**  
  - Fixed vs dynamic storage  
  - How microcontrollers handle them
- **Code layout**  
  - Organising files  
  - Naming conventions  
  - Keeping code readable

## 4. Embedded‑Specific Concepts
- **Timing and timers**  
  - Delays, periodic tasks, non‑blocking code
- **Memory**  
  - RAM vs flash  
  - Stack vs heap  
  - Avoiding fragmentation
- **Speed**  
  - Why performance matters on small controllers  
  - Common bottlenecks
- **Debugging approaches**  
  - Print debugging  
  - LED signalling  
  - Hardware debuggers
- **Interrupts**  
  - When to use them  
  - Pitfalls and best practices
- **Getting code onto the controller**  
  - Bootloaders  
  - Programmers  
  - Upload protocols

## 5. Design Philosophies
- **Building for execution speed and efficient memory usage**  
  - Thinking in terms of constraints  
  - Avoiding unnecessary work
- **Working without floating‑point operations**  
  - Fixed‑point arithmetic  
  - Lookup tables  
  - Scaling and integer maths

## 6. Build and Debug
- Overview of the build process  
- Understanding compiler output  
- Using debugging tools effectively  
- Project structure and reproducible builds  
- See: `build-and-debug/index.md`
