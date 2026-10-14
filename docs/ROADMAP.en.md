# 🗺️ Project timeline

> **Project:** Automated system for material processing, handling and quality control  
> **Architecture:** Siemens S7-1200 | Fischertechnik 3D Robot 24V | TIA Portal | PROFINET  

---

## 📌 Phase summary
```text
[Phase 1: planning] ──► [Phase 2: mechanics] ──► [Phase 3: electronics] ──► [Phase 4: TIA Portal] ──► [Phase 5: HMI] ──► [Phase 6: testing]
```

---

## 🚀 Phase 1: scope definition, architecture & Git repository
> **Objective:** establish the project foundations, bilingual documentation architecture, and component procurement.

* [x] **1.1 Technical scope definition:**
  * Cell boundary: conveyor belt + Fischertechnik 3D Robot 24V + load cell press + OK/reject sorting.
* [x] **1.2 GitHub repository structure:**
  * Repository creation: `cc-material`.
  * Modular folder hierarchy setup (`/docs`, `/plc`, `/hmi`, `/cad`, `/schematics`).
  * `.gitignore` configuration to exclude TIA Portal and CAD temporary files.
* [x] **1.3 Main readme & license setup:**
  * Bilingual `README.md` creation (Spanish / English) with technology badges.
  * Open-source license configuration under **Apache License 2.0**.
* [x] **1.4 Bill of materials & tools inventory (BOM):**
  * Creation of `docs/MATERIALS_BOM.es.md` and `docs/MATERIALS_BOM.en.md` categorized by workshop tools, automation, sensors, and mechanics.

---

## 🔩 Phase 2: mechanical assembly & testing press structure
> **Objective:** assemble the compression gantry using aluminum extrusions and align linear motion axes.

* [ ] **2.1 2020 aluminum extrusion frame:**
  * Cutting, $90^\circ$ squaring, and mounting $2020$ V-Slot profiles using corner brackets and M4/M5 T-nuts.
* [ ] **2.2 Z-Axis linear motion mechanism:**
  * Installation of smooth steel guide rods ($\varnothing 8\text{ mm}$) with $LM8UU$ linear bearings.
  * Mounting the $T8$ lead screw with an anti-backlash brass nut.
  * Securing the NEMA 17 stepper motor and $5-8\text{ mm}$ flexible coupler.
* [ ] **2.3 Test bed & load cell mount:**
  * Machining/3D printing structural mounts for the straight bar load cell ($20\text{ kg} / 50\text{ kg}$).
  * Aligning the compression indenter with the sample support center to prevent shear or off-center forces.
* [ ] **2.4 Conveyor belt & manipulator layout:**
  * Mounting and leveling the educational conveyor belt and the **Fischertechnik 3D Robot 24V (Art. 511938)** on the workbench.

---

## ⚡ Phase 3: Electrical wiring, power & analog signal conditioning
> **Objective:** build the control panel, connect PLC I/O signals, and condition the force measurement circuit.

* [ ] **3.1 Power distribution & safety system:**
  * Wiring the DIN-rail power supply unit ($24\text{ V DC} / 5\text{ A}$).
  * Emergency stop mushroom button wired in series with actuator supply lines (TB6600 driver and Robot 24V motors).
  * Terminal block distribution and common ground ($M$) distribution.
* [ ] **3.2 Load cell signal conditioning (0–10V):**
  * Connecting the 4 load cell wires ($E+, E-, S+, S-$) to the **DY220** analog transmitter.
  * Connecting the transmitter $0-10\text{ V}$ output to the Siemens S7-1200 analog input channel (`IW64`).
* [ ] **3.3 Fischertechnik robot interface & TB6600 Driver:**
  * Wiring pulse (`PUL`) and direction (`DIR`) control signals from PLC $PTO$ outputs (`Q0.0`, `Q0.1`) to the **TB6600** driver.
  * Wiring 24V control signals/relays to the Fischertechnik robot for 3-axis and gripper actuation.
  * Wiring optical presence sensors on the conveyor line.

---

## 💻 Phase 4: PLC programming in TIA Portal (SCL / LAD)
> **Objective:** develop control logic, analog scaling, finite state machine, and break detection algorithm.

* [ ] **4.1 Analog normalisation & scaling:**
  * Function block development for normalising (`NORM_X`: $0 - 27648$) and scaling (`SCALE_X`: $0.0 - 50.0\text{ kg}$) force readings.
  * Physical calibration procedure using *Zero* (tare) and *Span* (gain) potentiometers on the DY220 transmitter.
* [ ] **4.2 Finite state machine (global cycle):**
  * Programming the main cycle logic in LAD/SCL:
    * `STATE 0: idle / awaiting start`
    * `STATE 1: conveyor belt advance until detection`
    * `STATE 2: Pick & Place sequence (press loading)`
    * `STATE 3: press compression & force measurement`
    * `STATE 4: break detection & immediate Z-axis retraction`
    * `STATE 5: product sorting (classify OK / reject)`
* [ ] **4.3 SCL peak force & drop detection algorithm:**
  * SCL algorithm recording maximum force (`Fuerza_Pico`) and detecting sharp force drops (material fracture) to stop the stepper motor instantly.
* [ ] **4.4 Material DB Logic:**
  * Material data block implementation storing test limits per material type (PLA, TPU, Wood): force tolerance, deformation limit, and test speed.

---

## 🖥️ Phase 5: SIMATIC WinCC HMI interface & communications
> **Objective:** design supervision screens, real-time trend graphs, and PROFINET communication.

* [ ] **5.1 PROFINET network configuration:**
  * Static IP allocation and network linkage between S7-1200 PLC and SIMATIC HMI (KTP400 / KTP700 Basic).
* [ ] **5.2 HMI screen design:**
  * **Main dashboard:** cell synoptic view, conveyor status, robot position, and Start/Stop/Reset controls.
  * **Test & graph screen:** real-time force vs time curve display during sample compression.
  * **Material screen:** dropdown selector to load test parameters based on chosen material.
  * **Alarm & diagnostic screen:** fault logging (active E-Stop, force overload, communication loss).
* [ ] **5.3 Multi-Language HMI Support:**
  * Language toggle configuration (🇪🇸 / 🇬🇧) for real-time interface translation.

---

## 📑 Phase 6: Integration testing, validation & final GitHub publication
> **Objective:** validate the complete cell with real physical tests, record media assets, and complete the repository.

* [ ] **6.1 Field testing with physical samples:**
  * Executing destructive and non-destructive compression tests on PLA, TPU, and wooden samples.
  * Fine-tuning NEMA 17 velocity profiles and fracture detection sensitivity.
* [ ] **6.2 Technical documentation completion:**
  * Creating `docs/HARDWARE_WIRING.es.md` with wiring schematics and I/O assignments.
  * Creating `docs/CALIBRATION_GUIDE.es.md` with step-by-step transmitter calibration procedures.
  * Generating system architecture diagrams in `docs/ARCHITECTURE.es.md`.
* [ ] **6.3 Uploading project files to GitHub:**
  * Uploading compressed TIA Portal projects (`.zap17` / `.zap18`) under the `/plc` directory.
  * Uploading CAD drawings and STL/STEP models under `/cad`.
  * Uploading HMI screenshots and PDF schematics under `/hmi` and `/schematics`.
* [ ] **6.4 Final project release:**
  * Adding photos of the assembled cell and test video clips/GIFs to the main `README.md`.
