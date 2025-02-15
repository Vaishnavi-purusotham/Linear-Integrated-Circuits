# Linear-Integrated-Circuits

## Aim 
Analysis of CS amplifier

Specifications: 180 nm, tsmc, VDD = 1.8 V, Power budget = 50 uW

Analysis: DC analysis, Transient analysis, AC analysis


## Approch

### Task 1

### CS amplifier analysis with resistive load

#### Components Needed
- **NMOS Transistors**: M1 (nmos-4).
- **Resistors**: R1 (1K ohm).
- **Power Supply**: Vdd (1.8V) for DC supply.
- **Input Signal Source**: Vin (0.9V) signal input.


#### Circuit diagram overview
1. **Transistor Setup**:
- **M1** (NMOS) as the main amplifying transistor.
- Gate of **M1** is connected to the input node **Vin**.
- Source of **M1** connected to the ground.
- Drain of **M1** connected to the resistor.

2. **Biasing**:
- **Vin** provides the input signal.

3. **Load resistor**:
- one terminal of resistor is connected to the drain of M1 and the other to Vdd.

## DC analysis
According to the power budget the required current to operate mosfet in saturation region is 27.7 micro ampears, so to obtain the required current the value of W and L obatined is


- **W**=690nm

- **L**=700nm

#### Results

- **Vdd**=1.8V


- **Vin**=0.9V


- **Vout**=1.77223V


- **Id(M1)**=27.7uA


- **Ig(M1)**=0A





## Transient analysis
A sinusoidal input signal of 0.9V peak-to-peak is applied to the gate, and the output voltage is observed at the drain


#### Results

An interveting output curve was obtained when Vin and Vout was plotted against voltage and time with 1ms cycle.
here we can observe a rough 180 degree phase shift between input and output.



## AC analysis
This AC analysis evaluates the frequency response of a common-source NMOS amplifier. The gain is plotted over a wide frequency range to observe how the circuit amplifies signals at different frequencies and determine its bandwidth limitations.

#### Results

The gain remains stable at lower frequencies.

The amplifier’s bandwidth and highlights its frequency-dependent performance.



### Task 2

### CS amplifier analyisis with PMOS replced by resistor

#### Components

