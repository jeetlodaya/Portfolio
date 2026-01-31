
![Auto_CPAP0](https://github.com/user-attachments/assets/e1f5136a-191e-480d-b88b-202abb93c364)


# Auto-CPAP Device 🫁

**An advanced embedded system for sleep apnea treatment with real-time breath event detection and intelligent motor control.**

## 📌 Project Overview
This project is a fully functional Auto-CPAP (Continuous Positive Airway Pressure) device designed to assist patients with Sleep Apnea. Built on the **STM32F4** platform, the system integrates complex signal processing for event detection, precise BLDC motor control for airflow regulation, and a user-friendly HMI.

The goal was to create a medical-grade device prototype that ensures patient comfort through adaptive pressure algorithms while accurately detecting and responding to respiratory events.

## 🚀 Key Features

### 🧠 Breath Event Detection (DSP)
Utilizes advanced Digital Signal Processing to analyze airway pressure and flow data in real-time:
* **Algorithms:** Implements **FFT (Fast Fourier Transform)** and **FIR (Finite Impulse Response)** filters to isolate signal frequencies.
* **Detection Capabilities:**
    * **OSA (Obstructive Sleep Apnea):** Detects airway collapse.
    * **CSA (Central Sleep Apnea):** Distinguishes clear airway apneas.
    * **Snoring:** Detects high-frequency vibrations in the airflow.
    * **Flow Limitation:** Identifies partial obstructions to preemptively adjust pressure.

### ⚙️ Motor Control & Pneumatics
* **Actuator:** High-speed **BLDC Blower Motor**.
* **Control Loop:** Implements a **Cascaded PID Controller** (Pressure Loop -> Speed Loop -> Current Loop) for rapid response to breath-by-breath variations.
* **Comfort Algorithms:**
    * **Ramp:** Gradually increases pressure over a set period to help the user fall asleep.
    * **EPR (Expiratory Pressure Relief):** Reduces pressure during exhalation to normalize breathing effort.

### 🖥️ Human Machine Interface (HMI)
* Developed using **TouchGFX** in C++.
* Interactive touchscreen UI for setting therapy modes, viewing therapy data, and adjusting comfort settings.
* Real-time graphing of pressure and flow waveforms.

## 🛠️ Technical Stack

| Category | Details |
| :--- | :--- |
| **MCU** | STM32F4 Series (ARM Cortex-M4) |
| **Language** | C++ (Embedded), C |
| **Frameworks** | TouchGFX, HAL/LL Drivers |
| **Sensors** | Differential Pressure Sensor, Thermal Mass Flow Sensor |
| **Algorithms** | FFT, FIR Filtering, PID Control |
| **Hardware** | Custom PCB, BLDC Driver Stage, Power Management |
