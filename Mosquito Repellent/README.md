# SmartMist: Bluetooth Mosquito Repellent Sprayer 🦟📱

**An IoT-enabled, ultra-low-power automatic sprayer for efficient mosquito control.**

## 📌 Project Overview
**SmartMist** is a compact, battery-operated device designed to automate the spraying of mosquito repellent. Unlike traditional "always-on" vaporizers, this device uses scheduled bursts or on-demand triggering via Bluetooth to maximize repellent efficiency and extend battery life.

The system is engineered for **low-power operation**, utilizing efficient DC-DC conversion and deep-sleep states to run for weeks on a single Li-Ion charge.

## 🚀 Key Features

### 🔋 Ultra-Low Power Architecture
* **Power Source:** Single Cell Li-Ion Battery (3.7V).
* **Power Management:**
    * **DC-DC Buck/Boost Converter:** Highly efficient voltage regulation to drive the pump/solenoid and the MCU without wasting energy as heat.
    * **Sleep Modes:** The MCU and NRF module enter deep sleep (<10µA) between spray events, waking up only for scheduled timers or Bluetooth interrupts.

### 📶 Wireless Control (Bluetooth LE)
* **Hardware:** NRF Series Module (nRF52/nRF24) for robust low-energy communication.
* **Functionality:**
    * **Mobile App Control:** Trigger a spray instantly from your phone.
    * **Scheduling:** Set intervals (e.g., "Spray every 30 mins between 6 PM and 6 AM").
    * **Battery Status:** Monitor battery percentage remotely.

### ⚙️ Electromechanical Design
* **Actuator:** Low-voltage DC pump or Solenoid valve integration.
* **Driver:** MOSFET low-side switch with flyback diode protection.

## 🛠️ Technical Stack

| Category | Details |
| :--- | :--- |
| **MCU/Radio** | **Nordic nRF52** (ARM Cortex-M4 + BLE) |
| **Power** | TP4056 Charger, Low-Quiescent Current DC-DC |
| **Actuator** | 5V/12V Peristaltic Pump or Solenoid |
| **Protocol** | Bluetooth Low Energy (BLE) |
| **App Interface** | MIT App Inventor / Custom Flutter App |

![MR1](https://github.com/user-attachments/assets/2cfdd33b-e493-400e-80a9-34f3a28df496)

