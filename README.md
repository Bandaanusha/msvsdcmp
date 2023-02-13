# SCL 180nm Comparator IP

## Introduction

A comparator is a device that compares two analog inputs and outputs a digital signal indicating which input is larger. So it has two analog input terminals and one binary digital output. When the difference between two analog input signals approach zero, noise on the inputs will cause spurious switching of digital output. This rapid change in output due to noise can be prevented by hysteresis. Hysteresis is switching the output high or low at different input signal levels. In place of one switching point, hysteresis introduces two: one for rising edge, and one for falling edge of voltage or current. The difference between the higher-level trip value (VH) and the lower-level trip value (VL) equals the hysteresis voltage (HYST).

## Specifications

## Schematic

![circuitschm](https://user-images.githubusercontent.com/62790565/218436868-936908e6-c0dc-4b51-8517-f5e12ccae5d3.png)

## Pre-Layout Simulation

<img width="802" alt="Screenshot 2023-02-13 223058" src="https://user-images.githubusercontent.com/62790565/218523018-afecd5ea-39d9-4f3b-a4e5-c2f40e42c96b.png">

- At Ihsyst = 0 circuit behave like a comparator with no hysteresis. The output voltage VOUT changes eachtime INP crosses INN
- At Ihsyst = 0.2 uA has slight hysteresis. Observed VTH = 1.3mV
- At Ihsyst = 0.8 uA has slight hysteresis. Observed VT = 10.3 mV
- At Ihsyst = 10 uA. Observed VT = 169.29 mV. This should have more hysteresis compared to the earlier simulations.
