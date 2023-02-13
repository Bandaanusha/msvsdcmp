# SCL 180nm Comparator IP

## Introduction

A comparator is a device that compares two analog inputs and outputs a digital signal indicating which input is larger. So it has two analog input terminals and one binary digital output. When the difference between two analog input signals approach zero, noise on the inputs will cause spurious switching of digital output. This rapid change in output due to noise can be prevented by hysteresis. Hysteresis is switching the output high or low at different input signal levels. In place of one switching point, hysteresis introduces two: one for rising edge, and one for falling edge of voltage or current. The difference between the higher-level trip value (VH) and the lower-level trip value (VL) equals the hysteresis voltage (HYST).

## Specifications

## Schematic

![circuitschm](https://user-images.githubusercontent.com/62790565/218436868-936908e6-c0dc-4b51-8517-f5e12ccae5d3.png)

## Pre-Layout Simulation

<img width="802" alt="Screenshot 2023-02-13 223058" src="https://user-images.githubusercontent.com/62790565/218523018-afecd5ea-39d9-4f3b-a4e5-c2f40e42c96b.png">

- At Ihsyst = 0 circuit behave like a comparator with no hysteresis. The output voltage VOUT changes eachtime INP crosses INN

<img width="782" alt="hyso" src="https://user-images.githubusercontent.com/62790565/218526854-2409f175-073b-40ef-abc6-7943cacb6c42.png">

- At Ihsyst = 0.2 uA.

<img width="782" alt="hys1" src="https://user-images.githubusercontent.com/62790565/218527001-5f2cab83-3659-481c-879f-e470f9b729e0.png">

- At Ihsyst = 0.8 uA.

<img width="785" alt="hys3" src="https://user-images.githubusercontent.com/62790565/218527085-f6d18840-6cd3-4903-9ec4-27910b2c3bc5.png">

- At Ihsyst = 10 uA.

<img width="782" alt="hys4" src="https://user-images.githubusercontent.com/62790565/218527127-b1167d6c-71f5-4905-b9bc-1c5ec938dd61.png">

