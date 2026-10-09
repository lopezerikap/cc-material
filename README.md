# 🏭 Sistema Automatizado de Gestión, Procesado de Materiales y Control de Calidad Industrial
> *Automated System for Material Processing, Handling and Quality Control (S7-1200 / Industry 4.0)*

[![PLC: Siemens S7-1200](https://img.shields.io/badge/PLC-Siemens%20S7--1200-006487?style=flat&logo=siemens)](https://www.siemens.com)
[![HMI: SIMATIC WinCC](https://img.shields.io/badge/HMI-SIMATIC%20WinCC-006487?style=flat&logo=siemens)](https://www.siemens.com)
[![Protocol: PROFINET](https://img.shields.io/badge/Protocol-PROFINET-red?style=flat)](https://www.profibus.com)
[![Software: TIA Portal](https://img.shields.io/badge/Software-TIA%20Portal-blue?style=flat)](https://www.siemens.com)
[![License: Apache 2.0](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

---

## 🌐 Language Selector / Selector de Idioma
- 🇪🇸 [Español (#español)](#-español)
- 🇬🇧 [English (#english)](#-english)

---

<a name="español"></a>
## 🇪🇸 Español

### 📌 Descripción del Proyecto
Este proyecto consiste en el diseño, integración y programación de un **sistema industrial automatizado para la gestión, procesado y control de calidad de materiales**, desarrollado bajo la arquitectura de la Industria 4.0.

El proceso combina el transporte en línea de probetas, la manipulación de piezas mediante un brazo robótico *Pick & Place*, un ensayo de caracterización mecánica (resistencia y flexión) usando una célula de carga con acondicionador analógico, y la posterior clasificación de productos según tolerancias y recetas de material.
### ⚙️ Características Principales
* **Gestión por Recetas de Material:** Selección y ajuste de parámetros de ensayo desde la HMI para diversos materiales (PLA, TPU, Madera, etc.).
* **Acondicionamiento Analógico Industrial:** Lectura de fuerza mediante célula de carga y transmisor analógico de $0-10\text{ V}$ conectado a las entradas integradas del PLC.
* **Control de Posición:** Gobierno del eje de compresión a través de salidas de pulsos ($PTO$) del PLC conectadas al driver $TB6600$ y motor paso a paso $NEMA17$.
* **Detección Automática de Rotura:** Algoritmo en PLC (TIA Portal SCL/LAD) para el análisis de caídas bruscas de tensión/fuerza, cálculo del pico crítico y parada inmediata por seguridad.
* **Trazabilidad y Supervisión:** Monitorización de curvas de esfuerzo en tiempo real y diagnóstico en la pantalla HMI SIMATIC.

### 📐 Integración por Módulos Formativos
| Módulo Formativo | Implementación en la Célula |
| :--- | :--- |
| **Comunicaciones Industriales** | Red PROFINET entre autómatas Siemens S7-1200 y pantalla HMI. |
| **Programación Industrial (PLC)** | Lógica de secuencia, máquinas de estados finitos, gestión de cinta y enclavamientos de seguridad. |
| **Robótica Industrial** | Rutinas de manipulación *Pick & Place* para el posicionamiento y evacuación de muestras. |
| **Integración de Sistemas Avanzados** | Escalado y normalización analógica (`NORM_X`, `SCALE_X`), gestión de recetas de materiales y algoritmo de detección de picos de esfuerzo. |

### 📂 Estructura de la Documentación
* 📄 [Lista de Materiales (BOM)](docs/MATERIALS_BOM.es.md)
* 📐 [Arquitectura del Sistema y Esquemas Eléctricos](docs/HARDWARE_WIRING.es.md)
* 🎯 [Guía de Calibración de la Célula de Carga](docs/CALIBRATION_GUIDE.es.md)

---

<a name="english"></a>
## 🇬🇧 English

### 📌 Project Description
This project focuses on the design, integration, and programming of an **automated industrial system for material processing, handling, and quality control**, developed within an Industry 4.0 framework.

The workflow integrates conveyor transport line automation, a *Pick & Place* robotic manipulator, a mechanical testing press using a load cell with analog conditioning, and automated product sorting based on material strength tolerances and recipes.
### ⚙️ Key Features
* **Material Recipe Management:** Recipe-based test parameters configurable from the HMI for different materials (PLA, TPU, Wood, etc.).
* **Industrial Analog Signal Conditioning:** Force acquisition using a load cell and $0-10\text{ V}$ transmitter directly connected to the PLC's integrated analog inputs.
* **Position Control:** Precision speed and position control of the compression axis via pulse train outputs ($PTO$) driving a $TB6600$ module and $NEMA17$ stepper motor.
* **Automatic Break Detection:** PLC algorithm (TIA Portal SCL/LAD) monitoring sharp force drops to calculate the critical yield point and trigger immediate safety stops.
* **Traceability & Supervision:** Real-time stress graph monitoring and system diagnostics on the SIMATIC HMI panel.

### 📐 Curriculum Module Integration
| Vocational Module | Implementation in the Cell |
| :--- | :--- |
| **Industrial Communications** | PROFINET network connecting Siemens S7-1200 PLCs and HMI panel. |
| **Industrial Programming (PLC)** | Finite state machine logic, conveyor control, and safety interlocks. |
| **Industrial Robotics** | *Pick & Place* manipulation sequences for sample loading/unloading. |
| **Advanced System Integration** | Analog scaling and normalization (`NORM_X`, `SCALE_X`), material recipe management, and peak force detection. |

### 📂 Documentation Structure
* 📄 [Bill of Materials (BOM)](docs/MATERIALS_BOM.en.md)
* 📐 [System Architecture & Electrical Schematics](docs/HARDWARE_WIRING.en.md)
* 🎯 [Load Cell Calibration Guide](docs/CALIBRATION_GUIDE.en.md)

---

## 🛠️ Hardware & Software Stack
* **PLC:** Siemens SIMATIC S7-1200 (CPU 1212C / 1214C DC/DC/DC)
* **HMI:** Siemens SIMATIC KTP400 / KTP700 Basic
* **Software:** TIA Portal V17 / V18 (WinCC Basic)
* **Actuation & Sensors:**
  * Straight Bar Load Cell ($20\text{ kg} / 50\text{ kg}$) + $0-10\text{ V}$ Analog Transmitter (DY220)
  * Stepper Motor NEMA17 + TB6600 Driver
  * $2020$ V-Slot Aluminum Profile Frame + $T8$ Lead Screw
  * Conveyor Belt Assembly + Pick & Place Manipulator

---

## 📄 License
Licensed under the Apache License, Version 2.0 (the "License"). You may obtain a copy of the License in the `LICENSE` file or at:
http://www.apache.org/licenses/LICENSE-2.0
