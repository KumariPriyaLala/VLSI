# VLSI
# Custom IC & VLSI Circuit Design Suite (Cadence Virtuoso)

An end-to-end implementation and characterization of fundamental CMOS digital and memory circuits designed in **Cadence Virtuoso** using the **Spectre Simulation Platform** and industry-standard physical verification flows.

---

## 🛠️ Tools & EDA Suite
* **Schematic Capture & Simulation:** Cadence Virtuoso Composer, Spectre Circuit Simulator (ADE L / ADE Assembler)
* **Physical Verification & Layout:** Cadence Virtuoso Layout Suite, Siemens Calibre / Pegasus (DRC, LVS, PEX)
* **Modeling Languages:** SPICE, Verilog, Verilog-A
* **PDK:** SkyWater 130nm / Generic 45nm/180nm PDK

---

## 🔬 Key Experiments & Implementation Details

### 1. Transistor Parameter Extraction & MOS Modeling
* Extracted threshold voltage ($V_{th}$), transconductance ($g_m$), and drain conductance ($g_{ds}$) for NMOS and PMOS devices.
* Analyzed second-order MOSFET effects including **Channel Length Modulation ($\lambda$)**, **Body Effect**, and $W/L$ aspect ratio variation.

### 2. CMOS Inverter Characterization & Sizing
* Measured Voltage Transfer Characteristics (VTC), switching thresholds ($V_M$), and **Noise Margins ($NM_L, NM_H$)**.
* Analyzed propagation delay ($t_{pLH}, t_{pHL}$) and power consumption (dynamic vs. static) across various capacitive load conditions.

### 3. Fanout & Progressive Sizing Optimization
* Implemented multi-stage inverter chains using **Logical Effort** principles and progressive taper ratios ($u \approx e$) to drive high-capacitance loads with minimum path delay.

### 4. Combinational & Sequential CMOS Logic
* **Static CMOS & Universal Gates:** Evaluated input reordering effects on stack capacitance and propagation delay in NAND/NOR structures.
* **Pass Transistor & Transmission Gates:** Modeled high-density logic architectures and full-transmission gate topologies.
* **Sequential Logic:** Characterized Master-Slave D-Flip-Flops and latches for **Setup Time ($t_{setup}$)**, **Hold Time ($t_{hold}$)**, and **Clock-to-Q ($t_{clk-q}$)** delay parameters.

### 5. Memory Cell Architecture (SRAM)
* Designed a standard 6T SRAM bit-cell.
* Analyzed static noise margins (SNM) during Read, Write, and Hold operations via Butterfly curves.

### 6. Physical Layout & Signoff Verification
* Created custom DRC-clean physical layouts for logic gates.
* Performed **Layout Versus Schematic (LVS)** checks and Parasitic Extraction (PEX/RC Extraction).
* Evaluated post-layout performance using **PVT Corner Analysis** (Process: SS, TT, FF; Voltage variation; Temp: -40°C to 125°C) and **Monte Carlo Simulations** for mismatch analysis.

---

## 📊 Repository Structure

```text
├── docs/                 # Simulation plots, VTC curves, and timing diagrams
├── netlists/             # Spectre SPICE netlists for all circuits
├── schematics/           # Virtuoso schematic view exports / cellviews
├── layout/               # GDSII / DRC & LVS reports
└── README.md             # Project documentation
