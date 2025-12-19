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

## Reduced Interference

It should be fairly clear that, by only lighting up one LED at a time, you can be sure that other detectors are not going to see light reflected from unexpected places. For example, the front sensors will easily detect light from side walls if the side emitters are illuminated. This effect gets worse as the mouse approaches a dead end and light from the side sensors can get reflected off the side walls onto  a wall ahead where is can easily be picked up by the front detectors.

It may be safe to light up the two side sensors together, or the two front sensors together but certainly not a side and front sensor on the same side. For best reliability, light each sensor individually.

Depending on your detector circuit and software configuration, it can be possible that the signal of one sensor is affected by the signal from the previous sensor. This should be rare but it is worth experimenting with the order in which the sensors are read and the interval between readings if you suspect that one sensor is interfering with another.

## Extra Bright Illumination

In normal, continuous illimination a sensor LED might only be able to handle a relatively low current without overheating. For the SFH4550 IR LED, for example, that limit is only about 100mA. However, the same device is able to handle currents as high as 1 Amp (10x bigger) for short periods up to about 100us. The light output is proportional to current so you can create very bright pulses of light but only for a short time. The detector and processor typically only need a few tens of microseconds at most to capture the resulting reflection. 

Pulsing the light like this reduces the average amount of current needed for each LED. If you were to turn each one on for just 25us out of every 1000us and provide a 250mA current pulse, the average current draw would be only 6mA and yet you are getting light pulses that are 2.5 times as bright as would be available for a continuous 100mA illumunation. The saving is huge - especially for half-size robots where the batteres are necessarily much smaller.

## Cancellation of Ambient Illumination

It is all well and good to turn on the emitter LED and then measure the amount of light reflected by the walls. However, some of that light comes from the other sources of illumination in the area - the ambient illumination. By making only one measureent, it is not possible to work out anything about the ambient light levels. Remember, if you are using IR sensors, you are unable to see any of that anyway so you cannot make a judgement about it either.

The usual method for handling this is to read the detectors twice. First, take a reading with the LED off. This is the ambient light level. Then, turn on the LED, wait a few microseconds to make sure everything is stable and then take another reading. This rading, coming very soon after the ambient reading, should have the same ambient component plus whatever is purely the result of any nearby objects reflecting the LED light.

Now you can just subtract the ambient reading from the 'lit' reading to get the raw, reflected intensity reading:

$$ I_{RAW} = I_{LIT} - I_{AMB} $$

