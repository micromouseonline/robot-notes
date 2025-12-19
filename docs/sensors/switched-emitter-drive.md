---
layout: default
title: Switched Drivers
parent: Sensors
nav_order: 20
# Leave has_children and permalink out
---

# Switched Emitter Driving

The fundamental task of the wall sensor emitters is to shine light on the walls so that it can be detected by some other device. It is nether practical, nor desirable to just turn on a LED and leave it on. Not only is the available light output not likely to be sufficient when the LED is operating safely within its limits, the light from each LED will also illuminate detectors other than the one for which it is intended.

A better solution is to turn on each LED in turn for a brief period and measure the light reflected from just that LED. This brings a few benefits:

 - Reduced interference from the other sensors
 - Extra bright pulses of light for less current
 - Cancellation of ambient illumination.

### Reduced Interference

It should be fairly clear that, by only lighting up one LED at a time, you can be sure that other detectors are not going to see light reflected from unexpected places. For example, the front sensors will easily detect light from side walls if the side emitters are illuminated. This effect gets worse as the mouse approaches a dead end and light from the side sensors can get reflected off the side walls onto  a wall ahead where is can easily be picked up by the front detectors.

It may be safe to light up the two side sensors together, or the two front sensors together but certainly not a side and front sensor on the same side. For best reliability, light each sensor individually.

Depending on your detector circuit and software configuration, it can be possible that the signal of one sensor is affected by the signal from the previous sensor. This should be rare but it is worth experimenting with the order in which the sensors are read and the interval between readings if you suspect that one sensor is interfering with another.

### Extra Bright Illumination

In normal, continuous illimination a sensor LED might only be able to handle a relatively low current without overheating. For the SFH4550 IR LED, for example, that limit is only about 100mA. However, the same device is able to handle currents as high as 1 Amp (10x bigger) for short periods up to about 100us. The light output is proportional to current so you can create very bright pulses of light but only for a short time. The detector and processor typically only need a few tens of microseconds at most to capture the resulting reflection. 

Pulsing the light like this reduces the average amount of current needed for each LED. If you were to turn each one on for just 25us out of every 1000us and provide a 250mA current pulse, the average current draw would be only 6mA and yet you are getting light pulses that are 2.5 times as bright as would be available for a continuous 100mA illumunation. The saving is huge - especially for half-size robots where the batteres are necessarily much smaller.

### Cancellation of Ambient Illumination

It is all well and good to turn on the emitter LED and then measure the amount of light reflected by the walls. However, some of that light comes from the other sources of illumination in the area - the ambient illumination. By making only one measureent, it is not possible to work out anything about the ambient light levels. Remember, if you are using IR sensors, you are unable to see any of that anyway so you cannot make a judgement about it either.

The usual method for handling this is to read the detectors twice. First, take a reading with the LED off. This is the ambient light level. Then, turn on the LED, wait a few microseconds to make sure everything is stable and then take another reading. This rading, coming very soon after the ambient reading, should have the same ambient component plus whatever is purely the result of any nearby objects reflecting the LED light.

Now you can just subtract the ambient reading from the 'lit' reading to get the raw, reflected intensity reading:

$$ I_{RAW} = I_{LIT} - I_{AMB} $$


## Switching Options

It seems unlikely that you would want to use anything mechanical so the usual choice is between different types of transistor. There are dedicated LED driver ICs but these don't always cater for the specific needs of micromouse robots. The choice then is probably limited to one of these transistor types:

- Single bipolar transistor
- Darlington bipolar transistor
- MOSFET transistor

### Single Bipolar Transistor

This is one of the simplest choices. All you need is a suitable bipolar transistor and a couple of resistors to build your circuit:

![single transistor](../assets/sensors/single-switching-transistor.png)

The circuit has some fairly arbitrary values so thet's take them in turn and look at how to choose your own values.

#### The LED

Arguably the most important component. You may choose Infra Red (IR) or visible light devices. Aside from any optical properties, all LEDs will result in a forward voltage drop when current flows through them. For a typical IR LED - the SFH4550 - this will be about 2.0 Volts at 500mA, rising to 2.5 Volts at 1 Amp. This voltage will need to be taken into account when calulating the current limit resistor R8.

For a visible light LED like the TLCR5800, that voltage drop can be much higher and might approach 3.5 Volts at 500mA, rising to 4.7 Volts at 1 Amp.

#### Current Limit Resistor R8

This resistor is used to limit the current that can flow through the LED. If the current is too high, or allowed to flow for too long, the LED can be damaged or destroyed. There is a power supply, $V_{LED}, that can provide the current needed. Assume for a moment that the transistor, Q2, can be turned fully on and the voltage between collector and emitter, $V_{CE}, is 0.2 Volts. It may be a little higher or lower, depending on the actual transistor type and the current we want through the LED.

The LED and the transistor then may account for about 2.5 Volts and we should be able to have $V_{LED}$ as low as 3.3 Volts and stil get the circuit to operate.

Suppose $V_{LED}$ is 3.3 Volts. There is $3.3 - 2.5 = 0.8 Volts$ across R8 and, if we want 500mA to flow, R8 must have the value $0.8/0.5 = 1.6\Omega$

That all seems well and good so long as the 3.3 Volt supply can provide the required current. It should be clear that, if the supply were 5 Volts, the value of R8 should increase to $(5.0 - 2.5) = 2.5/0.5 = 5\Omega$ 

For many micromouse designs, 250mA through an IR LED is sufficient and, with a 3.3 Volt supply, R8 could be 5.6 Ohms. For others, the goal might be nearer 1 Amp.

But, what if the design required  a visible light LED like the TLCR5800. Now the forward voltage drop of the LED exceeds the available voltage from a 3.3 Volt supply and only a 5.0 Volt supply will do.

#### The Transistor, Q2

It is always possible to go exotic with transistor choices but simple is often better. Here the BC337-40 has been chosen because it is cheap, easy to find and has characteristics that are adequate for most use cases. This transistor has a current gain of about 100 even at the kinds of collector current we have considered. For safety though, consider the current gain to be just 50 and the maximum collector current we need to be just 500mA. That means the base will need $500/50 = 10mA$ which is well within he capabilities of most microprocessor IO pins. 


#### The base resistor, R9
To the processor, the base will just look like a diode connected to ground. Suppose the processor IO pin high voltage is 3.3 Volts. To limit the current from the processor to the 10mA we need, the base resistor, R9, should be chosen to be $(3.3 - 0.7)/260\Omega$.  The circuit has a value of 220 Ohms for a bit of extra margin.

If the LED current required is substantially higher, the base current will need to be higher as well. Do not reduce the base resistor any more than needed to get the required transistor base current. You microcontroller will not play well with large current demands from its IO pins. 

If you are expecting higher output currents from the IO pins, check to see if your processor of choice has settings that limit the amount of drive available. The STM32 series do this as a power saving option so make sure sufficient drive is available.

--- 

So there we have it a simple, low component count LED emitter drive. What more could we need?
