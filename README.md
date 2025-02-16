# Experiment-1

## Aim:
To perform DC analysis, Transient analysis, and AC analysis of a Common Source (CS) amplifier circuit and extract various parameters using LTSpice.


## Introduction to the Topic:
A MOSFET (Metal-Oxide-Semiconductor Field-Effect Transistor) is a crucial component in modern electronics due to its compact design, low power consumption, and compatibility with VLSI technology.


In saturation mode, an NMOS transistor operates under the conditions:
- **Vgs > Vth** (Gate-to-Source Voltage greater than Threshold Voltage)
- **Vds ≥ Vov** (Drain-to-Source Voltage greater than Overdrive Voltage)

In a CS amplifier, the output will give 180-degree phase shift with respect to input 

the current equation in saturation mode is given by
**Id = (1/2) kn Vov²**, where:
- **Vov = Vgs - Vth**


The voltage gain is given by:

**Av = -gm Rd**
or
**Av = Vout/Vin**



## Task 1: CS amplifier with resistive load

## Components Required:
- NMOS (nmos4)
- Resistor (1kΩ)
- Voltage sources (1.8V, 0.9V)


## Circuit diagram:

![Image](https://github.com/user-attachments/assets/1b2c5533-e1e6-4054-8d47-0d09afde970d)

## Procedure:

1. **Create a New Project**

2. **Set Up the values for MOSFET**
   - Configure the **NMOS transistor (CMOSN)** with:
     - Length: **700nm**
     - Width: **690nm**
  
3. **Perform DC Analysis**
   - Connect all circuit components properly.
   - Apply:
     - **Vdd = 1.8V**
     - **Vin = 0.9V**
   - Run **DC analysis** to obtain:
     - **Vout**
     - **Id**

4. **Run Transient Analysis**
   - Apply a **sine wave input**:
     - **Vin = 0.9V**
     - **Amplitude = 50mV**
     - **Frequency = 1kHz**
   - Run **transient analysis**
   - 
5. **Run AC Analysis**
   - Include all required library files.
   - Run **AC analysis** with:
     -Start and end frequency: **0.1Hz to 1THz**



## Results:
### DC Analysis:
- **DC Operating Point:**
  - **Id =27.7uA**
  - **Vout =1.77223V**
  - **Width = 690nm**
  - **length = 700nm**
  - **Q-Point:** (1,77223V, 27.7uA)

![Image](https://github.com/user-attachments/assets/0d6e5187-2a6e-44bc-9947-70d0613b423d)

### Transient Analysis:
- The output shows a **180-degree phase shift** between input and output.
- **Vout = 1.77223V** at **Width = 690nm** and **length = 700nm**.

![Image](https://github.com/user-attachments/assets/fa317551-685a-419a-bc34-0aa4bfb393c3)


### AC Analysis:
- **Gain = 30.5282dB** at 1KHz frequency.

## Inference:
1. The MOSFET's **current (Id) is directly proportional to its width**, affecting overall circuit performance.
2. Operating in saturation region.
3. Transient analysis helps in evaluating the circuit’s response to time-varying signals, crucial for high-speed applications.
4. AC analysis aids in designing amplifiers with desired gain and understanding frequency behavior.
5. The overall analysis ensures proper design, optimization, and stability of the amplifier circuit.

## Circuit 2: CS Amplifier with Diode-Connected MOSFET

### Theory:
A **diode-connected MOSFET** is always in saturation and acts as a **constant current source**, making it useful for amplifier circuits.

- **Drain current equation:**
  **Id = (1/2) kn Vov²**, where **Vov = Vgs - Vth**.

- The amplifier gain follows **Av = -gm Rd**.

### Procedure:
1. Set the NMOS transistor (CMOSN) with a length of **180nm** and width of **2μm**.
2. **DC Analysis:**
   - Apply **Vdd = 1.8V** and **Vgs = 0.9V**.
   - Run DC analysis to determine **Vout** and **Id**.

3. **Transient Analysis:**
   - Apply a sine wave input and observe the response.

4. **AC Analysis:**
   - Run AC analysis to measure gain and frequency response.

## Results:
### DC Analysis:
- **DC Operating Point:**
  - **Id = 55.55μA**
  - **Vout = 1.658V**
  - **Width = 2μm**

### Transient Analysis:
- Output shows a **180-degree phase shift** and **DC level shift**.
- **Vout = 1.658V**.

### AC Analysis:
- **Gain = -0.95dB**.

## Inference:
1. **Current (Id) depends on MOSFET width**, while other parameters remain stable.
2. Proper biasing ensures MOSFET operation in saturation with a **stable Q-point**.
3. **Transient analysis** helps in evaluating circuit response to time variations.
4. **AC analysis** is crucial for designing circuits with specific gain and impedance matching.
5. Combining these analyses helps in designing and optimizing amplifiers effectively.
