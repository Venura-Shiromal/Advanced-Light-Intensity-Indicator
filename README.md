# Advanced Light Intensity Indicator (ALII)

An analog and discrete-digital hardware module designed to monitor, filter, stabilize, and average ambient light levels for smart energy conservation and automated municipal lighting.

---

## Overview

The ALII module captures ambient light data using a Light Dependent Resistor (LDR) and displays both real-time stabilized light levels and rolling average intensity values using seven-segment displays. The architecture is designed without microcontrollers or specialized black-box ICs, relying strictly on analog signal conditioning, discrete logic gates, and flip-flops.

---

## Progress

### Simulation

- [x] Design of the filter (Sallen-Key 2nd order low pass filter at cut-off at 2Hz)
- [x] Simulation of the filter in LTSpice to get the bode plot
- [x] Simulation of subcircuits in Falstad 
	* Low-pass filter
	* Priority encoder
	* Flash ADC (including the encoder) 
	* Multiplexer
	* Change detector
	* Counter
	* Latch system
- [x] Simulation of the current value indicator 
- [x] Design the whole circuit
- [ ] Test and simulate the complete circuit

---

## Technical Specifications & Constraints

| Parameter | Specification |
| :--- | :--- |
| **Sensor Type** | Light Dependent Resistor (LDR) |
| **Interference Rejection** | 50 Hz / 100 Hz powerline hum attenuation |
| **Output Displays** | 2× Seven-Segment Displays (Current Level, Rolling Average) |
| **Intensity Range** | Levels 0 (Lowest) to 7 (Highest) |
| **Stabilization Time Window** | 30 s – 300 s (potentiometer controlled, toggled by switch) |
| **Averaging Window** | 300 s – 900 s (potentiometer controlled, reset by push button) |
| **Design Rules** | **No microcontrollers/programmable ICs**; logic gates and flip-flops only |

---
