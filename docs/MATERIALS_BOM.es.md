# 📦 Lista de Materiales y Herramientas (BOM)
> **Proyecto:** Sistema automatizado de gestión, procesado de materiales y control de calidad industrial  
> **Plataforma:** Siemens S7-1200 / PROFINET / TIA Portal  

*** La selección de materiales e investigación de componentes se encuentra actualmente en fase de evaluación. ***

---

## 🛠️ 1. Herramientas y equipamiento de taller

### 🔧 1.1 Herramientas de montaje mecánico
* **Juego de llaves Allen (hexagonales):** $2.5\text{ mm}$, $3\text{ mm}$, $4\text{ mm}$ y $5\text{ mm}$ (para tornillos M3, M4 y M5).
* **Llaves fijas / de vaso:** $7\text{ mm}$, $8\text{ mm}$ y $10\text{ mm}$ (para tuercas de perfilería y célula de carga).
* **Destornilladores de precisión:** planos y de estrella (Phillips).
* **Calibrador / pie de rey:** para verificación de dimensiones de probetas y alineación de guías.
* **Escuadra de taller o nivel de burbuja:** para el escuadrado del pórtico a $90^\circ$.
* **Cúter y tijeras:** para ajuste de tubos de protección y cinta transportadora.

### ⚡ 1.2 Herramientas eléctricas y cableado
* **Destornilladores aislados de electricista (VDE):** planos ($2-3\text{ mm}$) para clemas de PLC y estrella (PH1/PH2) para fuente y driver.
* **Alicate pelacables automático:** para mangueras de $0.25\text{ mm}^2$ (señal) a $1.5\text{ mm}^2$ (potencia).
* **Crimpadora de punteras terminales:** para punteras huecas aisladas de $0.5\text{ mm}^2$ a $1.5\text{ mm}^2$.
* **Alicate de corte diagonal:** para corte de cableado y bridas.
* **Estación de soldadura de estaño:** para empalmes de sensores y prolongaciones.
* **Tubo termorretráctil:** para aislamiento térmico de soldaduras.
* **Bridas y espiral organizadora:** para peinado y embridado de cables.

### 🧪 1.3 Instrumentación de medida y ajuste
* **Multímetro digital:** para comprobación de continuidad, tensión ($24\text{ V DC}$) y señal analógica ($0-10\text{ V}$).
* **Destornillador plano de ajuste:** mínimo, para potenciómetros de *Zero* y *Span* del transmisor.
* **Ordenador:** con TIA Portal V17/V18 (WinCC Basic) instalado.
* **Cable de red Ethernet RJ45:** categoría 5e/6 para programación por PROFINET.

---

## 🧱 2. Materiales y hardware del sistema

### 🤖 2.1 Control y automatización (PLC & HMI)
* **1-2x PLC Siemens S7-1200**  
  * *Modelo:* CPU 1212C / 1214C DC/DC/DC  
  * *Características:* entradas analógicas de $0-10\text{ V}$ e interfaz PROFINET integradas.
* **1x Pantalla HMI SIMATIC**  
  * *Modelo:* Siemens KTP400 / KTP700 Basic  
  * *Características:* comunicación PROFINET para supervisión y materiales.
* **1x Fuente de alimentación**  
  * *Especificaciones:* $24\text{ V DC} / 5\text{ A}$ para montaje en carril DIN.
* **1x Seta de parada de emergencia**  
  * *Tipo:* pulsador normalmente cerrado (NC) con enclavamiento de seguridad.
* **1x Botonera de control**  
  * *Contenido:* pulsadores de marcha/paro e indicadores luminosos de estado.

### 🔬 2.2 Sensores y acondicionamiento de señal
* **1x Célula de carga de barra**  
  * *Rango:* $20\text{ kg}$ o $50\text{ kg}$  
  * *Conexión:* 4 hilos (excitación y señal).
* **1x Transmisor analógico para célula de carga**  
  * *Modelo:* DY220 (o equivalente)  
  * *Especificaciones:* alimentación a $24\text{ V DC}$ y salida analógica de $0-10\text{ V}$.
* **2-3x Sensores ópticos / inductivos**  
  * *Función:* detección de presencia de pieza en la cinta transportadora.

### ⚙️ 2.3 Mecánica y actuación
* **1x Motor paso a paso NEMA 17**  
  * *Función:* motor de alto par para la prensa de compresión vertical.
* **1x Driver para motor paso a paso TB6600**  
  * *Especificaciones:* $9-42\text{ V DC}$, control por pulsos y dirección ($PTO$).
* **Varios perfiles de aluminio $2020$**  
  * *Tipo:* extruido V-Slot / T-Slot para el bastidor principal.
* **Varios escuadras y tuercas T**  
  * *Tipo:* uniones metálicas y tornillería M4/M5 para perfilería de aluminio.
* **1x Husillo $T8$ con tuerca de latón**  
  * *Función:* transmisión de avance lineal para el eje vertical.
* **2x Varillas lisas y rodamientos lineales**  
  * *Especificaciones:* varillas de acero $\varnothing 8\text{ mm}$ y rodamientos $LM8UU$ para guiado.
* **1x Acoplamiento flexible $5-8\text{ mm}$**  
  * *Función:* unión entre el eje del motor NEMA 17 y el husillo $T8$.
* **1x Robot manipulador 3D Pick & Place**  
  * *Modelo:* Fischertechnik 3D Robot - 24V  
  * *Referencia / rev:* art.: 511938 (Rev: M1.6)  
  * *Especificaciones:* estructura de 3 ejes cartesianos/rotativos a $24\text{ V DC}$ con garra, finales de carrera, placa PCB de adaptación y bornera de conexiones etiquetada.
  * *Función:* carga de probetas desde la cinta transportadora hacia la prensa de ensayo y evacuación según clasificación (OK/Rechazo).
* **1x Línea de cinta transportadora**  
  * *Modelo:* Fischertechnik Punching Machine with Conveyor Belt - 24V  
  * *Referencia / rev:* art.: 96785 (Rev: M1.6)  
  * *Especificaciones:* cinta de arrastre a $24\text{ V DC}$ con motorización integrada, barreras de luz/sensores de paso y PCB de adaptación (Knobloch RL-146).
  * *Función:* transporte automatizado de piezas desde la zona de carga inicial hasta el punto de recogida del robot Pick & Place.
