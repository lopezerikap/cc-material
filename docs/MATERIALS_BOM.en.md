# 📦 Bill of materials & tools (BOM)
> **Project:** Automated system for material processing, handling and quality control  
> **Platform:** Siemens S7-1200 / PROFINET / TIA Portal  

---

## 🛠️ 1. Tools & workshop equipment

### 🔧 1.1 Mechanical assembly tools
* **Hex key / Allen Set:** $2.5\text{ mm}$, $3\text{ mm}$, $4\text{ mm}$, and $5\text{ mm}$ (for M3, M4, and M5 bolts).
* **Open-end / socket wrenches:** $7\text{ mm}$, $8\text{ mm}$, and $10\text{ mm}$ (for aluminum brackets and load cell mounting).
* **Precision screwdriver set:** flathead and Phillips head bits.
* **Digital vernier caliper:** for sample dimension verification and guide rail alignment.
* **Engineer square / bubble level:** to ensure $90^\circ$ perpendicularity of the vertical frame.
* **Utility knife & scissors:** for cable sleeving and conveyor belt adjustments.

### ⚡ 1.2 Electrical & wiring tools
* **VDE insulated screwdrivers:** flathead ($2-3\text{ mm}$) for PLC terminals and Phillips (PH1/PH2) for PSU and driver.
* **Automatic wire stripper:** for wire gauges from $0.25\text{ mm}^2$ (signals) to $1.5\text{ mm}^2$ (power).
* **Ferrule crimping tool:** for insulated wire end ferrules ($0.5\text{ mm}^2$ to $1.5\text{ mm}^2$).
* **Diagonal wire cutters:** for trimming wire leads and zip ties.
* **Soldering station & solder:** for sensor extensions and permanent splices.
* **Heat shrink tubing:** for insulation of soldered wire joints.
* **Cable ties & spiral wrap:** for neat wire bundling and routing.

### 🧪 1.3 Measurement & calibration instruments
* **Digital multimeter:** for continuity testing, DC voltage check ($24\text{ V DC}$), and analog signal measurement ($0-10\text{ V}$).
* **Trimmer screwdriver:** flathead for *Zero* and *Span* potentiometer adjustments on the transmitter.
* **Engineering laptop:** running TIA Portal V17/V18 (WinCC Basic).
* **Ethernet cable RJ45:** cat 5e/6 for PROFINET programming and communication.

---

## 🧱 2. System hardware & materials

### 🤖 2.1 Control & automation (PLC & HMI)
* **1-2x Siemens S7-1200 PLC**  
  * *Model:* CPU 1212C / 1214C DC/DC/DC  
  * *Features:* integrated $0-10\text{ V}$ analog inputs and PROFINET interface.
* **1x SIMATIC HMI Panel**  
  * *Model:* Siemens KTP400 / KTP700 Basic  
  * *Features:* PROFINET communication for supervision and recipe control.
* **1x Power supply unit (PSU)**  
  * *Specifications:* $24\text{ V DC} / 5\text{ A}$ DIN-rail mounted.
* **1x Emergency stop button**  
  * *Type:* latching NC (Normally Closed) mushroom button for safety.
* **1x Control station**  
  * *Includes:* Start/Stop pushbuttons and status indicator lights.

### 🔬 2.2 Sensors & signal conditioning
* **1x Straight bar load cell**  
  * *Range:* $20\text{ kg}$ or $50\text{ kg}$ capacity  
  * *Connection:* 4-wire configuration (excitation & signal).
* **1x Analog load cell transmitter**  
  * *Model:* DY220 (or equivalent)  
  * *Specifications:* $24\text{ V DC}$ power input and $0-10\text{ V}$ analog output.
* **2-3x optical / inductive sensors**  
  * *Function:* sample presence detection on the conveyor belt.

### ⚙️ 2.3 Mechanics & actuation
* **1x NEMA 17 stepper motor**  
  * *Function:* high-torque motor for the vertical compression press.
* **1x TB6600 stepper driver**  
  * *Specifications:* $9-42\text{ V DC}$ input, pulse and direction control ($PTO$).
* **Various $2020$ aluminum extrusions**  
  * *Type:* V-Slot / T-Slot profiles for the main structural frame.
* **Various brackets & t-nuts**  
  * *Type:* corner connectors and M4/M5 hardware for aluminum profiles.
* **1x $T8$ lead screw with brass nut**  
  * *Function:* threaded drive assembly for linear vertical travel.
* **2x Smooth rods & linear bearings**  
  * *Specifications:* $\varnothing 8\text{ mm}$ steel shafts with $LM8UU$ bearings for guided motion.
* **1x Flexible coupling $5-8\text{ mm}$**  
  * *Function:* connects the NEMA 17 motor shaft to the $T8$ lead screw.
* **1x Educational conveyor belt**  
  * *Function:* motorized transport line with integrated rollers.
* **1x Pick & Place manipulator**  
  * *Function:* actuator/arm for sample loading, positioning, and unloading.
