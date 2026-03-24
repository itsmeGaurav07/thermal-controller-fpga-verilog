# 🌡️ Thermal Controller – Verilog | FPGA (Xilinx Vivado)

## 📌 Overview

This project implements a **Thermal Controller** using **Verilog HDL** based on a **Finite State Machine (FSM)** architecture.
The system monitors temperature input and generates control signals such as **throttle, alert, and shutdown** based on predefined threshold levels.

The design is fully simulated, synthesized, and implemented on FPGA using **Xilinx Vivado**.

---

## 🎯 Objectives

* Design a temperature monitoring and control system
* Implement FSM-based decision logic
* Generate control signals based on temperature thresholds
* Perform simulation and FPGA implementation

---

## ⚙️ Specifications

* **Input:** 8-bit temperature value (`temp_in`)
* **Clock:** 100 MHz
* **States:** IDLE, NORMAL, WARNING, CRITICAL
* **Outputs:** throttle, alert, shutdown

---

## 🧠 Architecture

The system consists of:

### 🔹 1. Temperature Comparator Logic

* Compares input temperature with predefined thresholds:

  * `NORMAL_T = 50`
  * `WARNING_T = 70`
  * `CRITICAL_T = 85`

---

### 🔹 2. Finite State Machine (FSM)

States:

* `IDLE` – System inactive / low temperature
* `NORMAL` – Safe operating condition
* `WARNING` – High temperature (throttle + alert)
* `CRITICAL` – Dangerous condition (shutdown activated)

---

### 🔹 3. Output Control Logic

* Generates signals based on state:

  * **Throttle:** Reduces system performance
  * **Alert:** Warning indication
  * **Shutdown:** Emergency stop

---

## 🔄 Working Principle

1. System starts in **IDLE** state
2. Temperature is continuously monitored
3. State transitions based on thresholds:

   * `temp >= 50` → NORMAL
   * `temp >= 70` → WARNING
   * `temp >= 85` → CRITICAL
4. Outputs are generated accordingly:

   * WARNING → throttle + alert
   * CRITICAL → throttle + alert + shutdown
5. System returns to lower states when temperature decreases

---

## 📂 Project Structure

```id="thermal_struct"
thermal-controller-fpga-verilog/
│
├── src/
│   └── thermal_controller.v
│
├── tb/
│   └── tb_thermal_controller.v
│
├── constraints/
│   └── thermal_controller.xdc
│
├── results/
│   ├── waveform.png
│   ├── rtl.png
│   └── implementation.png
│
└── README.md
```

---

## 🧪 Simulation

* Testbench applies different temperature values:

  * 20 → IDLE
  * 40 → NORMAL
  * 60 → WARNING
  * 80+ → CRITICAL

### ✔️ Observations:

* Correct state transitions
* Proper activation of control signals
* Shutdown triggered in critical condition

---

## 🖥️ FPGA Implementation

* Tool: **Xilinx Vivado**
* Steps:

  * Synthesis ✔️
  * Implementation ✔️
  * Bitstream Generation ✔️

---

## 📸 Results

### 🔹 Simulation Waveform

![Waveform](results/waveform.png)

### 🔹 RTL Schematic

![RTL](results/rtl.png)

### 🔹 FPGA Implementation

![Implementation](results/implementation.png)

---

## 💡 Key Features

* FSM-based control system
* Multi-level temperature threshold handling
* Real-time hardware control signals
* Fully synthesizable and FPGA-ready design

---

## 🚀 Future Improvements

* Integration with UART for temperature logging
* Sensor interfacing (LM35 / digital sensors)
* AXI-based system integration
* Display output (LCD / UART terminal)

---

## 🧑‍💻 Tools Used

* Verilog HDL
* Xilinx Vivado
* FPGA Board

---

## 📚 Learning Outcome

* FSM design for control systems
* Digital system implementation on FPGA
* Hardware-level decision making
* End-to-end VLSI design flow

---

## 🤝 Contribution

Feel free to fork and improve this project!

---

## ⭐ Acknowledgment

Developed as part of learning **VLSI design and FPGA-based system implementation**.

---
V. Gaurav Sai 
B.Tech – Electronics and Communication Engineering
