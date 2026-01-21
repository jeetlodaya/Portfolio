# Picoammeter ⚡🔍

**A high-precision, low-current measurement device designed to measure currents in the picoampere (pA) range.**

## 📌 Project Overview
This project is a portable, battery-operated Picoammeter capable of detecting ultra-low currents often found in photodiode sensors, ionization chambers, and high-impedance material characterization.

The core challenge in measuring currents this small is not just the amplification, but preventing **parasitic leakage paths** on the PCB itself. This design leverages advanced layout techniques to ensure the signal measured is the signal of interest, not board leakage.

## 🚀 Key Design Techniques

### 🛡️ Low-Leakage PCB Layout
Measuring picoamps requires fighting the physics of the PCB materials. The following techniques were implemented:
* **Guard Traces / Guard Rings:**
    * **Concept:** A low-impedance track surrounds the sensitive high-impedance input node. This guard ring is driven to the *same potential* as the input signal (via a unity gain buffer).
    * **Result:** Since there is practically zero voltage difference between the input trace and the guard ring, leakage current is effectively nullified ($I = V/R$, if $V \approx 0$, then $I \approx 0$).
* **Solder Mask Removal:**
    * **Technique:** The solder mask (green layer) was explicitly removed from the sensitive input area and under the feedback components.
    * **Reasoning:** Standard solder mask can absorb humidity and create conductive paths in the $G\Omega$ range. Exposing the FR4 (or using Teflon standoffs) increases surface resistance.

### 🔌 Connectivity & Power
* **Li-Ion Battery Power:** Operates on a floating battery source to eliminate **ground loops** and mains frequency (50/60Hz) hum, which is critical for low-noise measurements.
* **USB to UART Bridge:** Provides isolated serial data logging to a PC for analysis and visualization.

## 🛠️ Technical Stack

| Category | Component/Detail |
| :--- | :--- |
| **MCU** | **ATmega328p** (AVR 8-bit) |
| **Analog Front End** | Transimpedance Amplifier (TIA) topology |
| **Leakage Control** | Active Guarding, Exposed Dielectrics |
| **Power Management** | Li-Ion Charger |
| **Interface** | USB-UART (CP2102/CH340) |
| **PCB Layer** | 2-Layer with careful analog/digital ground separation |
