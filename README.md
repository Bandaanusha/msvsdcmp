# SCL 180nm Comparator IP

## Introduction

A comparator is a device that compares two analog inputs and outputs a digital signal indicating which input is larger. So it has two analog input terminals and one binary digital output. When the difference between two analog input signals approach zero, noise on the inputs will cause spurious switching of digital output. This rapid change in output due to noise can be prevented by hysteresis. Hysteresis is switching the output high or low at different input signal levels. In place of one switching point, hysteresis introduces two: one for rising edge, and one for falling edge of voltage or current. The difference between the higher-level trip value (VH) and the lower-level trip value (VL) equals the hysteresis voltage (HYST).

## Schematic

![circuitschm](https://user-images.githubusercontent.com/62790565/218436868-936908e6-c0dc-4b51-8517-f5e12ccae5d3.png)

### Inputs to the circuit

- VCC - 3.3 v
- GND - Ground
- INN - Negative differential input
- INP - Positive differential input
- EN - Enable pin
- Ihyst - Current to control hysteresis

### Output of the circuit

- VOUT - Comparator output


## Pre-Layout Simulation

![Screenshot from 2023-02-14 10-24-03](https://user-images.githubusercontent.com/62790565/218642830-1a0673da-47f3-480c-9bae-fd097968492c.png)


- At Ihsyst = 0 circuit behave like a comparator with no hysteresis. The output voltage VOUT changes eachtime INP crosses INN

<img width="782" alt="hyso" src="https://user-images.githubusercontent.com/62790565/218526854-2409f175-073b-40ef-abc6-7943cacb6c42.png">

- At Ihsyst = 0.2 uA. Observed VTH=3.77mV

<img width="782" alt="hys1" src="https://user-images.githubusercontent.com/62790565/218527001-5f2cab83-3659-481c-879f-e470f9b729e0.png">

- At Ihsyst = 0.8 uA.Observed VTH=4.37mV

<img width="785" alt="hys3" src="https://user-images.githubusercontent.com/62790565/218527085-f6d18840-6cd3-4903-9ec4-27910b2c3bc5.png">

- At Ihsyst = 10 uA.Observed VTH=63.58mV

<img width="782" alt="hys4" src="https://user-images.githubusercontent.com/62790565/218527127-b1167d6c-71f5-4905-b9bc-1c5ec938dd61.png">

```
VTH is hysteresis voltage. It is the difference between the higher-level trip value (VH) and the lower-level trip value (VL)
VTH= VH - VL
VTH defines the width of hysteresis. At Ihyst=10uA it has more hysteresis compared with the Ihyst=0.2 or 0.8 uA
```

##### Transfer Characteristics
Plot graph of INP vs Vout by varying INP through DC sweep and IHyst

##### Ihyst=0uA
![Screenshot from 2023-02-22 22-41-04](https://user-images.githubusercontent.com/62790565/220704395-1ccd9469-b95c-485b-a306-f27a227413b9.png)

##### Ihyst=0.2uA
![Screenshot from 2023-02-22 22-36-14](https://user-images.githubusercontent.com/62790565/220704477-553c2f64-30fa-4620-a2c6-3fe1357b4fb0.png)


##### Ihyst=0.8uA
![Screenshot from 2023-02-22 22-22-58](https://user-images.githubusercontent.com/62790565/220704629-47247da4-06d2-470e-b267-143673c21d0d.png)


##### Ihyst=10uA
![Screenshot from 2023-02-22 22-20-55](https://user-images.githubusercontent.com/62790565/220704665-72b18310-98a6-478c-ae52-1ba0a3d8b9cd.png)
