---
# 1. FRONT MATTER (REQUIRED)
# The MkDocs title is automatically used for the navigation and the page heading.
# title: Template
subtitle: 
description:
# icon: octicons/dot-fill-16
icon: octicons/dot-16
# icon: octicons/dash-16
# icon: octicons/chevron-right-12
status:
---

# Advanced Emitter Control

This page will examine some other options for controlling the emitters.

## Better Current Sink

Improved constant current circuit with better regulation. More parts though.

### MOSFETS

One of the improvements for the basic switched emitter control was to replace the bipolar transistor with a MOSFET. In the basic constant current circuit, the MOSFET can also be simply swapped with the BJT - the source goes to the current sense resistor, the gate to the GPIO and the Drain to the LED cathode.

There are, however, a couple of issues that should give you pause for thought.

*** Circuit for MOSFET version ***

The first problem is finding a suitable device. MOSFETS are voltage operated devices. As the voltage on the gate, $V_{GS}$, increases, the resistance between Drain and Source will decrease. The gate draws very little current when operating normally aside from the brief charge/discharge current associated with the gate capacitance during switching.. If you look at datasheets for typical MOSFET devices, you will see a value quoted for the gate-source threshold voltage ($V_{GS(th)}$). This is the gate voltage at which the body of the MOSFET only just begins to conduct. The Drain-Source resistance, $R_{DS}$, will still be quite high. Typical values for ($V_{GS(th)}$) are given for drain currents in the hundreds of microAmps, not the tens or hundreds of milliAmps the sensor needs.  

As $V_{GS}$ increases, the value of $R_{DS}$ will fall, often to quite small values. Elsewhere in the datasheet, you will often find some minimum value, $R_{DS(on)}$ with a corresponding $V_{GS}$. Alternatively, you might see a maximum continuous current, again with an associated $V_{GS}$. Although the datasheet might indicate that the maximum current can be large, that will be with the lowest value for $R_{DS}$. High-performance MOSFETs may have $R_{DS(on)}$ as small as a few tens of milliOhms while small through-hole parts might only be able to get $R_{DS(on)}$ down to one or two Ohms.

It is important to realise that, while a low $V_{GS(th)}$ might be essential for operation in this circuit, it is not a reliable guide to the $V_{GS}$ required for correct operation at the intended LED current.

The ZVN4206A is an attractive MOSFET in a convenient TO92 package. See the [datasheet](https://www.diodes.com/assets/Datasheets/ZVN4206A.pdf){target="_blank"}

In the datasheet for the ZVN4206A, $V_{GS(th)}$ is given as no more than 3 Volts. It could, then, be turned on by a GPIO pin delivering 3.3 Volts. However, this overlooks the voltage across the current regulating resistor. The key parameter for the MOSFET is the voltage between gate and source, not the voltage between the gate and ground.

Remember that common LED currents might be in the 100mA to 200mA range for a phototransistor detector but much higher pulse currents may be desired when a photodiode detector is used.

Suppose then that you want 150mA through the LED and the current sense resistor is 5 Ohms. That resistor will drop (0.15 * 5) = 0.75 Volts. That becomes the voltage at the MOSFET source. Now you need to raise the gate voltage by at least another 3 Volts just to get the transistor operating. Clearly, only a 5 Volt GPIO output can manage that.

As the current through the MOSFET rises, so too does the voltage across the sense resistor, reducing $V_{GS}$ from its initial value of 5 Volts. This increases the MOSFET resistance and raises $R_{DS}$ until an equilibrium is reached and the current becomes stable.

Just like the bipolar version of this regulator, there must still be some headroom in the supply voltage for the MOSFET to operate correctly. If the value of $R_{DS(on)}$ cannot fall low enough with the available $V_{GS}$, the transistor will saturate and regulation is no longer possible. The supply voltage must exceed the sum of the LED forward voltage. the sense resistor voltage drop and the MOSFET' required $V_{DS}$ for regulation.

In short, it should be possible to replace the bipolar transistor used in the basic constant current circuit with a ZVN4206A MOSFET. BUT **only** if you have a 5 Volt GPIO pin. With a 3.3 Volt GPIO level, it is unlikely to work without very small sense resistor values. Even for the same part number, some devices can have $V_{GS(th)}$ as low as 1.3 Volts while for others it may be 3.0 Volts. You really want more certainty than that. In fact, a device like the ZVN4206 is going to be inherently unreliable with only a 3.3 Volt gate drive.

There are MOSFET devices with lower values for $V_{GS(th)}$ and which can reach low values of $R_{DS}$ even for relatively small gate voltages. These are typically described as "logic-level" MOSFETS, designed to switch on fully with a 3.3V logic '1' from a GPIO pin. Unfortunately, these are rare in friendly, small packages for through-hole use. They are, however, plentiful in SMT packages like SOT-23. When selecting a device to be used in this current regulating circuit, always bear in mind the additional voltage at the Source pin due to the drop across the current sense resistor.


**More Details to follow**

## Multiple Output Levels

The requirements for running along orthogonal straights and diagonal straights are a little different since the range of expected sensor signals changes with the orientation and distance of the walls. Diagonal running can produce much stronger responses than orthogonal paths. To deal with that, some builders have a reduced emitter output that is used only for diagonals.

**Details to follow**




