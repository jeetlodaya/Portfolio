![O2](https://github.com/user-attachments/assets/5b0e740d-7ee5-4017-85ff-ae9f3f5fb095)

# OxySense: High-Purity Oxygen Concentrator Controller 🌬️🩺

**A real-time control and monitoring system designed to maintain 92% ±3% oxygen purity for medical-grade concentrators.**

## 📌 Project Overview
**OxySense** is an embedded control system built on the cost-effective **STM32G030** microcontroller. It is designed to monitor the critical parameters of an oxygen concentrator—specifically purity, flow rate, and operating temperature.

The system features an interrupt-driven architecture to reliably process asynchronous data streams from digital oxygen sensors while simultaneously managing flow sensors and thermal safety checks, ensuring the output remains consistently above the **90% medical standard**.

## 🚀 Key Features

### 🧪 Precision O2 Monitoring
* **Target Purity:** Calibrated to maintain and verify **92% purity**.
* **Interface:** Implements **UART with Ring Buffer & Interrupts**.
    * *Why?* The O2 sensor streams data asynchronously. Using RX interrupts prevents data loss and keeps the main loop free for critical safety checks, unlike blocking `HAL_UART_Receive`.

### 🌡️ Multi-Sensor Integration
* **Flow Sensor:** Measures output in LPM (Liters Per Minute) to ensure consistent dosage.
* **Temperature Sensor:** Monitors compressor and sieve bed temperature to prevent overheating and optimize the PSA (Pressure Swing Adsorption) cycle efficiency.

### ⚡ Efficient MCU Utilization
* **Hardware:** **STM32G030** (ARM Cortex-M0+).
* **Optimization:** Designed to run on a low-cost, low-pin-count MCU, demonstrating the ability to maximize hardware resources for mass-production viability.

## 🛠️ Technical Stack

| Category | Details |
| :--- | :--- |
| **MCU** | STM32G030 (Value Line) |
| **O2 Sensor** | Ultrasonic (UART Interface) |
| **Flow Sensor** | Mass Flow Sensor I2C) |
| **Communication** | UART (Interrupt-Driven), I2C |
| **Firmware** | C, HAL/LL Drivers, State Machine Architecture |

