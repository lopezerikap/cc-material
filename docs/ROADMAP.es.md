# 🗺️ Cronograma de proyecto

> **Proyecto:** Sistema automatizado de gestión, procesado de materiales y control de calidad industrial  
> **Arquitectura:** Siemens S7-1200 | Fischertechnik 3D Robot 24V | TIA Portal | PROFINET  

---

## 📌 Resumen de fases
```text
[Fase 1: planificación] ──► [Fase 2: mecánica] ──► [Fase 3: electrónica] ──► [Fase 4: TIA Portal] ──► [Fase 5: HMI] ──► [Fase 6: pruebas]
```

---

## 🚀 Fase 1: definición de alcance, arquitectura y repositorio git
> **Objetivo:** establecer los cimientos del proyecto, la arquitectura bilingüe de la documentación y el aprovisionamiento de componentes.

* [x] **1.1 Definición técnica del alcance:**
  * Delimitación de la celda: cinta transportadora + robot Fischertechnik 3D Robot 24V + prensa con célula de carga + clasificación OK/Rechazo.
* [x] **1.2 Estructura del repositorio en GitHub:**
  * Creación del repositorio `cc-material`.
  * Configuración de la estructura modular de carpetas (`/docs`, `/plc`, `/hmi`, `/cad`, `/schematics`).
  * Integración del archivo `.gitignore` para ignorar archivos temporales de TIA Portal y CAD.
* [x] **1.3 Documentación de portada y licencia:**
  * Elaboración del `README.md` bilingüe (Español / Inglés) con badges de tecnologías.
  * Selección y configuración de la licencia de código abierto **Apache License 2.0**.
* [x] **1.4 Inventariado de materiales y herramientas (BOM):**
  * Creación de `docs/MATERIALS_BOM.es.md` y `docs/MATERIALS_BOM.en.md` categorizados por herramientas de taller, automatización, sensórica y mecánica.

---

## 🔩 Fase 2: montaje mecánico y estructura física
> **Objetivo:** ensamblar el pórtico de compresión en perfilería de aluminio y alinear los ejes de movimiento.

* [ ] **2.1 Chasis de aluminio extruido 2020:**
  * Cortado, escuadrado a $90^\circ$ y ensamblado de los perfiles $2020$ V-Slot mediante escuadras metálicas y tuercas T M4/M5.
* [ ] **2.2 Mecanismo de guiado y avance lineal (eje Z):**
  * Montaje de varillas lisas de acero ($\varnothing 8\text{ mm}$) con rodamientos lineales $LM8UU$.
  * Instalación del husillo $T8$ con tuerca de latón anti-holgura.
  * Fijación del motor paso a paso NEMA 17 y acoplamiento flexible $5-8\text{ mm}$.
* [ ] **2.3 Bancada del ensayo y célula de carga:**
  * Mecanizado/impresión 3D de soportes para la célula de carga de barra ($20\text{ kg} / 50\text{ kg}$).
  * Alineación del punzón de compresión con el centro de apoyo de la probeta para evitar esfuerzos cortantes o descentrados.
* [ ] **2.4 Disposición de la cinta y manipulador robotizado:**
  * Fijación y nivelación de la cinta transportadora didáctica y del robot **Fischertechnik 3D Robot 24V (Art. 511938)** en la mesa de trabajo.

---

## ⚡ Fase 3: cableado eléctrico, potencia y acondicionamiento analógico
> **Objetivo:** realizar el cuadro de control, conectar las señales I/O del PLC y acondicionar la lectura analógica de fuerza.

* [ ] **3.1 Distribución de potencia y seguridad:**
  * Cableado de la fuente de alimentación Riel DIN ($24\text{ V DC} / 5\text{ A}$).
  * Cableado de la seta de parada de emergencia en serie con la alimentación de actuadores (Driver TB6600 y Motores 24V del Robot).
  * Instalación de borneras y reparto de masas ($M$).
* [ ] **3.2 Acondicionamiento de la célula de carga (0–10V):**
  * Conexión de los 4 hilos de la célula de carga ($E+, E-, S+, S-$) al transmisor analógico **DY220**.
  * Conexión de la salida $0-10\text{ V}$ del transmisor al canal de entrada analógica del PLC Siemens S7-1200 (`IW64`).
* [ ] **3.3 Interfaz del robot Fischertechnik y driver TB6600:**
  * Cableado de las señales de pulsos (`PUL`) y dirección (`DIR`) desde las salidas $PTO$ del PLC (`Q0.0`, `Q0.1`) al driver **TB6600**.
  * Cableado de los relés/entradas de control a 24V del robot Fischertechnik para la gestión de los 3 ejes y la garra.
  * Cableado de los sensores ópticos de presencia en la cinta transportadora.

---

## 💻 Fase 4: programación del PLC en TIA Portal (SCL / LAD)
> **Objetivo:** desarrollar la lógica de control, el escalado analógico, la máquina de estados finitos y el algoritmo de rotura.

* [ ] **4.1 Escalado y normalización analógica:**
  * Creación del bloque de función para normalizar (`NORM_X`: $0 - 27648$) y escalar (`SCALE_X`: $0.0 - 50.0\text{ kg}$) la lectura analógica de fuerza.
  * Protocolo de calibrado físico mediante los potenciómetros de *Zero* (tara) y *Span* (ganancia) del transmisor DY220.
* [ ] **4.2 Máquina de estados finitos (secuencia global):**
  * Programación del ciclo principal en LAD/SCL:
    * `ESTADO 0: reposo / espera de inicio`
    * `ESTADO 1: avance de cinta transportadora hasta detección`
    * `ESTADO 2: secuencia Pick & Place (carga a prensa)`
    * `ESTADO 3: bajada de prensa y medición de fuerza`
    * `ESTADO 4: detección de rotura y retorno inmediato del eje Z`
    * `ESTADO 5: clasificación del producto (clasificar OK / rechazo)`
* [ ] **4.3 Algoritmo SCL de detección de pico y caída de fuerza:**
  * Desarrollo del algoritmo en SCL que registra el valor máximo de fuerza alcanzado (`Fuerza_Pico`) y detecta la pendiente negativa brusca (rotura del material) para detener el motor paso a paso al instante.
* [ ] **4.4 Lógica de materiales:**
  * Implementación del bloque DB de materiales para almacenar los parámetros de ensayo de cada material (PLA, TPU, Madera): límite de fuerza permisible, tolerancia de deformación y velocidad de ensayo.

---

## 🖥️ Fase 5: interfaz HMI SIMATIC WinCC y comunicaciones
> **Objetivo:** diseñar la pantalla de supervisión, las gráficas en tiempo real y el control de la celda por PROFINET.

* [ ] **5.1 Configuración de red PROFINET:**
  * Asignación de direcciones IP estáticas e interconexión del autómata S7-1200 y la pantalla SIMATIC HMI (KTP400 / KTP700 Basic).
* [ ] **5.2 Diseño de pantallas HMI:**
  * **Pantalla principal (dashboard):** sinóptico visual de la celda, estado de la cinta, posición del robot y botones de Start/Stop/Reset.
  * **Pantalla de ensayo y gráfica:** muestra en tiempo real de la curva Esfuerzo vs Tiempo durante la compresión de la muestra.
  * **Pantalla de selección de materiales:** menú desplegable para cargar parámetros según el material a testear.
  * **Pantalla de alarmas y diagnóstico:** registro de fallos (parada de emergencia activa, sobrecarga de fuerza, fallo de comunicación).
* [ ] **5.3 Soporte multi-idioma en HMI:**
  * configuración del conmutador de idioma (🇪🇸 / 🇬🇧) para alternar los textos de la interfaz en tiempo real.

---

## 📑 Fase 6: pruebas de integración, validación y publicación final en GitHub
> **Objetivo:** validar el sistema con ensayos reales, capturar recursos multimedia y completar el repositorio.

* [ ] **6.1 Ensayos de campo con probetas reales:**
  * Ejecución de tests destructivos y no destructivos con probetas de PLA, TPU y madera.
  * Ajuste fino de la velocidad del NEMA 17 y la sensibilidad de parada por rotura.
* [ ] **6.2 Elaboración de documentos técnicos finales:**
  * Creación de `docs/HARDWARE_WIRING.es.md` con los esquemas de conexiones y asignación de pines I/O.
  * Creación de `docs/CALIBRATION_GUIDE.es.md` con el manual paso a paso de ajuste del transmisor analógico.
  * Generación del diagrama de arquitectura `docs/ARCHITECTURE.es.md`.
* [ ] **6.3 Carga de Archivos de Proyecto en GitHub:**
  * Subida del proyecto comprimido de TIA Portal (`.zap17` / `.zap18`) en la carpeta `/plc`.
  * Subida de los planos mecánicos y archivos STL/STEP en la carpeta `/cad`.
  * Subida de capturas HMI y esquemas eléctricos en PDF/PNG en las carpetas `/hmi` y `/schematics`.
* [ ] **6.4 Cierre y Publicación:**
  * Inclusión de fotos del montaje real y un GIF/vídeo del ensayo en el `README.md` principal.
