---
# 1. FRONT MATTER (REQUIRED)
# The MkDocs title is automatically used for the navigation and the page heading.
title: Outline and TOC
subtitle: 
description:
icon:
status:
---

# Micromouse & Line‑Follower Robotics Guide

## Part I — Foundations

### Introduction to Micromouse & Line‑Following
- What the contests are
- Typical robot constraints
- What “success” looks like

### Core Principles of Small Robot Design
- Weight, size, power, cost
- Trade‑offs and design philosophy

### Essential Tools & Skills
- Soldering and PCB basics
- Firmware development workflow
- Debugging tools (oscilloscope, logic analyser, etc.)

---

## Part II — Electronics for Small Robots

### Power Systems
- LiPo batteries
- Voltage regulators
- Power distribution and grounding
- Noise considerations

### Microcontrollers & Processing
- Choosing an MCU
- Timers, ADCs, interrupts, DMA
- Clocking and power modes

### Motors & Drivers
- DC motors, coreless motors, brushless options
- H‑bridges and current limits
- Thermal considerations

### Encoders
- Optical, magnetic, reflective
- Quadrature decoding
- Mounting and alignment

### Sensor Overview
- Differences between micromouse and line‑follower sensing
- Reflectivity, geometry, timing, noise

---

## Part III — Sensor Systems (Deep Dive)

### Emitters
- IR vs visible LEDs
- Forward voltage, current, pulse driving
- Safety and lifetime

### Detectors
- Phototransistors
- Photodiodes
- Transimpedance amplifiers

### Emitter Drive Circuits
- Simple switched drive
- Reservoir‑capacitor‑assisted drive
- Constant‑current drive (BJT and MOSFET)
- Trade‑offs and limitations

### Geometry & Optical Design
- Beam shaping
- Sensor placement
- Wall reflectivity and angle effects

### Signal Conditioning
- Filtering
- Amplification
- ADC sampling strategies

### Calibration & Testing
- Wall distance calibration
- Line reflectivity calibration
- Temperature effects

---

## Part IV — Mechanics & Chassis Design

### Chassis Materials & Construction
- 3D printing, carbon fibre, FR4

### Wheel Design
- Diameter, grip, inertia

### Gearboxes & Direct Drive

### Weight Distribution & Centre of Gravity

---

## Part V — Motion Control

### Kinematics of Differential Drive
- Speed, acceleration, turning

### PID Control
- Tuning strategies
- Feedforward terms

### Trajectory Generation
- For line followers
- For micromouse (straight, diagonal, turns)

### Motor Characterisation
- Back‑EMF
- Stall current
- PWM strategies

---

## Part VI — Navigation & Algorithms

### Maze Representation
- Cells, walls, bitfields

### Mapping
- Flood‑fill
- Distance transforms
- Wall‑following

### Path Planning
- Shortest path
- Speed‑optimised path

### State Estimation
- Odometry
- Sensor fusion
- Drift management

---

## Part VII — Firmware Architecture

### Real‑Time Structure
- Main loop vs RTOS
- Interrupt design

### Modular Code Organisation
- Drivers
- Control loops
- Navigation logic

### Testing & Simulation
- Unit testing
- Maze simulators
- Logging and telemetry

---

## Part VIII — Building, Debugging, and Iteration

### Prototyping Workflow
- Breadboard → PCB → revision cycles

### Common Failure Modes
- Electrical noise
- Sensor misalignment
- Motor imbalance

### Debugging Techniques
- Oscilloscope use
- Capturing sensor waveforms
- Motor current monitoring

### Competition Preparation
- Calibration routines
- Battery management
- Reliability checks

---

## Part IX — Advanced Topics

### High‑Performance Micromouse
- High‑speed turns
- Diagonal movement
- Dynamic speed control

### Advanced Line‑Follower Techniques
- Multi‑sensor arrays
- High‑speed cornering

### Custom Electronics
- Designing your own motor drivers
- Custom sensor boards

### Machine Learning (Optional)
- Line classification
- Predictive control

---

## Part X — Appendices

### Reference Designs
- Example schematics
- PCB layouts

### Component Selection Guides
- LEDs, photodiodes, motors, MCUs

### Datasheet Interpretation

### Mathematical Tools
- PID derivations
- Kinematic equations
- Flood‑fill math
