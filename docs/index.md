---
# 1. FRONT MATTER (REQUIRED)
# The MkDocs title is automatically used for the navigation and the page heading.
# title: Template
subtitle: 
description:
icon:
status:
---


# Micromouse & Line‑Follower Robotics Guide

!!! warning

    This is a draft outline, generated originally by CoPilot, and should not be considered binding. As pages are available, the entries will become highlighted links to those pages. Entries may change or disappear. Do not bookmark links if you see this note on the index page.

## Foundations

### Introduction to Micromouse & Line‑Following
- What the contests are
- Typical robot constraints
- What “success” looks like

### Core Principles of Small Robot Design
- Weight, size, power, cost
- Trade‑offs and design philosophy

### Essential Tools & Skills
- Electronics Knowledge
- Soldering and PCB basics
- Mechanical Design and Manufacture
- Firmware development workflow
- Debugging tools (oscilloscope, logic analyser, etc.)

---

## Electronics for Small Robots

### Power Systems
- Battery Types
- Voltage regulators
- Power distribution and grounding
- Noise considerations

### Microcontrollers & Processing
- Choosing a Microcontroller
- Timers, ADCs, interrupts, DMA
- Development Tools

### Motors & Drivers
- Electric Motor Types
- Motor Driver Electronics
- Motor Driving Software
- Back‑EMF
- Stall current
- PWM strategies

### Encoders
- Odometry Requirements
- Optical, magnetic, reflective
- Quadrature decoding
- Mounting and alignment

### Sensor Overview
- Differences between micromouse and line‑follower sensing
- Reflectivity, geometry, timing, noise

---

## Wall Sensor Systems

### Geometry & Optical Design
- Beam shapes
- Sensor placement
- Wall reflectivity and angle effects

### Emitters
- IR vs visible LEDs
- Forward voltage, current, pulse driving
- Safety and lifetime

### Detectors
- Phototransistors
- Photodiodes
- Transimpedance amplifiers

### Emitter Drive Circuits
- [Simple switched drive](sensors/switched-emitter-drive.md)
- [Constant‑current drive](sensors/basic-constant-current-drive.md)
- [Improved Constant‑current drive](sensors/improved-current-regulation.md)
- Trade‑offs and limitations


### Signal Conditioning
- Filtering
- Amplification
- ADC sampling strategies

### Calibration & Testing
- Normalisation
- Wall distance calibration

---

## Line Sensor Systems

### Geometry & Optical Design
- Digital vs Analogue
- Sensor placement
- Line and Marker Detection

### Emitters
- IR vs visible LEDs
- Forward voltage, current, pulse driving
- Safety and lifetime

### Detectors
- Phototransistors
- Photodiodes
- Transimpedance amplifiers

### Emitter Drive Circuits
- Special Requirements for Line Followers
- Trade‑offs and limitations


### Signal Conditioning
- Filtering
- Amplification
- ADC sampling strategies

### Calibration & Testing
- Line Sensor Calibration
- Marker Sensor Calibration
- Line Reflectivity
- Special Cases

---

## Mechanics & Chassis Design

### Chassis Materials & Construction
- Materials
- Dimensions
- Clearances

### Drive System
- Gearboxes
- Wheel Count
- Wheel Size
- Grip

### Weight Distribution
- Mass (Weight)
- Centre of Gravity
- Inertia

---

## Motion Control

### Kinematics of Differential Drive
- Speed, acceleration, turning

### Controller Design
- System Characterisation
- Controller Types, PD, PID, etc
- Velocity Profiles
- Tuning strategies
- Feedforward terms

### Trajectory Generation
- For micromouse (straight, diagonal, turns)
- For line followers

---

## Micromouse Navigation & Algorithms

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
- IMU (Gyro)
- Sensor fusion
- Drift management

---


## Line Follower Navigation & Algorithms

### Track Representation
- Segments, Markers

### Mapping
- Track Recording

### Path Planning
- Track Playback

### State Estimation
- Odometry
- IMU (Gyro)
- Sensor fusion

---

## Firmware Architecture

### Real‑Time Structure
- Main loop vs RTOS
- Interrupt design

### Modular Code Organisation
- Drivers
- Control loops
- Navigation logic

### Testing & Simulation
- Unit testing
- Simulators
- Logging and telemetry

---

## Building, Debugging, and Iteration

### Prototyping Workflow
- Breadboard → PCB → revision cycles

### Common Failure Modes
- Electrical noise
- Sensor misalignment
- Connectors

### Debugging Techniques
- Oscilloscope use
- Capturing sensor traces
- In Circuit Debugging

### Competition Preparation
- Calibration routines
- Battery management
- Reliability checks

---

## Advanced Topics

### High‑Performance Micromouse
- High‑speed turns
- Diagonal movement
- Dynamic speed control

### Advanced Line‑Follower Techniques
- Multi‑sensor arrays
- High‑speed cornering
- Course straightening

### Increased Downforce
- The Grip Problem
- Suction Fans
- 
---

## Appendices

### Reference Designs
- Example schematics
- PCB layouts

### Component Selection Guides
- Optical Sensors,
- Motor Drivers
- Motors
- Batteries
- IMUs 
- Microcontrollers

### Mathematical Tools
- PID derivations
- Kinematic equations
- Flood‑fill math

