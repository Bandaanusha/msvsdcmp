# SCL 180nm Comparator IP
## Table of Contents
- [Introduction](https://github.com/Bandaanusha/msvsdcmp#introduction)<br>
- [Specifications](https://github.com/Bandaanusha/msvsdcmp#specifications)<br>
- [Schematic](https://github.com/Bandaanusha/msvsdcmp#schematic)<br>
  - [Inputs to the circuit](https://github.com/Bandaanusha/msvsdcmp#inputs-to-the-circuit)
  - [Output of the circuit](https://github.com/Bandaanusha/msvsdcmp#output-of-the-circuit)
  - [Circuit details](https://github.com/Bandaanusha/msvsdcmp#output-of-the-circuit)<br>
 
- [Pre-Layout Simulation](https://github.com/Bandaanusha/msvsdcmp#pre-layout-simulation)<br>
  - [Transient Analysis](https://github.com/Bandaanusha/msvsdcmp#transient-analysis)<br>
  - [Transfer Characteristics](https://github.com/Bandaanusha/msvsdcmp#transfer-characteristics)<br>
- [Layout]()<br>
- [Future Work]()<br>
- [Contributors]()<br>
- [Acknowledgements]()<br>
- [Contact Information]()<br>
## Introduction

A comparator is a device that compares two analog inputs and outputs a digital signal indicating which input is larger. So it has two analog input terminals and one binary digital output. When the difference between two analog input signals approach zero, noise on the inputs will cause spurious switching of digital output. This rapid change in output due to noise can be prevented by hysteresis. Hysteresis is switching the output high or low at different input signal levels. In place of one switching point, hysteresis introduces two: one for rising edge, and one for falling edge of voltage or current. The difference between the higher-level trip value (VH) and the lower-level trip value (VL) equals the hysteresis voltage (HYST).

## Specifications

<img width="637" alt="specifications" src="https://user-images.githubusercontent.com/62790565/220716290-ca39649c-4f11-48ef-94c8-724fb423cef6.png">

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

### Circuit details

A comparator can be divided into three distinctive pieces – a frontend differential amplifier, amplifier stage and output stage.

This comparator consists of

1. Frontend differential amplifier
2. Amplifier of the output from frontend differential sage
3. NAND gate to act as buffer as well as incorporate the enable pin
4. Inverter to act as final buffer before output. The NAND and Inverter improves the slew and provides a little gain.
5. Positive feedback differential set-up.


## Pre-Layout Simulation

### Transient Analysis

![Screenshot from 2023-02-14 10-24-03](https://user-images.githubusercontent.com/62790565/218642830-1a0673da-47f3-480c-9bae-fd097968492c.png)


- At Ihsyst = 0 circuit behave like a comparator with no hysteresis. The output voltage VOUT changes eachtime INP crosses INN


<img width="782" alt="hyso" src="https://user-images.githubusercontent.com/62790565/218526854-2409f175-073b-40ef-abc6-7943cacb6c42.png">

- At Ihsyst = 0.2 uA. Observed VHYST=2mV


<img width="782" alt="hys1" src="https://user-images.githubusercontent.com/62790565/218527001-5f2cab83-3659-481c-879f-e470f9b729e0.png">

- At Ihsyst = 0.8 uA.Observed VHYST=10mV


<img width="785" alt="hys3" src="https://user-images.githubusercontent.com/62790565/218527085-f6d18840-6cd3-4903-9ec4-27910b2c3bc5.png">

- At Ihsyst = 10 uA.Observed VHYST=60mV


<img width="782" alt="hys4" src="https://user-images.githubusercontent.com/62790565/218527127-b1167d6c-71f5-4905-b9bc-1c5ec938dd61.png">



```
VHYST is hysteresis voltage. It is the difference between the higher-level trip value (VH) and the lower-level trip value (VL)
VHYST= VH - VL
VHYST defines the width of hysteresis. At Ihyst=10uA it has more hysteresis compared with the Ihyst=0.2 or 0.8 uA
```

### Transfer Characteristics
Plot graph of INP vs Vout by varying INP through DC sweep and IHyst

### Ihyst=0uA
![Screenshot from 2023-02-22 22-41-04](https://user-images.githubusercontent.com/62790565/220704395-1ccd9469-b95c-485b-a306-f27a227413b9.png)

### Ihyst=0.2uA
![Screenshot from 2023-02-22 22-36-14](https://user-images.githubusercontent.com/62790565/220704477-553c2f64-30fa-4620-a2c6-3fe1357b4fb0.png)


### Ihyst=0.8uA
![Screenshot from 2023-02-22 22-22-58](https://user-images.githubusercontent.com/62790565/220704629-47247da4-06d2-470e-b267-143673c21d0d.png)


### Ihyst=10uA
![Screenshot from 2023-02-22 22-20-55](https://user-images.githubusercontent.com/62790565/220704665-72b18310-98a6-478c-ae52-1ba0a3d8b9cd.png)

## Layout 
Below is the layout of comparator created in Cadence Virtuoso using SCL180 pdk

![Screenshot from 2023-05-08 23-08-39](https://user-images.githubusercontent.com/62790565/236894315-317aab72-b3dc-463a-975c-4ef9c1a47592.png)

![Screenshot from 2023-05-08 23-13-46](https://user-images.githubusercontent.com/62790565/236894390-c51c1404-ae8a-4912-bce0-fbab9b5dd233.png)

![Screenshot from 2023-05-08 23-13-54](https://user-images.githubusercontent.com/62790565/236894401-a4bbf0c7-d55f-4898-b540-7d7407b45923.png)

![Screenshot from 2023-05-08 23-14-00](https://user-images.githubusercontent.com/62790565/236894411-21ba96e3-e72b-4293-a2b2-6f6308fc9f97.png)

## Future Work
Post-Layout simulations pending due to PDK integration issues.

## Contributors

- Banda Anusha
- Kunal Ghosh

## Acknowledgements
- Kunal Ghosh, Director, VSD Corp. Pvt. Ltd.
- Madhav Rao, Professor, IIITB
- Nanditha Rao, Professor, IIITB

## Contact Information
- Banda Anusha, Postgraduate Student, International Institute of Information Technology, Bangalore Banda.Anusha@iiitb.ac.in
- Kunal Ghosh, Director, VSD Corp. Pvt. Ltd. kunalghosh@gmail.com
- Nanditha Rao, nanditha.rao@iiitb.ac.in
- Madhav Rao, mr@iiitb.ac.in
