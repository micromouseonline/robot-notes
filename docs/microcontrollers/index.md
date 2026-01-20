---
# 1. FRONT MATTER (REQUIRED)
# The MkDocs title is automatically used for the navigation and the page heading.
# title: Template
subtitle: 
description:
icon:
status:
---

# Microcontrollers

***Placeholder Page - AI suggested Outline***

## 1. Introduction
- What microcontrollers do in small robots  
- How they differ from general‑purpose computers  
- Overview of this section

## 2. Types of Controller
- 8‑bit, 16‑bit, 32‑bit families  
- Common examples (Arduino‑class, ESP32‑class, STM32‑class)  
- Choosing the right controller for a small robot

## 3. GPIO Pins

### 3.1 Digital Pins
- **Input and output**  
  - Reading switches, sensors  
  - Driving LEDs, controlling devices
- **Push‑pull vs open‑drain**  
  - What they mean  
  - When each is used
- **Pull‑up and pull‑down resistors**  
  - Internal vs external  
  - Why floating inputs cause trouble
- **Voltages and currents**  
  - Logic levels (3.3 V vs 5 V)  
  - Safe current limits  
  - Protecting pins from damage

### 3.2 Analog Pins
- What “analog input” really means  
- Typical voltage ranges  
- Common uses in robotics (sensors, battery monitoring)

## 4. PWM
- How PWM works  
- Duty cycle and frequency  
- Using PWM for motors, LEDs, and servos

## 5. ADC
- Resolution (8‑bit, 10‑bit, 12‑bit, etc.)  
- Sampling rate  
- Noise and filtering basics  
- Practical examples with sensors

## 6. Interrupts
- What interrupts are and why they matter  
- External interrupts (buttons, sensors)  
- Timer interrupts  
- Debouncing and timing considerations

## 7. Timers
- What hardware timers do  
- Periodic tasks  
- Generating PWM  
- Measuring time intervals (pulse width, frequency)

