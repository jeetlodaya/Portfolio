# HbA1c Optical Analyzer (IVD) 🩸

**A precision In-Vitro Diagnostic device for quantitative diabetes monitoring using optical reflectance photometry.**

## 📌 Project Overview
This project is an automated IVD system designed to calculate Hemoglobin A1c (HbA1c) levels by analyzing the optical intensity of immunochromatographic test strips. 

The device automates the scanning process using a stepper motor linear drive and employs a high-sensitivity optical frontend to detect subtle color variations on the test line using green wavelength spectrometry. A core focus of this project was optimizing **mixed-signal PCB design** to prevent motor driver noise from corrupting the sensitive photodiode measurements on a constrained board layout.

## 🚀 Key Features

### 👁️ Precision Optical Sensing
* **Source:** Green LED (approx. 525nm) optimized for the absorbance spectrum of the reagent line.
* **Detector:** Low-noise Photodiode with a custom **Transimpedance Amplifier (TIA)**.
* **Automatic Gain Control (AGC):** Implemented dynamic gain adjustment to maximize dynamic range, ensuring accurate readings across different test strip batches and ambient lighting conditions.

### 🖥️ Human Machine Interface (HMI)
* **Display:** Integrated **DWIN 4.3" TFT LCD (480x272)** for a rich graphical user interface.
* **Functionality:** * Real-time status indication (Scanning, Analyzing, Error).
    * Visualization of HbA1c results and intensity graphs.
    * Touch controls for calibration and motor testing.
* **Communication:** Optimized **UART** protocol for reliable data exchange between the STM32 MCU and the DWIN Smart Screen.

### ⚡ Mixed-Signal Hardware Design
* **Noise Isolation:** Engineered distinct power and ground zones on the PCB to isolate the high-current stepper motor drivers (24V) from the sensitive analog signal chain (3.3V/5V).
* **Signal Integrity:** Utilized careful component placement and shielding to protect the highly sensitive, single-ended analog signals from the photodiode.

### ⚙️ Electromechanical Control
* **Motion:** Micro-stepping stepper motor control for smooth, vibration-free scanning of the test strip.
* **Synchronization:** Precise timing to correlate motor position with ADC sampling triggers for high-resolution mapping of the test line intensity profile.

## 🛠️ Technical Stack

| Category | Details |
| :--- | :--- |
| **Measurement** | Reflectance Photometry (Green $\lambda$) |
| **Analog FE** | Photodiode, Op-Amp TIA, Programmable Gain Amplifier (PGA) |
| **HMI** | **DWIN Smart Display (DGUS II OS)** |
| **Actuation** | Bipolar Stepper Motor + Driver (A4988) |
| **MCU** | STM32 / ARM Cortex-M |
| **PCB Design** | Mixed-signal 2-layer design (Star Grounding/Split Zones) |
