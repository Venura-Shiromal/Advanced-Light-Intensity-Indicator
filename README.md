# Advanced Light Intensity Indicator (ALII)

An analog and discrete-digital hardware module designed to monitor, filter, stabilize, and average ambient light levels for smart energy conservation and automated municipal lighting.

---

## Overview

The ALII module captures ambient light data using a Light Dependent Resistor (LDR) and displays both real-time stabilized light levels and rolling average intensity values using seven-segment displays. The architecture is designed without microcontrollers or specialized black-box ICs, relying strictly on analog signal conditioning, discrete logic gates, and flip-flops.

---

## Key Features

* **Analog Noise Filtering:** An active low-pass or notch filter attenuates 50–100 Hz powerline interference and optical flicker from artificial lighting, isolating true ambient light changes.
* **Real-Time 3-Bit Quantization (0–7):** Maps filtered light intensity across 8 discrete levels ("0" for dark to "7" for maximum brightness) on a primary 7-segment display.
* **Fluctuation Suppression (Hysteresis/Stabilization):** Updates display values only after lighting stabilizes for an adjustable delay between 30 and 300 seconds. Includes a dedicated toggle switch to bypass or engage stabilization.
* **Long-Term Averaging:** Computes and displays the average light intensity on a secondary 7-segment display over an adjustable window of 300 to 900 seconds.
* **Manual Reset:** A tactile push button instantly clears the rolling average display.

---

## Technical Specifications & Constraints

| Parameter | Specification |
| :--- | :--- |
| **Sensor Type** | Light Dependent Resistor (LDR) |
| **Interference Rejection** | 50 Hz / 100 Hz powerline hum attenuation |
| **Output Displays** | 2× Seven-Segment Displays (Current Level, Rolling Average) |
| **Intensity Range** | Levels 0 (Lowest) to 7 (Highest) |
| **Stabilization Time Window** | 30 s – 300 s (potentiometer controlled, toggleable) |
| **Averaging Window** | 300 s – 900 s (potentiometer controlled) |
| **Design Rules** | **No microcontrollers/programmable ICs**; logic gates and flip-flops only |

---

## Circuit Architecture

* **Analog Stage:** LDR voltage divider coupled to an active RC filter stage removing AC ripple.
* **ADC / Level Slicing:** Multi-level comparator/flash ladder converting analog voltages to 3-bit binary representations (0–7).
* **Timing & Debounce:** Variable RC timer network controlling clock pulses to stabilization flip-flops.
* **Averaging Unit:** Discrete digital accumulation registers and counter logic clocking over the extended 300–900 s duration.
* **Display Decoders:** Combinational logic mapping binary values to 7-segment outputs.

---
