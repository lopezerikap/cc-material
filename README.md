# 🏭 Sistema automatizado de gestión, procesado de materiales y control de calidad industrial (S7-1200 / Industria 4.0)
> *Automated system for material processing, handling and quality control (S7-1200 / Industry 4.0)*

[![PLC: Siemens S7-1200](https://img.shields.io/badge/PLC-Siemens%20S7--1200-006487?style=flat&logo=siemens)](https://www.siemens.com)
[![HMI: SIMATIC WinCC](https://img.shields.io/badge/HMI-SIMATIC%20WinCC-006487?style=flat&logo=siemens)](https://www.siemens.com)
[![Protocol: PROFINET](https://img.shields.io/badge/Protocol-PROFINET-red?style=flat)](https://www.profibus.com)
[![Software: TIA Portal](https://img.shields.io/badge/Software-TIA%20Portal-blue?style=flat)](https://www.siemens.com)
[![License: Apache 2.0](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

---

## 🌐 Language Selector / Selector de Idioma
- 🇪🇸 [español](#-español)
- 🇬🇧 [english](#-english)

---

<a name="español"></a>
## 🇪🇸 español

### 📌 Descripción del proyecto
Este proyecto consiste en el diseño, integración y programación de un **sistema industrial automatizado para la gestión, procesado y control de calidad de materiales**, desarrollado bajo la arquitectura de la Industria 4.0.

El proceso combina el transporte en línea, la manipulación de piezas mediante un brazo robótico *Pick & Place*, un ensayo de caracterización mecánica (resistencia y flexión) usando una célula de carga con acondicionador analógico, y la posterior clasificación de productos según tolerancias y recetas de material.

### ⚙️ Características principales
* **Gestión por material:** selección y ajuste de parámetros de ensayo desde la HMI para diversos materiales (PLA, TPU, madera, etc.).
* **Acondicionamiento analógico industrial:** lectura de fuerza mediante célula de carga y transmisor analógico de $0-10\text{ V}$ conectado a las entradas integradas del PLC.
* **Control de posición:** gobierno del eje de compresión a través de salidas de pulsos ($PTO$) del PLC conectadas al driver $TB6600$ y motor paso a paso $NEMA17$.
* **Detección automática de rotura:** algoritmo en PLC (TIA Portal SCL/LAD) para el análisis de caídas bruscas de tensión/fuerza, cálculo del pico crítico y parada inmediata por seguridad.
* **Trazabilidad y supervisión:** monitorización de curvas de esfuerzo en tiempo real y diagnóstico en la pantalla HMI SIMATIC.

### 📂 Estructura de la Documentación
* 📄 [Lista de materiales y herramientas (BOM)](docs/MATERIALS_BOM.es.md)
* 🗺️ [Cronograma de proyecto](docs/ROADMAP.es.md)
* 📐 [Arquitectura del sistema y esquemas eléctricos](schematics/HARDWARE_WIRING.es.md)
* 🎯 [Guía de calibración de la célula de carga](docs/CALIBRATION_GUIDE.es.md)

### 🛠️ Tecnologías y componentes (hardware y software)
* **PLC:** Siemens SIMATIC S7-1200 (CPU 1212C / 1214C DC/DC/DC)
* **HMI:** Siemens SIMATIC KTP400 / KTP700 Basic
* **Software:** TIA Portal V17 / V18 (WinCC Basic)
* **Actuación y Sensórica:**
  * Célula de carga de barra ($20\text{ kg} / 50\text{ kg}$) + transmisor analógico de $0-10\text{ V}$ (DY220)
  * Motor paso a paso NEMA 17 + Driver TB6600
  * Chasis en perfil de aluminio extruido $2020$ V-Slot + husillo $T8$
  * Cinta transportadora + manipulador *Pick & Place*

### 📄 Licencia
Distribuido bajo la Licencia Apache, Versión 2.0 (la "Licencia"). Puedes obtener una copia de la Licencia en el archivo `LICENSE` o en:
http://www.apache.org/licenses/LICENSE-2.0

----------

<a name="english"></a>
## 🇬🇧 english

### 📌 Project description
This project focuses on the design, integration, and programming of an **automated industrial system for material processing, handling, and quality control**, developed within an Industry 4.0 framework.

The workflow integrates conveyor transport line automation, a *Pick & Place* robotic manipulator, a mechanical testing press using a load cell with analog conditioning, and automated product sorting based on material strength tolerances and recipes.

### ⚙️ Key features
* **Material management:** material test parameters configurable from the HMI for different materials (PLA, TPU, Wood, etc.).
* **Industrial analog signal conditioning:** force acquisition using a load cell and $0-10\text{ V}$ transmitter directly connected to the PLC's integrated analog inputs.
* **Position control:** precision speed and position control of the compression axis via pulse train outputs ($PTO$) driving a $TB6600$ module and $NEMA17$ stepper motor.
* **Automatic break detection:** PLC algorithm (TIA Portal SCL/LAD) monitoring sharp force drops to calculate the critical yield point and trigger immediate safety stops.
* **Traceability & supervision:** real-time stress graph monitoring and system diagnostics on the SIMATIC HMI panel.

### 📂 Documentation Structure
* 📄 [Bill of materials & tools (BOM)](docs/MATERIALS_BOM.en.md)
* 🗺️ [Project timeline](docs/ROADMAP.en.md)
* 📐 [System architecture & electrical schematics](schematics/HARDWARE_WIRING.en.md)
* 🎯 [Load cell calibration guide](docs/CALIBRATION_GUIDE.en.md)

### 🛠️ Hardware & software stack
* **PLC:** Siemens SIMATIC S7-1200 (CPU 1212C / 1214C DC/DC/DC)
* **HMI:** Siemens SIMATIC KTP400 / KTP700 Basic
* **Software:** TIA Portal V17 / V18 (WinCC Basic)
* **Actuation & sensors:**
  * Straight bar load cell ($20\text{ kg} / 50\text{ kg}$) + $0-10\text{ V}$ analog transmitter (DY220)
  * Stepper motor NEMA17 + TB6600 Driver
  * $2020$ V-Slot aluminum profile frame + $T8$ lead screw
  * Conveyor belt assembly + Pick & Place manipulator

### 📄 License
Licensed under the Apache License, Version 2.0 (the "License"). You may obtain a copy of the License in the `LICENSE` file or at:
http://www.apache.org/licenses/LICENSE-2.0
