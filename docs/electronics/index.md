---
# 1. FRONT MATTER (REQUIRED)
# The MkDocs title is automatically used for the navigation and the page heading.
# title: Template
subtitle: 
description:
icon:
status:
---

# Electronics for Small Robot Builders
*A beginner‑friendly article series*

***Placeholder Page - AI suggested Outline***


## 1. Introduction
- **What electronics knowledge you actually need for small robots**
- **How to use this guide**
- **Tools you’ll want on your bench**  
  Soldering iron, cutters, breadboard, etc.

## 2. Basics
- **Electricity in one page**
  - Voltage, current, resistance  
  - Power and why it matters for motors
- **Ohm’s Law and why it matters**
  - Practical examples: LED resistor sizing, sensor pull‑ups
- **Circuit diagrams**
  - Symbols, conventions, ground, nets, reference designators  
  - How to follow a schematic like a story
- **Power Supply**
  - 3.3 V vs 5 V logic  
  - Battery packs for small robots  
  - Motor supply vs logic supply
  - Power Budget and Management
- **Breadboards and prototyping basics**
  - How breadboards are internally connected  
  - Common mistakes beginners make

## 3. Passive Components
- **Resistors**
  - Fixed, variable, pull‑ups, pull‑downs  
  - Power ratings and why they matter
- **Capacitors**
  - Ceramic vs electrolytic  
  - Decoupling and smoothing  
  - Why robots need lots of them
- **Inductors**
  - Basic behaviour  
  - Where they show up in robotics (DC‑DC converters, motors)
- **Connectors**
  - JST, Dupont, screw terminals  
  - Polarity, strain relief, avoiding accidental unplugging

## 4. Semiconductors
- **Diodes**
  - Rectifiers, flyback diodes for motors
- **LEDs**
  - Indicators, status lights, current limiting
- **Transistors**
  - Bipolar (NPN/PNP)  
  - MOSFETs (logic‑level vs not)  
  - Using transistors to switch motors, solenoids, and lights
- **Voltage regulators**
  - Linear vs switching  
  - Why robots often need both

## 5. Integrated Circuits 
- **Op‑amps** (buffering, filtering)
- **555 timer** (simple PWM, delays)
- **Logic ICs** (level shifting, gates)
- **Motor drivers** (DRV8833, etc.)
- **Microcontrollers** (very high‑level overview)

## 6. Circuit Debugging
- **Multimeter**
  - Measuring voltage, continuity, resistance  
  - Avoiding common mistakes
- **Oscilloscope**
  - What it shows and why it’s useful  
  - Reading PWM, noise, motor spikes
- **Debugging workflow**
  - Divide and conquer  
  - Check power first  
  - Check connectors
  - Finding shorts and bad grounds
- **Real‑world examples**
  - Robot resets when motors start  
  - Sensor readings full of noise
  - Common pitfalls and how to avoid them
