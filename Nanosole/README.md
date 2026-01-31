![UPAC0](https://github.com/user-attachments/assets/5f4ad5e1-be74-4c10-bc37-2f9bd1b5efc4)

# Nanosole 🩺💧

**Precision Ultrasonic Aerosolization System for Intraoperative Chemotherapy**

## 📌 Project Overview
**Nanosole** is a medical device designed for the targeted delivery of liquid medication during cancer surgery. It utilizes high-frequency ultrasonic vibrations to aerosolize liquid drugs into a fine mist, allowing for uniform coverage of cancerous tissues in the operating room.

The system features a custom-designed high-voltage drive circuit with **active resonance tracking** to maintain peak atomization efficiency despite changing load conditions (e.g., fluid density or temperature changes).

## 🚀 Key Features

### 🔊 Ultrasonic Aerosolization Engine
* **Piezoelectric Actuation:** Drives a piezo transducer to create cavitation and capillary waves, turning liquid medication into micron-sized aerosol droplets.
* **DDS (Direct Digital Synthesis):** Utilizes a dedicated DDS chip to generate precise, low-jitter frequency waveforms.
* **Resonance Tracking:** Implements a **Phase Locked Loop (PLL)** to continuously monitor voltage-current phase relationships. This ensures the system stays locked to the piezo's resonant frequency (typically 100kHz - 2MHz range) for maximum power transfer.

### ⚡ High Voltage Drive Circuit
* **Sine Wave Generation:** Converts low-voltage DC logic signals into high-voltage AC sine waves required to drive the piezo element.
* **Safety Mechanisms:** Includes over-current protection and isolation to meet medical safety standards (IEC 60601-1 considerations).

### 🖥️ Advanced HMI (STM32F7)
* Built on the high-performance **STM32F7** microcontroller.
* Features a responsive GUI for surgeons to control flow rate, dosage limits, and view system status.
* Real-time visualization of frequency lock and power output.

## 🛠️ Technical Stack

| Category | Details |
| :--- | :--- |
| **MCU** | STM32F7 Series (ARM Cortex-M7) |
| **Signal Gen** | DDS Chip (e.g., AD9850/AD9833) |
| **Control Logic** | Phase Locked Loop (PLL) Hardware & Firmware |
| **Actuator** | Ultrasonic Piezoelectric Transducer |
| **Power Electronics** | High Voltage Step-up (Transformer/Boost), Class-E or D Amplifier |
| **Display** | TFT LCD with Touch capability |
