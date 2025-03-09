# Experiment-3

## Aim:
To design differential amplifier for the given specification and perform DC analysis, Transient analysis and AC analysis to extract the required parameters from LT spice. 


## Introduction to the MOS Differential Amplifier:

The MOS differential amplifier is a key component in analog circuits that amplifies the difference between two input voltages while rejecting common-mode signals. It typically consists of two MOSFETs configured in a differential pair, with the output determined by the difference between the inputs. This configuration is essential in applications such as operational amplifiers, instrumentation, and high-precision signal processing.

The performance of a MOS differential amplifier is characterized by parameters such as differential gain, transconductance (gm), and common-mode rejection ratio (CMRR). The amplifier's ability to reject common-mode noise, expressed by CMRR, is particularly crucial in minimizing interference from external sources. Biasing the differential pair, often using current mirrors or active loads, ensures proper operation and stability of the amplifier.

![Image](https://github.com/user-attachments/assets/4eb8c832-f45d-4463-89be-12299225f6e8)


## Design question: Design differential amplifier for the following specification and 

                    a) Perform DC, Transient and AC analysis and justify the results
                    b) Calculate maximum input and output swing
                    c) Gain equation using small signal model

- Vdd=3.2V
- Power<=2.8mW
- Vicm=1.6V
- Vocm=1.7V
- Vp=0.6V

## Design

Iss= P/Vdd <br>
   = 2.8mW/3.2 <br>
   = 0.875mA
 <br>
  <br>
Id1= Id2= Iss/2  <br>
   = 0.4375mA <br>
   = 0.4375mA
 <br>
  <br>
Rss= Vp/Iss <br>
   = 0.6/0.875mA <br>
   = 685.7Ω
 <br>
  <br>
Rd= Vdd-Vocm/Id1 <br>
  = 3.2-1.7/0.4375mA <br>
  = 3.42KΩ
 <br>
  <br>
 
## Components Required:
- NMOS (nmos4)
- Resistor (3.42KkΩ and 650Ω)
- Voltage sources (3.2V, 1.6V sin wave)

## Task 1: Differential amplifier with Emitter resistor 

## Circuit diagram:

![Image](https://github.com/user-attachments/assets/e3e34c82-ed6e-4d07-bcaf-bcdcda963e6b)


## Procedure:

1. *Create a New Project*

2. *Set Up the values for MOSFET*
   - Configure the *NMOS transistor (CMOSN)* with:
     - Length: *180nm*
     - Width: *2529nm*
  
3. *Perform DC Analysis*
   - Connect all circuit components properly.
   - Apply:
     - *Vdd = 3.2V*
     - *Vin = 1.6V*
   - Run *DC analysis* to obtain:
     - *Vout*
     - *Id*

4. *Run Transient Analysis*
   - Apply a *sine wave input*:
     - *Vin = 1.6V*
     - *Amplitude = 50mV*
     - *Frequency = 1kHz*
   - Run *transient analysis*
   - 
5. *Run AC Analysis*
   - Include all required library files.
   - Run *AC analysis* with:
     -Start and end frequency: *0.1Hz to 1THz*



## Results:
## DC Analysis:
- *DC Operating Point:*
  - *Id =0.4373mA*
  - *Iss =0.8746mA*
  - *Vout =1.70005V*
  - *Width = 2529nm*
  - *length = 180nm*
  - *Q-Point:* (1,70005V, 0.4373mA)

![Image](https://github.com/user-attachments/assets/94135aab-4be2-4285-be01-47d74c205da3)

### Transient Analysis:
- The output shows a *180-degree phase shift* between input and output.
- *Vout = 1.70005V* at *Width = 2529nm* and *length = 180nm*.

![Image](https://github.com/user-attachments/assets/8c96f460-1276-4491-93cb-1792c37d2d2b)


### AC Analysis:

![Image](https://github.com/user-attachments/assets/e3ba49d1-0ef7-4a58-bc92-02ba09646aff)

## Gain:

*Av = -gm Rd*<br>
*Av = 3.8988*<br>
*Gain in dB = 20*log10(Av)*
           <br>= *27.21dB*

Practical result: *Gain = 29.033dB* at 1KHz frequency.

![Image](https://github.com/user-attachments/assets/e95b8718-13ea-49ed-8e30-3480caa5344f)

## What happens if we vary Vicm?

Lets vary Vicm to 1.8V instead of 1.6V and observe changes 

## Results:

## DC Analysis:
- *DC Operating Point:*
  - *Id =0.4373mA*
  - *Iss =0.8746mA*
  - *Vout =1.70005V*
  - *Width = 2529nm*
  - *length = 180nm*
  - *Q-Point:* (1,70005V, 0.4373mA)

![Image](https://github.com/user-attachments/assets/94135aab-4be2-4285-be01-47d74c205da3)

### Transient Analysis:
- The output shows a *180-degree phase shift* between input and output.
- *Vout = 1.70005V* at *Width = 2529nm* and *length = 180nm*.

![Image](https://github.com/user-attachments/assets/8c96f460-1276-4491-93cb-1792c37d2d2b)

### AC Analysis:

![Image](https://github.com/user-attachments/assets/e3ba49d1-0ef7-4a58-bc92-02ba09646aff)


## Gain:

*Av = -gm Rd*<br>
*Av = 3.8988*<br>
*Gain in dB = 20*log10(Av)*
           <br>= *27.21dB*

Practical result: *Gain = 29.033dB* at 1KHz frequency.

![Image](https://github.com/user-attachments/assets/e95b8718-13ea-49ed-8e30-3480caa5344f)

## Output minimum and maximum swing:

The output minimum and maximum swing of a MOS differential amplifier are critical to understanding its dynamic range. The output swing defines the voltage range over which the amplifier can operate linearly, without clipping or distorting the signal.

The maximum output swing corresponds to the highest voltage the output can reach without saturating the MOSFET on the high side of the differential pair. This is determined by the saturation region of the MOSFETs and the voltage drop across the load resistor.

The minimum output swing corresponds to the lowest voltage the output can reach without saturating the MOSFET on the low side of the differential pair. The minimum output swing is limited by the drain-to-source voltage of the transistor in the low state.

## Calculation:

Vout(max) = Vdd-Vd(sat)<br>
          = 3.2V-0.228V
          = 2.972V

Vout(min) = Vgs-Vt
          = 1V-0.489V
          =0.511V

## Result

![Image](https://github.com/user-attachments/assets/ba4b3923-5704-4c80-a1a9-c1b854147d87)


## Inference:
1. The MOSFET's *current (Id) is directly proportional to its width*, affecting overall circuit performance.
2. Operating in saturation region.
3. Transient analysis helps in evaluating the circuit’s response to time-varying signals, crucial for high-speed applications.
4. AC analysis aids in designing amplifiers with desired gain and understanding frequency behavior.
5. The overall analysis ensures proper design, optimization, and stability of the amplifier circuit.

   

## Task 2: CS Amplifier with Diode-Connected MOSFET

## Components Required:
- NMOS (nmos4) and PMOS(pmos4)
- Voltage sources (1.8V, 0.9V)
- Bias DC source (-2.5V)

## Circuit diagram:

![Image](https://github.com/user-attachments/assets/9a419501-4d55-425b-94e7-36d225453950)


### Procedure:
1. Set the PMOS transistor (CMOSP) with a length of *302nm* and width of *360μm*.

2. *DC Analysis:*
   - Apply *Vdd = 1.8V* , *Vin = 0.9V* 
   - As the MOSFET should be in saturation region,
     Here Vb is connected to gate , so for us both the mosfet should be in saturation so for that Vgs>Vt 
    |Vg-Vs|>|Vt|
    here Vg is unknown so I calculated Vg ie Vg =Vb
    Vb=-2V
   - Run DC analysis to determine *Vout* and *Id*.

3. *Transient Analysis:*
   - Apply a sine wave input and observe the response.

4. *AC Analysis:*
   - Run AC analysis to measure gain and frequency response.


## Results:


### DC Analysis:
- *DC Operating Point:*
  - *Id1 =27.7uA*
  - *Id2 =27.7uA*
  - *Vout =1.79981V*
  - *Width = 690nm* (NMOS)
  - *length = 700nm* (NMOS)
  -  *Width = 360Um* (PMOS)
  - *length = 302nm* (PMOS)
  - *Q-Point:* (1,79981V, 27.7uA)


![Image](https://github.com/user-attachments/assets/076773ae-cb10-45f6-bed1-9193ff1f8564)


### Transient Analysis:
- The output shows a *180-degree phase shift* between input and output.
- *Vout = 1.79981V* 


![Image](https://github.com/user-attachments/assets/0645a560-4518-4b8d-810f-b852f6cfc73f)



### AC Analysis:

![Image](https://github.com/user-attachments/assets/efdabf4f-7389-4f89-a955-7690d7be3f20)

## Gain:

*Av = -gm Rd*
*gm = 1/lamda*Id*

Practical result: *Gain = 36.7361dB* at 1KHz frequency.

![Image](https://github.com/user-attachments/assets/b8175d28-f620-4588-9f58-48f3623757c7)

## Inference

1. The MOSFET's **drain current (Id) is directly proportional to its width (W)**, influencing circuit performance and power consumption.  
2. The MOSFET operates in the **saturation region** for amplification, ensuring a stable output.  
3. **Transient analysis** evaluates the circuit’s response to time-varying signals, which is crucial for high-speed applications and switching performance.  
4. **AC analysis** helps in designing amplifiers by determining gain, bandwidth, and frequency response.  
5. A comprehensive analysis ensures **optimal design, performance, and stability** of the amplifier circuit.
