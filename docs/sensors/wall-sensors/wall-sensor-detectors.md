---
# 1. FRONT MATTER (REQUIRED)
# The MkDocs title is automatically used for the navigation and the page heading.
# title: Template
subtitle: 
description:
# icon: octicons/dot-fill-16
# icon: octicons/dot-16
# icon: octicons/dash-16
# icon: octicons/chevron-right-12
status:
---


# Wall Sensor Detector Types


There are many options for sensing the walls in a micromouse. They are not (yet) describe here but include:

 - time-of-flight optical sensors
 - ultrasonic transceivers
 - 2D and 1D cameras
 - geometric optical sensors

On these pages though we consider only reflected light optical methods using an LED to illuminate the wall and a device to measure the reflected light power.

For the kinds of reflected-light sensors described here, there are two basic choices for the detector, each with their own pros and cons. By far the most common choice is a phototransistor with a single load resistor. Less frequently, you might find photodiodes used in place of phototransistors. They can be used with a single load resistor but may benefit from adding a simple amplifier.

- [Phototransistors](./wall-sensor-phototransistor.md)
- [Photodiodes](./wall-sensor-photodiode.md)

## Summary

Phototransistor give larger signals and simplified circuits at the expense of slower responses, reduced dynamic range, and poorer linearity.
Photodiodes offer higher speeds, larger dynamic range, and greater linearity at the expense of weaker outputs and higher impedance.

### Comparison: Photodiode and Phototransistor Configurations

| Feature | Phototransistor | Photodiode (Load Resistor) | Photodiode (TIA Mode) |
| :------ | :-------------- | :------------------------- | :-------------------- |
| **Response Speed** | **Relatively Slow** (µs). Limits sample rate. | **Fast** (ns to µs). Speed limited by RC constant. | **Excellent** (ns to µs). Best balance of speed/gain. |
| **Linearity** | **Fair.** Non-linear gain at all light levels. | **Excellent.** Very linear current-to-light ratio. | **Excellent.** Maintains linearity via virtual ground. |
| **Circuit Type** | Simple Emitter-Follower    | Simple Voltage Divider      | Op-Amp Feedback Loop         |
| **Resistor Range** | 470 Ω to 2.2 kΩ            | 10 kΩ to 100 kΩ             | 10 kΩ to 100 kΩ+               |
| **Output Level** | **High.** Easy to read with a simple resistor. | **Very Low.** Requires very large resistors for usable voltage. | **Adjustable.** $R_f$ allows for high gain/voltage. |
| **Source Impedance** | **Medium.** Depends on the load resistor. | **High.** High impedance makes it prone to noise. | **Low.** Active output is ideal for driving ADCs. |
| **Complexity** | **Low.** Simple voltage divider. | **Low.** Simple voltage divider. | **Medium.** Requires Op-Amp and stability capacitor. |
| **Micromouse usage** | **Very common** due to strong signal and easy ADC interfacing | **Less common** but useful for high‑performance or high‑speed sensing | **Rare** due to additional circuit complexity |
