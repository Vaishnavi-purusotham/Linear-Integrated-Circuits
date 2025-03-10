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



## DC Analysis:
- *DC Operating Point:*
  - *Id =0.5167mA*
  - *Iss =1.033mA*
  - *Vout =1.4274V*
  - *Width = 2529nm*
  - *length = 180nm*
  - *Q-Point:* (1.4274V, 0.5167mA)

![Image](https://github.com/user-attachments/assets/51f9bc56-cc43-486f-a2c9-7407639e5cab)

### Transient Analysis:
- The output shows a *180-degree phase shift* between input and output.
- *Vout = 1.70005V* at *Width = 2529nm* and *length = 180nm*.

![Image](https://github.com/user-attachments/assets/b5362c62-8e60-4aa1-ad80-7e36ebbc73eb)

### AC Analysis:

![Image](https://github.com/user-attachments/assets/50abcd53-420c-40d6-8766-be1e18d18375)


## Gain:

Practical result: *Gain = 28.971dB* at 1KHz frequency.

![Image](https://github.com/user-attachments/assets/ba378881-d9c1-431e-be32-6799fa4ec30e)


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

## Result:

![Image](https://github.com/user-attachments/assets/ba4b3923-5704-4c80-a1a9-c1b854147d87)

## Final result with Inference:

| Parameter    | Value  | Value when Vicm varied |
|-------------|--------|------|
| Vout   | 1.70005V  | 1.4274V    |  
| Id   | 0.4373V  | 0.5167mA   | 
| Gain  | 29.033dB | 28.9719dB  | 

Due to the increses in the input node the volatge in the output node decreses because its corresponding transistor conducts more current, leading to large voltage drop across the load. 
   

## Task 2: Differential amplifier with tail current source

## Circuit diagram:

![Image](https://github.com/user-attachments/assets/41bec9b8-6d03-428d-8719-14d4c8ac80d0)


## Procedure:

*Follow the same procedure as task 1 and do the circuit by replacing Rss with current source* 

## Results:
## DC Analysis:
- *DC Operating Point:*
  - *Id =0.4372mA*
  - *Iss =0.8745mA*
  - *Vout =1.70023V*
  - *Width = 2529nm*
  - *length = 180nm*
  - *Q-Point:* (1,70023V, 0.4372mA)

![Image](https://github.com/user-attachments/assets/2b20c925-fa16-470a-a65c-4ef9342a835a)


### Transient Analysis:
- The output shows a *180-degree phase shift* between input and output.
- *Vout = 1.70005V* at *Width = 2529nm* and *length = 180nm*.


![Image](https://github.com/user-attachments/assets/fdfb228f-2cba-40c2-84e2-a133d0bcfdf7)


### AC Analysis:

![Image](https://github.com/user-attachments/assets/97950060-3f1e-40eb-81be-64e7ce864571)


## Gain:

*Av = -gm Rd*<br>
*Av = 3.8988*<br>
*Gain in dB = 20*log10(Av)*
           <br>= *27.21dB*

Practical result: *Gain = 28.8327dB* at 1KHz frequency.

![Image](https://github.com/user-attachments/assets/5be6398c-6b9f-4437-b483-32c7fefe8a62)

## What happens if we vary Vicm?

Lets vary Vicm to 1.8V instead of 1.6V and observe changes 



## DC Analysis:
- *DC Operating Point:*
  - *Id =0.43725mA*
  - *Iss =0.8745mA*
  - *Vout =1.70023V*
  - *Width = 2529nm*
  - *length = 180nm*
  - *Q-Point:* (1.70023V, 0.43725mA)

![Image](https://github.com/user-attachments/assets/fa2e5670-d4ce-4e69-895f-128833333654)

### Transient Analysis:
- The output shows a *180-degree phase shift* between input and output.
- *Vout = 1.70005V* at *Width = 2529nm* and *length = 180nm*.

![Image](https://github.com/user-attachments/assets/153204c9-2d62-489d-8810-fb7bc6bd7699)


### AC Analysis:

![Image](https://github.com/user-attachments/assets/998b697d-0781-4601-a836-1cbccda6d154)


## Gain:

Practical result: *Gain = 28.82dB* at 1KHz frequency.

![Image](https://github.com/user-attachments/assets/9dea65d0-15aa-42c9-a494-8c4fa18d1824)

## Final result with Inference:

| Parameter    | Value  | Value when Vicm varied |
|-------------|--------|------|
| Vout   | 1.70023V  | 1.70023V    |  
| Id   | 0.4372V  | 0.4372mA   | 
| Gain  | 28.8327dB | 28.82dB  | 

There is no much variation in Vout and Id as the current sorce is providing fixed current but there is a very small amount of decreses in gain. 

## Task 3: Differential amplifier having NMOS replacing the current source

## Circuit diagram:

![Image](https://github.com/user-attachments/assets/4e4b99c9-cec4-4c1a-9642-01ac9fe691f9)


## Procedure:

*Follow the same procedure as task 1 and do the circuit by replacing Rss with current source* 


## Results:
## DC Analysis:
- *DC Operating Point:*
  - *Id =0.4371mA*
  - *I(M3) =0.8742mA*
  - *Vout =1.70073V*
  - *Width = 2529nm*
  - *length = 180nm*
  - *Q-Point:* (1,70073V, 0.4371mA)

![Image](https://github.com/user-attachments/assets/dd77b0b7-db5a-460b-8c68-18d1d564b80f)


### Transient Analysis:
- The output shows a *180-degree phase shift* between input and output.
- *Vout = 1.70073V* at *Width = 2529nm* and *length = 180nm*.

![Image](https://github.com/user-attachments/assets/7a38bdda-4ac4-45fd-9a80-84651f246a12)

### AC Analysis:

![Image](https://github.com/user-attachments/assets/eb0bb39c-06b3-44ff-89cf-2553e33f2a0e)

## Gain:

Practical result: *Gain = 28.874dB* at 1KHz frequency.

![Image](https://github.com/user-attachments/assets/e95b8718-13ea-49ed-8e30-3480caa5344f)

## What happens if we vary Vicm?

Lets vary Vicm to 1.8V instead of 1.6V and observe changes 



## DC Analysis:
- *DC Operating Point:*
  - *Id =0.4506mA*
  - *I(M3) =0.9014mA*
  - *Vout =1.65401V*
  - *Width = 2529nm*
  - *length = 180nm*
  - *Q-Point:* (1.65401V, 0.4506mA)

![Image](https://github.com/user-attachments/assets/aff3e02c-3fb9-4887-b16a-3568c4480742)

### Transient Analysis:
- The output shows a *180-degree phase shift* between input and output.
- *Vout = 1.65401V* at *Width = 2529nm* and *length = 180nm*.

![Image](https://github.com/user-attachments/assets/d3a5ee33-ff05-4ef5-83ed-c70b12aa9c87)

### AC Analysis:

![Image](https://github.com/user-attachments/assets/6e8fda46-ae58-4750-8ba9-e4ba73374f35)


## Gain:

Practical result: *Gain = 28.8406dB* at 1KHz frequency.

![Image](https://github.com/user-attachments/assets/086e3120-5020-4fba-b6e4-d94415b2559c)

## Final result with Inference:

| Parameter    | Value  | Value when Vicm varied |
|-------------|--------|------|
| Vout   | 1.70073V  | 1.6540V    |  
| Id   | 0.4371A | 0.4506mA   | 
| Gain  | 28.87dB | 28.840dB  | 

 Due to the increses in the input node the volatge in the output node decreses because its corresponding transistor conducts more current, leading to large voltage drop across the load. But the gain is stable because differential gain is proportional to gm * R_D, where gm is the transconductance of the input MOSFETs.
If the increase in Iss increases gm, but the same current redistribution happens in both branches, the overall gain remains the same.
